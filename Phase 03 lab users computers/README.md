# Phase 03 — Users & Computers

> Create and manage Active Directory user accounts manually and at scale via CSV bulk import. Provision service accounts, manage computer objects, and verify the domain environment from CLIENT1.

---

## Steps

### 01 — Manual User Provisioning
Created individual user accounts in **Active Directory Users and Computers (ADUC)** for department representatives. Each account was configured with:
- First/Last name, display name, UPN (`user@vertex.local`)
- Department and title attributes
- Placed in the correct department OU (IT, HR, Finance, Sales, etc.)
- Initial password set with "User must change password at next logon" enforced

**Screenshots:** `01-Manual-User-Provisioning/` (13+ images)

---

### 02 — Service Account Provisioning
Created dedicated **service accounts** used by applications and services:
- Named with the `svc_` prefix convention (e.g., `svc_sql`, `svc_backup`)
- Password set to never expire (with strong passwords)
- Placed in a dedicated `Service Accounts` OU
- "User cannot change password" enabled

**Screenshots:** `02-Service-Account-Provisioning/`

---

### 03 — CLIENT1: Domain Administrator Login
Logged into CLIENT1 with a domain administrator account to verify:
- Domain authentication working via Kerberos
- Group Policy applying on login
- Domain resources accessible from the workstation

**Screenshots:** `03-Client1-Domain-Administrator-Login/`

---

### 04 — Computer Object OU Migration
Moved computer objects from the default **Computers** container into the correct OUs:
- CLIENT1 → `Workstations` OU
- Servers → `Member Servers` OU

This is required for Group Policy to apply correctly to computers.

**Screenshots:** `04-Computer-Object-OU-Migration/`

---

### 05 — CLIENT1 Computer Name Modification
Renamed CLIENT1's computer object in AD and verified the change reflected in both AD and on the machine itself.

**Screenshots:** `05-Client1-Computername-Modification/`

---

### 06 — Bulk User Provisioning via CSV
Used **PowerShell** with the `Import-Csv` cmdlet and `New-ADUser` to bulk-create multiple users from a CSV file. This simulates onboarding a new department or importing migrated users.

Example CSV structure:
```csv
GivenName,Surname,SamAccountName,Department,OU
John,Smith,jsmith,Finance,OU=Finance,OU=London HQ,DC=vertex,DC=local
Jane,Doe,jdoe,IT,OU=IT,OU=London HQ,DC=vertex,DC=local
```

**Screenshots:** `06-Bulk-User-Provisioning-via-CSV/`

---

### 07 — Active Directory User Count Verification
Ran an AD query to verify the total number of user accounts created, confirming bulk provisioning succeeded.

```powershell
(Get-ADUser -Filter *).Count
```

**Screenshots:** `07-Active-Directory-User-Count-Verification/`

---

## Key Concepts

- **UPN (User Principal Name)** — the login name in `user@domain` format; used for modern authentication
- **sAMAccountName** — the legacy `DOMAIN\username` format; still required for compatibility
- Computer objects must be in OUs (not the default `Computers` container) for GPOs to apply
- Service accounts should be in a dedicated OU and never used as interactive login accounts
- Bulk provisioning via CSV + PowerShell is a core real-world admin skill

---

## Tools Used

`Active Directory Users and Computers (ADUC)` · `PowerShell` · `Import-Csv` · `New-ADUser`

---

*Previous: [Phase 02 — Install Active Directory](<../Phase 02 lab install ad/README.md>) · Next: [Phase 04 — DNS Configuration](<../Phase 04 lab dns/README.md>)*
