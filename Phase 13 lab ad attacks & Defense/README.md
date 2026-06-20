# Phase 13 — AD Attacks & Defense

> Simulate and defend against the most common Active Directory attack techniques: LLMNR/NBT-NS poisoning, password spraying, Kerberoasting, AS-REP roasting, and DCSync. For each attack, understand how it works, how to detect it, and how to prevent it.

> ⚠️ **Lab use only.** All simulations were performed in the isolated `vertex.local` lab environment. Never perform these techniques on systems you don't own or have explicit written authorisation for.

---

## Steps

### 01 — Disable LLMNR and NBT-NS (Quick Win Defense)
**LLMNR** (Link-Local Multicast Name Resolution) and **NBT-NS** (NetBIOS Name Service) are legacy Windows name resolution protocols that broadcast queries on the local network when DNS fails. Attackers run tools like **Responder** to intercept these broadcasts and steal NTLMv2 hashes.

**Defense implemented via GPO:**

Created and enforced a GPO: `Security - Disable LLMNR and NBTNS`

- Computer Configuration → Administrative Templates → Network → DNS Client
  - ✅ Turn off multicast name resolution: **Enabled**
- Computer Configuration → Windows Settings → Security Settings → Local Policies → Security Options
  - Network security: Restrict NTLM: ...

Also disabled NBT-NS via registry:
```
HKLM\SYSTEM\CurrentControlSet\Services\NetBT\Parameters\Interfaces\{GUID}\
NetbiosOptions = 2  (0=default, 1=enabled, 2=disabled)
```

Verified with `gpresult /r` on CLIENT1.

**Screenshots:** `01-DISABLE LLMNR AND NBT-NS (Quick Win Defense)/` (13+ images)

---

### 02 — Simulate and Detect Password Spraying
**Password spraying** tries one common password (e.g., `Winter2024!`) against many accounts, staying under lockout thresholds by spreading attempts over time.

**Attack simulation:**
- Attempted a single password against multiple accounts in the domain
- Used slow iteration to avoid triggering the 3-attempt lockout policy

**Detection:**
Filtered Security event log on DC1 for Event ID **4625** (Failed Logon):
- Looked for: multiple 4625 events across different accounts within a short window
- LogonType 3 (network) with the same failure reason

**Defense implemented:**
- Fine-Grained Password Policy with lockout after 3 attempts (Phase 08)
- Azure AD Password Protection (concept demonstrated — blocks known spray passwords)
- Audit logging to catch the pattern

**Screenshots:** `02-SIMULATE AND DETECT PASSWORD SPRAYING/`

---

### 03 — Kerberoasting Simulation and Defense
**Kerberoasting** exploits the Kerberos TGS mechanism: any authenticated domain user can request a service ticket for *any* SPN in the domain. Service tickets are encrypted with the service account's password hash — attackers take the ticket offline and crack it.

**Why it works:** Service accounts often have weak passwords and SPNs registered.

**Attack simulation:**
```powershell
# Request service tickets for all Kerberoastable accounts
Add-Type -AssemblyName System.IdentityModel
$Tickets = Get-ADUser -Filter {ServicePrincipalName -ne "$null"} -Properties ServicePrincipalName |
    ForEach-Object {
        New-Object System.IdentityModel.Tokens.KerberosRequestorSecurityToken `
            -ArgumentList $_.ServicePrincipalName[0]
    }
# Export hashes for offline cracking (simulation only - not actually cracked in lab)
```

**Detection:** Event ID **4769** (Service Ticket Request) with `RC4-HMAC` encryption type (etype 23) — AES requests are legitimate, RC4 requests on service accounts indicate Kerberoasting.

**Defense implemented:**
- Changed all service accounts to use **AES-256** only (Phase 09)
- Set service account passwords to 25+ character random strings
- Added service accounts to **Protected Users** (forces AES, breaks RC4 Kerberoasting)
- Enabled auditing for 4769 events with etype 23

**Screenshots:** `03-KERBEROASTING SIMULATION AND DEFENSE/`

---

### 04 — AS-REP Roasting (No Pre-Auth Accounts)
**AS-REP Roasting** targets accounts with **"Do not require Kerberos preauthentication"** enabled. Without pre-auth, the KDC returns an AS-REP encrypted with the user's password hash — no authentication needed to request it.

**Attack simulation:**
1. Identified vulnerable accounts:
```powershell
Get-ADUser -Filter {DoesNotRequirePreAuth -eq $true} -Properties DoesNotRequirePreAuth
```
2. Requested AS-REP for the vulnerable account
3. The returned hash format is crackable offline with Hashcat (`$krb5asrep$`)

**Detection:** Event ID **4768** (TGT Request) — look for successful AS-REQ from accounts that don't require pre-auth, especially from workstations.

**Defense implemented:**
- Audited and remediated all accounts with pre-auth disabled (only left test account for demonstration)
- PowerShell audit script from Phase 12 now flags any future accounts with this setting

**Screenshots:** `04-AS-REP ROASTING (NO PRE-AUTH ACCOUNTS)/`

---

### 05 — DCSync Detection and Analysis
**DCSync** abuses the `DS-Replication-Get-Changes-All` right — the right that DCs use to replicate the AD database between themselves. An account with this right can simulate a DC and request password hash replication from any DC, effectively dumping the entire `NTDS.DIT` including the `krbtgt` hash.

**Impact:** With the `krbtgt` hash, attackers can forge **Golden Tickets** — Kerberos TGTs that never expire and grant access to everything.

**Who has this right by default:**
- Domain Controllers
- Domain Admins
- Enterprise Admins

**Simulation:**
- Demonstrated the replication rights using `mimikatz lsadump::dcsync` syntax (concept only — Mimikatz was not installed in the lab)
- Reviewed which accounts held the `DS-Replication-Get-Changes-All` right using PowerShell

**Detection:** Event IDs to monitor:
- **4662** — Operation performed on an object (look for DS-Replication-Get-Changes-All access right on domain NC)
- **4929** — AD source replication session removed

Detection query (PowerShell):
```powershell
# Check who has DCSync rights
$Domain = (Get-ADDomain).DistinguishedName
$ACL = Get-ACL "AD:$Domain"
$ACL.Access | Where-Object {
    $_.ObjectType -eq "1131f6ad-9c07-11d1-f79f-00c04fc2dcd2" -or  # DS-Replication-Get-Changes-All
    $_.ObjectType -eq "1131f6ac-9c07-11d1-f79f-00c04fc2dcd2"       # DS-Replication-Get-Changes
} | Select-Object IdentityReference, ActiveDirectoryRights
```

**Defense implemented:**
- Verified only DCs and expected admin groups hold replication rights
- Enabled auditing on the domain NC object
- Documented the list of accounts with replication rights as a baseline

**Screenshots:** `05-DCSync-Detection-And-Analysis/`

---

### 06 — Verify Your Defenses Are Working
After implementing all defenses, ran a final verification pass:

| Defense | Verification Method | Status |
|---------|-------------------|--------|
| LLMNR disabled | `gpresult /r` on CLIENT1, Wireshark shows no LLMNR traffic | ✅ |
| NBT-NS disabled | Registry check, no UDP/137 broadcasts | ✅ |
| Lockout policy active | Tested 3 failed logins → account locked (Event 4740) | ✅ |
| AES-only Kerberos | `klist` shows AES256 tickets, RC4 ticket requests fail | ✅ |
| Pre-auth required | `Get-ADUser -Filter {DoesNotRequirePreAuth -eq $true}` returns 0 | ✅ |
| DCSync rights audited | Only DCs, Domain Admins, Enterprise Admins have replication rights | ✅ |
| Audit logging | All key Event IDs generating in Security log | ✅ |

**Screenshots:** `06-VERIFY YOUR DEFENSES ARE WORKING/`

---

## Attack to Defense Summary

| Attack | Technique | Key Defense |
|--------|-----------|-------------|
| LLMNR Poisoning | Intercept broadcast name resolution | Disable LLMNR/NBT-NS via GPO |
| Password Spraying | Brute-force with low attempt rate | Account lockout + audit Event 4625 |
| Kerberoasting | Crack offline service ticket hashes | AES-only + strong service account passwords |
| AS-REP Roasting | Dump hash without authentication | Require pre-auth on all accounts |
| DCSync | Simulate DC to dump NTDS.DIT | Audit replication rights + monitor Event 4662 |
| Golden Ticket | Forge TGTs with krbtgt hash | Protect DCs, monitor for anomalous TGTs, rotate krbtgt |

---

## Tools & References

`Group Policy Management` · `PowerShell ActiveDirectory module` · `Event Viewer` · `Sysinternals Suite`

References: MITRE ATT&CK for Enterprise — [Credential Access (TA0006)](https://attack.mitre.org/tactics/TA0006/)

---

*Previous: [Phase 12 — PowerShell Automation](<../Phase 12 lab powershell ad/README.md>) · [← Back to Main README](<../README.md>)*
