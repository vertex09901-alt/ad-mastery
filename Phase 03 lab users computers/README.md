# 👥 Phase 03 — Users & Computers

> **Manually create domain users, provision service accounts, log into CLIENT1 with domain admin credentials, move computer objects to proper OUs, rename CLIENT1, bulk-create users via CSV + PowerShell, and verify user counts.**

**Prerequisites:** Phase 02 completed — vertex.local domain operational with OU structure.

---
## 📑 Table of Contents

- [Step 1 — Manual User Provisioning](#step-1-manual-user-provisioning)
- [Step 2 — Service Account Provisioning](#step-2-service-account-provisioning)
- [Step 3 — Log into CLIENT1 as Domain Admin](#step-3-log-into-client1-as-domain-admin)
- [Step 4 — Move Computer Objects to Correct OUs](#step-4-move-computer-objects-to-correct-ous)
- [Step 5 — Modify CLIENT1 Computer Name](#step-5-modify-client1-computer-name)
- [Step 6 — Bulk User Creation via CSV + PowerShell](#step-6-bulk-user-creation-via-csv-+-powershell)
- [Step 7 — Verify User Count](#step-7-verify-user-count)

---

## Step 1 — Manual User Provisioning

Create domain user accounts manually in ADUC. For each user, set the full name, username (SAMAccountName), UPN, password, and place them in the correct department OU.

### Screenshot 1

![Step 1 — Manual User Provisioning - Screenshot 1](01-Manual-User-Provisioning/User-Provisioning-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 1 — Manual User Provisioning - Screenshot 2](01-Manual-User-Provisioning/User-Provisioning-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 1 — Manual User Provisioning - Screenshot 3](01-Manual-User-Provisioning/User-Provisioning-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 1 — Manual User Provisioning - Screenshot 4](01-Manual-User-Provisioning/User-Provisioning-%20%284%29.png)

**Continue the configuration (step 4 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 1 — Manual User Provisioning - Screenshot 5](01-Manual-User-Provisioning/User-Provisioning-%20%285%29.png)

**Continue the configuration (step 5 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 1 — Manual User Provisioning - Screenshot 6](01-Manual-User-Provisioning/User-Provisioning-%20%286%29.png)

**Continue the configuration (step 6 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 1 — Manual User Provisioning - Screenshot 7](01-Manual-User-Provisioning/User-Provisioning-%20%287%29.png)

**Continue the configuration (step 7 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 1 — Manual User Provisioning - Screenshot 8](01-Manual-User-Provisioning/User-Provisioning-%20%288%29.png)

**Continue the configuration (step 8 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 1 — Manual User Provisioning - Screenshot 9](01-Manual-User-Provisioning/User-Provisioning-%20%289%29.png)

**Continue the configuration (step 9 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 1 — Manual User Provisioning - Screenshot 10](01-Manual-User-Provisioning/User-Provisioning-%20%2810%29.png)

**Continue the configuration (step 10 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 1 — Manual User Provisioning - Screenshot 11](01-Manual-User-Provisioning/User-Provisioning-%20%2811%29.png)

**Continue the configuration (step 11 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 1 — Manual User Provisioning - Screenshot 12](01-Manual-User-Provisioning/User-Provisioning-%20%2812%29.png)

**Continue the configuration (step 12 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 1 — Manual User Provisioning - Screenshot 13](01-Manual-User-Provisioning/User-Provisioning-%20%2813%29.png)

**Continue the configuration (step 13 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 1 — Manual User Provisioning - Screenshot 14](01-Manual-User-Provisioning/User-Provisioning-%20%2814%29.png)

**Continue the configuration (step 14 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 1 — Manual User Provisioning - Screenshot 15](01-Manual-User-Provisioning/User-Provisioning-%20%2815%29.png)

**Continue the configuration (step 15 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 1 — Manual User Provisioning - Screenshot 16](01-Manual-User-Provisioning/User-Provisioning-%20%2816%29.png)

**Continue the configuration (step 16 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 1 — Manual User Provisioning - Screenshot 17](01-Manual-User-Provisioning/User-Provisioning-%20%2817%29.png)

**Continue the configuration (step 17 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 1 — Manual User Provisioning - Screenshot 18](01-Manual-User-Provisioning/User-Provisioning-%20%2818%29.png)

**Continue the configuration (step 18 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 1 — Manual User Provisioning - Screenshot 19](01-Manual-User-Provisioning/User-Provisioning-%20%2819%29.png)

**Continue the configuration (step 19 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 1 — Manual User Provisioning - Screenshot 20](01-Manual-User-Provisioning/User-Provisioning-%20%2820%29.png)

**Continue the configuration (step 20 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 1 — Manual User Provisioning - Screenshot 21](01-Manual-User-Provisioning/User-Provisioning-%20%2821%29.png)

**Continue the configuration (step 21 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 22

![Step 1 — Manual User Provisioning - Screenshot 22](01-Manual-User-Provisioning/User-Provisioning-%20%2822%29.png)

**Continue the configuration (step 22 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 23

![Step 1 — Manual User Provisioning - Screenshot 23](01-Manual-User-Provisioning/User-Provisioning-%20%2823%29.png)

**Continue the configuration (step 23 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 24

![Step 1 — Manual User Provisioning - Screenshot 24](01-Manual-User-Provisioning/User-Provisioning-%20%2824%29.png)

**Continue the configuration (step 24 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 25

![Step 1 — Manual User Provisioning - Screenshot 25](01-Manual-User-Provisioning/User-Provisioning-%20%2825%29.png)

**Continue the configuration (step 25 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 26

![Step 1 — Manual User Provisioning - Screenshot 26](01-Manual-User-Provisioning/User-Provisioning-%20%2826%29.png)

**Continue the configuration (step 26 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 27

![Step 1 — Manual User Provisioning - Screenshot 27](01-Manual-User-Provisioning/User-Provisioning-%20%2827%29.png)

**Continue the configuration (step 27 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 28

![Step 1 — Manual User Provisioning - Screenshot 28](01-Manual-User-Provisioning/User-Provisioning-%20%2828%29.png)

**Continue the configuration (step 28 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 29

![Step 1 — Manual User Provisioning - Screenshot 29](01-Manual-User-Provisioning/User-Provisioning-%20%2829%29.png)

**Continue the configuration (step 29 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 30

![Step 1 — Manual User Provisioning - Screenshot 30](01-Manual-User-Provisioning/User-Provisioning-%20%2830%29.png)

**Continue the configuration (step 30 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 31

![Step 1 — Manual User Provisioning - Screenshot 31](01-Manual-User-Provisioning/User-Provisioning-%20%2831%29.png)

**Continue the configuration (step 31 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 32

![Step 1 — Manual User Provisioning - Screenshot 32](01-Manual-User-Provisioning/User-Provisioning-%20%2832%29.png)

**Continue the configuration (step 32 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 33

![Step 1 — Manual User Provisioning - Screenshot 33](01-Manual-User-Provisioning/User-Provisioning-%20%2833%29.png)

**Continue the configuration (step 33 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 34

![Step 1 — Manual User Provisioning - Screenshot 34](01-Manual-User-Provisioning/User-Provisioning-%20%2834%29.png)

**Continue the configuration (step 34 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 35

![Step 1 — Manual User Provisioning - Screenshot 35](01-Manual-User-Provisioning/User-Provisioning-%20%2835%29.png)

**Continue the configuration (step 35 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 36

![Step 1 — Manual User Provisioning - Screenshot 36](01-Manual-User-Provisioning/User-Provisioning-%20%2836%29.png)

**Continue the configuration (step 36 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 37

![Step 1 — Manual User Provisioning - Screenshot 37](01-Manual-User-Provisioning/User-Provisioning-%20%2837%29.png)

**Continue the configuration (step 37 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 38

![Step 1 — Manual User Provisioning - Screenshot 38](01-Manual-User-Provisioning/User-Provisioning-%20%2838%29.png)

**Continue the configuration (step 38 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 39

![Step 1 — Manual User Provisioning - Screenshot 39](01-Manual-User-Provisioning/User-Provisioning-%20%2839%29.png)

**Continue the configuration (step 39 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 40

![Step 1 — Manual User Provisioning - Screenshot 40](01-Manual-User-Provisioning/User-Provisioning-%20%2840%29.png)

**Continue the configuration (step 40 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 41

![Step 1 — Manual User Provisioning - Screenshot 41](01-Manual-User-Provisioning/User-Provisioning-%20%2841%29.png)

**Continue the configuration (step 41 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 42

![Step 1 — Manual User Provisioning - Screenshot 42](01-Manual-User-Provisioning/User-Provisioning-%20%2842%29.png)

**Continue the configuration (step 42 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 43

![Step 1 — Manual User Provisioning - Screenshot 43](01-Manual-User-Provisioning/User-Provisioning-%20%2843%29.png)

**Continue the configuration (step 43 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 44

![Step 1 — Manual User Provisioning - Screenshot 44](01-Manual-User-Provisioning/User-Provisioning-%20%2844%29.png)

**Continue the configuration (step 44 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 45

![Step 1 — Manual User Provisioning - Screenshot 45](01-Manual-User-Provisioning/User-Provisioning-%20%2845%29.png)

**Continue the configuration (step 45 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 46

![Step 1 — Manual User Provisioning - Screenshot 46](01-Manual-User-Provisioning/User-Provisioning-%20%2846%29.png)

**Continue the configuration (step 46 of 47) — follow the red arrows/boxes for guidance.**

### Screenshot 47

![Step 1 — Manual User Provisioning - Screenshot 47](01-Manual-User-Provisioning/User-Provisioning-%20%2847%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 2 — Service Account Provisioning

Create dedicated service accounts for applications and services. Configure them with 'Password never expires' and 'User cannot change password' flags.

### Screenshot 1

![Step 2 — Service Account Provisioning - Screenshot 1](02-Service-Account-Provisioning/Service-Account-Provisioning-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 2 — Service Account Provisioning - Screenshot 2](02-Service-Account-Provisioning/Service-Account-Provisioning-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 2 — Service Account Provisioning - Screenshot 3](02-Service-Account-Provisioning/Service-Account-Provisioning-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 2 — Service Account Provisioning - Screenshot 4](02-Service-Account-Provisioning/Service-Account-Provisioning-%20%284%29.png)

**Continue the configuration (step 4 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 2 — Service Account Provisioning - Screenshot 5](02-Service-Account-Provisioning/Service-Account-Provisioning-%20%285%29.png)

**Continue the configuration (step 5 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 2 — Service Account Provisioning - Screenshot 6](02-Service-Account-Provisioning/Service-Account-Provisioning-%20%286%29.png)

**Continue the configuration (step 6 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 2 — Service Account Provisioning - Screenshot 7](02-Service-Account-Provisioning/Service-Account-Provisioning-%20%287%29.png)

**Continue the configuration (step 7 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 2 — Service Account Provisioning - Screenshot 8](02-Service-Account-Provisioning/Service-Account-Provisioning-%20%288%29.png)

**Continue the configuration (step 8 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 2 — Service Account Provisioning - Screenshot 9](02-Service-Account-Provisioning/Service-Account-Provisioning-%20%289%29.png)

**Continue the configuration (step 9 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 2 — Service Account Provisioning - Screenshot 10](02-Service-Account-Provisioning/Service-Account-Provisioning-%20%2810%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 3 — Log into CLIENT1 as Domain Admin

Log into CLIENT1 using domain administrator credentials (`VERTEX\Administrator` or `administrator@vertex.local`) to verify domain join and admin access.

### Screenshot 1

![Step 3 — Log into CLIENT1 as Domain Admin - Screenshot 1](03-Client1-Domain-Administrator-Login/Domain-Administrator-Login-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 3 — Log into CLIENT1 as Domain Admin - Screenshot 2](03-Client1-Domain-Administrator-Login/Domain-Administrator-Login-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 3 — Log into CLIENT1 as Domain Admin - Screenshot 3](03-Client1-Domain-Administrator-Login/Domain-Administrator-Login-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 3 — Log into CLIENT1 as Domain Admin - Screenshot 4](03-Client1-Domain-Administrator-Login/Domain-Administrator-Login-%20%284%29.png)

**Continue the configuration (step 4 of 8) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 3 — Log into CLIENT1 as Domain Admin - Screenshot 5](03-Client1-Domain-Administrator-Login/Domain-Administrator-Login-%20%285%29.png)

**Continue the configuration (step 5 of 8) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 3 — Log into CLIENT1 as Domain Admin - Screenshot 6](03-Client1-Domain-Administrator-Login/Domain-Administrator-Login-%20%286%29.png)

**Continue the configuration (step 6 of 8) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 3 — Log into CLIENT1 as Domain Admin - Screenshot 7](03-Client1-Domain-Administrator-Login/Domain-Administrator-Login-%20%287%29.png)

**Continue the configuration (step 7 of 8) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 3 — Log into CLIENT1 as Domain Admin - Screenshot 8](03-Client1-Domain-Administrator-Login/Domain-Administrator-Login-%20%288%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 4 — Move Computer Objects to Correct OUs

Move computer objects from the default 'Computers' container to their proper OUs within the VERTEX structure. This ensures GPOs apply correctly.

### Screenshot 1

![Step 4 — Move Computer Objects to Correct OUs - Screenshot 1](04-Computer-Object-OU-Migration/OU-Migration-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 4 — Move Computer Objects to Correct OUs - Screenshot 2](04-Computer-Object-OU-Migration/OU-Migration-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 4 — Move Computer Objects to Correct OUs - Screenshot 3](04-Computer-Object-OU-Migration/OU-Migration-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 4 — Move Computer Objects to Correct OUs - Screenshot 4](04-Computer-Object-OU-Migration/OU-Migration-%20%284%29.png)

**Continue the configuration (step 4 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 4 — Move Computer Objects to Correct OUs - Screenshot 5](04-Computer-Object-OU-Migration/OU-Migration-%20%285%29.png)

**Continue the configuration (step 5 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 4 — Move Computer Objects to Correct OUs - Screenshot 6](04-Computer-Object-OU-Migration/OU-Migration-%20%286%29.png)

**Continue the configuration (step 6 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 4 — Move Computer Objects to Correct OUs - Screenshot 7](04-Computer-Object-OU-Migration/OU-Migration-%20%287%29.png)

**Continue the configuration (step 7 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 4 — Move Computer Objects to Correct OUs - Screenshot 8](04-Computer-Object-OU-Migration/OU-Migration-%20%288%29.png)

**Continue the configuration (step 8 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 4 — Move Computer Objects to Correct OUs - Screenshot 9](04-Computer-Object-OU-Migration/OU-Migration-%20%289%29.png)

**Continue the configuration (step 9 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 4 — Move Computer Objects to Correct OUs - Screenshot 10](04-Computer-Object-OU-Migration/OU-Migration-%20%2810%29.png)

**Continue the configuration (step 10 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 4 — Move Computer Objects to Correct OUs - Screenshot 11](04-Computer-Object-OU-Migration/OU-Migration-%20%2811%29.png)

**Continue the configuration (step 11 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 4 — Move Computer Objects to Correct OUs - Screenshot 12](04-Computer-Object-OU-Migration/OU-Migration-%20%2812%29.png)

**Continue the configuration (step 12 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 4 — Move Computer Objects to Correct OUs - Screenshot 13](04-Computer-Object-OU-Migration/OU-Migration-%20%2813%29.png)

**Continue the configuration (step 13 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 4 — Move Computer Objects to Correct OUs - Screenshot 14](04-Computer-Object-OU-Migration/OU-Migration-%20%2814%29.png)

**Continue the configuration (step 14 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 4 — Move Computer Objects to Correct OUs - Screenshot 15](04-Computer-Object-OU-Migration/OU-Migration-%20%2815%29.png)

**Continue the configuration (step 15 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 4 — Move Computer Objects to Correct OUs - Screenshot 16](04-Computer-Object-OU-Migration/OU-Migration-%20%2816%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 5 — Modify CLIENT1 Computer Name

Rename CLIENT1 within the domain if needed, and verify the updated name appears correctly in ADUC.

### Screenshot 1

![Step 5 — Modify CLIENT1 Computer Name - Screenshot 1](05-Client1-Computername-Modification/Modification-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 5 — Modify CLIENT1 Computer Name - Screenshot 2](05-Client1-Computername-Modification/Modification-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 5 — Modify CLIENT1 Computer Name - Screenshot 3](05-Client1-Computername-Modification/Modification-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 5 — Modify CLIENT1 Computer Name - Screenshot 4](05-Client1-Computername-Modification/Modification-%20%284%29.png)

**Continue the configuration (step 4 of 8) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 5 — Modify CLIENT1 Computer Name - Screenshot 5](05-Client1-Computername-Modification/Modification-%20%285%29.png)

**Continue the configuration (step 5 of 8) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 5 — Modify CLIENT1 Computer Name - Screenshot 6](05-Client1-Computername-Modification/Modification-%20%286%29.png)

**Continue the configuration (step 6 of 8) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 5 — Modify CLIENT1 Computer Name - Screenshot 7](05-Client1-Computername-Modification/Modification-%20%287%29.png)

**Continue the configuration (step 7 of 8) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 5 — Modify CLIENT1 Computer Name - Screenshot 8](05-Client1-Computername-Modification/Modification-%20%288%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 6 — Bulk User Creation via CSV + PowerShell

Create a CSV file with user data and use a PowerShell script to bulk-create users in Active Directory.

**CSV Format:**
```csv
FirstName,LastName,Username,Department,Title
Christopher,Brown,christopher.brown,Development,Senior Developer
Yuki,Tanaka,yuki.tanaka,Development,Frontend Developer
...
```

**PowerShell Script:**
```powershell
Import-Csv C:\users.csv | ForEach-Object {
    New-ADUser -Name "$($_.FirstName) $($_.LastName)" `
        -GivenName $_.FirstName `
        -Surname $_.LastName `
        -SamAccountName $_.Username `
        -UserPrincipalName "$($_.Username)@vertex.local" `
        -Path "OU=$($_.Department),OU=HQ-London,OU=VERTEX,DC=vertex,DC=local" `
        -AccountPassword (ConvertTo-SecureString 'P@ssw0rd123!' -AsPlainText -Force) `
        -Enabled $true `
        -Title $_.Title `
        -Department $_.Department
}
```

### Screenshot 1

![Step 6 — Bulk User Creation via CSV + PowerShell - Screenshot 1](06-Bulk-User-Provisioning-via-CSV/Bulk-User-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 6 — Bulk User Creation via CSV + PowerShell - Screenshot 2](06-Bulk-User-Provisioning-via-CSV/Bulk-User-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 6 — Bulk User Creation via CSV + PowerShell - Screenshot 3](06-Bulk-User-Provisioning-via-CSV/Bulk-User-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 6 — Bulk User Creation via CSV + PowerShell - Screenshot 4](06-Bulk-User-Provisioning-via-CSV/Bulk-User-%20%284%29.png)

**Continue the configuration (step 4 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 6 — Bulk User Creation via CSV + PowerShell - Screenshot 5](06-Bulk-User-Provisioning-via-CSV/Bulk-User-%20%285%29.png)

**Continue the configuration (step 5 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 6 — Bulk User Creation via CSV + PowerShell - Screenshot 6](06-Bulk-User-Provisioning-via-CSV/Bulk-User-%20%286%29.png)

**Continue the configuration (step 6 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 6 — Bulk User Creation via CSV + PowerShell - Screenshot 7](06-Bulk-User-Provisioning-via-CSV/Bulk-User-%20%287%29.png)

**Continue the configuration (step 7 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 6 — Bulk User Creation via CSV + PowerShell - Screenshot 8](06-Bulk-User-Provisioning-via-CSV/Bulk-User-%20%288%29.png)

**Continue the configuration (step 8 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 6 — Bulk User Creation via CSV + PowerShell - Screenshot 9](06-Bulk-User-Provisioning-via-CSV/Bulk-User-%20%289%29.png)

**Continue the configuration (step 9 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 6 — Bulk User Creation via CSV + PowerShell - Screenshot 10](06-Bulk-User-Provisioning-via-CSV/Bulk-User-%20%2810%29.png)

**Continue the configuration (step 10 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 6 — Bulk User Creation via CSV + PowerShell - Screenshot 11](06-Bulk-User-Provisioning-via-CSV/Bulk-User-%20%2811%29.png)

**Continue the configuration (step 11 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 6 — Bulk User Creation via CSV + PowerShell - Screenshot 12](06-Bulk-User-Provisioning-via-CSV/Bulk-User-%20%2812%29.png)

**Continue the configuration (step 12 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 6 — Bulk User Creation via CSV + PowerShell - Screenshot 13](06-Bulk-User-Provisioning-via-CSV/Bulk-User-%20%2813%29.png)

**Continue the configuration (step 13 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 6 — Bulk User Creation via CSV + PowerShell - Screenshot 14](06-Bulk-User-Provisioning-via-CSV/Bulk-User-%20%2814%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 7 — Verify User Count

Verify the total number of users created in Active Directory using PowerShell:

```powershell
(Get-ADUser -Filter *).Count
Get-ADUser -Filter * -SearchBase "OU=VERTEX,DC=vertex,DC=local" | Measure-Object
```

### Screenshot 1

![Step 7 — Verify User Count - Screenshot 1](07-Active-Directory-User-Count-Verification/Verification-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 7 — Verify User Count - Screenshot 2](07-Active-Directory-User-Count-Verification/Verification-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 7 — Verify User Count - Screenshot 3](07-Active-Directory-User-Count-Verification/Verification-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 7 — Verify User Count - Screenshot 4](07-Active-Directory-User-Count-Verification/Verification-%20%284%29.png)

**Final result — verify the configuration is complete and working.**

---

## 🔗 Navigation

[⬆️ Back to Top](#)

[📚 Back to Master README](../README.md)
