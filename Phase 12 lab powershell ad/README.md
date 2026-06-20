# ⚡ Phase 12 — PowerShell AD Automation

> **Prepare a scripts folder, create PowerShell scripts for user management, group management, AD reporting, JML (Joiner-Mover-Leaver) automation, and security auditing.**

**Prerequisites:** All prior phases completed — full AD environment ready for automation.

---
## 📑 Table of Contents

- [Step 1 — Prepare the Scripts Folder](#step-1-prepare-the-scripts-folder)
- [Step 2 — User Management Script](#step-2-user-management-script)
- [Step 3 — Group Management Script](#step-3-group-management-script)
- [Step 4 — AD Reporting Script](#step-4-ad-reporting-script)
- [Step 5 — JML (Joiner-Mover-Leaver) Automation](#step-5-jml-joiner-mover-leaver-automation)
- [Step 6 — Security Audit Script](#step-6-security-audit-script)

---

## Step 1 — Prepare the Scripts Folder

Create a dedicated folder for PowerShell AD scripts:

```powershell
New-Item -Path C:\Scripts -ItemType Directory
Set-Location C:\Scripts
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### Screenshot 1

![Step 1 — Prepare the Scripts Folder - Screenshot 1](01-PREPARE%20THE%20SCRIPTS%20FOLDER/SCRIPTS%20-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 1 — Prepare the Scripts Folder - Screenshot 2](01-PREPARE%20THE%20SCRIPTS%20FOLDER/SCRIPTS%20-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 1 — Prepare the Scripts Folder - Screenshot 3](01-PREPARE%20THE%20SCRIPTS%20FOLDER/SCRIPTS%20-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 1 — Prepare the Scripts Folder - Screenshot 4](01-PREPARE%20THE%20SCRIPTS%20FOLDER/SCRIPTS%20-%20%284%29.png)

**Continue the configuration (step 4 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 1 — Prepare the Scripts Folder - Screenshot 5](01-PREPARE%20THE%20SCRIPTS%20FOLDER/SCRIPTS%20-%20%285%29.png)

**Continue the configuration (step 5 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 1 — Prepare the Scripts Folder - Screenshot 6](01-PREPARE%20THE%20SCRIPTS%20FOLDER/SCRIPTS%20-%20%286%29.png)

**Continue the configuration (step 6 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 1 — Prepare the Scripts Folder - Screenshot 7](01-PREPARE%20THE%20SCRIPTS%20FOLDER/SCRIPTS%20-%20%287%29.png)

**Continue the configuration (step 7 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 1 — Prepare the Scripts Folder - Screenshot 8](01-PREPARE%20THE%20SCRIPTS%20FOLDER/SCRIPTS%20-%20%288%29.png)

**Continue the configuration (step 8 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 1 — Prepare the Scripts Folder - Screenshot 9](01-PREPARE%20THE%20SCRIPTS%20FOLDER/SCRIPTS%20-%20%289%29.png)

**Continue the configuration (step 9 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 1 — Prepare the Scripts Folder - Screenshot 10](01-PREPARE%20THE%20SCRIPTS%20FOLDER/SCRIPTS%20-%20%2810%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 2 — User Management Script

Create a PowerShell script for common user management tasks:

```powershell
# Create a new user
New-ADUser -Name 'Test User' -SamAccountName 'test.user' ...

# Disable a user
Disable-ADAccount -Identity 'test.user'

# Reset password
Set-ADAccountPassword -Identity 'test.user' -Reset ...

# Unlock account
Unlock-ADAccount -Identity 'test.user'
```

### Screenshot 1

![Step 2 — User Management Script - Screenshot 1](02-User-Management-Script/User-Management-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 2 — User Management Script - Screenshot 2](02-User-Management-Script/User-Management-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 2 — User Management Script - Screenshot 3](02-User-Management-Script/User-Management-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 2 — User Management Script - Screenshot 4](02-User-Management-Script/User-Management-%20%284%29.png)

**Continue the configuration (step 4 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 2 — User Management Script - Screenshot 5](02-User-Management-Script/User-Management-%20%285%29.png)

**Continue the configuration (step 5 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 2 — User Management Script - Screenshot 6](02-User-Management-Script/User-Management-%20%286%29.png)

**Continue the configuration (step 6 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 2 — User Management Script - Screenshot 7](02-User-Management-Script/User-Management-%20%287%29.png)

**Continue the configuration (step 7 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 2 — User Management Script - Screenshot 8](02-User-Management-Script/User-Management-%20%288%29.png)

**Continue the configuration (step 8 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 2 — User Management Script - Screenshot 9](02-User-Management-Script/User-Management-%20%289%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 3 — Group Management Script

PowerShell script for group operations:

```powershell
# Create group
New-ADGroup -Name 'G_ProjectAlpha' -GroupScope Global ...

# Add members
Add-ADGroupMember -Identity 'G_ProjectAlpha' -Members 'user1','user2'

# List group members
Get-ADGroupMember -Identity 'G_IT' | Select Name
```

### Screenshot 1

![Step 3 — Group Management Script - Screenshot 1](03-Group-Management-Script/Group-Management-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 3 — Group Management Script - Screenshot 2](03-Group-Management-Script/Group-Management-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 3 — Group Management Script - Screenshot 3](03-Group-Management-Script/Group-Management-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 3 — Group Management Script - Screenshot 4](03-Group-Management-Script/Group-Management-%20%284%29.png)

**Continue the configuration (step 4 of 5) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 3 — Group Management Script - Screenshot 5](03-Group-Management-Script/Group-Management-%20%285%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 4 — AD Reporting Script

Create PowerShell reports for AD environment:

```powershell
# Users last logon report
Get-ADUser -Filter * -Properties LastLogonDate |
    Select Name, LastLogonDate | Export-Csv C:\Reports\LastLogon.csv

# Disabled accounts
Search-ADAccount -AccountDisabled | Select Name, DistinguishedName

# Password expiring soon
Search-ADAccount -PasswordExpiring -TimeSpan '7.00:00:00'
```

### Screenshot 1

![Step 4 — AD Reporting Script - Screenshot 1](04-Reporting-Script/Reporting-Script-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 4 — AD Reporting Script - Screenshot 2](04-Reporting-Script/Reporting-Script-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 4 — AD Reporting Script - Screenshot 3](04-Reporting-Script/Reporting-Script-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 4 — AD Reporting Script - Screenshot 4](04-Reporting-Script/Reporting-Script-%20%284%29.png)

**Continue the configuration (step 4 of 6) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 4 — AD Reporting Script - Screenshot 5](04-Reporting-Script/Reporting-Script-%20%285%29.png)

**Continue the configuration (step 5 of 6) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 4 — AD Reporting Script - Screenshot 6](04-Reporting-Script/Reporting-Script-%20%286%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 5 — JML (Joiner-Mover-Leaver) Automation

Automate the user lifecycle:

```powershell
# JOINER — New employee onboarding
function New-Employee { ... }

# MOVER — Department transfer
function Move-Employee { ... }

# LEAVER — Offboarding
function Remove-Employee {
    Disable-ADAccount -Identity $user
    Move-ADObject ... -TargetPath 'OU=Disabled,...'
    Remove-ADGroupMember ...
}
```

### Screenshot 1

![Step 5 — JML (Joiner-Mover-Leaver) Automation - Screenshot 1](05-JML-Automation-Script/JML-Automation-Script-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 5 — JML (Joiner-Mover-Leaver) Automation - Screenshot 2](05-JML-Automation-Script/JML-Automation-Script-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 5 — JML (Joiner-Mover-Leaver) Automation - Screenshot 3](05-JML-Automation-Script/JML-Automation-Script-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 5 — JML (Joiner-Mover-Leaver) Automation - Screenshot 4](05-JML-Automation-Script/JML-Automation-Script-%20%284%29.png)

**Continue the configuration (step 4 of 7) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 5 — JML (Joiner-Mover-Leaver) Automation - Screenshot 5](05-JML-Automation-Script/JML-Automation-Script-%20%285%29.png)

**Continue the configuration (step 5 of 7) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 5 — JML (Joiner-Mover-Leaver) Automation - Screenshot 6](05-JML-Automation-Script/JML-Automation-Script-%20%286%29.png)

**Continue the configuration (step 6 of 7) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 5 — JML (Joiner-Mover-Leaver) Automation - Screenshot 7](05-JML-Automation-Script/JML-Automation-Script-%20%287%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 6 — Security Audit Script

PowerShell script for security auditing:

```powershell
# Find users with password never expires
Get-ADUser -Filter 'PasswordNeverExpires -eq $true' | Select Name

# Find inactive accounts (90+ days)
Search-ADAccount -AccountInactive -TimeSpan '90.00:00:00'

# Find admin group members
Get-ADGroupMember -Identity 'Domain Admins' -Recursive

# Check for weak service account configs
Get-ADUser -Filter 'ServicePrincipalName -like "*"' -Properties ServicePrincipalName
```

### Screenshot 1

![Step 6 — Security Audit Script - Screenshot 1](06-Security-Audit-Script/Security-Audit-Script-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 6 — Security Audit Script - Screenshot 2](06-Security-Audit-Script/Security-Audit-Script-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 6 — Security Audit Script - Screenshot 3](06-Security-Audit-Script/Security-Audit-Script-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 6 — Security Audit Script - Screenshot 4](06-Security-Audit-Script/Security-Audit-Script-%20%284%29.png)

**Continue the configuration (step 4 of 11) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 6 — Security Audit Script - Screenshot 5](06-Security-Audit-Script/Security-Audit-Script-%20%285%29.png)

**Continue the configuration (step 5 of 11) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 6 — Security Audit Script - Screenshot 6](06-Security-Audit-Script/Security-Audit-Script-%20%286%29.png)

**Continue the configuration (step 6 of 11) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 6 — Security Audit Script - Screenshot 7](06-Security-Audit-Script/Security-Audit-Script-%20%287%29.png)

**Continue the configuration (step 7 of 11) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 6 — Security Audit Script - Screenshot 8](06-Security-Audit-Script/Security-Audit-Script-%20%288%29.png)

**Continue the configuration (step 8 of 11) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 6 — Security Audit Script - Screenshot 9](06-Security-Audit-Script/Security-Audit-Script-%20%289%29.png)

**Continue the configuration (step 9 of 11) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 6 — Security Audit Script - Screenshot 10](06-Security-Audit-Script/Security-Audit-Script-%20%2810%29.png)

**Continue the configuration (step 10 of 11) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 6 — Security Audit Script - Screenshot 11](06-Security-Audit-Script/Security-Audit-Script-%20%2811%29.png)

**Final result — verify the configuration is complete and working.**

---

## 🔗 Navigation

[⬆️ Back to Top](#)

[📚 Back to Master README](../README.md)
