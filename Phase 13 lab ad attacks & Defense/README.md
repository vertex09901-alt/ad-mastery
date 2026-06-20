# 🛡️ Phase 13 — AD Attacks & Defense

> **Disable LLMNR and NBT-NS as quick-win defenses, simulate and detect password spraying attacks, perform Kerberoasting simulation and defense, test AS-REP Roasting on accounts without pre-authentication, detect DCSync attacks, and verify all defenses are working.**

**Prerequisites:** All prior phases completed — full enterprise AD lab with security controls.

---
## 📑 Table of Contents

- [Step 1 — Disable LLMNR & NBT-NS](#step-1-disable-llmnr-nbt-ns)
- [Step 2 — Simulate & Detect Password Spraying](#step-2-simulate-detect-password-spraying)
- [Step 3 — Kerberoasting Simulation & Defense](#step-3-kerberoasting-simulation-defense)
- [Step 4 — AS-REP Roasting Detection](#step-4-as-rep-roasting-detection)
- [Step 5 — DCSync Detection & Analysis](#step-5-dcsync-detection-analysis)
- [Step 6 — Verify All Defenses](#step-6-verify-all-defenses)

---

## Step 1 — Disable LLMNR & NBT-NS

Disable LLMNR (Link-Local Multicast Name Resolution) and NBT-NS (NetBIOS Name Service) to prevent poisoning attacks:

**Via GPO:**
```
Computer Configuration → Admin Templates → Network → DNS Client
→ Turn off multicast name resolution → Enabled
```

**Disable NBT-NS via registry or network adapter settings.**

### Screenshot 1

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 1](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 2](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 3](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 4](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%284%29.png)

**Continue the configuration (step 4 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 5](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%285%29.png)

**Continue the configuration (step 5 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 6](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%286%29.png)

**Continue the configuration (step 6 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 7](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%287%29.png)

**Continue the configuration (step 7 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 8](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%288%29.png)

**Continue the configuration (step 8 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 9](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%289%29.png)

**Continue the configuration (step 9 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 10](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%2810%29.png)

**Continue the configuration (step 10 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 11](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%2811%29.png)

**Continue the configuration (step 11 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 12](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%2812%29.png)

**Continue the configuration (step 12 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 13](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%2813%29.png)

**Continue the configuration (step 13 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 14](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%2814%29.png)

**Continue the configuration (step 14 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 15](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%2815%29.png)

**Continue the configuration (step 15 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 16](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%2816%29.png)

**Continue the configuration (step 16 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 17](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%2817%29.png)

**Continue the configuration (step 17 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 18](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%2818%29.png)

**Continue the configuration (step 18 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 19](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%2819%29.png)

**Continue the configuration (step 19 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 20](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%2820%29.png)

**Continue the configuration (step 20 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 21](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%2821%29.png)

**Continue the configuration (step 21 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 22

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 22](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%2822%29.png)

**Continue the configuration (step 22 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 23

![Step 1 — Disable LLMNR & NBT-NS - Screenshot 23](01-DISABLE%20LLMNR%20AND%20NBT-NS%20(Quick%20Win%20Defense)/Quick%20Win%20Defense-%20%2823%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 2 — Simulate & Detect Password Spraying

Simulate a password spraying attack and detect it via Event Viewer:

```powershell
# Simulate spray — try common password against multiple accounts
$users = Get-ADUser -Filter * -SearchBase 'OU=HQ-London,OU=VERTEX,DC=vertex,DC=local'
foreach ($user in $users) {
    # Attempt logon with a bad password (simulation)
}
```

**Detection:** Look for Event ID 4625 (failed logon) with multiple different usernames from the same source in a short window.

### Screenshot 1

![Step 2 — Simulate & Detect Password Spraying - Screenshot 1](02-SIMULATE%20AND%20DETECT%20PASSWORD%20SPRAYING/SPRAYING-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 2 — Simulate & Detect Password Spraying - Screenshot 2](02-SIMULATE%20AND%20DETECT%20PASSWORD%20SPRAYING/SPRAYING-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 2 — Simulate & Detect Password Spraying - Screenshot 3](02-SIMULATE%20AND%20DETECT%20PASSWORD%20SPRAYING/SPRAYING-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 2 — Simulate & Detect Password Spraying - Screenshot 4](02-SIMULATE%20AND%20DETECT%20PASSWORD%20SPRAYING/SPRAYING-%20%284%29.png)

**Continue the configuration (step 4 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 2 — Simulate & Detect Password Spraying - Screenshot 5](02-SIMULATE%20AND%20DETECT%20PASSWORD%20SPRAYING/SPRAYING-%20%285%29.png)

**Continue the configuration (step 5 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 2 — Simulate & Detect Password Spraying - Screenshot 6](02-SIMULATE%20AND%20DETECT%20PASSWORD%20SPRAYING/SPRAYING-%20%286%29.png)

**Continue the configuration (step 6 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 2 — Simulate & Detect Password Spraying - Screenshot 7](02-SIMULATE%20AND%20DETECT%20PASSWORD%20SPRAYING/SPRAYING-%20%287%29.png)

**Continue the configuration (step 7 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 2 — Simulate & Detect Password Spraying - Screenshot 8](02-SIMULATE%20AND%20DETECT%20PASSWORD%20SPRAYING/SPRAYING-%20%288%29.png)

**Continue the configuration (step 8 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 2 — Simulate & Detect Password Spraying - Screenshot 9](02-SIMULATE%20AND%20DETECT%20PASSWORD%20SPRAYING/SPRAYING-%20%289%29.png)

**Continue the configuration (step 9 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 2 — Simulate & Detect Password Spraying - Screenshot 10](02-SIMULATE%20AND%20DETECT%20PASSWORD%20SPRAYING/SPRAYING-%20%2810%29.png)

**Continue the configuration (step 10 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 2 — Simulate & Detect Password Spraying - Screenshot 11](02-SIMULATE%20AND%20DETECT%20PASSWORD%20SPRAYING/SPRAYING-%20%2811%29.png)

**Continue the configuration (step 11 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 2 — Simulate & Detect Password Spraying - Screenshot 12](02-SIMULATE%20AND%20DETECT%20PASSWORD%20SPRAYING/SPRAYING-%20%2812%29.png)

**Continue the configuration (step 12 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 2 — Simulate & Detect Password Spraying - Screenshot 13](02-SIMULATE%20AND%20DETECT%20PASSWORD%20SPRAYING/SPRAYING-%20%2813%29.png)

**Continue the configuration (step 13 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 2 — Simulate & Detect Password Spraying - Screenshot 14](02-SIMULATE%20AND%20DETECT%20PASSWORD%20SPRAYING/SPRAYING-%20%2814%29.png)

**Continue the configuration (step 14 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 2 — Simulate & Detect Password Spraying - Screenshot 15](02-SIMULATE%20AND%20DETECT%20PASSWORD%20SPRAYING/SPRAYING-%20%2815%29.png)

**Continue the configuration (step 15 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 2 — Simulate & Detect Password Spraying - Screenshot 16](02-SIMULATE%20AND%20DETECT%20PASSWORD%20SPRAYING/SPRAYING-%20%2816%29.png)

**Continue the configuration (step 16 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 2 — Simulate & Detect Password Spraying - Screenshot 17](02-SIMULATE%20AND%20DETECT%20PASSWORD%20SPRAYING/SPRAYING-%20%2817%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 3 — Kerberoasting Simulation & Defense

Simulate Kerberoasting and implement defenses:

```powershell
# Find Kerberoastable accounts
Get-ADUser -Filter 'ServicePrincipalName -like "*"' -Properties ServicePrincipalName
```

**Defense:**
- Use long (25+ char), random passwords for service accounts
- Use Group Managed Service Accounts (gMSA)
- Monitor Event ID 4769 with RC4 encryption type

### Screenshot 1

![Step 3 — Kerberoasting Simulation & Defense - Screenshot 1](03-KERBEROASTING%20SIMULATION%20AND%20DEFENSE/KERBEROASTING-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 3 — Kerberoasting Simulation & Defense - Screenshot 2](03-KERBEROASTING%20SIMULATION%20AND%20DEFENSE/KERBEROASTING-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 3 — Kerberoasting Simulation & Defense - Screenshot 3](03-KERBEROASTING%20SIMULATION%20AND%20DEFENSE/KERBEROASTING-%20%283%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 4 — AS-REP Roasting Detection

Find accounts vulnerable to AS-REP Roasting (pre-auth disabled):

```powershell
Get-ADUser -Filter 'DoesNotRequirePreAuth -eq $true' -Properties DoesNotRequirePreAuth
```

**Defense:** Ensure all accounts require Kerberos pre-authentication. Monitor Event ID 4768.

### Screenshot 1

![Step 4 — AS-REP Roasting Detection - Screenshot 1](04-AS-REP%20ROASTING%20(NO%20PRE-AUTH%20ACCOUNTS)/%20ROASTING-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 4 — AS-REP Roasting Detection - Screenshot 2](04-AS-REP%20ROASTING%20(NO%20PRE-AUTH%20ACCOUNTS)/%20ROASTING-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 4 — AS-REP Roasting Detection - Screenshot 3](04-AS-REP%20ROASTING%20(NO%20PRE-AUTH%20ACCOUNTS)/%20ROASTING-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 4 — AS-REP Roasting Detection - Screenshot 4](04-AS-REP%20ROASTING%20(NO%20PRE-AUTH%20ACCOUNTS)/%20ROASTING-%20%284%29.png)

**Continue the configuration (step 4 of 6) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 4 — AS-REP Roasting Detection - Screenshot 5](04-AS-REP%20ROASTING%20(NO%20PRE-AUTH%20ACCOUNTS)/%20ROASTING-%20%285%29.png)

**Continue the configuration (step 5 of 6) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 4 — AS-REP Roasting Detection - Screenshot 6](04-AS-REP%20ROASTING%20(NO%20PRE-AUTH%20ACCOUNTS)/%20ROASTING-%20%286%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 5 — DCSync Detection & Analysis

Detect DCSync attacks by monitoring for replication requests from non-DC sources:

**Detection:**
- Event ID 4662 — Directory Service Access
- Look for `Replicating Directory Changes` permissions on non-DC accounts

```powershell
# Check who has replication rights
(Get-Acl 'AD:\DC=vertex,DC=local').Access |
    Where-Object { $_.ObjectType -eq '1131f6ad-9c07-11d1-f79f-00c04fc2dcd2' }
```

### Screenshot 1

![Step 5 — DCSync Detection & Analysis - Screenshot 1](05-DCSync-Detection-And-Analysis/DCSync-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 5 — DCSync Detection & Analysis - Screenshot 2](05-DCSync-Detection-And-Analysis/DCSync-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 5 — DCSync Detection & Analysis - Screenshot 3](05-DCSync-Detection-And-Analysis/DCSync-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 5 — DCSync Detection & Analysis - Screenshot 4](05-DCSync-Detection-And-Analysis/DCSync-%20%284%29.png)

**Continue the configuration (step 4 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 5 — DCSync Detection & Analysis - Screenshot 5](05-DCSync-Detection-And-Analysis/DCSync-%20%285%29.png)

**Continue the configuration (step 5 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 5 — DCSync Detection & Analysis - Screenshot 6](05-DCSync-Detection-And-Analysis/DCSync-%20%286%29.png)

**Continue the configuration (step 6 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 5 — DCSync Detection & Analysis - Screenshot 7](05-DCSync-Detection-And-Analysis/DCSync-%20%287%29.png)

**Continue the configuration (step 7 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 5 — DCSync Detection & Analysis - Screenshot 8](05-DCSync-Detection-And-Analysis/DCSync-%20%288%29.png)

**Continue the configuration (step 8 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 5 — DCSync Detection & Analysis - Screenshot 9](05-DCSync-Detection-And-Analysis/DCSync-%20%289%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 6 — Verify All Defenses

Run a comprehensive defense verification:

```powershell
# Verify LLMNR is disabled
Get-ItemProperty 'HKLM:\SOFTWARE\Policies\Microsoft\Windows NT\DNSClient' -Name EnableMulticast

# Verify no accounts without pre-auth
Get-ADUser -Filter 'DoesNotRequirePreAuth -eq $true'

# Verify admin tiering
Get-ADGroupMember 'Domain Admins'

# Verify LAPS
Get-ADComputer -Filter * -Properties ms-Mcs-AdmPwdExpirationTime

# Check audit policy
auditpol /get /category:*
```

### Screenshot 1

![Step 6 — Verify All Defenses - Screenshot 1](06-VERIFY%20YOUR%20DEFENSES%20ARE%20WORKING/VERIFY-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 6 — Verify All Defenses - Screenshot 2](06-VERIFY%20YOUR%20DEFENSES%20ARE%20WORKING/VERIFY-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 6 — Verify All Defenses - Screenshot 3](06-VERIFY%20YOUR%20DEFENSES%20ARE%20WORKING/VERIFY-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 6 — Verify All Defenses - Screenshot 4](06-VERIFY%20YOUR%20DEFENSES%20ARE%20WORKING/VERIFY-%20%284%29.png)

**Continue the configuration (step 4 of 5) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 6 — Verify All Defenses - Screenshot 5](06-VERIFY%20YOUR%20DEFENSES%20ARE%20WORKING/VERIFY-%20%285%29.png)

**Final result — verify the configuration is complete and working.**

---

## 🔗 Navigation

[⬆️ Back to Top](#)

[📚 Back to Master README](../README.md)
