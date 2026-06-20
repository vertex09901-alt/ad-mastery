# 🏗️ Phase 02 — Install Active Directory

> **Install the AD DS role on DC1, promote it to the first domain controller of the `vertex.local` forest, create the full OU structure (VERTEX → HQ-London, Branch-Mumbai, Branch-Dubai, Branch-Singapore), join DC2 and CLIENT1 to the domain, and promote DC2 as an additional domain controller.**

**Prerequisites:** Phase 01 completed — all three VMs running and reachable on 192.168.10.0/24.

---
## 📑 Table of Contents

- [Step 1 — Install AD DS Role on DC1](#step-1-install-ad-ds-role-on-dc1)
- [Step 2 — Promote DC1 to Domain Controller](#step-2-promote-dc1-to-domain-controller)
- [Step 3 — Open Active Directory Users & Computers](#step-3-open-active-directory-users-computers)
- [Step 4 — Create the Vertex OU Structure](#step-4-create-the-vertex-ou-structure)
- [Step 5 — Create London HQ Users, Groups & Computers OUs](#step-5-create-london-hq-users-groups-computers-ous)
- [Step 6 — Create Security Groups & Server OUs](#step-6-create-security-groups-server-ous)
- [Step 7 — Configure AD Sites & Services](#step-7-configure-ad-sites-services)
- [Step 8 — Join DC2 to the Domain](#step-8-join-dc2-to-the-domain)
- [Step 9 — Verify CLIENT1 Domain Connectivity](#step-9-verify-client1-domain-connectivity)
- [Step 10 — Install AD DS Role on DC2](#step-10-install-ad-ds-role-on-dc2)
- [Step 11 — Promote DC2 as Additional DC](#step-11-promote-dc2-as-additional-dc)

---

## Step 1 — Install AD DS Role on DC1

Use Server Manager to add the Active Directory Domain Services (AD DS) role on DC1. This installs the necessary components before promoting DC1 to a domain controller.

### Screenshot 1

![Step 1 — Install AD DS Role on DC1 - Screenshot 1](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 1 — Install AD DS Role on DC1 - Screenshot 2](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 1 — Install AD DS Role on DC1 - Screenshot 3](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 1 — Install AD DS Role on DC1 - Screenshot 4](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%284%29.png)

**Continue the configuration (step 4 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 1 — Install AD DS Role on DC1 - Screenshot 5](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%285%29.png)

**Continue the configuration (step 5 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 1 — Install AD DS Role on DC1 - Screenshot 6](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%286%29.png)

**Continue the configuration (step 6 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 1 — Install AD DS Role on DC1 - Screenshot 7](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%287%29.png)

**Continue the configuration (step 7 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 1 — Install AD DS Role on DC1 - Screenshot 8](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%288%29.png)

**Continue the configuration (step 8 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 1 — Install AD DS Role on DC1 - Screenshot 9](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%289%29.png)

**Continue the configuration (step 9 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 1 — Install AD DS Role on DC1 - Screenshot 10](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%2810%29.png)

**Continue the configuration (step 10 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 1 — Install AD DS Role on DC1 - Screenshot 11](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%2811%29.png)

**Continue the configuration (step 11 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 1 — Install AD DS Role on DC1 - Screenshot 12](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%2812%29.png)

**Continue the configuration (step 12 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 1 — Install AD DS Role on DC1 - Screenshot 13](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%2813%29.png)

**Continue the configuration (step 13 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 1 — Install AD DS Role on DC1 - Screenshot 14](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%2814%29.png)

**Continue the configuration (step 14 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 1 — Install AD DS Role on DC1 - Screenshot 15](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%2815%29.png)

**Continue the configuration (step 15 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 1 — Install AD DS Role on DC1 - Screenshot 16](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%2816%29.png)

**Continue the configuration (step 16 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 1 — Install AD DS Role on DC1 - Screenshot 17](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%2817%29.png)

**Continue the configuration (step 17 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 1 — Install AD DS Role on DC1 - Screenshot 18](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%2818%29.png)

**Continue the configuration (step 18 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 1 — Install AD DS Role on DC1 - Screenshot 19](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%2819%29.png)

**Continue the configuration (step 19 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 1 — Install AD DS Role on DC1 - Screenshot 20](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%2820%29.png)

**Continue the configuration (step 20 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 1 — Install AD DS Role on DC1 - Screenshot 21](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%2821%29.png)

**Continue the configuration (step 21 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 22

![Step 1 — Install AD DS Role on DC1 - Screenshot 22](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%2822%29.png)

**Continue the configuration (step 22 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 23

![Step 1 — Install AD DS Role on DC1 - Screenshot 23](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%2823%29.png)

**Continue the configuration (step 23 of 24) — follow the red arrows/boxes for guidance.**

### Screenshot 24

![Step 1 — Install AD DS Role on DC1 - Screenshot 24](01-DC1-ADDS-Role-Installation/ADDS-Role-Installation-%20%2824%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 2 — Promote DC1 to Domain Controller

Promote DC1 to the first domain controller in a **new forest** with the root domain name `vertex.local`. Set the DSRM password and configure DNS delegation.

### Screenshot 1

![Step 2 — Promote DC1 to Domain Controller - Screenshot 1](02-DC1-Promote-To-Domain-Controller/Domain-Controller-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 2 — Promote DC1 to Domain Controller - Screenshot 2](02-DC1-Promote-To-Domain-Controller/Domain-Controller-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 2 — Promote DC1 to Domain Controller - Screenshot 3](02-DC1-Promote-To-Domain-Controller/Domain-Controller-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 2 — Promote DC1 to Domain Controller - Screenshot 4](02-DC1-Promote-To-Domain-Controller/Domain-Controller-%20%284%29.png)

**Continue the configuration (step 4 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 2 — Promote DC1 to Domain Controller - Screenshot 5](02-DC1-Promote-To-Domain-Controller/Domain-Controller-%20%285%29.png)

**Continue the configuration (step 5 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 2 — Promote DC1 to Domain Controller - Screenshot 6](02-DC1-Promote-To-Domain-Controller/Domain-Controller-%20%286%29.png)

**Continue the configuration (step 6 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 2 — Promote DC1 to Domain Controller - Screenshot 7](02-DC1-Promote-To-Domain-Controller/Domain-Controller-%20%287%29.png)

**Continue the configuration (step 7 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 2 — Promote DC1 to Domain Controller - Screenshot 8](02-DC1-Promote-To-Domain-Controller/Domain-Controller-%20%288%29.png)

**Continue the configuration (step 8 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 2 — Promote DC1 to Domain Controller - Screenshot 9](02-DC1-Promote-To-Domain-Controller/Domain-Controller-%20%289%29.png)

**Continue the configuration (step 9 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 2 — Promote DC1 to Domain Controller - Screenshot 10](02-DC1-Promote-To-Domain-Controller/Domain-Controller-%20%2810%29.png)

**Continue the configuration (step 10 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 2 — Promote DC1 to Domain Controller - Screenshot 11](02-DC1-Promote-To-Domain-Controller/Domain-Controller-%20%2811%29.png)

**Continue the configuration (step 11 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 2 — Promote DC1 to Domain Controller - Screenshot 12](02-DC1-Promote-To-Domain-Controller/Domain-Controller-%20%2812%29.png)

**Continue the configuration (step 12 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 2 — Promote DC1 to Domain Controller - Screenshot 13](02-DC1-Promote-To-Domain-Controller/Domain-Controller-%20%2813%29.png)

**Continue the configuration (step 13 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 2 — Promote DC1 to Domain Controller - Screenshot 14](02-DC1-Promote-To-Domain-Controller/Domain-Controller-%20%2814%29.png)

**Continue the configuration (step 14 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 2 — Promote DC1 to Domain Controller - Screenshot 15](02-DC1-Promote-To-Domain-Controller/Domain-Controller-%20%2815%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 3 — Open Active Directory Users & Computers

Open ADUC (Active Directory Users and Computers) from Server Manager → Tools to verify the domain was created successfully. Explore the default containers.

### Screenshot 1

![Step 3 — Open Active Directory Users & Computers - Screenshot 1](03-Active-Directory-Users-And-Computers/Users-And-Computers-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 3 — Open Active Directory Users & Computers - Screenshot 2](03-Active-Directory-Users-And-Computers/Users-And-Computers-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 3 — Open Active Directory Users & Computers - Screenshot 3](03-Active-Directory-Users-And-Computers/Users-And-Computers-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 3 — Open Active Directory Users & Computers - Screenshot 4](03-Active-Directory-Users-And-Computers/Users-And-Computers-%20%284%29.png)

**Continue the configuration (step 4 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 3 — Open Active Directory Users & Computers - Screenshot 5](03-Active-Directory-Users-And-Computers/Users-And-Computers-%20%285%29.png)

**Continue the configuration (step 5 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 3 — Open Active Directory Users & Computers - Screenshot 6](03-Active-Directory-Users-And-Computers/Users-And-Computers-%20%286%29.png)

**Continue the configuration (step 6 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 3 — Open Active Directory Users & Computers - Screenshot 7](03-Active-Directory-Users-And-Computers/Users-And-Computers-%20%287%29.png)

**Continue the configuration (step 7 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 3 — Open Active Directory Users & Computers - Screenshot 8](03-Active-Directory-Users-And-Computers/Users-And-Computers-%20%288%29.png)

**Continue the configuration (step 8 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 3 — Open Active Directory Users & Computers - Screenshot 9](03-Active-Directory-Users-And-Computers/Users-And-Computers-%20%289%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 4 — Create the Vertex OU Structure

Build the complete organizational unit hierarchy under `vertex.local`:

```
VERTEX
├── HQ-London
│   ├── IT
│   ├── Finance
│   ├── HR
│   ├── Security
│   ├── Development
│   ├── Operations
│   ├── Helpdesk
│   └── Executive
├── Branch-Mumbai
├── Branch-Dubai
└── Branch-Singapore
```

### Screenshot 1

![Step 4 — Create the Vertex OU Structure - Screenshot 1](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 4 — Create the Vertex OU Structure - Screenshot 2](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 4 — Create the Vertex OU Structure - Screenshot 3](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 4 — Create the Vertex OU Structure - Screenshot 4](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%284%29.png)

**Continue the configuration (step 4 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 4 — Create the Vertex OU Structure - Screenshot 5](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%285%29.png)

**Continue the configuration (step 5 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 4 — Create the Vertex OU Structure - Screenshot 6](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%286%29.png)

**Continue the configuration (step 6 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 4 — Create the Vertex OU Structure - Screenshot 7](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%287%29.png)

**Continue the configuration (step 7 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 4 — Create the Vertex OU Structure - Screenshot 8](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%288%29.png)

**Continue the configuration (step 8 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 4 — Create the Vertex OU Structure - Screenshot 9](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%289%29.png)

**Continue the configuration (step 9 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 4 — Create the Vertex OU Structure - Screenshot 10](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2810%29.png)

**Continue the configuration (step 10 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 4 — Create the Vertex OU Structure - Screenshot 11](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2811%29.png)

**Continue the configuration (step 11 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 4 — Create the Vertex OU Structure - Screenshot 12](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2812%29.png)

**Continue the configuration (step 12 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 4 — Create the Vertex OU Structure - Screenshot 13](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2813%29.png)

**Continue the configuration (step 13 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 4 — Create the Vertex OU Structure - Screenshot 14](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2814%29.png)

**Continue the configuration (step 14 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 4 — Create the Vertex OU Structure - Screenshot 15](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2815%29.png)

**Continue the configuration (step 15 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 4 — Create the Vertex OU Structure - Screenshot 16](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2816%29.png)

**Continue the configuration (step 16 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 4 — Create the Vertex OU Structure - Screenshot 17](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2817%29.png)

**Continue the configuration (step 17 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 4 — Create the Vertex OU Structure - Screenshot 18](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2818%29.png)

**Continue the configuration (step 18 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 4 — Create the Vertex OU Structure - Screenshot 19](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2819%29.png)

**Continue the configuration (step 19 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 4 — Create the Vertex OU Structure - Screenshot 20](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2820%29.png)

**Continue the configuration (step 20 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 4 — Create the Vertex OU Structure - Screenshot 21](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2821%29.png)

**Continue the configuration (step 21 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 22

![Step 4 — Create the Vertex OU Structure - Screenshot 22](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2822%29.png)

**Continue the configuration (step 22 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 23

![Step 4 — Create the Vertex OU Structure - Screenshot 23](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2823%29.png)

**Continue the configuration (step 23 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 24

![Step 4 — Create the Vertex OU Structure - Screenshot 24](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2824%29.png)

**Continue the configuration (step 24 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 25

![Step 4 — Create the Vertex OU Structure - Screenshot 25](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2825%29.png)

**Continue the configuration (step 25 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 26

![Step 4 — Create the Vertex OU Structure - Screenshot 26](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2826%29.png)

**Continue the configuration (step 26 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 27

![Step 4 — Create the Vertex OU Structure - Screenshot 27](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2827%29.png)

**Continue the configuration (step 27 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 28

![Step 4 — Create the Vertex OU Structure - Screenshot 28](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2828%29.png)

**Continue the configuration (step 28 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 29

![Step 4 — Create the Vertex OU Structure - Screenshot 29](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2829%29.png)

**Continue the configuration (step 29 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 30

![Step 4 — Create the Vertex OU Structure - Screenshot 30](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2830%29.png)

**Continue the configuration (step 30 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 31

![Step 4 — Create the Vertex OU Structure - Screenshot 31](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2831%29.png)

**Continue the configuration (step 31 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 32

![Step 4 — Create the Vertex OU Structure - Screenshot 32](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2832%29.png)

**Continue the configuration (step 32 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 33

![Step 4 — Create the Vertex OU Structure - Screenshot 33](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2833%29.png)

**Continue the configuration (step 33 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 34

![Step 4 — Create the Vertex OU Structure - Screenshot 34](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2834%29.png)

**Continue the configuration (step 34 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 35

![Step 4 — Create the Vertex OU Structure - Screenshot 35](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2835%29.png)

**Continue the configuration (step 35 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 36

![Step 4 — Create the Vertex OU Structure - Screenshot 36](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2836%29.png)

**Continue the configuration (step 36 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 37

![Step 4 — Create the Vertex OU Structure - Screenshot 37](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2837%29.png)

**Continue the configuration (step 37 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 38

![Step 4 — Create the Vertex OU Structure - Screenshot 38](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2838%29.png)

**Continue the configuration (step 38 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 39

![Step 4 — Create the Vertex OU Structure - Screenshot 39](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2839%29.png)

**Continue the configuration (step 39 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 40

![Step 4 — Create the Vertex OU Structure - Screenshot 40](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2840%29.png)

**Continue the configuration (step 40 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 41

![Step 4 — Create the Vertex OU Structure - Screenshot 41](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2841%29.png)

**Continue the configuration (step 41 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 42

![Step 4 — Create the Vertex OU Structure - Screenshot 42](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2842%29.png)

**Continue the configuration (step 42 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 43

![Step 4 — Create the Vertex OU Structure - Screenshot 43](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2843%29.png)

**Continue the configuration (step 43 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 44

![Step 4 — Create the Vertex OU Structure - Screenshot 44](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2844%29.png)

**Continue the configuration (step 44 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 45

![Step 4 — Create the Vertex OU Structure - Screenshot 45](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2845%29.png)

**Continue the configuration (step 45 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 46

![Step 4 — Create the Vertex OU Structure - Screenshot 46](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2846%29.png)

**Continue the configuration (step 46 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 47

![Step 4 — Create the Vertex OU Structure - Screenshot 47](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2847%29.png)

**Continue the configuration (step 47 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 48

![Step 4 — Create the Vertex OU Structure - Screenshot 48](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2848%29.png)

**Continue the configuration (step 48 of 49) — follow the red arrows/boxes for guidance.**

### Screenshot 49

![Step 4 — Create the Vertex OU Structure - Screenshot 49](04-Vertex-OU-Structure-Creation/Structure-Creation-%20%2849%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 5 — Create London HQ Users, Groups & Computers OUs

Under each HQ-London department, create sub-OUs for Users, Groups, and Computers to organize objects properly.

### Screenshot 1

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 1](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 2](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 3](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 4](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%284%29.png)

**Continue the configuration (step 4 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 5](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%285%29.png)

**Continue the configuration (step 5 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 6](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%286%29.png)

**Continue the configuration (step 6 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 7](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%287%29.png)

**Continue the configuration (step 7 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 8](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%288%29.png)

**Continue the configuration (step 8 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 9](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%289%29.png)

**Continue the configuration (step 9 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 10](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2810%29.png)

**Continue the configuration (step 10 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 11](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2811%29.png)

**Continue the configuration (step 11 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 12](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2812%29.png)

**Continue the configuration (step 12 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 13](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2813%29.png)

**Continue the configuration (step 13 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 14](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2814%29.png)

**Continue the configuration (step 14 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 15](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2815%29.png)

**Continue the configuration (step 15 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 16](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2816%29.png)

**Continue the configuration (step 16 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 17](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2817%29.png)

**Continue the configuration (step 17 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 18](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2818%29.png)

**Continue the configuration (step 18 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 19](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2819%29.png)

**Continue the configuration (step 19 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 20](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2820%29.png)

**Continue the configuration (step 20 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 21](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2821%29.png)

**Continue the configuration (step 21 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 22

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 22](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2822%29.png)

**Continue the configuration (step 22 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 23

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 23](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2823%29.png)

**Continue the configuration (step 23 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 24

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 24](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2824%29.png)

**Continue the configuration (step 24 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 25

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 25](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2825%29.png)

**Continue the configuration (step 25 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 26

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 26](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2826%29.png)

**Continue the configuration (step 26 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 27

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 27](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2827%29.png)

**Continue the configuration (step 27 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 28

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 28](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2828%29.png)

**Continue the configuration (step 28 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 29

![Step 5 — Create London HQ Users, Groups & Computers OUs - Screenshot 29](05-London-HQ-Users-Groups-And-Computers/London-HQ-%20%2829%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 6 — Create Security Groups & Server OUs

Create security groups for administrative purposes and server OUs for organizing domain controller and member server objects.

### Screenshot 1

![Step 6 — Create Security Groups & Server OUs - Screenshot 1](06-Security-Groups-And-Servers/Groups-And-Servers-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 6 — Create Security Groups & Server OUs - Screenshot 2](06-Security-Groups-And-Servers/Groups-And-Servers-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 6 — Create Security Groups & Server OUs - Screenshot 3](06-Security-Groups-And-Servers/Groups-And-Servers-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 6 — Create Security Groups & Server OUs - Screenshot 4](06-Security-Groups-And-Servers/Groups-And-Servers-%20%284%29.png)

**Continue the configuration (step 4 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 6 — Create Security Groups & Server OUs - Screenshot 5](06-Security-Groups-And-Servers/Groups-And-Servers-%20%285%29.png)

**Continue the configuration (step 5 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 6 — Create Security Groups & Server OUs - Screenshot 6](06-Security-Groups-And-Servers/Groups-And-Servers-%20%286%29.png)

**Continue the configuration (step 6 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 6 — Create Security Groups & Server OUs - Screenshot 7](06-Security-Groups-And-Servers/Groups-And-Servers-%20%287%29.png)

**Continue the configuration (step 7 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 6 — Create Security Groups & Server OUs - Screenshot 8](06-Security-Groups-And-Servers/Groups-And-Servers-%20%288%29.png)

**Continue the configuration (step 8 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 6 — Create Security Groups & Server OUs - Screenshot 9](06-Security-Groups-And-Servers/Groups-And-Servers-%20%289%29.png)

**Continue the configuration (step 9 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 6 — Create Security Groups & Server OUs - Screenshot 10](06-Security-Groups-And-Servers/Groups-And-Servers-%20%2810%29.png)

**Continue the configuration (step 10 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 6 — Create Security Groups & Server OUs - Screenshot 11](06-Security-Groups-And-Servers/Groups-And-Servers-%20%2811%29.png)

**Continue the configuration (step 11 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 6 — Create Security Groups & Server OUs - Screenshot 12](06-Security-Groups-And-Servers/Groups-And-Servers-%20%2812%29.png)

**Continue the configuration (step 12 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 6 — Create Security Groups & Server OUs - Screenshot 13](06-Security-Groups-And-Servers/Groups-And-Servers-%20%2813%29.png)

**Continue the configuration (step 13 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 6 — Create Security Groups & Server OUs - Screenshot 14](06-Security-Groups-And-Servers/Groups-And-Servers-%20%2814%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 7 — Configure AD Sites & Services

Open AD Sites and Services, rename the default site, create additional sites for branch offices, and configure site links for replication topology.

### Screenshot 1

![Step 7 — Configure AD Sites & Services - Screenshot 1](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 7 — Configure AD Sites & Services - Screenshot 2](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 7 — Configure AD Sites & Services - Screenshot 3](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 7 — Configure AD Sites & Services - Screenshot 4](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%284%29.png)

**Continue the configuration (step 4 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 7 — Configure AD Sites & Services - Screenshot 5](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%285%29.png)

**Continue the configuration (step 5 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 7 — Configure AD Sites & Services - Screenshot 6](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%286%29.png)

**Continue the configuration (step 6 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 7 — Configure AD Sites & Services - Screenshot 7](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%287%29.png)

**Continue the configuration (step 7 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 7 — Configure AD Sites & Services - Screenshot 8](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%288%29.png)

**Continue the configuration (step 8 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 7 — Configure AD Sites & Services - Screenshot 9](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%289%29.png)

**Continue the configuration (step 9 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 7 — Configure AD Sites & Services - Screenshot 10](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%2810%29.png)

**Continue the configuration (step 10 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 7 — Configure AD Sites & Services - Screenshot 11](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%2811%29.png)

**Continue the configuration (step 11 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 7 — Configure AD Sites & Services - Screenshot 12](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%2812%29.png)

**Continue the configuration (step 12 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 7 — Configure AD Sites & Services - Screenshot 13](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%2813%29.png)

**Continue the configuration (step 13 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 7 — Configure AD Sites & Services - Screenshot 14](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%2814%29.png)

**Continue the configuration (step 14 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 7 — Configure AD Sites & Services - Screenshot 15](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%2815%29.png)

**Continue the configuration (step 15 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 7 — Configure AD Sites & Services - Screenshot 16](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%2816%29.png)

**Continue the configuration (step 16 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 7 — Configure AD Sites & Services - Screenshot 17](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%2817%29.png)

**Continue the configuration (step 17 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 7 — Configure AD Sites & Services - Screenshot 18](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%2818%29.png)

**Continue the configuration (step 18 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 7 — Configure AD Sites & Services - Screenshot 19](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%2819%29.png)

**Continue the configuration (step 19 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 7 — Configure AD Sites & Services - Screenshot 20](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%2820%29.png)

**Continue the configuration (step 20 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 7 — Configure AD Sites & Services - Screenshot 21](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%2821%29.png)

**Continue the configuration (step 21 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 22

![Step 7 — Configure AD Sites & Services - Screenshot 22](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%2822%29.png)

**Continue the configuration (step 22 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 23

![Step 7 — Configure AD Sites & Services - Screenshot 23](07-Active-Directory-Sites-And-Services/Sites-And-Services-%20%2823%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 8 — Join DC2 to the Domain

Join DC2 to the `vertex.local` domain as a member server before promoting it to a domain controller.

### Screenshot 1

![Step 8 — Join DC2 to the Domain - Screenshot 1](08-DC2-Domain-Join/Domain-Join-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 8 — Join DC2 to the Domain - Screenshot 2](08-DC2-Domain-Join/Domain-Join-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 8 — Join DC2 to the Domain - Screenshot 3](08-DC2-Domain-Join/Domain-Join-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 8 — Join DC2 to the Domain - Screenshot 4](08-DC2-Domain-Join/Domain-Join-%20%284%29.png)

**Continue the configuration (step 4 of 22) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 8 — Join DC2 to the Domain - Screenshot 5](08-DC2-Domain-Join/Domain-Join-%20%285%29.png)

**Continue the configuration (step 5 of 22) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 8 — Join DC2 to the Domain - Screenshot 6](08-DC2-Domain-Join/Domain-Join-%20%286%29.png)

**Continue the configuration (step 6 of 22) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 8 — Join DC2 to the Domain - Screenshot 7](08-DC2-Domain-Join/Domain-Join-%20%287%29.png)

**Continue the configuration (step 7 of 22) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 8 — Join DC2 to the Domain - Screenshot 8](08-DC2-Domain-Join/Domain-Join-%20%288%29.png)

**Continue the configuration (step 8 of 22) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 8 — Join DC2 to the Domain - Screenshot 9](08-DC2-Domain-Join/Domain-Join-%20%289%29.png)

**Continue the configuration (step 9 of 22) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 8 — Join DC2 to the Domain - Screenshot 10](08-DC2-Domain-Join/Domain-Join-%20%2810%29.png)

**Continue the configuration (step 10 of 22) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 8 — Join DC2 to the Domain - Screenshot 11](08-DC2-Domain-Join/Domain-Join-%20%2811%29.png)

**Continue the configuration (step 11 of 22) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 8 — Join DC2 to the Domain - Screenshot 12](08-DC2-Domain-Join/Domain-Join-%20%2812%29.png)

**Continue the configuration (step 12 of 22) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 8 — Join DC2 to the Domain - Screenshot 13](08-DC2-Domain-Join/Domain-Join-%20%2813%29.png)

**Continue the configuration (step 13 of 22) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 8 — Join DC2 to the Domain - Screenshot 14](08-DC2-Domain-Join/Domain-Join-%20%2814%29.png)

**Continue the configuration (step 14 of 22) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 8 — Join DC2 to the Domain - Screenshot 15](08-DC2-Domain-Join/Domain-Join-%20%2815%29.png)

**Continue the configuration (step 15 of 22) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 8 — Join DC2 to the Domain - Screenshot 16](08-DC2-Domain-Join/Domain-Join-%20%2816%29.png)

**Continue the configuration (step 16 of 22) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 8 — Join DC2 to the Domain - Screenshot 17](08-DC2-Domain-Join/Domain-Join-%20%2817%29.png)

**Continue the configuration (step 17 of 22) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 8 — Join DC2 to the Domain - Screenshot 18](08-DC2-Domain-Join/Domain-Join-%20%2818%29.png)

**Continue the configuration (step 18 of 22) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 8 — Join DC2 to the Domain - Screenshot 19](08-DC2-Domain-Join/Domain-Join-%20%2819%29.png)

**Continue the configuration (step 19 of 22) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 8 — Join DC2 to the Domain - Screenshot 20](08-DC2-Domain-Join/Domain-Join-%20%2820%29.png)

**Continue the configuration (step 20 of 22) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 8 — Join DC2 to the Domain - Screenshot 21](08-DC2-Domain-Join/Domain-Join-%20%2821%29.png)

**Continue the configuration (step 21 of 22) — follow the red arrows/boxes for guidance.**

### Screenshot 22

![Step 8 — Join DC2 to the Domain - Screenshot 22](08-DC2-Domain-Join/Domain-Join-%20%2822%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 9 — Verify CLIENT1 Domain Connectivity

Test that CLIENT1 can resolve the domain name and connect to DC1. Use `nslookup`, `ping`, and attempt domain join.

### Screenshot 1

![Step 9 — Verify CLIENT1 Domain Connectivity - Screenshot 1](09-Client1-Domain-Connectivity-Verification/Connectivity-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 9 — Verify CLIENT1 Domain Connectivity - Screenshot 2](09-Client1-Domain-Connectivity-Verification/Connectivity-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 9 — Verify CLIENT1 Domain Connectivity - Screenshot 3](09-Client1-Domain-Connectivity-Verification/Connectivity-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 9 — Verify CLIENT1 Domain Connectivity - Screenshot 4](09-Client1-Domain-Connectivity-Verification/Connectivity-%20%284%29.png)

**Continue the configuration (step 4 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 9 — Verify CLIENT1 Domain Connectivity - Screenshot 5](09-Client1-Domain-Connectivity-Verification/Connectivity-%20%285%29.png)

**Continue the configuration (step 5 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 9 — Verify CLIENT1 Domain Connectivity - Screenshot 6](09-Client1-Domain-Connectivity-Verification/Connectivity-%20%286%29.png)

**Continue the configuration (step 6 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 9 — Verify CLIENT1 Domain Connectivity - Screenshot 7](09-Client1-Domain-Connectivity-Verification/Connectivity-%20%287%29.png)

**Continue the configuration (step 7 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 9 — Verify CLIENT1 Domain Connectivity - Screenshot 8](09-Client1-Domain-Connectivity-Verification/Connectivity-%20%288%29.png)

**Continue the configuration (step 8 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 9 — Verify CLIENT1 Domain Connectivity - Screenshot 9](09-Client1-Domain-Connectivity-Verification/Connectivity-%20%289%29.png)

**Continue the configuration (step 9 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 9 — Verify CLIENT1 Domain Connectivity - Screenshot 10](09-Client1-Domain-Connectivity-Verification/Connectivity-%20%2810%29.png)

**Continue the configuration (step 10 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 9 — Verify CLIENT1 Domain Connectivity - Screenshot 11](09-Client1-Domain-Connectivity-Verification/Connectivity-%20%2811%29.png)

**Continue the configuration (step 11 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 9 — Verify CLIENT1 Domain Connectivity - Screenshot 12](09-Client1-Domain-Connectivity-Verification/Connectivity-%20%2812%29.png)

**Continue the configuration (step 12 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 9 — Verify CLIENT1 Domain Connectivity - Screenshot 13](09-Client1-Domain-Connectivity-Verification/Connectivity-%20%2813%29.png)

**Continue the configuration (step 13 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 9 — Verify CLIENT1 Domain Connectivity - Screenshot 14](09-Client1-Domain-Connectivity-Verification/Connectivity-%20%2814%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 10 — Install AD DS Role on DC2

Install the Active Directory Domain Services role on DC2 via Server Manager, preparing it for promotion as an additional domain controller.

### Screenshot 1

![Step 10 — Install AD DS Role on DC2 - Screenshot 1](10-DC2-ADDS-Role-Installation/DC2-ADDS-Installation%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 10 — Install AD DS Role on DC2 - Screenshot 2](10-DC2-ADDS-Role-Installation/DC2-ADDS-Installation%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 10 — Install AD DS Role on DC2 - Screenshot 3](10-DC2-ADDS-Role-Installation/DC2-ADDS-Installation%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 10 — Install AD DS Role on DC2 - Screenshot 4](10-DC2-ADDS-Role-Installation/DC2-ADDS-Installation%20%284%29.png)

**Continue the configuration (step 4 of 13) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 10 — Install AD DS Role on DC2 - Screenshot 5](10-DC2-ADDS-Role-Installation/DC2-ADDS-Installation%20%285%29.png)

**Continue the configuration (step 5 of 13) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 10 — Install AD DS Role on DC2 - Screenshot 6](10-DC2-ADDS-Role-Installation/DC2-ADDS-Installation%20%286%29.png)

**Continue the configuration (step 6 of 13) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 10 — Install AD DS Role on DC2 - Screenshot 7](10-DC2-ADDS-Role-Installation/DC2-ADDS-Installation%20%287%29.png)

**Continue the configuration (step 7 of 13) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 10 — Install AD DS Role on DC2 - Screenshot 8](10-DC2-ADDS-Role-Installation/DC2-ADDS-Installation%20%288%29.png)

**Continue the configuration (step 8 of 13) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 10 — Install AD DS Role on DC2 - Screenshot 9](10-DC2-ADDS-Role-Installation/DC2-ADDS-Installation%20%289%29.png)

**Continue the configuration (step 9 of 13) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 10 — Install AD DS Role on DC2 - Screenshot 10](10-DC2-ADDS-Role-Installation/DC2-ADDS-Installation%20%2810%29.png)

**Continue the configuration (step 10 of 13) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 10 — Install AD DS Role on DC2 - Screenshot 11](10-DC2-ADDS-Role-Installation/DC2-ADDS-Installation%20%2811%29.png)

**Continue the configuration (step 11 of 13) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 10 — Install AD DS Role on DC2 - Screenshot 12](10-DC2-ADDS-Role-Installation/DC2-ADDS-Installation%20%2812%29.png)

**Continue the configuration (step 12 of 13) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 10 — Install AD DS Role on DC2 - Screenshot 13](10-DC2-ADDS-Role-Installation/DC2-ADDS-Installation%20%2813%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 11 — Promote DC2 as Additional DC

Promote DC2 as an **additional domain controller** in the existing `vertex.local` domain. Select 'Add a domain controller to an existing domain' and provide domain admin credentials.

### Screenshot 1

![Step 11 — Promote DC2 as Additional DC - Screenshot 1](11-DC2-Promote-To-Additional-Domain-Controller/DC2-Promote-To-Domain-Controller%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 11 — Promote DC2 as Additional DC - Screenshot 2](11-DC2-Promote-To-Additional-Domain-Controller/DC2-Promote-To-Domain-Controller%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 11 — Promote DC2 as Additional DC - Screenshot 3](11-DC2-Promote-To-Additional-Domain-Controller/DC2-Promote-To-Domain-Controller%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 11 — Promote DC2 as Additional DC - Screenshot 4](11-DC2-Promote-To-Additional-Domain-Controller/DC2-Promote-To-Domain-Controller%20%284%29.png)

**Continue the configuration (step 4 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 11 — Promote DC2 as Additional DC - Screenshot 5](11-DC2-Promote-To-Additional-Domain-Controller/DC2-Promote-To-Domain-Controller%20%285%29.png)

**Continue the configuration (step 5 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 11 — Promote DC2 as Additional DC - Screenshot 6](11-DC2-Promote-To-Additional-Domain-Controller/DC2-Promote-To-Domain-Controller%20%286%29.png)

**Continue the configuration (step 6 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 11 — Promote DC2 as Additional DC - Screenshot 7](11-DC2-Promote-To-Additional-Domain-Controller/DC2-Promote-To-Domain-Controller%20%287%29.png)

**Continue the configuration (step 7 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 11 — Promote DC2 as Additional DC - Screenshot 8](11-DC2-Promote-To-Additional-Domain-Controller/DC2-Promote-To-Domain-Controller%20%288%29.png)

**Continue the configuration (step 8 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 11 — Promote DC2 as Additional DC - Screenshot 9](11-DC2-Promote-To-Additional-Domain-Controller/DC2-Promote-To-Domain-Controller%20%289%29.png)

**Continue the configuration (step 9 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 11 — Promote DC2 as Additional DC - Screenshot 10](11-DC2-Promote-To-Additional-Domain-Controller/DC2-Promote-To-Domain-Controller%20%2810%29.png)

**Continue the configuration (step 10 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 11 — Promote DC2 as Additional DC - Screenshot 11](11-DC2-Promote-To-Additional-Domain-Controller/DC2-Promote-To-Domain-Controller%20%2811%29.png)

**Continue the configuration (step 11 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 11 — Promote DC2 as Additional DC - Screenshot 12](11-DC2-Promote-To-Additional-Domain-Controller/DC2-Promote-To-Domain-Controller%20%2812%29.png)

**Continue the configuration (step 12 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 11 — Promote DC2 as Additional DC - Screenshot 13](11-DC2-Promote-To-Additional-Domain-Controller/DC2-Promote-To-Domain-Controller%20%2813%29.png)

**Continue the configuration (step 13 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 11 — Promote DC2 as Additional DC - Screenshot 14](11-DC2-Promote-To-Additional-Domain-Controller/DC2-Promote-To-Domain-Controller%20%2814%29.png)

**Continue the configuration (step 14 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 11 — Promote DC2 as Additional DC - Screenshot 15](11-DC2-Promote-To-Additional-Domain-Controller/DC2-Promote-To-Domain-Controller%20%2815%29.png)

**Continue the configuration (step 15 of 16) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 11 — Promote DC2 as Additional DC - Screenshot 16](11-DC2-Promote-To-Additional-Domain-Controller/DC2-Promote-To-Domain-Controller%20%2816%29.png)

**Final result — verify the configuration is complete and working.**

---

## 🔗 Navigation

[⬆️ Back to Top](#)

[📚 Back to Master README](../README.md)
