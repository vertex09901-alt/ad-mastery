# 🏢 Active Directory Enterprise Lab — Vertex Corporation

<div align="center">

![Active Directory](https://img.shields.io/badge/Active%20Directory-Windows%20Server%202022-0078D4?style=for-the-badge&logo=windows&logoColor=white)
![VirtualBox](https://img.shields.io/badge/Hypervisor-Oracle%20VirtualBox-183A61?style=for-the-badge&logo=virtualbox&logoColor=white)
![PowerShell](https://img.shields.io/badge/Automation-PowerShell%205.1-5391FE?style=for-the-badge&logo=powershell&logoColor=white)
![Phases](https://img.shields.io/badge/Phases%20Completed-13%20of%2013-success?style=for-the-badge)
![Screenshots](https://img.shields.io/badge/Screenshots-1581-orange?style=for-the-badge)
![Domain](https://img.shields.io/badge/Domain-vertex.local-blueviolet?style=for-the-badge)

**A fully documented, enterprise-grade Active Directory home lab simulating a real multinational technology company built from scratch in Oracle VirtualBox**

</div>

---

## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [Business Scenario](#-business-scenario---vertex-corporation)
- [Lab Architecture](#-lab-architecture)
- [Network Design](#-network-design)
- [Virtual Machine Inventory](#-virtual-machine-inventory)
- [Domain Architecture](#-domain-architecture)
- [OU Structure](#-ou-structure)
- [Technologies Used](#-technologies-used)
- [Skills Demonstrated](#-skills-demonstrated)
- [Phase Summary](#-phase-summary)
- [Security Architecture](#-security-architecture)
- [PowerShell Automation](#-powershell-automation)
- [Attack and Defense](#-attack-and-defense-simulation)
- [Repository Structure](#-repository-structure)
- [Key Outcomes](#-key-outcomes)
- [Future Improvements](#-future-improvements)

---

## 🎯 Project Overview

This repository documents a **complete, enterprise-grade Active Directory environment** built from scratch on a personal workstation using Oracle VirtualBox. The lab simulates **Vertex Corporation** — a fictional multinational technology consulting company with 3,800 employees across six global offices.

Every phase was completed hands-on. Every configuration decision was justified against real enterprise requirements. Every major step was captured in screenshots — **1,581 screenshots** across 13 phases documenting the entire implementation.

**This is not a tutorial following steps blindly.** Every decision — why a particular OU structure, why AGDLP over direct assignment, why tiered admin accounts, why LAPS — is grounded in enterprise architecture reasoning and documented accordingly.

**Target Role:** IAM Analyst / Active Directory Administrator / Systems Engineer

---

## 🏢 Business Scenario — Vertex Corporation

```
╔══════════════════════════════════════════════════════════════════╗
║                    VERTEX CORPORATION                            ║
║              Technology Consulting & Managed Services            ║
╠══════════════════════════════════════════════════════════════════╣
║  Employees  : 3,800                                              ║
║  Revenue    : £420 Million Annually                              ║
║  Founded    : 2005                                               ║
║  HQ         : London, United Kingdom                             ║
║  Offices    : London · Mumbai · Dubai · Singapore · Berlin · NYC ║
║  Domain     : vertex.local                                       ║
║  Forest     : vertex.local                                       ║
║  NetBIOS    : VERTEX                                             ║
╚══════════════════════════════════════════════════════════════════╝
```

### Global Office Distribution

| Office | Location | Employees | IP Subnet | DC Assigned |
|--------|----------|-----------|-----------|-------------|
| **Headquarters** | London, UK | 1,200 | 192.168.10.0/24 | DC1 + DC2 |
| Branch | Mumbai, India | 800 | 192.168.20.0/24 | MUM-DC-001 (planned) |
| Branch | Dubai, UAE | 400 | 192.168.30.0/24 | DXB-DC-001 (planned) |
| Branch | Singapore | 350 | 192.168.40.0/24 | SIN-DC-001 (planned) |
| Branch | Berlin, Germany | 600 | 192.168.50.0/24 | BER-DC-001 (planned) |
| Branch | New York, USA | 450 | 192.168.60.0/24 | NYC-DC-001 (planned) |

---

## 🏗️ Lab Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        HOST MACHINE — Windows 11 Pro                         │
│                          Oracle VirtualBox 7.x                               │
│                                                                               │
│  ┌──────────────────┐   ┌──────────────────┐   ┌──────────────────────────┐ │
│  │       DC1        │   │       DC2        │   │       LON-WKS-001        │ │
│  │  ┌────────────┐  │   │  ┌────────────┐  │   │  ┌────────────────────┐  │ │
│  │  │ Windows    │  │   │  │ Windows    │  │   │  │   Windows 11 Pro   │  │ │
│  │  │ Server     │  │   │  │ Server     │  │   │  └────────────────────┘  │ │
│  │  │ 2022       │  │   │  │ 2022       │  │   │                          │ │
│  │  └────────────┘  │   │  └────────────┘  │   │  Domain-Joined           │ │
│  │                  │   │                  │   │  Workstation             │ │
│  │  Roles:          │   │  Roles:          │   │                          │ │
│  │  ✦ AD DS         │   │  ✦ AD DS         │   │  Used For:               │ │
│  │  ✦ DNS Server    │   │  ✦ DNS Server    │   │  ✦ GPO Testing           │ │
│  │  ✦ All FSMO      │   │  ✦ Global Cat.   │   │  ✦ User Logon Tests      │ │
│  │                  │   │                  │   │  ✦ Attack Simulation     │ │
│  │  IP:             │   │  IP:             │   │  ✦ LDAP Client           │ │
│  │  192.168.10.10   │   │  192.168.10.11   │   │                          │ │
│  │                  │   │                  │   │  IP: 192.168.10.50       │ │
│  │  RAM: 4 GB       │   │  RAM: 4 GB       │   │  RAM: 2 GB               │ │
│  │  Disk: 60 GB     │   │  Disk: 60 GB     │   │  Disk: 40 GB             │ │
│  └────────┬─────────┘   └────────┬─────────┘   └───────────┬──────────────┘ │
│           │                      │                          │                │
│           └──────────────────────┴──────────────────────────┘                │
│                              LabSwitch                                        │
│                    (VirtualBox Internal Network)                              │
│                      192.168.10.0/24                                          │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 🌐 Network Design

```
NETWORK: 192.168.10.0/24
SUBNET:  255.255.255.0
GATEWAY: 192.168.10.1

┌────────────────┬──────────────────┬─────────────────┬──────────────────────┐
│   Hostname     │   IP Address     │   DNS Primary   │   DNS Secondary      │
├────────────────┼──────────────────┼─────────────────┼──────────────────────┤
│ DC1            │ 192.168.10.10    │ 127.0.0.1       │ —                    │
│ DC2            │ 192.168.10.11    │ 192.168.10.10   │ —                    │
│ LON-WKS-001    │ 192.168.10.50    │ 192.168.10.10   │ 192.168.10.11        │
├────────────────┼──────────────────┼─────────────────┼──────────────────────┤
│ DNS Forwarder 1│ 8.8.8.8          │ Google DNS      │ Internet resolution  │
│ DNS Forwarder 2│ 1.1.1.1          │ Cloudflare DNS  │ Internet resolution  │
└────────────────┴──────────────────┴─────────────────┴──────────────────────┘

Virtual Switch Type: Internal Network (isolated from host and internet)
Switch Name: LabSwitch
```

---

## 🖥️ Virtual Machine Inventory

### DC1 — Primary Domain Controller

```
┌──────────────────────────────────────────────────────┐
│                        DC1                           │
├──────────────────────────┬───────────────────────────┤
│ Operating System         │ Windows Server 2022       │
│                          │ Standard Evaluation       │
│                          │ (Desktop Experience)      │
├──────────────────────────┼───────────────────────────┤
│ RAM                      │ 4,096 MB                  │
│ Storage                  │ 60 GB (Dynamic VDI)       │
│ IP Address               │ 192.168.10.10             │
│ Network                  │ LabSwitch (Internal)      │
├──────────────────────────┼───────────────────────────┤
│ Roles Installed          │ AD DS, DNS Server         │
│ FSMO Roles Held          │ PDC Emulator              │
│                          │ RID Master                │
│                          │ Infrastructure Master     │
│                          │ Schema Master             │
│                          │ Domain Naming Master      │
├──────────────────────────┼───────────────────────────┤
│ Global Catalog           │ Yes                       │
│ Preferred Bridgehead     │ Yes                       │
│ AD Functional Level      │ Windows Server 2025       │
│ Forest Functional Level  │ Windows Server 2025       │
└──────────────────────────┴───────────────────────────┘
```

### DC2 — Secondary Domain Controller

```
┌──────────────────────────────────────────────────────┐
│                        DC2                           │
├──────────────────────────┬───────────────────────────┤
│ Operating System         │ Windows Server 2022       │
│                          │ Standard Evaluation       │
│                          │ (Desktop Experience)      │
├──────────────────────────┼───────────────────────────┤
│ RAM                      │ 4,096 MB                  │
│ Storage                  │ 60 GB (Dynamic VDI)       │
│ IP Address               │ 192.168.10.11             │
│ Network                  │ LabSwitch (Internal)      │
├──────────────────────────┼───────────────────────────┤
│ Roles Installed          │ AD DS, DNS Server         │
│ Site Assignment          │ London-HQ                 │
│ Replicates From          │ DC1.vertex.local          │
│ Global Catalog           │ Yes                       │
└──────────────────────────┴───────────────────────────┘
```

### LON-WKS-001 — Domain Workstation

```
┌──────────────────────────────────────────────────────┐
│                    LON-WKS-001                       │
├──────────────────────────┬───────────────────────────┤
│ Operating System         │ Windows 11 Pro            │
│ RAM                      │ 2,048 MB                  │
│ Storage                  │ 40 GB (Dynamic VDI)       │
│ IP Address               │ 192.168.10.50             │
│ Domain Joined            │ vertex.local              │
│ OU Location              │ IT → Computers            │
│ Original Name            │ CLIENT1 → LON-WKS-001     │
└──────────────────────────┴───────────────────────────┘
```

---

## 🌳 Domain Architecture

```
FOREST: vertex.local
│
└── DOMAIN: vertex.local
    │
    ├── FUNCTIONAL LEVEL: Windows Server 2025
    │
    ├── DOMAIN CONTROLLERS
    │   ├── DC1.vertex.local  [Primary DC — All FSMO Roles]
    │   └── DC2.vertex.local  [Secondary DC — GC — DNS]
    │
    ├── DNS ZONES
    │   ├── Forward: vertex.local  [AD-Integrated]
    │   ├── Reverse: 10.168.192.in-addr.arpa
    │   ├── CNAME: intranet.vertex.local → DC1.vertex.local
    │   └── Conditional Forwarder: apex-tech.com → 10.50.0.53
    │
    ├── AD SITES
    │   ├── London-HQ       [192.168.10.0/24]  ← DC1 + DC2
    │   ├── Mumbai-Branch   [192.168.20.0/24]
    │   ├── Dubai-Branch    [192.168.30.0/24]
    │   ├── Singapore-Branch[192.168.40.0/24]
    │   ├── Berlin-Branch   [192.168.50.0/24]
    │   └── NewYork-Branch  [192.168.60.0/24]
    │
    └── FSMO ROLE PLACEMENT
        ├── Schema Master         → DC1.vertex.local
        ├── Domain Naming Master  → DC1.vertex.local
        ├── PDC Emulator          → DC1.vertex.local
        ├── RID Master            → DC1.vertex.local
        └── Infrastructure Master → DC1.vertex.local
```

---

## 🗂️ OU Structure

```
DC=vertex,DC=local
│
└── OU=VERTEX
    │
    ├── OU=HQ-London
    │   ├── OU=IT
    │   │   ├── OU=Users          [riyan.patel, sarah.jones, michael.chen ...]
    │   │   ├── OU=Computers      [LON-WKS-001]
    │   │   ├── OU=Service-Accounts [svc-sql, svc-iis, svc-backup ...]
    │   │   └── OU=Admins
    │   │       ├── OU=Tier0      [adm0-riyan.patel, adm0-sarah.jones ...]
    │   │       └── OU=Tier1
    │   │
    │   ├── OU=Finance
    │   │   ├── OU=Users          [thomas.grant, lisa.huang, ahmed.hassan ...]
    │   │   └── OU=Computers
    │   │
    │   ├── OU=HR
    │   │   ├── OU=Users          [jennifer.thompson, marcus.wilson ...]
    │   │   └── OU=Computers
    │   │
    │   ├── OU=Security
    │   │   ├── OU=Users          [priya.singh, leon.petrov ...]
    │   │   └── OU=Computers
    │   │
    │   ├── OU=Development
    │   │   ├── OU=Users          [christopher.brown, yuki.tanaka ...]
    │   │   └── OU=Computers
    │   │
    │   ├── OU=Operations
    │   │   ├── OU=Users          [oliver.smith, nina.garcia ...]
    │   │   └── OU=Computers
    │   │
    │   ├── OU=Helpdesk
    │   │   ├── OU=Users          [james.okafor, grace.chen ...]
    │   │   └── OU=Computers
    │   │
    │   └── OU=Executive
    │       ├── OU=Users          [victor.harrington, amanda.pierce ...]
    │       └── OU=Computers
    │
    ├── OU=Branch-Mumbai
    ├── OU=Branch-Dubai
    ├── OU=Branch-Singapore
    ├── OU=Branch-Berlin
    ├── OU=Branch-NewYork
    │
    ├── OU=Groups
    │   ├── OU=Security-Groups    [G-Finance-All, DL-Finance-Share-Read ...]
    │   └── OU=Distribution-Groups[DL-Finance-Email, DL-IT-Email ...]
    │
    └── OU=Servers
        ├── OU=Member-Servers
        └── OU=Tier0-Servers
```

---

## ⚙️ Technologies Used

| Technology | Version | Purpose in Lab |
|-----------|---------|----------------|
| **Windows Server 2022** | 21H2 | Operating System for DC1 and DC2 |
| **Windows 11 Pro** | 22H2 | End-user workstation (LON-WKS-001) |
| **Active Directory Domain Services** | Built-in | Core identity and access management |
| **DNS Server** | Built-in | Name resolution, SRV records, AD locator |
| **Group Policy** | Built-in | Centralized configuration management |
| **Kerberos v5** | Built-in | Primary authentication protocol |
| **LDAP / LDAPS** | v3 / Port 636 | Directory access protocol |
| **DFSR** | Built-in | SYSVOL replication between DCs |
| **Oracle VirtualBox** | 7.x | Type-2 Hypervisor |
| **PowerShell** | 5.1 | Administration and automation |
| **LDP.exe** | Built-in | LDAP browser and testing |
| **ADExplorer** | Sysinternals | Advanced directory browser |
| **repadmin / dcdiag** | Built-in | Replication and health diagnostics |
| **ntdsutil** | Built-in | AD database maintenance |
| **Windows Server Backup** | Built-in | System State backup |
| **LAPS** | Microsoft | Local admin password management |
| **BloodHound CE** | Community | AD attack path analysis |

---

## 🎓 Skills Demonstrated

### Identity & Access Management
- ✅ Enterprise AD forest and domain design from scratch
- ✅ OU hierarchy design aligned to org structure (8 departments, 6 branches)
- ✅ User lifecycle management — creation, modification, disable, delete
- ✅ Group design using AGDLP (Accounts → Global → Domain Local → Permissions)
- ✅ Naming convention design and enforcement
- ✅ Service account provisioning with security-appropriate settings
- ✅ Joiner / Mover / Leaver (JML) process automation
- ✅ Access review concepts and stale account detection

### Active Directory Administration
- ✅ AD DS role installation and DC promotion
- ✅ FSMO role management — verification, transfer, best placement
- ✅ Secondary DC promotion and replication configuration
- ✅ AD Sites and Services — 6 sites, 5 site links, subnet assignments
- ✅ Replication health verification with repadmin / dcdiag
- ✅ AD database maintenance with ntdsutil
- ✅ AD Recycle Bin enablement and object restoration
- ✅ System State backup with Windows Server Backup
- ✅ DNS scavenging configuration

### DNS Administration
- ✅ AD-integrated forward and reverse lookup zones
- ✅ SRV, A, PTR, CNAME record management
- ✅ Forwarder configuration (8.8.8.8, 1.1.1.1)
- ✅ Conditional forwarder for partner domains
- ✅ DNS health verification with dcdiag /test:DNS
- ✅ DC locator process understanding

### Group Policy
- ✅ 6 GPOs built for real business scenarios
- ✅ LSDOU processing order and inheritance management
- ✅ Security filtering to scope GPO to specific groups
- ✅ Loopback processing (Replace mode) for shared computers
- ✅ Password policy, lockout, complexity enforcement
- ✅ USB device blocking, screensaver, Control Panel restriction
- ✅ GPO testing with gpresult and HTML reports

### Security Engineering
- ✅ Administrative Tiering Model (Tier 0/1/2 separation)
- ✅ Delegation of Control — least privilege helpdesk permissions
- ✅ LAPS deployment for unique local admin passwords
- ✅ Protected Users group — executives and Domain Admins
- ✅ Fine-Grained Password Policies (PSOs) — per-group password rules
- ✅ Advanced Audit Policy — targeted event logging
- ✅ Security event monitoring and analysis

### Kerberos & Authentication
- ✅ Kerberos ticket lifecycle observation with klist
- ✅ SPN registration and duplicate detection
- ✅ AES 256 encryption enforcement on key accounts
- ✅ Constrained delegation configuration
- ✅ Time synchronization verification
- ✅ Kerberos vs NTLM understanding

### LDAP
- ✅ LDP.exe — directory browsing, search, attribute modification
- ✅ ADExplorer (Sysinternals) — advanced directory exploration
- ✅ LDAP filter construction for 10+ query types
- ✅ PowerShell LDAP queries with Get-ADUser -LDAPFilter
- ✅ LDAPS (port 636) connection and certificate setup

### PowerShell Automation
- ✅ Bulk user provisioning from CSV
- ✅ JML automation — Joiner, Mover, Leaver functions
- ✅ Group membership management scripts
- ✅ Multi-section AD reporting (stale, locked, password, admin)
- ✅ Security baseline audit automation
- ✅ Error handling and validation in production-style scripts

### Attack & Defense
- ✅ LLMNR/NBT-NS poisoning prevention via GPO
- ✅ Password spray simulation and event-based detection
- ✅ Kerberoastable account identification and mitigation
- ✅ AS-REP Roasting detection and remediation
- ✅ DCSync rights auditing and event-based detection
- ✅ Defense verification scripting

---

## 📋 Phase Summary

```
┌──────────┬──────────────────────────────────────┬─────────────┬──────────┐
│  Phase   │  Title                               │ Screenshots │  Status  │
├──────────┼──────────────────────────────────────┼─────────────┼──────────┤
│  01      │  Lab VM Setup                        │     201     │  ✅ Done │
│  02      │  Active Directory Installation       │     228     │  ✅ Done │
│  03      │  Users and Computers                 │     107     │  ✅ Done │
│  04      │  DNS Configuration                   │      80     │  ✅ Done │
│  05      │  Groups and AGDLP                    │     146     │  ✅ Done │
│  06      │  Group Policy                        │     188     │  ✅ Done │
│  07      │  Domain Controllers and FSMO         │      91     │  ✅ Done │
│  08      │  Active Directory Security           │     186     │  ✅ Done │
│  09      │  Kerberos Authentication             │      74     │  ✅ Done │
│  10      │  LDAP                                │      77     │  ✅ Done │
│  11      │  Enterprise Design                   │      92     │  ✅ Done │
│  12      │  PowerShell for AD                   │      48     │  ✅ Done │
│  13      │  AD Attacks and Defense              │      63     │  ✅ Done │
├──────────┼──────────────────────────────────────┼─────────────┼──────────┤
│  TOTAL   │  13 Phases Completed                 │    1,581    │  ✅ 100% │
└──────────┴──────────────────────────────────────┴─────────────┴──────────┘
```

### Phase Details

#### 🖥️ Phase 01 — Lab VM Setup (201 screenshots)
Built the entire virtualized infrastructure from zero. Downloaded Oracle VirtualBox, created the internal `LabSwitch` network, provisioned all three VMs (DC1, DC2, LON-WKS-001), installed Windows Server 2022 on both DCs and Windows 11 on the workstation, configured static IP addresses, and verified cross-VM connectivity.

**Sub-sections:** VirtualBox Download → Hyper-V Installation → ISO Download → VM Creation and ISO Mount → Virtual Network Creation → DC Network Adapter Configuration → DC1 Installation → DC1 Rename and DNS Configuration → DC2 Installation → DC2 Rename and DNS Configuration → CLIENT1 Installation → CLIENT1 Rename and DNS Configuration

---

#### 🏗️ Phase 02 — Active Directory Installation (228 screenshots)
Installed the AD DS role on DC1 via Server Manager, promoted DC1 to the first Domain Controller creating the `vertex.local` forest, configured functional levels at Windows Server 2025, built the complete OU structure (8 departments + 6 branches + groups + servers), opened ADUC to verify the structure, configured AD Sites and Services creating the London-HQ site, joined DC2 to the domain, installed AD DS on DC2, and promoted DC2 as a secondary DC.

**Sub-sections:** DC1 ADDS Role Installation → DC1 Promote to Domain Controller → Active Directory Users and Computers → Vertex OU Structure Creation → London HQ Users Groups and Computers → Security Groups and Servers → Active Directory Sites and Services → DC2 Domain Join → Client1 Domain Connectivity Verification → DC2 ADDS Role Installation → DC2 Promote to Additional Domain Controller

---

#### 👥 Phase 03 — Users and Computers (107 screenshots)
Created 28+ user accounts across 8 departments manually and via CSV bulk import. Provisioned 5 service accounts (svc-sql, svc-backup, svc-monitoring, svc-iis, svc-scanner) with appropriate password settings. Logged into CLIENT1 as a domain user, moved the computer object to the correct IT/Computers OU, and renamed the machine from CLIENT1 to LON-WKS-001.

**Sub-sections:** Manual User Provisioning → Service Account Provisioning → Client1 Domain Administrator Login → Computer Object OU Migration → Client1 Computername Modification → Bulk User Provisioning via CSV → Active Directory User Count Verification

---

#### 🌐 Phase 04 — DNS Configuration (80 screenshots)
Explored auto-created DNS records (SRV, A records) after AD promotion. Created the reverse lookup zone `10.168.192.in-addr.arpa`. Added PTR records for DC1 and DC2. Configured forwarders to 8.8.8.8 and 1.1.1.1 for internet resolution. Created a CNAME alias `intranet.vertex.local`. Added a conditional forwarder for partner domain `apex-tech.com`. Tested all records with nslookup and ran full DNS health verification with dcdiag.

**Sub-sections:** Open DNS Manager and Explore Auto-Created Records → Create the Reverse Lookup Zone → Create PTR Records → Configure Forwarders → Create a CNAME Alias Record → Create a Conditional Forwarder → Test All DNS with NSLOOKUP → DNS Health Verification → Test DNS from CLIENT1

---

#### 🔑 Phase 05 — Groups and AGDLP (146 screenshots)
Implemented the complete AGDLP group strategy for Vertex Corporation. Created 12 Global Security groups (by department), 17 Domain Local groups (for resource permissions), and 7 Distribution groups (for email). Nested Global groups inside Domain Local groups to complete the AGDLP chain. Created a shared Finance folder, applied Domain Local groups to its ACL, and tested access from CLIENT1 verifying Finance users can access and Security users are denied.

**Sub-sections:** Create Global Security Groups → Create Domain Local Groups → Create Distribution Groups → Apply DL Group to a File Share (AGDLP in Action)

**AGDLP Chain Built:**
```
ahmed.hassan → G-Finance-All → DL-Finance-Share-Read → Finance Folder (Read)
lisa.huang   → G-Finance-Managers → DL-Finance-Share-Write → Finance Folder (Modify)
```

---

#### 📋 Phase 06 — Group Policy (188 screenshots)
Built 6 production-equivalent GPOs covering the main enterprise policy scenarios. Tested all policies on LON-WKS-001 using gpupdate /force and gpresult HTML reports.

| GPO Name | Linked To | Key Settings |
|----------|-----------|-------------|
| VERTEX-01-Base-Security | Domain (Enforced) | Password policy, lockout, complexity |
| VERTEX-Finance-Security | Finance OU | USB blocked, screen lock 5min, no Control Panel |
| VERTEX-IT-Admin-Policy | IT OU (filtered to G-IT-Admins) | PowerShell execution allowed |
| VERTEX-HQ-Desktop-Policy | HQ-London OU | Wallpaper, AutoPlay disabled |
| VERTEX-Audit-Policy | VERTEX OU | Advanced audit — logon, lockout, group changes |
| VERTEX-Operations-Kiosk-Loopback | Operations/Computers | Loopback Replace mode |

**Sub-sections:** Open Group Policy Management Console → GPO2 Finance Security Policy → GPO3 IT Admin Policy → GPO4 Desktop Policy → GPO5 Audit Policy → GPO6 Loopback Operations Shared PCs → Enforce Base Policy and Test

---

#### 🔄 Phase 07 — Domain Controllers and FSMO (91 screenshots)
Verified all 5 FSMO roles on DC1 using `netdom query fsmo` and PowerShell. Practiced PDC Emulator transfer to DC2 and back. Verified replication with `repadmin /replsummary` and `repadmin /showrepl`. Explored SYSVOL folder structure and ntds.dit file. Created 6 AD sites with IP subnets and configured 5 site links with 15-minute replication intervals.

**Sub-sections:** FSMO Roles → Verify Replication → Explore SYSVOL and NTDS → Create Sites and Site Links

**Replication Topology Built:**
```
London-HQ ─── London-Mumbai-Link (cost:100, 15min) ─── Mumbai-Branch
London-HQ ─── London-Dubai-Link (cost:100, 15min) ──── Dubai-Branch
London-HQ ─── London-Singapore-Link (cost:100, 15min) ─ Singapore-Branch
London-HQ ─── London-Berlin-Link (cost:100, 15min) ──── Berlin-Branch
London-HQ ─── London-NewYork-Link (cost:100, 15min) ─── NewYork-Branch
```

---

#### 🔒 Phase 08 — Active Directory Security (186 screenshots)
Implemented the Microsoft Administrative Tiering Model with dedicated Tier 0 admin accounts. Delegated password reset and account unlock permissions to G-IT-Helpdesk across all department Users OUs. Deployed LAPS — extended schema, set permissions, configured GPO, and read a live LAPS password from a computer object. Added executives and Domain Admins to the Protected Users group. Created two PSOs (PSO-IT-Admins precedence 10, PSO-ServiceAccounts precedence 20) in ADAC. Configured Advanced Audit Policy and verified Events 4624, 4625, 4740, and 4728 in Event Viewer.

**Sub-sections:** Tiering Admin Accounts → Delegate Password Reset to Helpdesk → LAPS → Protected Users Group → Fine-Grained Password Policies → Security Audit Event Verification

**Security Controls Implemented:**
```
┌────────────────────────────────────────────────────────────────┐
│ CONTROL               │ WHAT IT PROTECTS AGAINST              │
├───────────────────────┼───────────────────────────────────────┤
│ Admin Tiering         │ Credential theft via lateral movement │
│ Delegation            │ Over-privileged helpdesk accounts     │
│ LAPS                  │ Shared local admin password attacks   │
│ Protected Users       │ Pass-the-hash, credential caching     │
│ PSO-IT-Admins         │ Weak admin account passwords          │
│ PSO-ServiceAccounts   │ Kerberoasting weak service passwords  │
│ Advanced Audit        │ Blind spots in security logging       │
└───────────────────────┴───────────────────────────────────────┘
```

---

#### 🎫 Phase 09 — Kerberos Authentication (74 screenshots)
Observed Kerberos tickets in real time using klist immediately after login. Purged the ticket cache and watched Windows transparently re-authenticate. Registered SQL Server SPNs on svc-sql with setspn. Demonstrated the duplicate SPN error. Searched all domain SPNs with `setspn -Q */*`. Verified time synchronization on all three VMs with w32tm. Enabled AES 128 and AES 256 on all key accounts. Configured constrained delegation on svc-iis to svc-sql (Kerberos only). Located Event ID 4768 and 4769 in Event Viewer.

**Sub-sections:** Observe Kerberos Tickets with klist → Manage SPNs → Verify Time Synchronization → Enable AES Encryption → Configure Kerberos Constrained Delegation → Kerberos Events in Event Viewer

---

#### 📡 Phase 10 — LDAP (77 screenshots)
Connected to DC1 on port 389 using LDP.exe, performed a Simple Bind as administrator, and browsed the entire directory tree visually. Ran 8 different LDAP search queries (all users, Finance users, disabled accounts, SPN accounts). Modified an attribute directly via LDAP Modify. Installed ADExplorer from Sysinternals and navigated the directory. Ran PowerShell LDAP queries using `-LDAPFilter`. Attempted LDAPS connection on port 636 with a self-signed certificate.

**Sub-sections:** Connect to AD using LDP.exe → Run LDAP Search Queries → Modify an Attribute with LDP → Install and Use ADExplorer → LDAP Queries with PowerShell → Connect with LDAPS

---

#### 🏛️ Phase 11 — Enterprise Design (92 screenshots)
Reviewed DC placement and replication topology in AD Sites and Services. Set DC1 as preferred bridgehead server. Enabled DNS scavenging (7-day no-refresh + 7-day refresh). Installed Windows Server Backup, created a scheduled backup, and ran a manual System State backup to C:\AD-Backups. Enabled the AD Recycle Bin via ADAC, created a test user, deleted it, and restored it from the Deleted Objects container. Ran domain health and capacity reporting.

**Sub-sections:** Review DC Placement and Topology → DNS Scavenging → Windows Server Backup → Enable AD Recycle Bin → Check Domain Health and Capacity

---

#### 💻 Phase 12 — PowerShell for Active Directory (48 screenshots)
Built a complete 6-script PowerShell library for AD management in `C:\Scripts\AD-Management\`.

| Script | Purpose |
|--------|---------|
| User Management Script | Create, disable, reset, unlock user accounts |
| Group Management Script | Add/remove members, query memberships |
| Reporting Script | Users by dept, stale accounts, password issues, admin groups |
| JML Automation Script | Full Joiner / Mover / Leaver automation with validation |
| Security Audit Script | 7-point security baseline check |

**Sub-sections:** Prepare Scripts Folder → User Management Script → Group Management Script → Reporting Script → JML Automation Script → Security Audit Script

---

#### 🛡️ Phase 13 — AD Attacks and Defense (63 screenshots)
Simulated five real Active Directory attack techniques in the isolated lab environment and implemented corresponding defenses.

| Attack | Detection Method | Defense |
|--------|-----------------|---------|
| LLMNR/NBT-NS Poisoning | Network traffic analysis | GPO disabling LLMNR + firewall rules |
| Password Spraying | Event 4625 pattern (multi-account) | GPO-enforced lockout + monitoring |
| Kerberoasting | Event 4769 RC4 encryption spike | PSO 32-char passwords on svc accounts |
| AS-REP Roasting | DoesNotRequirePreAuth audit | Pre-auth enforced on all accounts |
| DCSync | Event 4662 replication GUID | ACL audit + replication rights review |

**Sub-sections:** Disable LLMNR and NBT-NS → Simulate and Detect Password Spraying → Kerberoasting Simulation and Defense → AS-REP Roasting → DCSync Detection and Analysis → Verify Your Defenses Are Working

---

## 🔐 Security Architecture

```
╔═══════════════════════════════════════════════════════════════╗
║           ADMINISTRATIVE TIERING MODEL                        ║
╠═══════════════════════════════════════════════════════════════╣
║                                                               ║
║  TIER 0 — DOMAIN CONTROLLERS (Highest Sensitivity)           ║
║  ┌─────────────────────────────────────────────────────┐     ║
║  │  Accounts: adm0-riyan.patel, adm0-sarah.jones       │     ║
║  │  Groups:   Domain Admins, Enterprise Admins          │     ║
║  │  Machines: DC1, DC2 ONLY                            │     ║
║  │  Rule:     These credentials NEVER touch Tier 2      │     ║
║  └─────────────────────────────────────────────────────┘     ║
║                          ↕ NO CROSSING                        ║
║  TIER 2 — WORKSTATIONS (Standard Users)                      ║
║  ┌─────────────────────────────────────────────────────┐     ║
║  │  Accounts: riyan.patel, ahmed.hassan (daily work)    │     ║
║  │  Machines: LON-WKS-001 (all workstations)           │     ║
║  │  Rule:     No Tier 0 credentials ever used here      │     ║
║  └─────────────────────────────────────────────────────┘     ║
╚═══════════════════════════════════════════════════════════════╝

PASSWORD POLICY STRATEGY
┌─────────────────────┬──────────────┬──────────┬───────────┐
│ Policy              │ Applies To   │ Min Len  │ Max Age   │
├─────────────────────┼──────────────┼──────────┼───────────┤
│ PSO-IT-Admins       │ G-IT-Admins  │ 16 chars │  60 days  │
│ (Precedence: 10)    │              │          │           │
├─────────────────────┼──────────────┼──────────┼───────────┤
│ PSO-ServiceAccounts │ svc-* accts  │ 32 chars │  Never    │
│ (Precedence: 20)    │              │          │           │
├─────────────────────┼──────────────┼──────────┼───────────┤
│ Domain Default      │ All others   │ 12 chars │  90 days  │
└─────────────────────┴──────────────┴──────────┴───────────┘
```

---

## ⚡ PowerShell Automation

All scripts are located in `Phase 12 lab powershell ad/`

### JML Automation — Core IAM Workflow

```powershell
# JOINER — Creates account, assigns to correct OU, adds to dept group
Invoke-Joiner -FirstName "New" -LastName "Employee" `
              -Department "Finance" -Title "Junior Analyst" `
              -EmployeeID "VTX-5001" -Manager "lisa.huang"

# MOVER — Updates dept/title, moves OU, adjusts group memberships
Invoke-Mover -Username "new.employee" `
             -OldDepartment "Finance" -NewDepartment "HR" `
             -NewTitle "HR Coordinator"

# LEAVER — Disables account, removes all groups, stamps description, expires
Invoke-Leaver -Username "new.employee"
```

### Security Audit

```powershell
# Runs 7 automated security checks — outputs PASS/FAIL for each
.\07-Security-Audit-Script.ps1

# Checks:
# ✓ Domain Admin member count
# ✓ Built-in Administrator status
# ✓ Guest account status
# ✓ Password policy strength
# ✓ AS-REP Roastable accounts
# ✓ Protected Users membership
# ✓ Stale Domain Admin accounts
```

---

## ⚔️ Attack and Defense Simulation

> ⚠️ All simulations performed in an isolated, offline lab environment for educational purposes only.

```
ATTACK SURFACE MAP

vertex.local domain
│
├── NETWORK LEVEL
│   ├── [ATTACK]  LLMNR/NBT-NS Poisoning → capture NTLMv2 hashes
│   └── [DEFENSE] GPO disables LLMNR + firewall blocks UDP 137/138
│
├── AUTHENTICATION LEVEL
│   ├── [ATTACK]  Password Spray → 1 password × many accounts
│   ├── [DETECT]  Event 4625 — multiple accounts, same source IP
│   └── [DEFENSE] GPO enforces lockout after 5 attempts
│
├── KERBEROS LEVEL
│   ├── [ATTACK]  Kerberoasting → offline crack service ticket
│   ├── [DETECT]  Event 4769 RC4 encryption requests
│   └── [DEFENSE] PSO-ServiceAccounts — 32 char min password
│
├── KERBEROS LEVEL
│   ├── [ATTACK]  AS-REP Roasting → no pre-auth accounts
│   ├── [DETECT]  DoesNotRequirePreAuth attribute audit
│   └── [DEFENSE] Pre-auth enforced on all accounts
│
└── DC LEVEL
    ├── [ATTACK]  DCSync → replicate all password hashes
    ├── [DETECT]  Event 4662 + Replication GUID check
    └── [DEFENSE] Replication rights ACL audit quarterly
```

---

## 📁 Repository Structure

```
ad-mastery/
│
├── README.md                                    ← This file
│
├── Phase 01 lab vm setup/                       [201 screenshots]
│   ├── 01-VirtualBox-Download/
│   ├── 02-HyperV-Installation/
│   ├── 03-Windows-Server-ISO-Download/
│   ├── 04-VM-Creation-And-ISO-Mount/
│   ├── 05-Virtual-Network-Creation/
│   ├── 06-DC-Network-Adapter-Configuration/
│   ├── 07-DC1-Installation/
│   ├── 08-DC1-Rename-And-DNS-Configuration/
│   ├── 09-DC2-Installation/
│   ├── 10-DC2-Rename-And-DNS-Configuration/
│   ├── 11-CLIENT1-Installation/
│   └── 12-CLIENT1-Rename-And-DNS-Configuration/
│
├── Phase 02 lab install ad/                     [228 screenshots]
│   ├── 01-DC1-ADDS-Role-Installation/
│   ├── 02-DC1-Promote-To-Domain-Controller/
│   ├── 03-Active-Directory-Users-And-Computers/
│   ├── 04-Vertex-OU-Structure-Creation/
│   ├── 05-London-HQ-Users-Groups-And-Computers/
│   ├── 06-Security-Groups-And-Servers/
│   ├── 07-Active-Directory-Sites-And-Services/
│   ├── 08-DC2-Domain-Join/
│   ├── 09-Client1-Domain-Connectivity-Verification/
│   ├── 10-DC2-ADDS-Role-Installation/
│   └── 11-DC2-Promote-To-Additional-Domain-Controller/
│
├── Phase 03 lab users computers/                [107 screenshots]
│   ├── 01-Manual-User-Provisioning/
│   ├── 02-Service-Account-Provisioning/
│   ├── 03-Client1-Domain-Administrator-Login/
│   ├── 04-Computer-Object-OU-Migration/
│   ├── 05-Client1-Computername-Modification/
│   ├── 06-Bulk-User-Provisioning-via-CSV/
│   └── 07-Active-Directory-User-Count-Verification/
│
├── Phase 04 lab dns/                            [80 screenshots]
│   ├── 01-OPEN DNS MANAGER AND EXPLORE.../
│   ├── 02-CREATE THE REVERSE LOOKUP ZONE/
│   ├── 03-Create-PTR-Records/
│   ├── 04-CONFIGURE FORWARDERS/
│   ├── 05-CREATE A CNAME ALIAS RECORD/
│   ├── 06-CREATE A CONDITIONAL FORWARDER/
│   ├── 07-TEST ALL DNS WITH NSLOOKUP/
│   ├── 08-DNS-Health-Verification/
│   └── 09-TEST DNS FROM CLIENT1/
│
├── Phase 05 lab groups agdl/                    [146 screenshots]
│   ├── 01-CREATE GLOBAL SECURITY GROUPS/
│   ├── 02-CREATE DOMAIN LOCAL GROUPS/
│   ├── 03-CREATE DISTRIBUTION GROUPS/
│   └── 04-APPLY DL GROUP TO A FILE SHARE/
│
├── Phase 06 lab group policy/                   [188 screenshots]
│   ├── 01-OPEN GROUP POLICY MANAGEMENT CONSOLE/
│   ├── 02-GPO 2 FINANCE SECURITY POLICY/
│   ├── 03-GPO 3 IT ADMIN POLICY/
│   ├── 04-GPO 4 DESKTOP POLICY/
│   ├── 05-GPO 5 AUDIT POLICY/
│   ├── 06-GPO 6 LOOPBACK (OPERATIONS SHARED PCS)/
│   └── 07-ENFORCE BASE POLICY AND TEST/
│
├── Phase 07 lab domaincontrollers fsmo/         [91 screenshots]
│   ├── 01-FSMO ROLES/
│   ├── 02-VERIFY REPLICATION/
│   ├── 03-EXPLORE SYSVOL AND NTDS/
│   └── 04-CREATE SITES AND SITE LINKS/
│
├── Phase 08 lab ad security/                    [186 screenshots]
│   ├── 01-TIERING ADMIN ACCOUNTS/
│   ├── 02-DELEGATE PASSWORD RESET TO HELPDESK/
│   ├── 03-LAPS (LOCAL ADMINISTRATOR PASSWORD SOLUTION)/
│   ├── 04-PROTECTED USERS GROUP/
│   ├── 05-FINE-GRAINED PASSWORD POLICIES (PSO)/
│   └── 06-SECURITY AUDIT EVENT VERIFICATION/
│
├── Phase 09 lab kerberos/                       [74 screenshots]
│   ├── 01-OBSERVE KERBEROS TICKETS WITH KLIST/
│   ├── 02-MANAGE SPNs (SERVICE PRINCIPAL NAMES)/
│   ├── 03-VERIFY TIME SYNCHRONIZATION/
│   ├── 04-ENABLE AES ENCRYPTION ON IMPORTANT ACCOUNTS/
│   ├── 05-CONFIGURE KERBEROS CONSTRAINED DELEGATION/
│   └── 06-LOOK AT KERBEROS EVENTS IN EVENT VIEWER/
│
├── Phase 10 lab ldap/                           [77 screenshots]
│   ├── 01-CONNECT TO AD USING LDP.EXE/
│   ├── 02-RUN LDAP SEARCH QUERIES/
│   ├── 03-MODIFY AN ATTRIBUTE WITH LDP/
│   ├── 04-INSTALL AND USE ADEXPLORER/
│   ├── 05-LDAP QUERIES WITH POWERSHELL/
│   └── 06-CONNECT WITH LDAPS (SECURE LDAP, PORT 636)/
│
├── Phase 11 lab enterprise Design/              [92 screenshots]
│   ├── 01-REVIEW DC PLACEMENT AND TOPOLOGY/
│   ├── 02-DNS SCAVENGING (MAINTENANCE)/
│   ├── 03-WINDOWS SERVER BACKUP (DISASTER RECOVERY)/
│   ├── 04-ENABLE AD RECYCLE BIN/
│   └── 05-CHECK DOMAIN HEALTH AND CAPACITY/
│
├── Phase 12 lab powershell ad/                  [48 screenshots]
│   ├── 01-PREPARE THE SCRIPTS FOLDER/
│   ├── 02-User-Management-Script/
│   ├── 03-Group-Management-Script/
│   ├── 04-Reporting-Script/
│   ├── 05-JML-Automation-Script/
│   └── 06-Security-Audit-Script/
│
└── Phase 13 lab ad attacks & Defense/           [63 screenshots]
    ├── 01-DISABLE LLMNR AND NBT-NS (Quick Win Defense)/
    ├── 02-SIMULATE AND DETECT PASSWORD SPRAYING/
    ├── 03-KERBEROASTING SIMULATION AND DEFENSE/
    ├── 04-AS-REP ROASTING (NO PRE-AUTH ACCOUNTS)/
    ├── 05-DCSync-Detection-And-Analysis/
    └── 06-VERIFY YOUR DEFENSES ARE WORKING/
```

---

## 🏆 Key Outcomes

### Technical Competencies Achieved

| Competency | Proficiency |
|-----------|-------------|
| AD DS Installation and Promotion | ★★★★★ |
| OU Design for Enterprise | ★★★★★ |
| User and Group Lifecycle Management | ★★★★★ |
| DNS for Active Directory | ★★★★★ |
| Group Policy Design and Troubleshooting | ★★★★★ |
| FSMO Roles and Replication | ★★★★☆ |
| AD Security Hardening | ★★★★★ |
| Kerberos Authentication | ★★★★☆ |
| LDAP Querying | ★★★★☆ |
| PowerShell Automation | ★★★★★ |
| AD Attack and Defense | ★★★★☆ |

### Key Lessons Learned

> **DNS is the foundation of everything.** Every AD failure scenario traced back to DNS. Understanding SRV records and the DC locator process is non-negotiable.

> **AGDLP scales to any size.** Adding a new resource requires creating one DL group. Adding a new user requires adding to one Global group. Two operations, any scale.

> **Tiering prevents the most common attack pattern.** Lateral movement via credential theft is stopped entirely when Tier 0 credentials never touch Tier 2 machines.

> **PowerShell is not optional.** Even in a 3-VM lab, the number of objects is too high for pure GUI management. Real enterprise environments are managed through scripted automation.

> **Attackers understand AD better than most defenders.** BloodHound reveals paths that look safe from the GUI but represent real, exploitable attack chains. Running attacker tools against your own environment is the most honest security assessment you can do.

---

## 🚀 Future Improvements

| Feature | Description |
|---------|-------------|
| **Hybrid Identity** | Microsoft Entra ID + Azure AD Connect + Password Hash Sync + Conditional Access + MFA |
| **AD CS (PKI)** | Internal Certificate Authority for LDAPS enforcement and certificate-based authentication |
| **Microsoft Defender for Identity** | Cloud-based detection of AD attacks using DC signals |
| **SIEM Integration** | Forward AD security events to Splunk or Microsoft Sentinel |
| **Privileged Access Workstations** | Hardened admin workstations for Tier 0 operations |
| **gMSA Migration** | Replace traditional service accounts with Group Managed Service Accounts |
| **Branch DC Deployment** | Deploy read-only DCs (RODCs) for Mumbai, Berlin, New York branch sites |
| **ADFS** | Active Directory Federation Services for SAML-based SSO |

---

## 📌 About This Project

This lab was built as part of a self-directed transition into **Identity and Access Management (IAM)**, targeting IAM Analyst and Active Directory Administrator roles in the enterprise technology sector, specifically the German market (Munich).

Every technology covered maps directly to what IAM employers require:

| Lab Technology | IAM Job Relevance |
|---------------|-----------------|
| Active Directory | Core of on-premises identity for 90%+ of enterprises |
| LDAP | The protocol every IAM platform uses to connect to AD |
| Group Policy | Centralized access control enforcement |
| Kerberos | Enterprise authentication — every IAM engineer must know this |
| PowerShell + JML | Daily work of an IAM Analyst |
| AGDLP Groups | RBAC model implementation |
| Security Auditing | Compliance and governance evidence |
| Attack Defense | SOC analyst and IAM security awareness |

---

<div align="center">

**Built with** Oracle VirtualBox · Windows Server 2022 · PowerShell · Active Directory

*13 Phases · 1,581 Screenshots · 1 Complete Enterprise AD Environment*

</div>
