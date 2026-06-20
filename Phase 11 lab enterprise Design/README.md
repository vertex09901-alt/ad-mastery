# 🏢 Phase 11 — Enterprise Design & Disaster Recovery

> **Review DC placement and site topology, configure DNS scavenging for stale record cleanup, set up Windows Server Backup for disaster recovery, enable the AD Recycle Bin for deleted object recovery, and check domain health and capacity.**

**Prerequisites:** Phase 07 completed — sites and replication configured.

---
## 📑 Table of Contents

- [Step 1 — Review DC Placement & Topology](#step-1-review-dc-placement-topology)
- [Step 2 — Configure DNS Scavenging](#step-2-configure-dns-scavenging)
- [Step 3 — Windows Server Backup](#step-3-windows-server-backup)
- [Step 4 — Enable AD Recycle Bin](#step-4-enable-ad-recycle-bin)
- [Step 5 — Check Domain Health & Capacity](#step-5-check-domain-health-capacity)

---

## Step 1 — Review DC Placement & Topology

Review the current AD topology in AD Sites and Services. Verify DC placement and replication connections:

```powershell
Get-ADDomainController -Filter * | Select Name, Site, IPv4Address
repadmin /replsummary
```

### Screenshot 1

![Step 1 — Review DC Placement & Topology - Screenshot 1](01-REVIEW%20DC%20PLACEMENT%20AND%20TOPOLOGY/TOPOLOGY-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 1 — Review DC Placement & Topology - Screenshot 2](01-REVIEW%20DC%20PLACEMENT%20AND%20TOPOLOGY/TOPOLOGY-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 1 — Review DC Placement & Topology - Screenshot 3](01-REVIEW%20DC%20PLACEMENT%20AND%20TOPOLOGY/TOPOLOGY-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 1 — Review DC Placement & Topology - Screenshot 4](01-REVIEW%20DC%20PLACEMENT%20AND%20TOPOLOGY/TOPOLOGY-%20%284%29.png)

**Continue the configuration (step 4 of 8) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 1 — Review DC Placement & Topology - Screenshot 5](01-REVIEW%20DC%20PLACEMENT%20AND%20TOPOLOGY/TOPOLOGY-%20%285%29.png)

**Continue the configuration (step 5 of 8) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 1 — Review DC Placement & Topology - Screenshot 6](01-REVIEW%20DC%20PLACEMENT%20AND%20TOPOLOGY/TOPOLOGY-%20%286%29.png)

**Continue the configuration (step 6 of 8) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 1 — Review DC Placement & Topology - Screenshot 7](01-REVIEW%20DC%20PLACEMENT%20AND%20TOPOLOGY/TOPOLOGY-%20%287%29.png)

**Continue the configuration (step 7 of 8) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 1 — Review DC Placement & Topology - Screenshot 8](01-REVIEW%20DC%20PLACEMENT%20AND%20TOPOLOGY/TOPOLOGY-%20%288%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 2 — Configure DNS Scavenging

Enable DNS scavenging to automatically remove stale DNS records:

1. Open DNS Manager
2. Right-click the server → Properties → Advanced → Enable scavenging
3. Set No-refresh interval: 7 days
4. Set Refresh interval: 7 days
5. Right-click the zone → Properties → Aging → Enable

### Screenshot 1

![Step 2 — Configure DNS Scavenging - Screenshot 1](02-DNS%20SCAVENGING%20(MAINTENANCE)/DNS%20SCAVENGING-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 2 — Configure DNS Scavenging - Screenshot 2](02-DNS%20SCAVENGING%20(MAINTENANCE)/DNS%20SCAVENGING-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 2 — Configure DNS Scavenging - Screenshot 3](02-DNS%20SCAVENGING%20(MAINTENANCE)/DNS%20SCAVENGING-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 2 — Configure DNS Scavenging - Screenshot 4](02-DNS%20SCAVENGING%20(MAINTENANCE)/DNS%20SCAVENGING-%20%284%29.png)

**Continue the configuration (step 4 of 8) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 2 — Configure DNS Scavenging - Screenshot 5](02-DNS%20SCAVENGING%20(MAINTENANCE)/DNS%20SCAVENGING-%20%285%29.png)

**Continue the configuration (step 5 of 8) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 2 — Configure DNS Scavenging - Screenshot 6](02-DNS%20SCAVENGING%20(MAINTENANCE)/DNS%20SCAVENGING-%20%286%29.png)

**Continue the configuration (step 6 of 8) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 2 — Configure DNS Scavenging - Screenshot 7](02-DNS%20SCAVENGING%20(MAINTENANCE)/DNS%20SCAVENGING-%20%287%29.png)

**Continue the configuration (step 7 of 8) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 2 — Configure DNS Scavenging - Screenshot 8](02-DNS%20SCAVENGING%20(MAINTENANCE)/DNS%20SCAVENGING-%20%288%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 3 — Windows Server Backup

Install Windows Server Backup feature and create a System State backup for disaster recovery:

```powershell
# Install the feature
Install-WindowsFeature Windows-Server-Backup

# Create a System State backup
wbadmin start systemstatebackup -backuptarget:E:
```

### Screenshot 1

![Step 3 — Windows Server Backup - Screenshot 1](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 3 — Windows Server Backup - Screenshot 2](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 3 — Windows Server Backup - Screenshot 3](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 3 — Windows Server Backup - Screenshot 4](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%284%29.png)

**Continue the configuration (step 4 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 3 — Windows Server Backup - Screenshot 5](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%285%29.png)

**Continue the configuration (step 5 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 3 — Windows Server Backup - Screenshot 6](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%286%29.png)

**Continue the configuration (step 6 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 3 — Windows Server Backup - Screenshot 7](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%287%29.png)

**Continue the configuration (step 7 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 3 — Windows Server Backup - Screenshot 8](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%288%29.png)

**Continue the configuration (step 8 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 3 — Windows Server Backup - Screenshot 9](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%289%29.png)

**Continue the configuration (step 9 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 3 — Windows Server Backup - Screenshot 10](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2810%29.png)

**Continue the configuration (step 10 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 3 — Windows Server Backup - Screenshot 11](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2811%29.png)

**Continue the configuration (step 11 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 3 — Windows Server Backup - Screenshot 12](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2812%29.png)

**Continue the configuration (step 12 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 3 — Windows Server Backup - Screenshot 13](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2813%29.png)

**Continue the configuration (step 13 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 3 — Windows Server Backup - Screenshot 14](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2814%29.png)

**Continue the configuration (step 14 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 3 — Windows Server Backup - Screenshot 15](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2815%29.png)

**Continue the configuration (step 15 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 3 — Windows Server Backup - Screenshot 16](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2816%29.png)

**Continue the configuration (step 16 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 3 — Windows Server Backup - Screenshot 17](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2817%29.png)

**Continue the configuration (step 17 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 3 — Windows Server Backup - Screenshot 18](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2818%29.png)

**Continue the configuration (step 18 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 3 — Windows Server Backup - Screenshot 19](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2819%29.png)

**Continue the configuration (step 19 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 3 — Windows Server Backup - Screenshot 20](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2820%29.png)

**Continue the configuration (step 20 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 3 — Windows Server Backup - Screenshot 21](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2821%29.png)

**Continue the configuration (step 21 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 22

![Step 3 — Windows Server Backup - Screenshot 22](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2822%29.png)

**Continue the configuration (step 22 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 23

![Step 3 — Windows Server Backup - Screenshot 23](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2823%29.png)

**Continue the configuration (step 23 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 24

![Step 3 — Windows Server Backup - Screenshot 24](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2824%29.png)

**Continue the configuration (step 24 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 25

![Step 3 — Windows Server Backup - Screenshot 25](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2825%29.png)

**Continue the configuration (step 25 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 26

![Step 3 — Windows Server Backup - Screenshot 26](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2826%29.png)

**Continue the configuration (step 26 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 27

![Step 3 — Windows Server Backup - Screenshot 27](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2827%29.png)

**Continue the configuration (step 27 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 28

![Step 3 — Windows Server Backup - Screenshot 28](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2828%29.png)

**Continue the configuration (step 28 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 29

![Step 3 — Windows Server Backup - Screenshot 29](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2829%29.png)

**Continue the configuration (step 29 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 30

![Step 3 — Windows Server Backup - Screenshot 30](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2830%29.png)

**Continue the configuration (step 30 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 31

![Step 3 — Windows Server Backup - Screenshot 31](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2831%29.png)

**Continue the configuration (step 31 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 32

![Step 3 — Windows Server Backup - Screenshot 32](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2832%29.png)

**Continue the configuration (step 32 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 33

![Step 3 — Windows Server Backup - Screenshot 33](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2833%29.png)

**Continue the configuration (step 33 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 34

![Step 3 — Windows Server Backup - Screenshot 34](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2834%29.png)

**Continue the configuration (step 34 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 35

![Step 3 — Windows Server Backup - Screenshot 35](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2835%29.png)

**Continue the configuration (step 35 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 36

![Step 3 — Windows Server Backup - Screenshot 36](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2836%29.png)

**Continue the configuration (step 36 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 37

![Step 3 — Windows Server Backup - Screenshot 37](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2837%29.png)

**Continue the configuration (step 37 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 38

![Step 3 — Windows Server Backup - Screenshot 38](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2838%29.png)

**Continue the configuration (step 38 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 39

![Step 3 — Windows Server Backup - Screenshot 39](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2839%29.png)

**Continue the configuration (step 39 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 40

![Step 3 — Windows Server Backup - Screenshot 40](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2840%29.png)

**Continue the configuration (step 40 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 41

![Step 3 — Windows Server Backup - Screenshot 41](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2841%29.png)

**Continue the configuration (step 41 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 42

![Step 3 — Windows Server Backup - Screenshot 42](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2842%29.png)

**Continue the configuration (step 42 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 43

![Step 3 — Windows Server Backup - Screenshot 43](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2843%29.png)

**Continue the configuration (step 43 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 44

![Step 3 — Windows Server Backup - Screenshot 44](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2844%29.png)

**Continue the configuration (step 44 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 45

![Step 3 — Windows Server Backup - Screenshot 45](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2845%29.png)

**Continue the configuration (step 45 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 46

![Step 3 — Windows Server Backup - Screenshot 46](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2846%29.png)

**Continue the configuration (step 46 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 47

![Step 3 — Windows Server Backup - Screenshot 47](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2847%29.png)

**Continue the configuration (step 47 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 48

![Step 3 — Windows Server Backup - Screenshot 48](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2848%29.png)

**Continue the configuration (step 48 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 49

![Step 3 — Windows Server Backup - Screenshot 49](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2849%29.png)

**Continue the configuration (step 49 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 50

![Step 3 — Windows Server Backup - Screenshot 50](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2850%29.png)

**Continue the configuration (step 50 of 51) — follow the red arrows/boxes for guidance.**

### Screenshot 51

![Step 3 — Windows Server Backup - Screenshot 51](03-WINDOWS%20SERVER%20BACKUP%20(DISASTER%20RECOVERY)/DISASTER%20RECOVERY-%20%2851%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 4 — Enable AD Recycle Bin

Enable the AD Recycle Bin to allow recovery of deleted AD objects:

```powershell
Enable-ADOptionalFeature 'Recycle Bin Feature' `
    -Scope ForestOrConfigurationSet `
    -Target 'vertex.local'
```

Test by deleting and restoring a user account.

### Screenshot 1

![Step 4 — Enable AD Recycle Bin - Screenshot 1](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 4 — Enable AD Recycle Bin - Screenshot 2](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 4 — Enable AD Recycle Bin - Screenshot 3](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 4 — Enable AD Recycle Bin - Screenshot 4](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%284%29.png)

**Continue the configuration (step 4 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 4 — Enable AD Recycle Bin - Screenshot 5](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%285%29.png)

**Continue the configuration (step 5 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 4 — Enable AD Recycle Bin - Screenshot 6](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%286%29.png)

**Continue the configuration (step 6 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 4 — Enable AD Recycle Bin - Screenshot 7](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%287%29.png)

**Continue the configuration (step 7 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 4 — Enable AD Recycle Bin - Screenshot 8](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%288%29.png)

**Continue the configuration (step 8 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 4 — Enable AD Recycle Bin - Screenshot 9](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%289%29.png)

**Continue the configuration (step 9 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 4 — Enable AD Recycle Bin - Screenshot 10](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%2810%29.png)

**Continue the configuration (step 10 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 4 — Enable AD Recycle Bin - Screenshot 11](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%2811%29.png)

**Continue the configuration (step 11 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 4 — Enable AD Recycle Bin - Screenshot 12](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%2812%29.png)

**Continue the configuration (step 12 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 4 — Enable AD Recycle Bin - Screenshot 13](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%2813%29.png)

**Continue the configuration (step 13 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 4 — Enable AD Recycle Bin - Screenshot 14](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%2814%29.png)

**Continue the configuration (step 14 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 4 — Enable AD Recycle Bin - Screenshot 15](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%2815%29.png)

**Continue the configuration (step 15 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 4 — Enable AD Recycle Bin - Screenshot 16](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%2816%29.png)

**Continue the configuration (step 16 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 4 — Enable AD Recycle Bin - Screenshot 17](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%2817%29.png)

**Continue the configuration (step 17 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 4 — Enable AD Recycle Bin - Screenshot 18](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%2818%29.png)

**Continue the configuration (step 18 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 4 — Enable AD Recycle Bin - Screenshot 19](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%2819%29.png)

**Continue the configuration (step 19 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 4 — Enable AD Recycle Bin - Screenshot 20](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%2820%29.png)

**Continue the configuration (step 20 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 4 — Enable AD Recycle Bin - Screenshot 21](04-ENABLE%20AD%20RECYCLE%20BIN/RECYCLE%20BIN-%20%2821%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 5 — Check Domain Health & Capacity

Run diagnostic commands to check overall domain health:

```cmd
dcdiag /v
dcdiag /test:dns
repadmin /replsummary
nltest /dsgetsite
```

### Screenshot 1

![Step 5 — Check Domain Health & Capacity - Screenshot 1](05-%20CHECK%20DOMAIN%20HEALTH%20AND%20CAPACITY/DOMAIN%20HEALTH-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 5 — Check Domain Health & Capacity - Screenshot 2](05-%20CHECK%20DOMAIN%20HEALTH%20AND%20CAPACITY/DOMAIN%20HEALTH-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 5 — Check Domain Health & Capacity - Screenshot 3](05-%20CHECK%20DOMAIN%20HEALTH%20AND%20CAPACITY/DOMAIN%20HEALTH-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 5 — Check Domain Health & Capacity - Screenshot 4](05-%20CHECK%20DOMAIN%20HEALTH%20AND%20CAPACITY/DOMAIN%20HEALTH-%20%284%29.png)

**Final result — verify the configuration is complete and working.**

---

## 🔗 Navigation

[⬆️ Back to Top](#)

[📚 Back to Master README](../README.md)
