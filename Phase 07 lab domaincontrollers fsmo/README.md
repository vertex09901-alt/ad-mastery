# Phase 07 — Domain Controllers & FSMO

> Identify and document the five FSMO role holders, verify AD replication between DC1 and DC2, explore the SYSVOL and NTDS directory structures, and configure Active Directory Sites and Site Links.

---

## Steps

### 01 — FSMO Roles
Identified all five **Flexible Single Master Operations (FSMO)** role holders using the command:

```cmd
netdom query fsmo
```

Results in the lab:

| FSMO Role | Holder |
|-----------|--------|
| Schema Master | DC1.vertex.local |
| Domain Naming Master | DC1.vertex.local |
| PDC Emulator | DC1.vertex.local |
| RID Pool Manager | DC1.vertex.local |
| Infrastructure Master | DC1.vertex.local |

All five roles on DC1 (expected for a new domain before manual transfer).

Also verified roles via GUI:
- **Schema Master** → Active Directory Schema snap-in
- **Domain Naming Master** → Active Directory Domains and Trusts
- **PDC, RID, Infrastructure** → Active Directory Users and Computers → right-click domain → Operations Masters

**Screenshots:** `01-FSMO ROLES/` (14 images)

---

### 02 — Verify Replication
Verified that AD replication is healthy between DC1 and DC2 using:

```cmd
repadmin /showrepl
repadmin /replsummary
```

Checked for:
- ✅ No replication errors
- ✅ Both DCs syncing all AD partitions (Domain, Schema, Configuration, DNS)
- ✅ Last successful replication time within expected window

**Screenshots:** `02-VERIFY REPLICATION/` (10 images)

---

### 03 — Explore SYSVOL and NTDS
Explored the critical Active Directory file system locations:

**SYSVOL** (`C:\Windows\SYSVOL\sysvol\vertex.local\`)
- Contains `Policies\` — GPO template files replicated to all DCs
- Contains `Scripts\` — logon/logoff scripts
- Replicated via **DFSR** (Distributed File System Replication) between DC1 and DC2

**NTDS** (`C:\Windows\NTDS\`)
- `NTDS.DIT` — the Active Directory database (all objects, attributes, passwords)
- `EDB*.log` — transaction log files (written before committing to NTDS.DIT)
- `NTDS.CHK` — checkpoint file tracking what's been committed

> ⚠️ Never manually edit or copy NTDS.DIT while AD is running.

**Screenshots:** `03-EXPLORE SYSVOL AND NTDS/` (7 images)

---

### 04 — Create Sites and Site Links
Configured **Active Directory Sites and Services** to represent the physical network topology:

Created two sites:
- `London-HQ` — for DC1 and CLIENT1 (local site)
- `Manchester-Branch` — simulated remote office

Created a **Site Link** between London-HQ and Manchester-Branch:
- Replication interval: 15 minutes
- Cost: 100

Moved DC1 and DC2 to the `London-HQ` site.

**Screenshots:** `04-CREATE SITES AND SITE LINKS/` (60 images)

---

## Key Concepts

**The Five FSMO Roles:**

| Role | Forest/Domain | Responsible For |
|------|--------------|-----------------|
| Schema Master | Forest-wide (1 per forest) | Controlling schema modifications |
| Domain Naming Master | Forest-wide (1 per forest) | Adding/removing domains from the forest |
| PDC Emulator | Domain-wide (1 per domain) | Password changes, time sync, legacy auth, GPO edits |
| RID Pool Manager | Domain-wide (1 per domain) | Allocating pools of RIDs used to build SIDs |
| Infrastructure Master | Domain-wide (1 per domain) | Cross-domain object reference updates |

- The **PDC Emulator** is the busiest FSMO role — it handles password change broadcasts and is the authoritative NTP source for the domain
- **SYSVOL** replication is how GPOs get to every DC — if SYSVOL is broken, Group Policy breaks
- **Sites** in AD map to physical subnets and control how clients find the nearest DC (site-aware authentication)

---

## Tools Used

`netdom` · `repadmin` · `Active Directory Sites and Services` · `Active Directory Domains and Trusts` · `Active Directory Schema (MMC snap-in)`

---

*Previous: [Phase 06 — Group Policy](<../Phase 06 lab group policy/README.md>) · Next: [Phase 08 — AD Security](<../Phase 08 lab ad security/README.md>)*
