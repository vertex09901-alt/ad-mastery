# Phase 01 — Lab VM Setup

> Build the entire virtual infrastructure from scratch: download VirtualBox, install Windows Server on two domain controllers and a Windows 11 client, configure networking, and verify connectivity before any Active Directory work begins.

---

## Steps

### 01 — VirtualBox Download
Downloaded Oracle VirtualBox 5.2 for Windows hosts from the official VirtualBox website.

![VirtualBox Download](<01-VirtualBox-Download/vbox-download- (1).png>)

---

### 02 — Hyper-V Installation Check
Verified and configured Hyper-V / hardware virtualisation settings to ensure VirtualBox can run 64-bit guest VMs.

**Screenshots:** `02-HyperV-Installation/` (5 images)

---

### 03 — Windows Server ISO Download
Downloaded the Windows Server 2022 evaluation ISO from Microsoft's official evaluation centre.

**Screenshots:** `03-Windows-Server-ISO-Download/` (3 images)

---

### 04 — VM Creation & ISO Mount
Created the DC1 VM in VirtualBox with the following configuration and mounted the Windows Server ISO:

- CPU: 2 cores
- RAM: 2048 MB
- Storage: 50 GB VDI (dynamically allocated)
- Network: Internal Network (`CorpNet`)

**Screenshots:** `04-VM-Creation-And-ISO-Mount/` (15 images)

---

### 05 — Virtual Network Creation
Created a dedicated internal VirtualBox network (`CorpNet`) to isolate all lab machines from the host's internet connection while allowing VM-to-VM communication.

**Screenshots:** `05-Virtual-Network-Creation/` (8 images)

---

### 06 — DC Network Adapter Configuration
Configured each Domain Controller with two NICs:
- **Adapter 1:** Internal Network (`CorpNet`) — for domain communication
- **Adapter 2:** NAT — for internet access during setup

**Screenshots:** `06-DC-Network-Adapter-Configuration/` (19 images)

---

### 07 — DC1 Installation
Performed a clean Windows Server 2022 installation on DC1 including:
- Boot from ISO
- Partition setup
- Windows Server 2022 Standard (Desktop Experience) selection
- Initial administrator password configuration

**Screenshots:** `07-DC1-Installation/` (37 images)

---

### 08 — DC1 Rename & DNS Configuration
After OS installation:
- Renamed the server to `DC1`
- Set a static IP address
- Pointed DNS to `127.0.0.1` (loopback, pre-AD DS)
- Configured the network adapter for the domain

**Screenshots:** `08-DC1-Rename-And-DNS-Configuration/` (13+ images)

---

### 09 — DC2 Installation
Repeated the Windows Server 2022 installation process for the second Domain Controller (DC2).

**Screenshots:** `09-DC2-Installation/`

---

### 10 — DC2 Rename & DNS Configuration
- Renamed to `DC2`
- Set a static IP pointing DNS to DC1's IP address

**Screenshots:** `10-DC2-Rename-And-DNS-Configuration/`

---

### 11 — CLIENT1 Installation
Installed Windows 11 Pro on CLIENT1, the domain-joined workstation used for user logon testing, Group Policy validation, and security exercises.

**Screenshots:** `11-CLIENT1-Installation/`

---

### 12 — CLIENT1 Rename & DNS Configuration
- Renamed to `CLIENT1`
- Set DNS to point to DC1's IP address
- Verified network connectivity (ping DC1)

**Screenshots:** `12-CLIENT1-Rename-And-DNS-Configuration/`

---

## Key Concepts

- VirtualBox internal networking isolates the lab from the host
- Static IPs are mandatory for Domain Controllers — DHCP can't be used for DCs
- DNS must point to the DC before a domain join can succeed
- Two NICs on DCs allow internet access for Windows Update while keeping domain traffic on the internal network

---

## Tools Used

`Oracle VirtualBox 5.2` · `Windows Server 2022` · `Windows 11 Pro`

---

*Next: [Phase 02 — Install Active Directory](<../Phase 02 lab install ad/README.md>)*
