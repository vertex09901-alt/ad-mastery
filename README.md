# 🏢 AD Mastery — Enterprise Active Directory Lab

## Complete 13-Phase Active Directory Lab with 1,581 Screenshots

> A comprehensive, screenshot-documented enterprise Active Directory lab built from scratch using Oracle VirtualBox. This project covers everything from VM setup to attack simulation and defense, with every single step captured in screenshots with red arrows and boxes for easy navigation.

---

## 🖥️ Lab Environment

| Component | Details |
|-----------|---------|
| **Hypervisor** | Oracle VirtualBox |
| **Domain Name** | `vertex.local` |
| **Forest Level** | Windows Server 2025 |
| **DC1 (Primary)** | Windows Server 2025 — `192.168.10.10` |
| **DC2 (Secondary)** | Windows Server 2025 — `192.168.10.11` |
| **CLIENT1 (Workstation)** | Windows 10 Pro — `192.168.10.50` |
| **Network** | Internal Network `192.168.10.0/24` + NAT for internet |

## 🏗️ OU Structure

```
vertex.local
└── VERTEX
    ├── HQ-London
    │   ├── IT           (Users, Groups, Computers)
    │   ├── Finance      (Users, Groups, Computers)
    │   ├── HR           (Users, Groups, Computers)
    │   ├── Security     (Users, Groups, Computers)
    │   ├── Development  (Users, Groups, Computers)
    │   ├── Operations   (Users, Groups, Computers)
    │   ├── Helpdesk     (Users, Groups, Computers)
    │   └── Executive    (Users, Groups, Computers)
    ├── Branch-Mumbai
    ├── Branch-Dubai
    └── Branch-Singapore
```

---

## 📚 Phase Guide

### 🖥️ [Phase 01 — Lab VM Setup](Phase%2001%20lab%20vm%20setup/README.md)
> Download VirtualBox, create virtual machines for DC1, DC2, and CLIENT1, configure internal networking, install Windows Server 2025 and Windows 10 Pro, assign static IPs, and rename each machine.
>
> **📸 201 screenshots** | 
> **Sections:** Step 1 — Download & Install VirtualBox → Step 2 — Disable Hyper-V (Required for VirtualBox) → Step 3 — Download Windows Server ISO → Step 4 — Create VMs & Mount ISO → Step 5 — Create Virtual Network → ...

### 🏗️ [Phase 02 — Install Active Directory](Phase%2002%20lab%20install%20ad/README.md)
> Install the AD DS role on DC1, promote it to the first domain controller of the `vertex.local` forest, create the full OU structure (VERTEX → HQ-London, Branch-Mumbai, Branch-Dubai, Branch-Singapore), join DC2 and CLIENT1 to the domain, and promote DC2 as an additional domain controller.
>
> **📸 228 screenshots** | 
> **Sections:** Step 1 — Install AD DS Role on DC1 → Step 2 — Promote DC1 to Domain Controller → Step 3 — Open Active Directory Users & Computers → Step 4 — Create the Vertex OU Structure → Step 5 — Create London HQ Users, Groups & Computers OUs → ...

### 👥 [Phase 03 — Users & Computers](Phase%2003%20lab%20users%20computers/README.md)
> Manually create domain users, provision service accounts, log into CLIENT1 with domain admin credentials, move computer objects to proper OUs, rename CLIENT1, bulk-create users via CSV + PowerShell, and verify user counts.
>
> **📸 107 screenshots** | 
> **Sections:** Step 1 — Manual User Provisioning → Step 2 — Service Account Provisioning → Step 3 — Log into CLIENT1 as Domain Admin → Step 4 — Move Computer Objects to Correct OUs → Step 5 — Modify CLIENT1 Computer Name → ...

### 🌐 [Phase 04 — DNS Configuration](Phase%2004%20lab%20dns/README.md)
> Explore auto-created DNS zones, create reverse lookup zones and PTR records, configure forwarders, create CNAME alias records, set up conditional forwarders, test DNS resolution with nslookup, verify DNS health, and test from CLIENT1.
>
> **📸 80 screenshots** | 
> **Sections:** Step 1 — Open DNS Manager & Explore Auto-Created Zones → Step 2 — Create the Reverse Lookup Zone → Step 3 — Create PTR Records → Step 4 — Configure DNS Forwarders → Step 5 — Create a CNAME Alias Record → ...

### 👫 [Phase 05 — Groups & AGDLP](Phase%2005%20lab%20groups%20agdl/README.md)
> Create Global Security groups for each department, create Domain Local groups for resource access, create Distribution groups for email, and implement AGDLP (Account → Global → Domain Local → Permission) on a shared folder.
>
> **📸 146 screenshots** | 
> **Sections:** Step 1 — Create Global Security Groups → Step 2 — Create Domain Local Groups → Step 3 — Create Distribution Groups → Step 4 — Apply AGDLP to a File Share

### 📋 [Phase 06 — Group Policy](Phase%2006%20lab%20group%20policy/README.md)
> Open GPMC, create and link GPOs: Base Security Policy, Finance Security Policy, IT Admin Policy, Desktop Policy, Audit Policy, and Loopback Processing for shared PCs. Enforce base policy and test with gpresult.
>
> **📸 188 screenshots** | 
> **Sections:** Step 1 — Open GPMC & Create Base Security GPO → Step 2 — GPO: Finance Security Policy → Step 3 — GPO: IT Admin Policy → Step 4 — GPO: Desktop Policy → Step 5 — GPO: Audit Policy → ...

### 🔄 [Phase 07 — Domain Controllers & FSMO](Phase%2007%20lab%20domaincontrollers%20fsmo/README.md)
> Identify and verify FSMO role holders, verify AD replication between DC1 and DC2, explore SYSVOL and NTDS folders, and create AD Sites and Site Links for topology management.
>
> **📸 91 screenshots** | 
> **Sections:** Step 1 — Identify FSMO Role Holders → Step 2 — Verify AD Replication → Step 3 — Explore SYSVOL & NTDS → Step 4 — Create Sites & Site Links

### 🔒 [Phase 08 — AD Security Hardening](Phase%2008%20lab%20ad%20security/README.md)
> Implement admin tiering (Tier 0/1/2 accounts), delegate password reset to Helpdesk, deploy LAPS for local admin passwords, configure Protected Users group, create Fine-Grained Password Policies (PSOs), and verify security audit events.
>
> **📸 186 screenshots** | 
> **Sections:** Step 1 — Implement Admin Tiering → Step 2 — Delegate Password Reset to Helpdesk → Step 3 — Deploy LAPS → Step 4 — Configure Protected Users Group → Step 5 — Create Fine-Grained Password Policies → ...

### 🎟️ [Phase 09 — Kerberos Authentication](Phase%2009%20lab%20kerberos/README.md)
> Observe Kerberos tickets with klist, manage SPNs (Service Principal Names), verify time synchronization (critical for Kerberos), enable AES-256 encryption on important accounts, configure Kerberos Constrained Delegation, and review Kerberos events in Event Viewer.
>
> **📸 74 screenshots** | 
> **Sections:** Step 1 — Observe Kerberos Tickets with klist → Step 2 — Manage SPNs (Service Principal Names) → Step 3 — Verify Time Synchronization → Step 4 — Enable AES-256 Encryption → Step 5 — Configure Kerberos Constrained Delegation → ...

### 📂 [Phase 10 — LDAP Operations](Phase%2010%20lab%20ldap/README.md)
> Connect to AD using LDP.exe, run LDAP search queries with filters, modify attributes via LDP, install and explore AD with Sysinternals ADExplorer, run LDAP queries with PowerShell, and connect using LDAPS (Secure LDAP, port 636).
>
> **📸 77 screenshots** | 
> **Sections:** Step 1 — Connect to AD Using LDP.exe → Step 2 — Run LDAP Search Queries → Step 3 — Modify an Attribute with LDP → Step 4 — Install & Use Sysinternals ADExplorer → Step 5 — LDAP Queries with PowerShell → ...

### 🏢 [Phase 11 — Enterprise Design & Disaster Recovery](Phase%2011%20lab%20enterprise%20Design/README.md)
> Review DC placement and site topology, configure DNS scavenging for stale record cleanup, set up Windows Server Backup for disaster recovery, enable the AD Recycle Bin for deleted object recovery, and check domain health and capacity.
>
> **📸 92 screenshots** | 
> **Sections:** Step 1 — Review DC Placement & Topology → Step 2 — Configure DNS Scavenging → Step 3 — Windows Server Backup → Step 4 — Enable AD Recycle Bin → Step 5 — Check Domain Health & Capacity

### ⚡ [Phase 12 — PowerShell AD Automation](Phase%2012%20lab%20powershell%20ad/README.md)
> Prepare a scripts folder, create PowerShell scripts for user management, group management, AD reporting, JML (Joiner-Mover-Leaver) automation, and security auditing.
>
> **📸 48 screenshots** | 
> **Sections:** Step 1 — Prepare the Scripts Folder → Step 2 — User Management Script → Step 3 — Group Management Script → Step 4 — AD Reporting Script → Step 5 — JML (Joiner-Mover-Leaver) Automation → ...

### 🛡️ [Phase 13 — AD Attacks & Defense](Phase%2013%20lab%20ad%20attacks%20%26%20Defense/README.md)
> Disable LLMNR and NBT-NS as quick-win defenses, simulate and detect password spraying attacks, perform Kerberoasting simulation and defense, test AS-REP Roasting on accounts without pre-authentication, detect DCSync attacks, and verify all defenses are working.
>
> **📸 63 screenshots** | 
> **Sections:** Step 1 — Disable LLMNR & NBT-NS → Step 2 — Simulate & Detect Password Spraying → Step 3 — Kerberoasting Simulation & Defense → Step 4 — AS-REP Roasting Detection → Step 5 — DCSync Detection & Analysis → ...

---

## 🛠️ Technologies & Tools Used

| Category | Tools |
|----------|-------|
| **Virtualization** | Oracle VirtualBox |
| **Server OS** | Windows Server 2025 Standard Evaluation |
| **Client OS** | Windows 10 Pro |
| **Directory Services** | Active Directory Domain Services (AD DS) |
| **DNS** | Microsoft DNS (AD-integrated) |
| **Group Policy** | GPMC, GPO Editor |
| **Security Tools** | LAPS, PSO, Protected Users, Audit Policy |
| **Protocol Analysis** | LDP.exe, ADExplorer (Sysinternals), klist |
| **Automation** | PowerShell, CSV bulk operations |
| **Monitoring** | Event Viewer, dcdiag, repadmin, nltest |

## 🎯 Skills Demonstrated

- Enterprise AD forest & domain design
- Multi-site topology with site links & replication
- OU hierarchy design following Microsoft best practices
- AGDLP group nesting model implementation
- Group Policy design and troubleshooting
- FSMO role management and transfer
- Admin tiering (Tier 0/1/2 security model)
- LAPS deployment for local admin password management
- Fine-Grained Password Policies (PSOs)
- Kerberos authentication deep-dive
- LDAP query construction and attribute modification
- Disaster recovery (Windows Server Backup, AD Recycle Bin)
- PowerShell automation for AD operations
- Attack simulation & defense (Password Spraying, Kerberoasting, AS-REP Roasting, DCSync)

---

## 📄 License

This project is for educational purposes. All lab work was performed in an isolated virtual environment.

## 👤 Author

**Mohammed Riyan Ahmed*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat&logo=linkedin)]()
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black?style=flat&logo=github)])
