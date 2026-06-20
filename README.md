# 🏛️ AD Mastery — Enterprise Active Directory Lab

> A complete, hands-on enterprise Active Directory lab built inside Oracle VirtualBox to simulate a real corporate Windows environment. Every phase is documented with step-by-step screenshots.

---

## Lab Environment

| Component | Details |
|-----------|---------|
| Hypervisor | Oracle VirtualBox |
| Domain | `vertex.local` |
| DC1 | Primary Domain Controller — AD DS, DNS, FSMO Roles |
| DC2 | Additional Domain Controller — Replication, Global Catalog |
| CLIENT1 | Windows 11 domain-joined workstation |

---

## 📋 Phases

| # | Phase | Topics Covered | Screenshots |
|---|-------|---------------|-------------|
| 01 | [Lab VM Setup](<Phase 01 lab vm setup/README.md>) | VirtualBox, Windows Server ISO, VM creation, networking, DC1/DC2/CLIENT1 install | 201 |
| 02 | [Install Active Directory](<Phase 02 lab install ad/README.md>) | AD DS role, forest creation, OU structure, DC2 promotion, domain join | 228 |
| 03 | [Users & Computers](<Phase 03 lab users computers/README.md>) | Manual & bulk user provisioning, service accounts, computer objects | 107 |
| 04 | [DNS Configuration](<Phase 04 lab dns/README.md>) | Reverse lookup zones, PTR records, forwarders, CNAME, NSLOOKUP testing | 80 |
| 05 | [Groups & AGDLP](<Phase 05 lab groups agdl/README.md>) | Global groups, Domain Local groups, distribution groups, file share permissions | 146 |
| 06 | [Group Policy](<Phase 06 lab group policy/README.md>) | Password policy, desktop restrictions, audit policy, loopback processing | 188 |
| 07 | [Domain Controllers & FSMO](<Phase 07 lab domaincontrollers fsmo/README.md>) | FSMO roles, AD replication, SYSVOL/NTDS, AD Sites & Services | 91 |
| 08 | [AD Security](<Phase 08 lab ad security/README.md>) | Admin tiering, LAPS, delegation, Protected Users, Fine-Grained Password Policies | 186 |
| 09 | [Kerberos](<Phase 09 lab kerberos/README.md>) | klist tickets, SPNs, AES encryption, constrained delegation, Event Viewer | 74 |
| 10 | [LDAP](<Phase 10 lab ldap/README.md>) | LDP.exe, LDAP queries, attribute modification, ADExplorer, LDAPS (port 636) | 77 |
| 11 | [Enterprise Design](<Phase 11 lab enterprise Design/README.md>) | DC placement, DNS scavenging, Windows Server Backup, AD Recycle Bin, health checks | 92 |
| 12 | [PowerShell Automation](<Phase 12 lab powershell ad/README.md>) | User/group management scripts, reporting, JML automation, security audit | 48 |
| 13 | [AD Attacks & Defense](<Phase 13 lab ad attacks & Defense/README.md>) | LLMNR/NBT-NS disable, password spraying, Kerberoasting, AS-REP roasting, DCSync | 63 |

**Total: 1,581 screenshots across all phases**

---

## Skills Demonstrated

**Identity & Access Management** — Active Directory, RBAC, AGDLP, delegation, service accounts

**Infrastructure** — Windows Server, DNS, multi-DC environments, AD replication, Sites & Services

**Security Hardening** — Admin tiering, LAPS, Protected Users, Fine-Grained Password Policies, audit logging

**Attack & Defense** — LLMNR poisoning defense, Kerberoasting simulation, AS-REP roasting, DCSync detection

**Automation** — PowerShell scripting for user lifecycle management, bulk provisioning, security auditing

**Virtualization** — Oracle VirtualBox, virtual networking, multi-VM infrastructure

---

## Who This Lab Prepares You For

- Windows System Administrator
- Identity & Access Management (IAM) Analyst
- IT Support Engineer
- Infrastructure / Security Operations

---

*Built June 2026 · Domain: `vertex.local` · Hypervisor: Oracle VirtualBox*
