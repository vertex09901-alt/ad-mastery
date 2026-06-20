# 🔄 Phase 07 — Domain Controllers & FSMO

> **Identify and verify FSMO role holders, verify AD replication between DC1 and DC2, explore SYSVOL and NTDS folders, and create AD Sites and Site Links for topology management.**

**Prerequisites:** Phase 02 completed — DC1 and DC2 both promoted as domain controllers.

---
## 📑 Table of Contents

- [Step 1 — Identify FSMO Role Holders](#step-1-identify-fsmo-role-holders)
- [Step 2 — Verify AD Replication](#step-2-verify-ad-replication)
- [Step 3 — Explore SYSVOL & NTDS](#step-3-explore-sysvol-ntds)
- [Step 4 — Create Sites & Site Links](#step-4-create-sites-site-links)

---

## Step 1 — Identify FSMO Role Holders

View all five FSMO (Flexible Single Master Operations) roles and their current holders:

```powershell
netdom query fsmo
```

**FSMO Roles:**
- Schema Master (Forest-wide)
- Domain Naming Master (Forest-wide)
- PDC Emulator (Domain-wide)
- RID Master (Domain-wide)
- Infrastructure Master (Domain-wide)

### Screenshot 1

![Step 1 — Identify FSMO Role Holders - Screenshot 1](01-FSMO%20ROLES/FSMO%20ROLES-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 1 — Identify FSMO Role Holders - Screenshot 2](01-FSMO%20ROLES/FSMO%20ROLES-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 1 — Identify FSMO Role Holders - Screenshot 3](01-FSMO%20ROLES/FSMO%20ROLES-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 1 — Identify FSMO Role Holders - Screenshot 4](01-FSMO%20ROLES/FSMO%20ROLES-%20%284%29.png)

**Continue the configuration (step 4 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 1 — Identify FSMO Role Holders - Screenshot 5](01-FSMO%20ROLES/FSMO%20ROLES-%20%285%29.png)

**Continue the configuration (step 5 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 1 — Identify FSMO Role Holders - Screenshot 6](01-FSMO%20ROLES/FSMO%20ROLES-%20%286%29.png)

**Continue the configuration (step 6 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 1 — Identify FSMO Role Holders - Screenshot 7](01-FSMO%20ROLES/FSMO%20ROLES-%20%287%29.png)

**Continue the configuration (step 7 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 1 — Identify FSMO Role Holders - Screenshot 8](01-FSMO%20ROLES/FSMO%20ROLES-%20%288%29.png)

**Continue the configuration (step 8 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 1 — Identify FSMO Role Holders - Screenshot 9](01-FSMO%20ROLES/FSMO%20ROLES-%20%289%29.png)

**Continue the configuration (step 9 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 1 — Identify FSMO Role Holders - Screenshot 10](01-FSMO%20ROLES/FSMO%20ROLES-%20%2810%29.png)

**Continue the configuration (step 10 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 1 — Identify FSMO Role Holders - Screenshot 11](01-FSMO%20ROLES/FSMO%20ROLES-%20%2811%29.png)

**Continue the configuration (step 11 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 1 — Identify FSMO Role Holders - Screenshot 12](01-FSMO%20ROLES/FSMO%20ROLES-%20%2812%29.png)

**Continue the configuration (step 12 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 1 — Identify FSMO Role Holders - Screenshot 13](01-FSMO%20ROLES/FSMO%20ROLES-%20%2813%29.png)

**Continue the configuration (step 13 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 1 — Identify FSMO Role Holders - Screenshot 14](01-FSMO%20ROLES/FSMO%20ROLES-%20%2814%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 2 — Verify AD Replication

Verify that replication is working between DC1 and DC2:

```cmd
repadmin /replsummary
repadmin /showrepl
repadmin /syncall /AdeP
```

### Screenshot 1

![Step 2 — Verify AD Replication - Screenshot 1](02-VERIFY%20REPLICATION/REPLICATION-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 2 — Verify AD Replication - Screenshot 2](02-VERIFY%20REPLICATION/REPLICATION-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 2 — Verify AD Replication - Screenshot 3](02-VERIFY%20REPLICATION/REPLICATION-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 2 — Verify AD Replication - Screenshot 4](02-VERIFY%20REPLICATION/REPLICATION-%20%284%29.png)

**Continue the configuration (step 4 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 2 — Verify AD Replication - Screenshot 5](02-VERIFY%20REPLICATION/REPLICATION-%20%285%29.png)

**Continue the configuration (step 5 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 2 — Verify AD Replication - Screenshot 6](02-VERIFY%20REPLICATION/REPLICATION-%20%286%29.png)

**Continue the configuration (step 6 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 2 — Verify AD Replication - Screenshot 7](02-VERIFY%20REPLICATION/REPLICATION-%20%287%29.png)

**Continue the configuration (step 7 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 2 — Verify AD Replication - Screenshot 8](02-VERIFY%20REPLICATION/REPLICATION-%20%288%29.png)

**Continue the configuration (step 8 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 2 — Verify AD Replication - Screenshot 9](02-VERIFY%20REPLICATION/REPLICATION-%20%289%29.png)

**Continue the configuration (step 9 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 2 — Verify AD Replication - Screenshot 10](02-VERIFY%20REPLICATION/REPLICATION-%20%2810%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 3 — Explore SYSVOL & NTDS

Explore the SYSVOL share and NTDS database locations:

```
SYSVOL: C:\Windows\SYSVOL\sysvol\vertex.local
NTDS:   C:\Windows\NTDS\ntds.dit
```

SYSVOL contains GPO templates, scripts, and logon scripts. NTDS.DIT is the AD database.

### Screenshot 1

![Step 3 — Explore SYSVOL & NTDS - Screenshot 1](03-EXPLORE%20SYSVOL%20AND%20NTDS/EXPLORE%20SYSVOL-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 3 — Explore SYSVOL & NTDS - Screenshot 2](03-EXPLORE%20SYSVOL%20AND%20NTDS/EXPLORE%20SYSVOL-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 3 — Explore SYSVOL & NTDS - Screenshot 3](03-EXPLORE%20SYSVOL%20AND%20NTDS/EXPLORE%20SYSVOL-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 3 — Explore SYSVOL & NTDS - Screenshot 4](03-EXPLORE%20SYSVOL%20AND%20NTDS/EXPLORE%20SYSVOL-%20%284%29.png)

**Continue the configuration (step 4 of 7) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 3 — Explore SYSVOL & NTDS - Screenshot 5](03-EXPLORE%20SYSVOL%20AND%20NTDS/EXPLORE%20SYSVOL-%20%285%29.png)

**Continue the configuration (step 5 of 7) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 3 — Explore SYSVOL & NTDS - Screenshot 6](03-EXPLORE%20SYSVOL%20AND%20NTDS/EXPLORE%20SYSVOL-%20%286%29.png)

**Continue the configuration (step 6 of 7) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 3 — Explore SYSVOL & NTDS - Screenshot 7](03-EXPLORE%20SYSVOL%20AND%20NTDS/EXPLORE%20SYSVOL-%20%287%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 4 — Create Sites & Site Links

Open AD Sites and Services and create sites for each office location:

- **London-HQ** (192.168.10.0/24)
- **Mumbai-Branch**
- **Dubai-Branch**
- **Singapore-Branch**

Create site links to control replication schedules and costs between sites.

### Screenshot 1

![Step 4 — Create Sites & Site Links - Screenshot 1](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 4 — Create Sites & Site Links - Screenshot 2](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 4 — Create Sites & Site Links - Screenshot 3](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 4 — Create Sites & Site Links - Screenshot 4](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%284%29.png)

**Continue the configuration (step 4 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 4 — Create Sites & Site Links - Screenshot 5](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%285%29.png)

**Continue the configuration (step 5 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 4 — Create Sites & Site Links - Screenshot 6](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%286%29.png)

**Continue the configuration (step 6 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 4 — Create Sites & Site Links - Screenshot 7](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%287%29.png)

**Continue the configuration (step 7 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 4 — Create Sites & Site Links - Screenshot 8](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%288%29.png)

**Continue the configuration (step 8 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 4 — Create Sites & Site Links - Screenshot 9](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%289%29.png)

**Continue the configuration (step 9 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 4 — Create Sites & Site Links - Screenshot 10](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2810%29.png)

**Continue the configuration (step 10 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 4 — Create Sites & Site Links - Screenshot 11](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2811%29.png)

**Continue the configuration (step 11 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 4 — Create Sites & Site Links - Screenshot 12](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2812%29.png)

**Continue the configuration (step 12 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 4 — Create Sites & Site Links - Screenshot 13](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2813%29.png)

**Continue the configuration (step 13 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 4 — Create Sites & Site Links - Screenshot 14](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2814%29.png)

**Continue the configuration (step 14 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 4 — Create Sites & Site Links - Screenshot 15](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2815%29.png)

**Continue the configuration (step 15 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 4 — Create Sites & Site Links - Screenshot 16](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2816%29.png)

**Continue the configuration (step 16 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 4 — Create Sites & Site Links - Screenshot 17](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2817%29.png)

**Continue the configuration (step 17 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 4 — Create Sites & Site Links - Screenshot 18](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2818%29.png)

**Continue the configuration (step 18 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 4 — Create Sites & Site Links - Screenshot 19](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2819%29.png)

**Continue the configuration (step 19 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 4 — Create Sites & Site Links - Screenshot 20](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2820%29.png)

**Continue the configuration (step 20 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 4 — Create Sites & Site Links - Screenshot 21](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2821%29.png)

**Continue the configuration (step 21 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 22

![Step 4 — Create Sites & Site Links - Screenshot 22](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2822%29.png)

**Continue the configuration (step 22 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 23

![Step 4 — Create Sites & Site Links - Screenshot 23](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2823%29.png)

**Continue the configuration (step 23 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 24

![Step 4 — Create Sites & Site Links - Screenshot 24](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2824%29.png)

**Continue the configuration (step 24 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 25

![Step 4 — Create Sites & Site Links - Screenshot 25](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2825%29.png)

**Continue the configuration (step 25 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 26

![Step 4 — Create Sites & Site Links - Screenshot 26](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2826%29.png)

**Continue the configuration (step 26 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 27

![Step 4 — Create Sites & Site Links - Screenshot 27](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2827%29.png)

**Continue the configuration (step 27 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 28

![Step 4 — Create Sites & Site Links - Screenshot 28](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2828%29.png)

**Continue the configuration (step 28 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 29

![Step 4 — Create Sites & Site Links - Screenshot 29](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2829%29.png)

**Continue the configuration (step 29 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 30

![Step 4 — Create Sites & Site Links - Screenshot 30](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2830%29.png)

**Continue the configuration (step 30 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 31

![Step 4 — Create Sites & Site Links - Screenshot 31](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2831%29.png)

**Continue the configuration (step 31 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 32

![Step 4 — Create Sites & Site Links - Screenshot 32](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2832%29.png)

**Continue the configuration (step 32 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 33

![Step 4 — Create Sites & Site Links - Screenshot 33](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2833%29.png)

**Continue the configuration (step 33 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 34

![Step 4 — Create Sites & Site Links - Screenshot 34](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2834%29.png)

**Continue the configuration (step 34 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 35

![Step 4 — Create Sites & Site Links - Screenshot 35](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2835%29.png)

**Continue the configuration (step 35 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 36

![Step 4 — Create Sites & Site Links - Screenshot 36](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2836%29.png)

**Continue the configuration (step 36 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 37

![Step 4 — Create Sites & Site Links - Screenshot 37](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2837%29.png)

**Continue the configuration (step 37 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 38

![Step 4 — Create Sites & Site Links - Screenshot 38](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2838%29.png)

**Continue the configuration (step 38 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 39

![Step 4 — Create Sites & Site Links - Screenshot 39](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2839%29.png)

**Continue the configuration (step 39 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 40

![Step 4 — Create Sites & Site Links - Screenshot 40](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2840%29.png)

**Continue the configuration (step 40 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 41

![Step 4 — Create Sites & Site Links - Screenshot 41](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2841%29.png)

**Continue the configuration (step 41 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 42

![Step 4 — Create Sites & Site Links - Screenshot 42](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2842%29.png)

**Continue the configuration (step 42 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 43

![Step 4 — Create Sites & Site Links - Screenshot 43](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2843%29.png)

**Continue the configuration (step 43 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 44

![Step 4 — Create Sites & Site Links - Screenshot 44](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2844%29.png)

**Continue the configuration (step 44 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 45

![Step 4 — Create Sites & Site Links - Screenshot 45](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2845%29.png)

**Continue the configuration (step 45 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 46

![Step 4 — Create Sites & Site Links - Screenshot 46](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2846%29.png)

**Continue the configuration (step 46 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 47

![Step 4 — Create Sites & Site Links - Screenshot 47](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2847%29.png)

**Continue the configuration (step 47 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 48

![Step 4 — Create Sites & Site Links - Screenshot 48](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2848%29.png)

**Continue the configuration (step 48 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 49

![Step 4 — Create Sites & Site Links - Screenshot 49](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2849%29.png)

**Continue the configuration (step 49 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 50

![Step 4 — Create Sites & Site Links - Screenshot 50](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2850%29.png)

**Continue the configuration (step 50 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 51

![Step 4 — Create Sites & Site Links - Screenshot 51](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2851%29.png)

**Continue the configuration (step 51 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 52

![Step 4 — Create Sites & Site Links - Screenshot 52](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2852%29.png)

**Continue the configuration (step 52 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 53

![Step 4 — Create Sites & Site Links - Screenshot 53](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2853%29.png)

**Continue the configuration (step 53 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 54

![Step 4 — Create Sites & Site Links - Screenshot 54](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2854%29.png)

**Continue the configuration (step 54 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 55

![Step 4 — Create Sites & Site Links - Screenshot 55](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2855%29.png)

**Continue the configuration (step 55 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 56

![Step 4 — Create Sites & Site Links - Screenshot 56](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2856%29.png)

**Continue the configuration (step 56 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 57

![Step 4 — Create Sites & Site Links - Screenshot 57](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2857%29.png)

**Continue the configuration (step 57 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 58

![Step 4 — Create Sites & Site Links - Screenshot 58](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2858%29.png)

**Continue the configuration (step 58 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 59

![Step 4 — Create Sites & Site Links - Screenshot 59](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2859%29.png)

**Continue the configuration (step 59 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 60

![Step 4 — Create Sites & Site Links - Screenshot 60](04-CREATE%20SITES%20AND%20SITE%20LINKS/SITE%20LINKS-%20%2860%29.png)

**Final result — verify the configuration is complete and working.**

---

## 🔗 Navigation

[⬆️ Back to Top](#)

[📚 Back to Master README](../README.md)
