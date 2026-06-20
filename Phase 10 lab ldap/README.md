# Phase 10 — LDAP & Directory Queries

> Connect to Active Directory using LDP.exe, run LDAP search queries against the directory, modify object attributes directly via LDAP, explore the directory with ADExplorer, query AD via PowerShell LDAP filters, and establish a secure LDAPS connection on port 636.

---

## What is LDAP in AD?

Active Directory is an **LDAP directory service**. Everything in AD — users, computers, groups, OUs, GPOs — is an LDAP object with attributes. The domain `vertex.local` maps to the LDAP Distinguished Name:

```
DC=vertex,DC=local
```

A user `jsmith` in the `IT` OU under `London HQ` has the DN:
```
CN=jsmith,OU=IT,OU=London HQ,DC=vertex,DC=local
```

---

## Steps

### 01 — Connect to AD Using LDP.exe
Opened **LDP.exe** (built-in Windows LDAP browser) and connected to DC1:

- Host: `DC1.vertex.local`
- Port: `389` (standard LDAP)
- Checked `SSL` option: No (plain LDAP for initial exploration)

Then **bound** (authenticated) using domain admin credentials to gain read/write access to the directory.

**Screenshots:** `01-CONNECT TO AD USING LDP.EXE/` (10+ images)

---

### 02 — Run LDAP Search Queries
Used LDP.exe **Search** function to query the directory:

Example queries run:

```ldap
# Find all users
Filter: (objectClass=user)
BaseDN: DC=vertex,DC=local

# Find a specific user
Filter: (&(objectClass=user)(sAMAccountName=jsmith))

# Find all enabled users
Filter: (&(objectClass=user)(!(userAccountControl:1.2.840.113556.1.4.803:=2)))

# Find all computers
Filter: (objectClass=computer)

# Find all Domain Admins
Filter: (&(objectClass=user)(memberOf=CN=Domain Admins,CN=Users,DC=vertex,DC=local))
```

Explored the returned attributes: `cn`, `sAMAccountName`, `userPrincipalName`, `distinguishedName`, `pwdLastSet`, `lastLogon`, `userAccountControl`, `memberOf`.

**Screenshots:** `02-RUN LDAP SEARCH QUERIES/`

---

### 03 — Modify an Attribute with LDP
Used LDP.exe to directly modify an AD object attribute (bypassing the GUI):

- Selected a user object
- Used **Modify** operation
- Changed the `description` attribute to a test value
- Verified the change appeared in ADUC immediately

This demonstrates that AD is fundamentally an LDAP database — the GUI tools are just LDAP clients.

**Screenshots:** `03-MODIFY AN ATTRIBUTE WITH LDP/`

---

### 04 — Install and Use ADExplorer
Downloaded and installed **Sysinternals ADExplorer** — a more user-friendly LDAP directory browser than LDP.exe.

Used ADExplorer to:
- Browse the entire AD tree visually
- View all attributes of user, computer, and group objects
- Take a **snapshot** of the AD database for offline analysis (a technique also used by attackers for AD enumeration)
- Search for objects by any attribute

**Screenshots:** `04-INSTALL AND USE ADEXPLORER/`

---

### 05 — LDAP Queries with PowerShell
Used PowerShell's `[adsisearcher]` and `Get-ADUser` with LDAP filters for programmatic AD queries:

```powershell
# Using ADSISearcher (no RSAT required)
$searcher = [adsisearcher]"(&(objectClass=user)(department=Finance))"
$searcher.SearchRoot = [adsi]"LDAP://DC=vertex,DC=local"
$searcher.FindAll() | ForEach-Object { $_.Properties.samaccountname }

# Using Get-ADUser with LDAP filter
Get-ADUser -LDAPFilter "(&(objectClass=user)(!(userAccountControl:1.2.840.113556.1.4.803:=2)))" `
           -Properties Department, LastLogonDate | 
           Select-Object Name, Department, LastLogonDate
```

**Screenshots:** `05-LDAP QUERIES WITH POWERSHELL/`

---

### 06 — Connect with LDAPS (Secure LDAP, Port 636)
Established a secure **LDAPS** connection to DC1 on port **636** (LDAP over SSL/TLS):

- Standard LDAP (port 389) sends data in plaintext — credentials are visible in packet captures
- LDAPS encrypts the entire session
- Requires a certificate on the DC (either from an internal CA or self-signed)

Configured LDP.exe to connect with SSL and verified the secure connection was established.

**Screenshots:** `06-CONNECT WITH LDAPS (SECURE LDAP, PORT 636)/`

---

## Key Concepts

- AD is an LDAP v3 compliant directory — any LDAP client can query it
- `userAccountControl` is a bitmask attribute encoding dozens of account properties (disabled, password never expires, trusted for delegation, etc.)
- `distinguishedName` uniquely identifies every object in the directory
- **LDAP filter syntax:** `(attribute=value)`, `(&(filter1)(filter2))` (AND), `(|(filter1)(filter2))` (OR), `(!(filter))` (NOT)
- Always use **LDAPS** (port 636) or **LDAP with STARTTLS** (port 389 with upgrade) in production — plain LDAP on port 389 is a credential theft risk
- ADExplorer snapshots are used by both defenders (AD baselines) and attackers (offline enumeration) — protect them accordingly

---

## Tools Used

`LDP.exe` · `Sysinternals ADExplorer` · `PowerShell (adsisearcher / ActiveDirectory module)` · `Wireshark` (optional, for LDAP packet inspection)

---

*Previous: [Phase 09 — Kerberos](<../Phase 09 lab kerberos/README.md>) · Next: [Phase 11 — Enterprise Design](<../Phase 11 lab enterprise Design/README.md>)*
