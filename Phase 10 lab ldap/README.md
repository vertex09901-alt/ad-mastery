# 📂 Phase 10 — LDAP Operations

> **Connect to AD using LDP.exe, run LDAP search queries with filters, modify attributes via LDP, install and explore AD with Sysinternals ADExplorer, run LDAP queries with PowerShell, and connect using LDAPS (Secure LDAP, port 636).**

**Prerequisites:** Phase 02 completed — AD operational.

---
## 📑 Table of Contents

- [Step 1 — Connect to AD Using LDP.exe](#step-1-connect-to-ad-using-ldp.exe)
- [Step 2 — Run LDAP Search Queries](#step-2-run-ldap-search-queries)
- [Step 3 — Modify an Attribute with LDP](#step-3-modify-an-attribute-with-ldp)
- [Step 4 — Install & Use Sysinternals ADExplorer](#step-4-install-use-sysinternals-adexplorer)
- [Step 5 — LDAP Queries with PowerShell](#step-5-ldap-queries-with-powershell)
- [Step 6 — Connect with LDAPS (Port 636)](#step-6-connect-with-ldaps-port-636)

---

## Step 1 — Connect to AD Using LDP.exe

Launch LDP.exe and connect to the domain controller:

```
Run → ldp.exe
Connection → Connect → Server: DC1.vertex.local, Port: 389
Connection → Bind → Bind as currently logged on user
```

### Screenshot 1

![Step 1 — Connect to AD Using LDP.exe - Screenshot 1](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 1 — Connect to AD Using LDP.exe - Screenshot 2](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 1 — Connect to AD Using LDP.exe - Screenshot 3](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 1 — Connect to AD Using LDP.exe - Screenshot 4](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%284%29.png)

**Continue the configuration (step 4 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 1 — Connect to AD Using LDP.exe - Screenshot 5](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%285%29.png)

**Continue the configuration (step 5 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 1 — Connect to AD Using LDP.exe - Screenshot 6](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%286%29.png)

**Continue the configuration (step 6 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 1 — Connect to AD Using LDP.exe - Screenshot 7](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%287%29.png)

**Continue the configuration (step 7 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 1 — Connect to AD Using LDP.exe - Screenshot 8](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%288%29.png)

**Continue the configuration (step 8 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 1 — Connect to AD Using LDP.exe - Screenshot 9](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%289%29.png)

**Continue the configuration (step 9 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 1 — Connect to AD Using LDP.exe - Screenshot 10](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%2810%29.png)

**Continue the configuration (step 10 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 1 — Connect to AD Using LDP.exe - Screenshot 11](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%2811%29.png)

**Continue the configuration (step 11 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 1 — Connect to AD Using LDP.exe - Screenshot 12](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%2812%29.png)

**Continue the configuration (step 12 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 1 — Connect to AD Using LDP.exe - Screenshot 13](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%2813%29.png)

**Continue the configuration (step 13 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 1 — Connect to AD Using LDP.exe - Screenshot 14](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%2814%29.png)

**Continue the configuration (step 14 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 1 — Connect to AD Using LDP.exe - Screenshot 15](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%2815%29.png)

**Continue the configuration (step 15 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 1 — Connect to AD Using LDP.exe - Screenshot 16](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%2816%29.png)

**Continue the configuration (step 16 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 1 — Connect to AD Using LDP.exe - Screenshot 17](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%2817%29.png)

**Continue the configuration (step 17 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 1 — Connect to AD Using LDP.exe - Screenshot 18](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%2818%29.png)

**Continue the configuration (step 18 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 1 — Connect to AD Using LDP.exe - Screenshot 19](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%2819%29.png)

**Continue the configuration (step 19 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 1 — Connect to AD Using LDP.exe - Screenshot 20](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%2820%29.png)

**Continue the configuration (step 20 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 1 — Connect to AD Using LDP.exe - Screenshot 21](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%2821%29.png)

**Continue the configuration (step 21 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 22

![Step 1 — Connect to AD Using LDP.exe - Screenshot 22](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%2822%29.png)

**Continue the configuration (step 22 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 23

![Step 1 — Connect to AD Using LDP.exe - Screenshot 23](01-CONNECT%20TO%20AD%20USING%20LDP.EXE/LDP%20%2823%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 2 — Run LDAP Search Queries

Execute LDAP queries in LDP to search the directory:

```
Base DN: DC=vertex,DC=local
Filter: (&(objectClass=user)(department=IT))
Scope: Subtree
```

### Screenshot 1

![Step 2 — Run LDAP Search Queries - Screenshot 1](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 2 — Run LDAP Search Queries - Screenshot 2](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 2 — Run LDAP Search Queries - Screenshot 3](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 2 — Run LDAP Search Queries - Screenshot 4](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%284%29.png)

**Continue the configuration (step 4 of 19) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 2 — Run LDAP Search Queries - Screenshot 5](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%285%29.png)

**Continue the configuration (step 5 of 19) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 2 — Run LDAP Search Queries - Screenshot 6](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%286%29.png)

**Continue the configuration (step 6 of 19) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 2 — Run LDAP Search Queries - Screenshot 7](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%287%29.png)

**Continue the configuration (step 7 of 19) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 2 — Run LDAP Search Queries - Screenshot 8](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%288%29.png)

**Continue the configuration (step 8 of 19) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 2 — Run LDAP Search Queries - Screenshot 9](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%289%29.png)

**Continue the configuration (step 9 of 19) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 2 — Run LDAP Search Queries - Screenshot 10](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%2810%29.png)

**Continue the configuration (step 10 of 19) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 2 — Run LDAP Search Queries - Screenshot 11](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%2811%29.png)

**Continue the configuration (step 11 of 19) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 2 — Run LDAP Search Queries - Screenshot 12](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%2812%29.png)

**Continue the configuration (step 12 of 19) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 2 — Run LDAP Search Queries - Screenshot 13](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%2813%29.png)

**Continue the configuration (step 13 of 19) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 2 — Run LDAP Search Queries - Screenshot 14](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%2814%29.png)

**Continue the configuration (step 14 of 19) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 2 — Run LDAP Search Queries - Screenshot 15](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%2815%29.png)

**Continue the configuration (step 15 of 19) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 2 — Run LDAP Search Queries - Screenshot 16](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%2816%29.png)

**Continue the configuration (step 16 of 19) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 2 — Run LDAP Search Queries - Screenshot 17](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%2817%29.png)

**Continue the configuration (step 17 of 19) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 2 — Run LDAP Search Queries - Screenshot 18](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%2818%29.png)

**Continue the configuration (step 18 of 19) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 2 — Run LDAP Search Queries - Screenshot 19](02-RUN%20LDAP%20SEARCH%20QUERIES/SEARCH%20QUERIES-%20%2819%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 3 — Modify an Attribute with LDP

Use LDP.exe to modify a user attribute:

```
Browse → Modify
DN: CN=John Smith,OU=IT,OU=HQ-London,OU=VERTEX,DC=vertex,DC=local
Attribute: description
Values: Senior System Administrator
Operation: Replace
```

### Screenshot 1

![Step 3 — Modify an Attribute with LDP - Screenshot 1](03-MODIFY%20AN%20ATTRIBUTE%20WITH%20LDP/MODIFY-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 3 — Modify an Attribute with LDP - Screenshot 2](03-MODIFY%20AN%20ATTRIBUTE%20WITH%20LDP/MODIFY-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 3 — Modify an Attribute with LDP - Screenshot 3](03-MODIFY%20AN%20ATTRIBUTE%20WITH%20LDP/MODIFY-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 3 — Modify an Attribute with LDP - Screenshot 4](03-MODIFY%20AN%20ATTRIBUTE%20WITH%20LDP/MODIFY-%20%284%29.png)

**Continue the configuration (step 4 of 5) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 3 — Modify an Attribute with LDP - Screenshot 5](03-MODIFY%20AN%20ATTRIBUTE%20WITH%20LDP/MODIFY-%20%285%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 4 — Install & Use Sysinternals ADExplorer

Download and run Sysinternals ADExplorer to visually browse the AD tree structure. Connect to `DC1.vertex.local` and explore objects, attributes, and permissions.

### Screenshot 1

![Step 4 — Install & Use Sysinternals ADExplorer - Screenshot 1](04-INSTALL%20AND%20USE%20ADEXPLORER/%20ADEXPLORER-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 4 — Install & Use Sysinternals ADExplorer - Screenshot 2](04-INSTALL%20AND%20USE%20ADEXPLORER/%20ADEXPLORER-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 4 — Install & Use Sysinternals ADExplorer - Screenshot 3](04-INSTALL%20AND%20USE%20ADEXPLORER/%20ADEXPLORER-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 4 — Install & Use Sysinternals ADExplorer - Screenshot 4](04-INSTALL%20AND%20USE%20ADEXPLORER/%20ADEXPLORER-%20%284%29.png)

**Continue the configuration (step 4 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 4 — Install & Use Sysinternals ADExplorer - Screenshot 5](04-INSTALL%20AND%20USE%20ADEXPLORER/%20ADEXPLORER-%20%285%29.png)

**Continue the configuration (step 5 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 4 — Install & Use Sysinternals ADExplorer - Screenshot 6](04-INSTALL%20AND%20USE%20ADEXPLORER/%20ADEXPLORER-%20%286%29.png)

**Continue the configuration (step 6 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 4 — Install & Use Sysinternals ADExplorer - Screenshot 7](04-INSTALL%20AND%20USE%20ADEXPLORER/%20ADEXPLORER-%20%287%29.png)

**Continue the configuration (step 7 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 4 — Install & Use Sysinternals ADExplorer - Screenshot 8](04-INSTALL%20AND%20USE%20ADEXPLORER/%20ADEXPLORER-%20%288%29.png)

**Continue the configuration (step 8 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 4 — Install & Use Sysinternals ADExplorer - Screenshot 9](04-INSTALL%20AND%20USE%20ADEXPLORER/%20ADEXPLORER-%20%289%29.png)

**Continue the configuration (step 9 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 4 — Install & Use Sysinternals ADExplorer - Screenshot 10](04-INSTALL%20AND%20USE%20ADEXPLORER/%20ADEXPLORER-%20%2810%29.png)

**Continue the configuration (step 10 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 4 — Install & Use Sysinternals ADExplorer - Screenshot 11](04-INSTALL%20AND%20USE%20ADEXPLORER/%20ADEXPLORER-%20%2811%29.png)

**Continue the configuration (step 11 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 4 — Install & Use Sysinternals ADExplorer - Screenshot 12](04-INSTALL%20AND%20USE%20ADEXPLORER/%20ADEXPLORER-%20%2812%29.png)

**Continue the configuration (step 12 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 4 — Install & Use Sysinternals ADExplorer - Screenshot 13](04-INSTALL%20AND%20USE%20ADEXPLORER/%20ADEXPLORER-%20%2813%29.png)

**Continue the configuration (step 13 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 4 — Install & Use Sysinternals ADExplorer - Screenshot 14](04-INSTALL%20AND%20USE%20ADEXPLORER/%20ADEXPLORER-%20%2814%29.png)

**Continue the configuration (step 14 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 4 — Install & Use Sysinternals ADExplorer - Screenshot 15](04-INSTALL%20AND%20USE%20ADEXPLORER/%20ADEXPLORER-%20%2815%29.png)

**Continue the configuration (step 15 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 4 — Install & Use Sysinternals ADExplorer - Screenshot 16](04-INSTALL%20AND%20USE%20ADEXPLORER/%20ADEXPLORER-%20%2816%29.png)

**Continue the configuration (step 16 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 4 — Install & Use Sysinternals ADExplorer - Screenshot 17](04-INSTALL%20AND%20USE%20ADEXPLORER/%20ADEXPLORER-%20%2817%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 5 — LDAP Queries with PowerShell

Run LDAP queries using PowerShell and the .NET DirectorySearcher:

```powershell
# Using Get-ADUser with LDAP filter
Get-ADUser -LDAPFilter '(department=IT)' -Properties *

# Using DirectorySearcher
$searcher = [adsisearcher]'(&(objectClass=user)(department=Finance))'
$searcher.FindAll()
```

### Screenshot 1

![Step 5 — LDAP Queries with PowerShell - Screenshot 1](05-LDAP%20QUERIES%20WITH%20POWERSHELL/LDAP%20QUERIES-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 5 — LDAP Queries with PowerShell - Screenshot 2](05-LDAP%20QUERIES%20WITH%20POWERSHELL/LDAP%20QUERIES-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 5 — LDAP Queries with PowerShell - Screenshot 3](05-LDAP%20QUERIES%20WITH%20POWERSHELL/LDAP%20QUERIES-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 5 — LDAP Queries with PowerShell - Screenshot 4](05-LDAP%20QUERIES%20WITH%20POWERSHELL/LDAP%20QUERIES-%20%284%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 6 — Connect with LDAPS (Port 636)

Configure and test LDAPS (LDAP over SSL/TLS) on port 636:

```
LDP.exe → Connection → Connect
Server: DC1.vertex.local
Port: 636
☑ SSL
```

Note: LDAPS requires a certificate installed on the DC.

### Screenshot 1

![Step 6 — Connect with LDAPS (Port 636) - Screenshot 1](06-CONNECT%20WITH%20LDAPS%20(SECURE%20LDAP,%20PORT%20636)/PORT%20636-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 6 — Connect with LDAPS (Port 636) - Screenshot 2](06-CONNECT%20WITH%20LDAPS%20(SECURE%20LDAP,%20PORT%20636)/PORT%20636-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 6 — Connect with LDAPS (Port 636) - Screenshot 3](06-CONNECT%20WITH%20LDAPS%20(SECURE%20LDAP,%20PORT%20636)/PORT%20636-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 6 — Connect with LDAPS (Port 636) - Screenshot 4](06-CONNECT%20WITH%20LDAPS%20(SECURE%20LDAP,%20PORT%20636)/PORT%20636-%20%284%29.png)

**Continue the configuration (step 4 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 6 — Connect with LDAPS (Port 636) - Screenshot 5](06-CONNECT%20WITH%20LDAPS%20(SECURE%20LDAP,%20PORT%20636)/PORT%20636-%20%285%29.png)

**Continue the configuration (step 5 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 6 — Connect with LDAPS (Port 636) - Screenshot 6](06-CONNECT%20WITH%20LDAPS%20(SECURE%20LDAP,%20PORT%20636)/PORT%20636-%20%286%29.png)

**Continue the configuration (step 6 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 6 — Connect with LDAPS (Port 636) - Screenshot 7](06-CONNECT%20WITH%20LDAPS%20(SECURE%20LDAP,%20PORT%20636)/PORT%20636-%20%287%29.png)

**Continue the configuration (step 7 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 6 — Connect with LDAPS (Port 636) - Screenshot 8](06-CONNECT%20WITH%20LDAPS%20(SECURE%20LDAP,%20PORT%20636)/PORT%20636-%20%288%29.png)

**Continue the configuration (step 8 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 6 — Connect with LDAPS (Port 636) - Screenshot 9](06-CONNECT%20WITH%20LDAPS%20(SECURE%20LDAP,%20PORT%20636)/PORT%20636-%20%289%29.png)

**Final result — verify the configuration is complete and working.**

---

## 🔗 Navigation

[⬆️ Back to Top](#)

[📚 Back to Master README](../README.md)
