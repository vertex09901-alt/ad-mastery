# Phase 08 — Active Directory Security

> Harden the Active Directory environment using a layered security approach: implement admin account tiering, delegate helpdesk password resets, deploy LAPS for local admin passwords, add privileged accounts to Protected Users, enforce fine-grained password policies, and verify security audit events.

---

## Steps

### 01 — Tiering Admin Accounts
Implemented the **Microsoft Admin Tiering Model** to limit credential exposure:

| Tier | Scope | Accounts Created |
|------|-------|-----------------|
| Tier 0 | Domain/Forest (DCs, AD itself) | `T0-Admin-[name]` in `Tier 0 Admins` OU |
| Tier 1 | Member servers, applications | `T1-Admin-[name]` in `Tier 1 Admins` OU |
| Tier 2 | Workstations, end-user devices | `T2-Admin-[name]` in `Tier 2 Admins` OU |

Key rules enforced via GPO:
- Tier 0 admins cannot log into Tier 1/2 systems
- Tier 1 admins cannot log into Tier 0 systems (DCs)
- Standard users have no local admin rights

This prevents **pass-the-hash** and **credential theft** from compromised lower-tier systems escalating to domain admin level.

**Screenshots:** `01-TIERING ADMIN ACCOUNTS/` (46 images)

---

### 02 — Delegate Password Reset to Helpdesk
Used **AD Delegation of Control Wizard** to grant the `GG_Helpdesk` group permission to reset passwords for users in the `London HQ` OU **without** giving them Domain Admin rights.

Permissions delegated:
- Reset user passwords and force password change at next logon

Verified delegation worked by logging in as a helpdesk user and successfully resetting another user's password.

**Screenshots:** `02-DELEGATE PASSWORD RESET TO HELPDESK/` (60 images)

---

### 03 — LAPS (Local Administrator Password Solution)
Deployed **Microsoft LAPS** to automatically manage the local Administrator password on all domain-joined workstations:

1. Extended the AD Schema with LAPS attributes (`ms-Mcs-AdmPwd`, `ms-Mcs-AdmPwdExpirationTime`)
2. Set permissions so computers can write their own password to AD
3. Set permissions so only `GG_IT` can read the `ms-Mcs-AdmPwd` attribute
4. Deployed LAPS GPO to `Workstations` OU (password complexity, age: 30 days)
5. Verified CLIENT1's local admin password was stored in AD and readable via LAPS UI

**Why LAPS?** Every workstation having the same local admin password is a massive lateral movement risk. LAPS makes every machine's local admin password unique and rotated automatically.

**Screenshots:** `03-LAPS (LOCAL ADMINISTRATOR PASSWORD SOLUTION)/` (38 images)

---

### 04 — Protected Users Group
Added privileged accounts to the built-in **Protected Users** security group:
- Domain Admins
- Tier 0 admin accounts
- Service accounts that don't need delegation

What **Protected Users** enforces automatically (no GPO needed):
- ❌ No NTLM authentication (Kerberos only)
- ❌ No CredSSP or Digest credential caching
- ❌ No Kerberos DES or RC4 encryption (AES only)
- ❌ Kerberos TGT renewal limited to 4 hours (no renewable tickets)
- ❌ No Kerberos constrained or unconstrained delegation

**Screenshots:** `04-PROTECTED USERS GROUP/` (5 images)

---

### 05 — Fine-Grained Password Policies (PSO)
Created **Password Settings Objects (PSOs)** to apply different password policies to different groups — overriding the single domain-wide password policy:

| PSO | Target Group | Min Length | Complexity | Max Age | Lockout |
|-----|-------------|-----------|-----------|---------|---------|
| `PSO-Admins` | Domain Admins | 16 chars | Required | 30 days | 3 attempts |
| `PSO-ServiceAccounts` | Service Accounts | 20 chars | Required | Never | 5 attempts |
| `PSO-Standard` | All Users | 10 chars | Required | 90 days | 5 attempts |

PSOs allow granular password control without multiple domains. Configured via **Active Directory Administrative Center (ADAC)** → Domain → System → Password Settings Container.

**Screenshots:** `05-FINE-GRAINED PASSWORD POLICIES (PSO)/` (23 images)

---

### 06 — Security Audit Event Verification
After configuring the audit GPO (Phase 06), verified security events were being logged in **Event Viewer**:

Key Event IDs verified:

| Event ID | Meaning | Verified |
|----------|---------|---------|
| 4624 | Successful logon | ✅ |
| 4625 | Failed logon | ✅ |
| 4648 | Logon with explicit credentials | ✅ |
| 4720 | User account created | ✅ |
| 4723 | Password change attempt | ✅ |
| 4740 | Account locked out | ✅ |
| 4776 | NTLM credential validation | ✅ |

**Screenshots:** `06-SECURITY AUDIT EVENT VERIFICATION/` (14 images)

---

## Key Concepts

- **Tiering** breaks the kill chain — a compromised workstation admin account cannot be used against DCs
- **Delegation** is the correct way to give helpdesk limited AD access — never give Domain Admin for simple tasks
- **LAPS** eliminates the "one password rules all workstations" lateral movement path
- **Protected Users** is the strongest single control for protecting privileged identities — but test carefully as it breaks some legacy apps
- **PSOs** replace the old need for multiple domains to have multiple password policies
- Audit logs are useless if no one monitors them — this phase is the foundation for a SIEM integration

---

## Tools Used

`Active Directory Users and Computers` · `Delegation of Control Wizard` · `Microsoft LAPS` · `Active Directory Administrative Center (ADAC)` · `Group Policy Management` · `Event Viewer`

---

*Previous: [Phase 07 — Domain Controllers & FSMO](<../Phase 07 lab domaincontrollers fsmo/README.md>) · Next: [Phase 09 — Kerberos](<../Phase 09 lab kerberos/README.md>)*
