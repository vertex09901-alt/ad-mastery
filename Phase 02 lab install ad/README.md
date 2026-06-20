# Phase 02 — Install Active Directory

> Install the AD DS role on DC1, create the `vertex.local` forest, build an enterprise OU structure, join CLIENT1 and DC2 to the domain, and promote DC2 as an additional domain controller.

---

## Steps

### 01 — DC1: Install AD DS Role
Opened Server Manager on DC1 and used **Add Roles and Features** to install the **Active Directory Domain Services** role.

![Server Manager — Installing AD DS](<01-DC1-ADDS-Role-Installation/ADDS-Role-Installation- (1).png>)

**Screenshots:** `01-DC1-ADDS-Role-Installation/`

---

### 02 — DC1: Promote to Domain Controller
After the role installed, ran the **Active Directory Domain Services Configuration Wizard** to:
- Create a **new forest**
- Set the domain name: `vertex.local`
- Set the Forest Functional Level and Domain Functional Level
- Configure DNS integration
- Set the DSRM (Directory Services Restore Mode) password
- Complete promotion and automatic reboot

**Screenshots:** `02-DC1-Promote-To-Domain-Controller/`

---

### 03 — Active Directory Users and Computers
Explored the default AD structure after promotion:
- Default containers: `Builtin`, `Computers`, `Domain Controllers`, `Users`
- Verified DC1 appeared in the **Domain Controllers** OU
- Explored default security groups (Domain Admins, Enterprise Admins, etc.)

**Screenshots:** `03-Active-Directory-Users-And-Computers/`

---

### 04 — Vertex OU Structure Creation
Designed and created the enterprise Organizational Unit hierarchy to mirror a real company structure:

```
vertex.local
├── London HQ
│   ├── IT
│   ├── HR
│   ├── Finance
│   ├── Sales
│   ├── Operations
│   └── Management
├── Servers
│   ├── Domain Controllers
│   └── Member Servers
└── Workstations
```

**Screenshots:** `04-Vertex-OU-Structure-Creation/` (12 images)

---

### 05 — London HQ Users, Groups & Computers
Created initial user accounts and computer objects under the `London HQ` OU structure to populate the directory.

**Screenshots:** `05-London-HQ-Users-Groups-And-Computers/`

---

### 06 — Security Groups & Servers
Created department-level security groups and registered server objects in Active Directory.

**Screenshots:** `06-Security-Groups-And-Servers/`

---

### 07 — Active Directory Sites and Services
Opened **AD Sites and Services** to verify the default site (`Default-First-Site-Name`) and understand how sites map to physical network locations.

**Screenshots:** `07-Active-Directory-Sites-And-Services/`

---

### 08 — DC2 Domain Join
Joined DC2 to the `vertex.local` domain as a member server before promoting it to an additional Domain Controller.

**Screenshots:** `08-DC2-Domain-Join/`

---

### 09 — CLIENT1 Domain Connectivity Verification
Joined CLIENT1 to the `vertex.local` domain and verified:
- Successful domain join
- DNS resolution of `vertex.local`
- Connectivity to DC1

**Screenshots:** `09-Client1-Domain-Connectivity-Verification/`

---

### 10 — DC2: Install AD DS Role
Installed the Active Directory Domain Services role on DC2 via Server Manager, same process as DC1.

![Server Manager on DC2 — AD DS and DNS roles installed](<10-DC2-ADDS-Role-Installation/DC2-ADDS-Role-Installation- (1).png>)

**Screenshots:** `10-DC2-ADDS-Role-Installation/`

---

### 11 — DC2: Promote to Additional Domain Controller
Ran the AD DS Configuration Wizard on DC2 to:
- Add it as an additional DC in the existing `vertex.local` domain
- Enable **Global Catalog**
- Configure DNS replication
- Complete promotion — DC2 now replicates all AD data from DC1

**Screenshots:** `11-DC2-Promote-To-Additional-Domain-Controller/`

---

## Key Concepts

- The first DC creates the **forest root domain** — a critical, irreversible decision
- `vertex.local` uses a `.local` suffix (non-routable, lab-appropriate)
- OU design should reflect your company's structure and delegation model
- A second DC provides fault tolerance — if DC1 goes down, DC2 can authenticate users
- **Global Catalog** on DC2 enables universal group membership lookups from any DC

---

## Tools Used

`Server Manager` · `Active Directory Domain Services Configuration Wizard` · `Active Directory Users and Computers` · `Active Directory Sites and Services`

---

*Previous: [Phase 01 — Lab VM Setup](<../Phase 01 lab vm setup/README.md>) · Next: [Phase 03 — Users & Computers](<../Phase 03 lab users computers/README.md>)*
