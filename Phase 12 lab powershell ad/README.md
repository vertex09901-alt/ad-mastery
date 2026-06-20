# Phase 12 — PowerShell Automation

> Build a library of PowerShell scripts for Active Directory administration: user lifecycle management, group management, AD reporting, JML (Joiner-Mover-Leaver) automation, and security auditing.

---

## Setup

### 01 — Prepare the Scripts Folder
Created a dedicated scripts directory on DC1 and configured the PowerShell execution policy:

```powershell
# Create scripts folder
New-Item -Path "C:\Scripts\AD-Admin" -ItemType Directory

# Set execution policy to allow local scripts
Set-ExecutionPolicy RemoteSigned -Scope LocalMachine

# Verify the ActiveDirectory module is available
Import-Module ActiveDirectory
Get-Command -Module ActiveDirectory | Measure-Object
```

**Screenshots:** `01-PREPARE THE SCRIPTS FOLDER/`

---

## Scripts

### 02 — User Management Script
Covers full user account lifecycle:

```powershell
# New-VertexUser.ps1
# Create a new AD user with standard attributes
function New-VertexUser {
    param(
        [string]$FirstName,
        [string]$LastName,
        [string]$Department,
        [string]$JobTitle
    )
    $SamAccountName = "$($FirstName[0])$LastName".ToLower()
    $UPN = "$SamAccountName@vertex.local"
    $OU = "OU=$Department,OU=London HQ,DC=vertex,DC=local"

    New-ADUser `
        -Name "$FirstName $LastName" `
        -GivenName $FirstName `
        -Surname $LastName `
        -SamAccountName $SamAccountName `
        -UserPrincipalName $UPN `
        -Department $Department `
        -Title $JobTitle `
        -Path $OU `
        -AccountPassword (ConvertTo-SecureString "TempP@ss123!" -AsPlainText -Force) `
        -ChangePasswordAtLogon $true `
        -Enabled $true

    Write-Host "Created user: $SamAccountName in $OU"
}
```

Also included: `Disable-VertexUser`, `Reset-VertexUserPassword`, `Move-VertexUserOU`

**Screenshots:** `02-User-Management-Script/`

---

### 03 — Group Management Script
Automate group membership management:

```powershell
# Add-UsersToGroup.ps1
# Add all users in a department OU to the corresponding global group
function Sync-DepartmentGroup {
    param([string]$Department)
    
    $OU = "OU=$Department,OU=London HQ,DC=vertex,DC=local"
    $GroupName = "GG_$Department"
    
    $Users = Get-ADUser -Filter * -SearchBase $OU
    $Users | ForEach-Object {
        Add-ADGroupMember -Identity $GroupName -Members $_ -ErrorAction SilentlyContinue
    }
    Write-Host "Synced $($Users.Count) users to $GroupName"
}

# Get all members of a group with details
function Get-GroupMembersDetailed {
    param([string]$GroupName)
    Get-ADGroupMember -Identity $GroupName -Recursive |
        Get-ADUser -Properties Department, Title, LastLogonDate |
        Select-Object Name, SamAccountName, Department, Title, LastLogonDate
}
```

**Screenshots:** `03-Group-Management-Script/`

---

### 04 — Reporting Script
Generate AD health and inventory reports:

```powershell
# AD-Report.ps1
# Export all users with key attributes to CSV
Get-ADUser -Filter * -Properties Department, Title, LastLogonDate, PasswordLastSet, Enabled |
    Select-Object Name, SamAccountName, Department, Title, LastLogonDate, PasswordLastSet, Enabled |
    Export-Csv -Path "C:\Scripts\Reports\AllUsers_$(Get-Date -f yyyyMMdd).csv" -NoTypeInformation

# Find accounts that haven't logged in for 30+ days
$CutoffDate = (Get-Date).AddDays(-30)
Get-ADUser -Filter {LastLogonDate -lt $CutoffDate -and Enabled -eq $true} `
           -Properties LastLogonDate |
    Select-Object Name, SamAccountName, LastLogonDate |
    Export-Csv -Path "C:\Scripts\Reports\StaleAccounts.csv" -NoTypeInformation

# Password expiry report — users expiring in next 14 days
Search-ADAccount -AccountExpiring -TimeSpan "14.00:00:00" |
    Select-Object Name, SamAccountName, AccountExpirationDate |
    Export-Csv -Path "C:\Scripts\Reports\ExpiringAccounts.csv" -NoTypeInformation
```

**Screenshots:** `04-Reporting-Script/`

---

### 05 — JML Automation Script
**Joiner-Mover-Leaver** automation — the three core user lifecycle events in any organisation:

```powershell
# JML-Process.ps1

# JOINER — New employee onboarding
function Invoke-Joiner { 
    param($CsvPath)
    Import-Csv $CsvPath | ForEach-Object {
        # Create account, add to groups, set manager, send welcome email notification
    }
}

# MOVER — Employee changes department
function Invoke-Mover {
    param($SamAccountName, $NewDepartment)
    $User = Get-ADUser $SamAccountName -Properties MemberOf
    # Remove from old department groups
    $User.MemberOf | Remove-ADGroupMember -Members $User -Confirm:$false
    # Move to new OU
    Move-ADObject -Identity $User -TargetPath "OU=$NewDepartment,OU=London HQ,DC=vertex,DC=local"
    # Add to new department groups
    Add-ADGroupMember -Identity "GG_$NewDepartment" -Members $User
    Set-ADUser $User -Department $NewDepartment
}

# LEAVER — Employee offboarding
function Invoke-Leaver {
    param($SamAccountName)
    # Disable account immediately
    Disable-ADAccount -Identity $SamAccountName
    # Move to Disabled Users OU
    Move-ADObject -Identity (Get-ADUser $SamAccountName) -TargetPath "OU=Disabled,DC=vertex,DC=local"
    # Remove all group memberships
    (Get-ADUser $SamAccountName -Properties MemberOf).MemberOf | 
        ForEach-Object { Remove-ADGroupMember -Identity $_ -Members $SamAccountName -Confirm:$false }
    # Set account description with leaver date
    Set-ADUser $SamAccountName -Description "LEAVER: $(Get-Date -f yyyy-MM-dd)"
}
```

**Screenshots:** `05-JML-Automation-Script/`

---

### 06 — Security Audit Script
Identify security misconfigurations and risks:

```powershell
# Security-Audit.ps1

Write-Host "=== AD Security Audit ===" -ForegroundColor Cyan

# 1. Accounts with password never expires
Write-Host "`n[!] Password Never Expires:" -ForegroundColor Yellow
Get-ADUser -Filter {PasswordNeverExpires -eq $true -and Enabled -eq $true} |
    Select-Object Name, SamAccountName | Format-Table

# 2. Accounts with no password required
Write-Host "`n[!] No Password Required:" -ForegroundColor Yellow
Get-ADUser -Filter {PasswordNotRequired -eq $true} |
    Select-Object Name, SamAccountName | Format-Table

# 3. Accounts trusted for unconstrained delegation
Write-Host "`n[!] Unconstrained Delegation (not DCs):" -ForegroundColor Red
Get-ADUser -Filter {TrustedForDelegation -eq $true} |
    Where-Object { $_.DistinguishedName -notlike "*Domain Controllers*" } |
    Select-Object Name, SamAccountName | Format-Table

# 4. Kerberoastable accounts (SPNs set on user accounts)
Write-Host "`n[!] Kerberoastable Accounts (SPNs on user accounts):" -ForegroundColor Red
Get-ADUser -Filter {ServicePrincipalName -ne "$null"} -Properties ServicePrincipalName |
    Select-Object Name, SamAccountName, ServicePrincipalName | Format-Table

# 5. Admin accounts not in Protected Users
Write-Host "`n[!] Domain Admins NOT in Protected Users:" -ForegroundColor Red
$DomainAdmins = Get-ADGroupMember "Domain Admins"
$ProtectedUsers = Get-ADGroupMember "Protected Users"
$DomainAdmins | Where-Object { $_.SamAccountName -notin $ProtectedUsers.SamAccountName } |
    Select-Object Name, SamAccountName | Format-Table
```

**Screenshots:** `06-Security-Audit-Script/`

---

## Key Concepts

- PowerShell's **ActiveDirectory module** (from RSAT) is the primary tool for AD automation in real environments
- Always use `ConvertTo-SecureString` for passwords — never pass passwords as plain strings in production
- **JML automation** is one of the highest-value AD tasks — manual offboarding leads to zombie accounts and security risks
- The security audit script above finds the same misconfigurations that attackers search for with BloodHound — fix them proactively
- Schedule audit reports to run weekly via Windows Task Scheduler and email results to the security team

---

## Tools Used

`PowerShell ISE` · `ActiveDirectory module` · `Import-Csv` · `Export-Csv` · `Windows Task Scheduler`

---

*Previous: [Phase 11 — Enterprise Design](<../Phase 11 lab enterprise Design/README.md>) · Next: [Phase 13 — AD Attacks & Defense](<../Phase 13 lab ad attacks & Defense/README.md>)*
