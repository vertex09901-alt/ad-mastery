# 🖥️ Phase 01 — Lab VM Setup

> **Download VirtualBox, create virtual machines for DC1, DC2, and CLIENT1, configure internal networking, install Windows Server 2025 and Windows 10 Pro, assign static IPs, and rename each machine.**

**Prerequisites:** Host machine with 16 GB+ RAM, VirtualBox installer, Windows Server 2025 ISO, Windows 10 Pro ISO.

### Network Configuration

| Machine  | Role                     | IP Address      | Subnet          | DNS Server     |
|----------|--------------------------|-----------------|-----------------|----------------|
| DC1      | Primary Domain Controller| 192.168.10.10   | 255.255.255.0   | 192.168.10.10  |
| DC2      | Secondary Domain Controller | 192.168.10.11 | 255.255.255.0  | 192.168.10.10  |
| CLIENT1  | Domain Workstation       | 192.168.10.50   | 255.255.255.0   | 192.168.10.10  |


---
## 📑 Table of Contents

- [Step 1 — Download & Install VirtualBox](#step-1-download-install-virtualbox)
- [Step 2 — Disable Hyper-V (Required for VirtualBox)](#step-2-disable-hyper-v-required-for-virtualbox)
- [Step 3 — Download Windows Server ISO](#step-3-download-windows-server-iso)
- [Step 4 — Create VMs & Mount ISO](#step-4-create-vms-mount-iso)
- [Step 5 — Create Virtual Network](#step-5-create-virtual-network)
- [Step 6 — Configure DC Network Adapters](#step-6-configure-dc-network-adapters)
- [Step 7 — Install Windows Server 2025 on DC1](#step-7-install-windows-server-2025-on-dc1)
- [Step 8 — Rename DC1 & Configure Static IP](#step-8-rename-dc1-configure-static-ip)
- [Step 9 — Install Windows Server 2025 on DC2](#step-9-install-windows-server-2025-on-dc2)
- [Step 10 — Rename DC2 & Configure Static IP](#step-10-rename-dc2-configure-static-ip)
- [Step 11 — Install Windows 10 Pro on CLIENT1](#step-11-install-windows-10-pro-on-client1)
- [Step 12 — Rename CLIENT1 & Configure Static IP](#step-12-rename-client1-configure-static-ip)

---

## Step 1 — Download & Install VirtualBox

Download Oracle VirtualBox from the official website and install it on the host machine. VirtualBox will serve as the hypervisor for all lab VMs.

### Screenshot 1

![Step 1 — Download & Install VirtualBox - Screenshot 1](01-VirtualBox-Download/vbox-download-%20%281%29.png)

**Navigate to the VirtualBox downloads page. Click **Windows hosts** (red arrow) to download the installer.**

### Screenshot 2

![Step 1 — Download & Install VirtualBox - Screenshot 2](01-VirtualBox-Download/vbox-download-%20%282%29.png)

**The VirtualBox installer `.exe` file is downloading in the browser.**

### Screenshot 3

![Step 1 — Download & Install VirtualBox - Screenshot 3](01-VirtualBox-Download/vbox-download-%20%283%29.png)

**Run the VirtualBox installer — the setup wizard appears. Click **Next** to proceed.**

### Screenshot 4

![Step 1 — Download & Install VirtualBox - Screenshot 4](01-VirtualBox-Download/vbox-download-%20%284%29.png)

**Custom Setup screen — leave all checkboxes enabled (Start menu, Desktop shortcut, Quick Launch, File associations). Click **Next**.**

### Screenshot 5

![Step 1 — Download & Install VirtualBox - Screenshot 5](01-VirtualBox-Download/vbox-download-%20%285%29.png)

**Network interface warning — VirtualBox will install virtual network adapters. Click **Yes** to proceed.**

### Screenshot 6

![Step 1 — Download & Install VirtualBox - Screenshot 6](01-VirtualBox-Download/vbox-download-%20%286%29.png)

**Ready to install — click **Install** to begin the installation.**

### Screenshot 7

![Step 1 — Download & Install VirtualBox - Screenshot 7](01-VirtualBox-Download/vbox-download-%20%287%29.png)

**Installation complete — VirtualBox is now installed. Click **Finish** to launch VirtualBox Manager.**

---

## Step 2 — Disable Hyper-V (Required for VirtualBox)

Hyper-V must be disabled on Windows because it conflicts with VirtualBox's virtualization. Open Windows Features and uncheck Hyper-V.

### Screenshot 1

![Step 2 — Disable Hyper-V (Required for VirtualBox) - Screenshot 1](02-HyperV-Installation/HyperV-Installation-%20%281%29.png)

**From the Windows desktop (red arrow pointing to taskbar search), search for **Windows Features**.**

### Screenshot 2

![Step 2 — Disable Hyper-V (Required for VirtualBox) - Screenshot 2](02-HyperV-Installation/HyperV-Installation-%20%282%29.png)

**Type `windows fea` in the search bar → select **Turn Windows features on or off**.**

### Screenshot 3

![Step 2 — Disable Hyper-V (Required for VirtualBox) - Screenshot 3](02-HyperV-Installation/HyperV-Installation-%20%283%29.png)

**The Windows Features dialog opens — scroll down to find **Hyper-V** and ensure it is **unchecked**.**

### Screenshot 4

![Step 2 — Disable Hyper-V (Required for VirtualBox) - Screenshot 4](02-HyperV-Installation/HyperV-Installation-%20%284%29.png)

**Scroll further to find **Virtual Machine Platform** and **Windows Hypervisor Platform** — ensure both are **unchecked**.**

### Screenshot 5

![Step 2 — Disable Hyper-V (Required for VirtualBox) - Screenshot 5](02-HyperV-Installation/HyperV-Installation-%20%285%29.png)

**Click **OK** to apply changes, then **restart** the computer when prompted.**

---

## Step 3 — Download Windows Server ISO

Download the Windows Server 2025 evaluation ISO from Microsoft's Evaluation Center. This will be used for DC1 and DC2.

### Screenshot 1

![Step 3 — Download Windows Server ISO - Screenshot 1](03-Windows-Server-ISO-Download/ISO-Download-%20%281%29.png)

**Navigate to the Microsoft Evaluation Center and select **Windows Server 2025**. Click **Download the ISO**.**

### Screenshot 2

![Step 3 — Download Windows Server ISO - Screenshot 2](03-Windows-Server-ISO-Download/ISO-Download-%20%282%29.png)

**Fill in the registration form if required, then select the **ISO** download option and preferred language.**

### Screenshot 3

![Step 3 — Download Windows Server ISO - Screenshot 3](03-Windows-Server-ISO-Download/ISO-Download-%20%283%29.png)

**The Windows Server 2025 ISO file is downloading. Save it to a known location on your host machine.**

---

## Step 4 — Create VMs & Mount ISO

Create virtual machines in VirtualBox for DC1 (primary domain controller). Configure RAM, CPU, disk, and mount the Windows Server ISO.

### Screenshot 1

![Step 4 — Create VMs & Mount ISO - Screenshot 1](04-VM-Creation-And-ISO-Mount/VM-Creation-%20%281%29.png)

**Open VirtualBox Manager. Click **New** (red arrow) to create a new virtual machine. Existing VMs are visible in the sidebar.**

### Screenshot 2

![Step 4 — Create VMs & Mount ISO - Screenshot 2](04-VM-Creation-And-ISO-Mount/VM-Creation-%20%282%29.png)

**Enter the VM name as **DC1**, select **Type: Microsoft Windows**, **Version: Windows Server 2022 (64-bit)**. Click **Next**.**

### Screenshot 3

![Step 4 — Create VMs & Mount ISO - Screenshot 3](04-VM-Creation-And-ISO-Mount/VM-Creation-%20%283%29.png)

**Set **Base Memory** to **4096 MB** (4 GB) and **Processors** to **2**. Click **Next**.**

### Screenshot 4

![Step 4 — Create VMs & Mount ISO - Screenshot 4](04-VM-Creation-And-ISO-Mount/VM-Creation-%20%284%29.png)

**Create a virtual hard disk — select **Create a virtual hard disk now**, set size to **60 GB**. Click **Next**.**

### Screenshot 5

![Step 4 — Create VMs & Mount ISO - Screenshot 5](04-VM-Creation-And-ISO-Mount/VM-Creation-%20%285%29.png)

**Review the VM summary — Name: DC1, RAM: 4096 MB, Processors: 2, Disk: 60 GB. Click **Finish**.**

### Screenshot 6

![Step 4 — Create VMs & Mount ISO - Screenshot 6](04-VM-Creation-And-ISO-Mount/VM-Creation-%20%286%29.png)

**DC1 VM is created and appears in the VirtualBox sidebar. Select it and click **Settings**.**

### Screenshot 7

![Step 4 — Create VMs & Mount ISO - Screenshot 7](04-VM-Creation-And-ISO-Mount/VM-Creation-%20%287%29.png)

**In VM Settings → **Storage**, click the empty optical drive icon to mount the ISO.**

### Screenshot 8

![Step 4 — Create VMs & Mount ISO - Screenshot 8](04-VM-Creation-And-ISO-Mount/VM-Creation-%20%288%29.png)

**Click the disk icon and select **Choose a disk file** to browse for the Windows Server ISO.**

### Screenshot 9

![Step 4 — Create VMs & Mount ISO - Screenshot 9](04-VM-Creation-And-ISO-Mount/VM-Creation-%20%289%29.png)

**Navigate to the downloaded Windows Server 2025 ISO file and select it.**

### Screenshot 10

![Step 4 — Create VMs & Mount ISO - Screenshot 10](04-VM-Creation-And-ISO-Mount/VM-Creation-%20%2810%29.png)

**The ISO is now mounted in the optical drive. Click **OK** to save settings.**

### Screenshot 11

![Step 4 — Create VMs & Mount ISO - Screenshot 11](04-VM-Creation-And-ISO-Mount/VM-Creation-%20%2811%29.png)

**Repeat the VM creation for **DC2** — same settings as DC1 (4 GB RAM, 2 CPUs, 60 GB disk).**

### Screenshot 12

![Step 4 — Create VMs & Mount ISO - Screenshot 12](04-VM-Creation-And-ISO-Mount/VM-Creation-%20%2812%29.png)

**Create the **CLIENT1** VM — set Type to **Windows 10 (64-bit)**, 4 GB RAM, 2 CPUs, 50 GB disk.**

### Screenshot 13

![Step 4 — Create VMs & Mount ISO - Screenshot 13](04-VM-Creation-And-ISO-Mount/VM-Creation-%20%2813%29.png)

**Mount the Windows 10 Pro ISO on CLIENT1's optical drive.**

### Screenshot 14

![Step 4 — Create VMs & Mount ISO - Screenshot 14](04-VM-Creation-And-ISO-Mount/VM-Creation-%20%2814%29.png)

**All three VMs (DC1, DC2, CLIENT1) are now visible in VirtualBox Manager.**

### Screenshot 15

![Step 4 — Create VMs & Mount ISO - Screenshot 15](04-VM-Creation-And-ISO-Mount/VM-Creation-%20%2815%29.png)

**Final overview showing all VMs created with their configuration summaries.**

---

## Step 5 — Create Virtual Network

Create an Internal Network in VirtualBox so all three VMs can communicate on the same subnet (192.168.10.0/24) while remaining isolated from the host.

### Screenshot 1

![Step 5 — Create Virtual Network - Screenshot 1](05-Virtual-Network-Creation/Virtual-Network-Creation-%20%281%29.png)

**Open VirtualBox and view the DC1 VM details. Note the current network adapter configuration.**

### Screenshot 2

![Step 5 — Create Virtual Network - Screenshot 2](05-Virtual-Network-Creation/Virtual-Network-Creation-%20%282%29.png)

**Go to **File → Host Network Manager** or **Tools → Network** to manage virtual networks.**

### Screenshot 3

![Step 5 — Create Virtual Network - Screenshot 3](05-Virtual-Network-Creation/Virtual-Network-Creation-%20%283%29.png)

**Click **Create** to add a new Host-Only network adapter if needed.**

### Screenshot 4

![Step 5 — Create Virtual Network - Screenshot 4](05-Virtual-Network-Creation/Virtual-Network-Creation-%20%284%29.png)

**Configure the network adapter settings — set the IPv4 address and subnet for the host-only adapter.**

### Screenshot 5

![Step 5 — Create Virtual Network - Screenshot 5](05-Virtual-Network-Creation/Virtual-Network-Creation-%20%285%29.png)

**Configure the NAT Network if using dual adapters (one for internal communication, one for internet).**

### Screenshot 6

![Step 5 — Create Virtual Network - Screenshot 6](05-Virtual-Network-Creation/Virtual-Network-Creation-%20%286%29.png)

**Verify the network configuration — both Internal Network and NAT adapters should be visible.**

### Screenshot 7

![Step 5 — Create Virtual Network - Screenshot 7](05-Virtual-Network-Creation/Virtual-Network-Creation-%20%287%29.png)

**Apply the network settings and ensure the virtual network is active.**

### Screenshot 8

![Step 5 — Create Virtual Network - Screenshot 8](05-Virtual-Network-Creation/Virtual-Network-Creation-%20%288%29.png)

**Network creation complete — all VMs will use this network for inter-VM communication.**

---

## Step 6 — Configure DC Network Adapters

Configure dual network adapters on DC1 and DC2: Adapter 1 as Internal Network (for domain traffic at 192.168.10.x) and Adapter 2 as NAT (for internet access).

### Screenshot 1

![Step 6 — Configure DC Network Adapters - Screenshot 1](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%281%29.png)

**Select DC1 in VirtualBox → click **Settings** → navigate to **Network**.**

### Screenshot 2

![Step 6 — Configure DC Network Adapters - Screenshot 2](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%282%29.png)

**Adapter 1 tab — currently set to NAT (default). We need to change this.**

### Screenshot 3

![Step 6 — Configure DC Network Adapters - Screenshot 3](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%283%29.png)

**Click the **Attached to** dropdown on Adapter 1.**

### Screenshot 4

![Step 6 — Configure DC Network Adapters - Screenshot 4](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%284%29.png)

**View the available network types: NAT, Bridged, Internal Network, Host-only, NAT Network.**

### Screenshot 5

![Step 6 — Configure DC Network Adapters - Screenshot 5](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%285%29.png)

**Adapter 1 is currently set to NAT. Click the dropdown to change it (red box highlighting the dropdown).**

### Screenshot 6

![Step 6 — Configure DC Network Adapters - Screenshot 6](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%286%29.png)

**Select **Internal Network** for Adapter 1 — this is for domain communication between VMs.**

### Screenshot 7

![Step 6 — Configure DC Network Adapters - Screenshot 7](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%287%29.png)

**Dropdown showing all network options — red box around **Host-only Adapter** (we use Internal Network instead).**

### Screenshot 8

![Step 6 — Configure DC Network Adapters - Screenshot 8](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%288%29.png)

**Set the Internal Network name to **intnet** (or your preferred name). All VMs must use the same name.**

### Screenshot 9

![Step 6 — Configure DC Network Adapters - Screenshot 9](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%289%29.png)

**Switch to **Adapter 2** tab — enable it by checking **Enable Network Adapter**.**

### Screenshot 10

![Step 6 — Configure DC Network Adapters - Screenshot 10](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%2810%29.png)

**Set Adapter 2 to **NAT** — this provides internet access through the host machine.**

### Screenshot 11

![Step 6 — Configure DC Network Adapters - Screenshot 11](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%2811%29.png)

**Adapter 2 configured as NAT for internet connectivity.**

### Screenshot 12

![Step 6 — Configure DC Network Adapters - Screenshot 12](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%2812%29.png)

**Verify both adapters: Adapter 1 = Internal Network (intnet), Adapter 2 = NAT.**

### Screenshot 13

![Step 6 — Configure DC Network Adapters - Screenshot 13](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%2813%29.png)

**Click **OK** to save the DC1 network configuration.**

### Screenshot 14

![Step 6 — Configure DC Network Adapters - Screenshot 14](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%2814%29.png)

**Repeat for DC2 — open DC2 Settings → Network → configure Adapter 1 as Internal Network.**

### Screenshot 15

![Step 6 — Configure DC Network Adapters - Screenshot 15](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%2815%29.png)

**DC2 Adapter 1 set to Internal Network with the same network name (**intnet**).**

### Screenshot 16

![Step 6 — Configure DC Network Adapters - Screenshot 16](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%2816%29.png)

**DC2 Adapter 2 set to NAT for internet access.**

### Screenshot 17

![Step 6 — Configure DC Network Adapters - Screenshot 17](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%2817%29.png)

**Repeat for CLIENT1 — configure Adapter 1 as Internal Network.**

### Screenshot 18

![Step 6 — Configure DC Network Adapters - Screenshot 18](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%2818%29.png)

**CLIENT1 Adapter 2 as NAT for internet access.**

### Screenshot 19

![Step 6 — Configure DC Network Adapters - Screenshot 19](06-DC-Network-Adapter-Configuration/Network-Adapter-%20%2819%29.png)

**All three VMs now have matching network configurations: Internal Network + NAT.**

---

## Step 7 — Install Windows Server 2025 on DC1

Boot DC1 from the ISO and complete the Windows Server 2025 installation. Select Desktop Experience edition and set the Administrator password.

### Screenshot 1

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 1](07-DC1-Installation/DC1-Installation-%20%281%29.png)

**Windows Server installation step 1 — Start DC1 VM — it boots from the mounted ISO. The Windows Setup screen appears.**

### Screenshot 2

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 2](07-DC1-Installation/DC1-Installation-%20%282%29.png)

**Windows Server installation step 2 — Select language, time format, and keyboard layout. Click **Next**.**

### Screenshot 3

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 3](07-DC1-Installation/DC1-Installation-%20%283%29.png)

**Windows Server installation step 3 — Click **Install now** to begin the installation.**

### Screenshot 4

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 4](07-DC1-Installation/DC1-Installation-%20%284%29.png)

**Windows Server installation step 4 — Select the Windows Server edition — choose **Windows Server 2025 Standard Evaluation (Desktop Experience)**.**

### Screenshot 5

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 5](07-DC1-Installation/DC1-Installation-%20%285%29.png)

**Windows Server installation step 5 — Accept the license terms and click **Next**.**

### Screenshot 6

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 6](07-DC1-Installation/DC1-Installation-%20%286%29.png)

**Windows Server installation step 6 — Select **Custom: Install Windows only** for a clean installation.**

### Screenshot 7

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 7](07-DC1-Installation/DC1-Installation-%20%287%29.png)

**Windows Server installation step 7 — Select the virtual hard disk (Drive 0, 60 GB) and click **Next**.**

### Screenshot 8

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 8](07-DC1-Installation/DC1-Installation-%20%288%29.png)

**Windows Server installation step 8 — Windows installation begins — files are being copied.**

### Screenshot 9

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 9](07-DC1-Installation/DC1-Installation-%20%289%29.png)

**Windows Server installation step 9 — Installation progress — Installing features and updates.**

### Screenshot 10

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 10](07-DC1-Installation/DC1-Installation-%20%2810%29.png)

**Windows Server installation step 10 — Installation continues — Getting devices ready.**

### Screenshot 11

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 11](07-DC1-Installation/DC1-Installation-%20%2811%29.png)

**Windows Server installation step 11 — The VM restarts automatically during installation.**

### Screenshot 12

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 12](07-DC1-Installation/DC1-Installation-%20%2812%29.png)

**Windows Server installation step 12 — Windows is finalizing the installation and preparing the system.**

### Screenshot 13

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 13](07-DC1-Installation/DC1-Installation-%20%2813%29.png)

**Windows Server installation step 13 — First boot — Windows is getting ready for first use.**

### Screenshot 14

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 14](07-DC1-Installation/DC1-Installation-%20%2814%29.png)

**Windows Server installation step 14 — Set the **Administrator password** — use a strong password you'll remember (e.g., `P@ssw0rd123!`).**

### Screenshot 15

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 15](07-DC1-Installation/DC1-Installation-%20%2815%29.png)

**Windows Server installation step 15 — Confirm the Administrator password and click **Finish**.**

### Screenshot 16

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 16](07-DC1-Installation/DC1-Installation-%20%2816%29.png)

**Windows Server installation step 16 — Windows Server desktop appears — press **Ctrl+Alt+Del** to sign in.**

### Screenshot 17

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 17](07-DC1-Installation/DC1-Installation-%20%2817%29.png)

**Windows Server installation step 17 — Enter the Administrator password to log in.**

### Screenshot 18

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 18](07-DC1-Installation/DC1-Installation-%20%2818%29.png)

**Windows Server installation step 18 — Server Manager launches automatically on first login.**

### Screenshot 19

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 19](07-DC1-Installation/DC1-Installation-%20%2819%29.png)

**Windows Server installation step 19 — Server Manager Dashboard — the base Windows Server installation is complete.**

### Screenshot 20

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 20](07-DC1-Installation/DC1-Installation-%20%2820%29.png)

**Windows Server installation step 20 — Server Manager shows the server is ready for role installation.**

### Screenshot 21

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 21](07-DC1-Installation/DC1-Installation-%20%2821%29.png)

**Windows Server installation step 21 — Optional: Install VirtualBox Guest Additions for better performance.**

### Screenshot 22

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 22](07-DC1-Installation/DC1-Installation-%20%2822%29.png)

**Windows Server installation step 22 — Click **Devices → Insert Guest Additions CD image** in the VirtualBox menu.**

### Screenshot 23

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 23](07-DC1-Installation/DC1-Installation-%20%2823%29.png)

**Windows Server installation step 23 — Open File Explorer and navigate to the Guest Additions CD drive.**

### Screenshot 24

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 24](07-DC1-Installation/DC1-Installation-%20%2824%29.png)

**Windows Server installation step 24 — Run **VBoxWindowsAdditions.exe** to install Guest Additions.**

### Screenshot 25

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 25](07-DC1-Installation/DC1-Installation-%20%2825%29.png)

**Windows Server installation step 25 — Guest Additions installation wizard — click **Next** to proceed.**

### Screenshot 26

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 26](07-DC1-Installation/DC1-Installation-%20%2826%29.png)

**Windows Server installation step 26 — Select installation components and click **Install**.**

### Screenshot 27

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 27](07-DC1-Installation/DC1-Installation-%20%2827%29.png)

**Windows Server installation step 27 — Guest Additions installing — device software is being installed.**

### Screenshot 28

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 28](07-DC1-Installation/DC1-Installation-%20%2828%29.png)

**Windows Server installation step 28 — Installation progress for Guest Additions drivers.**

### Screenshot 29

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 29](07-DC1-Installation/DC1-Installation-%20%2829%29.png)

**Windows Server installation step 29 — Guest Additions installation complete — click **Finish**.**

### Screenshot 30

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 30](07-DC1-Installation/DC1-Installation-%20%2830%29.png)

**Windows Server installation step 30 — Restart the VM for Guest Additions to take effect.**

### Screenshot 31

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 31](07-DC1-Installation/DC1-Installation-%20%2831%29.png)

**Windows Server installation step 31 — After restart, the VM has better screen resolution and mouse integration.**

### Screenshot 32

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 32](07-DC1-Installation/DC1-Installation-%20%2832%29.png)

**Windows Server installation step 32 — Verify Guest Additions are working — check display resolution options.**

### Screenshot 33

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 33](07-DC1-Installation/DC1-Installation-%20%2833%29.png)

**Windows Server installation step 33 — Server Manager dashboard after Guest Additions installation.**

### Screenshot 34

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 34](07-DC1-Installation/DC1-Installation-%20%2834%29.png)

**Windows Server installation step 34 — Adjust display settings if needed for comfortable viewing.**

### Screenshot 35

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 35](07-DC1-Installation/DC1-Installation-%20%2835%29.png)

**Windows Server installation step 35 — Windows Server 2025 installation on DC1 is fully complete.**

### Screenshot 36

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 36](07-DC1-Installation/DC1-Installation-%20%2836%29.png)

**Windows Server installation step 36 — Final view of the DC1 desktop with Server Manager ready.**

### Screenshot 37

![Step 7 — Install Windows Server 2025 on DC1 - Screenshot 37](07-DC1-Installation/DC1-Installation-%20%2837%29.png)

**Windows Server installation step 37 — DC1 is ready for the next step — renaming and network configuration.**

---

## Step 8 — Rename DC1 & Configure Static IP

Rename the server to `DC1`, assign the static IP address `192.168.10.10/24`, and set the DNS server to point to itself (`192.168.10.10`).

### Screenshot 1

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 1](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%281%29.png)

**Press **Win+R** to open the Run dialog on DC1.**

### Screenshot 2

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 2](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%282%29.png)

**Type `sysdm.cpl` and press **Enter** to open System Properties.**

### Screenshot 3

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 3](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%283%29.png)

**System Properties opens — click the **Computer Name** tab.**

### Screenshot 4

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 4](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%284%29.png)

**Click **Change** to modify the computer name.**

### Screenshot 5

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 5](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%285%29.png)

**Change the Computer name to **DC1**. Click **OK**.**

### Screenshot 6

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 6](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%286%29.png)

**A restart prompt appears — click **OK** to acknowledge.**

### Screenshot 7

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 7](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%287%29.png)

**Click **Restart Now** to apply the computer name change.**

### Screenshot 8

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 8](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%288%29.png)

**After restart, log back in as Administrator. Verify the hostname is now **DC1**.**

### Screenshot 9

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 9](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%289%29.png)

**Open **Control Panel → Network and Internet → Network Connections** (or type `ncpa.cpl` in Run).**

### Screenshot 10

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 10](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2810%29.png)

**Network Connections window shows two Ethernet adapters (Internal + NAT).**

### Screenshot 11

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 11](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2811%29.png)

**Right-click the first Ethernet adapter (Internal Network) → click **Properties**.**

### Screenshot 12

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 12](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2812%29.png)

**Select **Internet Protocol Version 4 (TCP/IPv4)** → click **Properties**.**

### Screenshot 13

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 13](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2813%29.png)

**The IPv4 properties dialog opens — currently set to obtain IP automatically.**

### Screenshot 14

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 14](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2814%29.png)

**Ethernet Properties showing the available network protocols. Double-click **Internet Protocol Version 4 (TCP/IPv4)**.**

### Screenshot 15

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 15](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2815%29.png)

**IPv4 Properties — currently set to DHCP. We need to set a static IP.**

### Screenshot 16

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 16](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2816%29.png)

**IPv4 Properties showing the IP configuration fields. Select **Use the following IP address** and **Use the following DNS server addresses** (red boxes).**

### Screenshot 17

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 17](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2817%29.png)

**Select **Use the following IP address** and **Use the following DNS server addresses** (red boxes highlighting the radio buttons).**

### Screenshot 18

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 18](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2818%29.png)

**Enter the static IP configuration:

```
IP address:        192.168.10.10
Subnet mask:       255.255.255.0
Preferred DNS:     192.168.10.10
```

Click **OK** to apply.**

### Screenshot 19

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 19](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2819%29.png)

**Close the Network Connections window.**

### Screenshot 20

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 20](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2820%29.png)

**Open **Command Prompt** — search for `cmd` in the Start menu.**

### Screenshot 21

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 21](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2821%29.png)

**Right-click Command Prompt and select **Run as administrator**.**

### Screenshot 22

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 22](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2822%29.png)

**Run `ipconfig /all` to verify the configuration:

```cmd
ipconfig /all
```

Confirm: Host Name = DC1, IPv4 = 192.168.10.10, DNS = 192.168.10.10.**

### Screenshot 23

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 23](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2823%29.png)

**Scroll down in ipconfig output to verify Ethernet adapter 2 (NAT) has DHCP-assigned IP for internet.**

### Screenshot 24

![Step 8 — Rename DC1 & Configure Static IP - Screenshot 24](08-DC1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2824%29.png)

**DC1 network configuration is complete and verified.**

---

## Step 9 — Install Windows Server 2025 on DC2

Boot DC2 from the Windows Server ISO and complete the installation. Same process as DC1 — select Desktop Experience and set the Administrator password.

### Screenshot 1

![Step 9 — Install Windows Server 2025 on DC2 - Screenshot 1](09-DC2-Installation/DC2-Installation-%20%281%29.png)

**DC2 Windows Server installation — Start DC2 VM — boots from the mounted ISO.**

### Screenshot 2

![Step 9 — Install Windows Server 2025 on DC2 - Screenshot 2](09-DC2-Installation/DC2-Installation-%20%282%29.png)

**DC2 Windows Server installation — Select language and regional settings. Click **Next**.**

### Screenshot 3

![Step 9 — Install Windows Server 2025 on DC2 - Screenshot 3](09-DC2-Installation/DC2-Installation-%20%283%29.png)

**DC2 Windows Server installation — Click **Install now**.**

### Screenshot 4

![Step 9 — Install Windows Server 2025 on DC2 - Screenshot 4](09-DC2-Installation/DC2-Installation-%20%284%29.png)

**DC2 Windows Server installation — Select **Windows Server 2025 Standard Evaluation (Desktop Experience)**.**

### Screenshot 5

![Step 9 — Install Windows Server 2025 on DC2 - Screenshot 5](09-DC2-Installation/DC2-Installation-%20%285%29.png)

**DC2 Windows Server installation — Accept license terms.**

### Screenshot 6

![Step 9 — Install Windows Server 2025 on DC2 - Screenshot 6](09-DC2-Installation/DC2-Installation-%20%286%29.png)

**DC2 Windows Server installation — Choose **Custom: Install Windows only**.**

### Screenshot 7

![Step 9 — Install Windows Server 2025 on DC2 - Screenshot 7](09-DC2-Installation/DC2-Installation-%20%287%29.png)

**DC2 Windows Server installation — Select the virtual disk and click **Next**.**

### Screenshot 8

![Step 9 — Install Windows Server 2025 on DC2 - Screenshot 8](09-DC2-Installation/DC2-Installation-%20%288%29.png)

**DC2 Windows Server installation — Installation begins — copying files.**

### Screenshot 9

![Step 9 — Install Windows Server 2025 on DC2 - Screenshot 9](09-DC2-Installation/DC2-Installation-%20%289%29.png)

**DC2 Windows Server installation — Installation in progress.**

### Screenshot 10

![Step 9 — Install Windows Server 2025 on DC2 - Screenshot 10](09-DC2-Installation/DC2-Installation-%20%2810%29.png)

**DC2 Windows Server installation — VM restarts during installation.**

### Screenshot 11

![Step 9 — Install Windows Server 2025 on DC2 - Screenshot 11](09-DC2-Installation/DC2-Installation-%20%2811%29.png)

**DC2 Windows Server installation — Windows is finalizing setup.**

### Screenshot 12

![Step 9 — Install Windows Server 2025 on DC2 - Screenshot 12](09-DC2-Installation/DC2-Installation-%20%2812%29.png)

**DC2 Windows Server installation — Set the **Administrator password** on DC2.**

### Screenshot 13

![Step 9 — Install Windows Server 2025 on DC2 - Screenshot 13](09-DC2-Installation/DC2-Installation-%20%2813%29.png)

**DC2 Windows Server installation — Confirm the password and click **Finish**.**

### Screenshot 14

![Step 9 — Install Windows Server 2025 on DC2 - Screenshot 14](09-DC2-Installation/DC2-Installation-%20%2814%29.png)

**DC2 Windows Server installation — Press Ctrl+Alt+Del and log in as Administrator.**

### Screenshot 15

![Step 9 — Install Windows Server 2025 on DC2 - Screenshot 15](09-DC2-Installation/DC2-Installation-%20%2815%29.png)

**DC2 Windows Server installation — Server Manager launches — DC2 base OS is ready.**

### Screenshot 16

![Step 9 — Install Windows Server 2025 on DC2 - Screenshot 16](09-DC2-Installation/DC2-Installation-%20%2816%29.png)

**DC2 Windows Server installation — Install VirtualBox Guest Additions on DC2.**

### Screenshot 17

![Step 9 — Install Windows Server 2025 on DC2 - Screenshot 17](09-DC2-Installation/DC2-Installation-%20%2817%29.png)

**DC2 Windows Server installation — Guest Additions installation in progress.**

### Screenshot 18

![Step 9 — Install Windows Server 2025 on DC2 - Screenshot 18](09-DC2-Installation/DC2-Installation-%20%2818%29.png)

**DC2 Windows Server installation — DC2 Windows Server installation complete — ready for renaming.**

---

## Step 10 — Rename DC2 & Configure Static IP

Rename the server to `DC2`, assign static IP `192.168.10.11/24`, and set DNS to point to DC1 (`192.168.10.10`).

### Screenshot 1

![Step 10 — Rename DC2 & Configure Static IP - Screenshot 1](10-DC2-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%281%29.png)

**Press **Win+R** → type `sysdm.cpl` to open System Properties on DC2.**

### Screenshot 2

![Step 10 — Rename DC2 & Configure Static IP - Screenshot 2](10-DC2-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%282%29.png)

**Click **Change** to rename the computer.**

### Screenshot 3

![Step 10 — Rename DC2 & Configure Static IP - Screenshot 3](10-DC2-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%283%29.png)

**Set the computer name to **DC2** and click **OK**.**

### Screenshot 4

![Step 10 — Rename DC2 & Configure Static IP - Screenshot 4](10-DC2-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%284%29.png)

**Restart the server to apply the name change.**

### Screenshot 5

![Step 10 — Rename DC2 & Configure Static IP - Screenshot 5](10-DC2-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%285%29.png)

**After restart, verify hostname is now **DC2**.**

### Screenshot 6

![Step 10 — Rename DC2 & Configure Static IP - Screenshot 6](10-DC2-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%286%29.png)

**Open **Network Connections** (`ncpa.cpl`).**

### Screenshot 7

![Step 10 — Rename DC2 & Configure Static IP - Screenshot 7](10-DC2-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%287%29.png)

**Two Ethernet adapters visible — right-click the Internal Network adapter.**

### Screenshot 8

![Step 10 — Rename DC2 & Configure Static IP - Screenshot 8](10-DC2-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%288%29.png)

**Open **Properties** → select **Internet Protocol Version 4 (TCP/IPv4)**.**

### Screenshot 9

![Step 10 — Rename DC2 & Configure Static IP - Screenshot 9](10-DC2-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%289%29.png)

**IPv4 Properties dialog — currently DHCP.**

### Screenshot 10

![Step 10 — Rename DC2 & Configure Static IP - Screenshot 10](10-DC2-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2810%29.png)

**Select **Use the following IP address** — enter the static IP config (red boxes highlighting fields).**

### Screenshot 11

![Step 10 — Rename DC2 & Configure Static IP - Screenshot 11](10-DC2-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2811%29.png)

**Enter the static IP:

```
IP address:        192.168.10.11
Subnet mask:       255.255.255.0
Preferred DNS:     192.168.10.10
```

DNS points to DC1. Click **OK**.**

### Screenshot 12

![Step 10 — Rename DC2 & Configure Static IP - Screenshot 12](10-DC2-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2812%29.png)

**Close Network Connections.**

### Screenshot 13

![Step 10 — Rename DC2 & Configure Static IP - Screenshot 13](10-DC2-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2813%29.png)

**Open **Command Prompt** as Administrator. Run:

```cmd
ipconfig /all
```

Verify: Host Name = DC2, IPv4 = 192.168.10.11, DNS = 192.168.10.10.**

### Screenshot 14

![Step 10 — Rename DC2 & Configure Static IP - Screenshot 14](10-DC2-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2814%29.png)

**Test connectivity to DC1:

```cmd
ping 192.168.10.10
```

Verify successful replies.**

### Screenshot 15

![Step 10 — Rename DC2 & Configure Static IP - Screenshot 15](10-DC2-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2815%29.png)

**DC2 network configuration is complete — DC1 and DC2 can communicate.**

---

## Step 11 — Install Windows 10 Pro on CLIENT1

Boot CLIENT1 from the Windows 10 Pro ISO and complete the installation. This workstation will be joined to the vertex.local domain.

### Screenshot 1

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 1](11-CLIENT1-Installation/CLIENT1-Installation-%20%281%29.png)

**CLIENT1 Windows 10 installation — Start CLIENT1 VM — boots from the Windows 10 ISO.**

### Screenshot 2

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 2](11-CLIENT1-Installation/CLIENT1-Installation-%20%282%29.png)

**CLIENT1 Windows 10 installation — Windows 10 Setup appears — select language and click **Next**.**

### Screenshot 3

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 3](11-CLIENT1-Installation/CLIENT1-Installation-%20%283%29.png)

**CLIENT1 Windows 10 installation — Click **Install now**.**

### Screenshot 4

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 4](11-CLIENT1-Installation/CLIENT1-Installation-%20%284%29.png)

**CLIENT1 Windows 10 installation — Enter product key or click **I don't have a product key**.**

### Screenshot 5

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 5](11-CLIENT1-Installation/CLIENT1-Installation-%20%285%29.png)

**CLIENT1 Windows 10 installation — Select **Windows 10 Pro** edition.**

### Screenshot 6

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 6](11-CLIENT1-Installation/CLIENT1-Installation-%20%286%29.png)

**CLIENT1 Windows 10 installation — Accept the license terms.**

### Screenshot 7

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 7](11-CLIENT1-Installation/CLIENT1-Installation-%20%287%29.png)

**CLIENT1 Windows 10 installation — Select **Custom: Install Windows only**.**

### Screenshot 8

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 8](11-CLIENT1-Installation/CLIENT1-Installation-%20%288%29.png)

**CLIENT1 Windows 10 installation — Select the virtual disk and click **Next**.**

### Screenshot 9

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 9](11-CLIENT1-Installation/CLIENT1-Installation-%20%289%29.png)

**CLIENT1 Windows 10 installation — Installation begins — copying Windows files.**

### Screenshot 10

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 10](11-CLIENT1-Installation/CLIENT1-Installation-%20%2810%29.png)

**CLIENT1 Windows 10 installation — Installation progress — Getting files ready.**

### Screenshot 11

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 11](11-CLIENT1-Installation/CLIENT1-Installation-%20%2811%29.png)

**CLIENT1 Windows 10 installation — VM restarts during installation.**

### Screenshot 12

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 12](11-CLIENT1-Installation/CLIENT1-Installation-%20%2812%29.png)

**CLIENT1 Windows 10 installation — Windows is setting up — Getting ready.**

### Screenshot 13

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 13](11-CLIENT1-Installation/CLIENT1-Installation-%20%2813%29.png)

**CLIENT1 Windows 10 installation — Region selection — choose your region.**

### Screenshot 14

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 14](11-CLIENT1-Installation/CLIENT1-Installation-%20%2814%29.png)

**CLIENT1 Windows 10 installation — Keyboard layout selection.**

### Screenshot 15

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 15](11-CLIENT1-Installation/CLIENT1-Installation-%20%2815%29.png)

**CLIENT1 Windows 10 installation — Skip second keyboard layout.**

### Screenshot 16

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 16](11-CLIENT1-Installation/CLIENT1-Installation-%20%2816%29.png)

**CLIENT1 Windows 10 installation — Network setup — select **I don't have internet** or skip.**

### Screenshot 17

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 17](11-CLIENT1-Installation/CLIENT1-Installation-%20%2817%29.png)

**CLIENT1 Windows 10 installation — Account setup — click **Set up for an organization** or create a local account.**

### Screenshot 18

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 18](11-CLIENT1-Installation/CLIENT1-Installation-%20%2818%29.png)

**CLIENT1 Windows 10 installation — Create a local user account (or skip Microsoft account).**

### Screenshot 19

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 19](11-CLIENT1-Installation/CLIENT1-Installation-%20%2819%29.png)

**CLIENT1 Windows 10 installation — Set the local account password.**

### Screenshot 20

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 20](11-CLIENT1-Installation/CLIENT1-Installation-%20%2820%29.png)

**CLIENT1 Windows 10 installation — Privacy settings — toggle as preferred and click **Accept**.**

### Screenshot 21

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 21](11-CLIENT1-Installation/CLIENT1-Installation-%20%2821%29.png)

**CLIENT1 Windows 10 installation — Cortana setup — choose preferences.**

### Screenshot 22

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 22](11-CLIENT1-Installation/CLIENT1-Installation-%20%2822%29.png)

**CLIENT1 Windows 10 installation — Windows 10 is finalizing setup.**

### Screenshot 23

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 23](11-CLIENT1-Installation/CLIENT1-Installation-%20%2823%29.png)

**CLIENT1 Windows 10 installation — Desktop appears — Windows 10 Pro is installed.**

### Screenshot 24

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 24](11-CLIENT1-Installation/CLIENT1-Installation-%20%2824%29.png)

**CLIENT1 Windows 10 installation — Install VirtualBox Guest Additions on CLIENT1.**

### Screenshot 25

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 25](11-CLIENT1-Installation/CLIENT1-Installation-%20%2825%29.png)

**CLIENT1 Windows 10 installation — Run VBoxWindowsAdditions.exe.**

### Screenshot 26

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 26](11-CLIENT1-Installation/CLIENT1-Installation-%20%2826%29.png)

**CLIENT1 Windows 10 installation — Guest Additions installing.**

### Screenshot 27

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 27](11-CLIENT1-Installation/CLIENT1-Installation-%20%2827%29.png)

**CLIENT1 Windows 10 installation — Installation progress.**

### Screenshot 28

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 28](11-CLIENT1-Installation/CLIENT1-Installation-%20%2828%29.png)

**CLIENT1 Windows 10 installation — Guest Additions complete — click **Finish** and restart.**

### Screenshot 29

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 29](11-CLIENT1-Installation/CLIENT1-Installation-%20%2829%29.png)

**CLIENT1 Windows 10 installation — After restart, better display resolution is available.**

### Screenshot 30

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 30](11-CLIENT1-Installation/CLIENT1-Installation-%20%2830%29.png)

**CLIENT1 Windows 10 installation — CLIENT1 desktop ready — Windows 10 Pro installed.**

### Screenshot 31

![Step 11 — Install Windows 10 Pro on CLIENT1 - Screenshot 31](11-CLIENT1-Installation/CLIENT1-Installation-%20%2831%29.png)

**CLIENT1 Windows 10 installation — CLIENT1 base OS installation is complete.**

---

## Step 12 — Rename CLIENT1 & Configure Static IP

Rename the workstation to `CLIENT1`, assign static IP `192.168.10.50/24`, and set DNS to point to DC1 (`192.168.10.10`).

### Screenshot 1

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 1](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%281%29.png)

**Open System Properties on CLIENT1 — press **Win+R** → `sysdm.cpl`.**

### Screenshot 2

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 2](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%282%29.png)

**System Properties opens — click the **Computer Name** tab.**

### Screenshot 3

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 3](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%283%29.png)

**Click **Change** to modify the computer name.**

### Screenshot 4

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 4](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%284%29.png)

**Enter **CLIENT1** as the new computer name.**

### Screenshot 5

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 5](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%285%29.png)

**Click **OK** — a restart prompt appears.**

### Screenshot 6

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 6](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%286%29.png)

**Restart the computer to apply the name change.**

### Screenshot 7

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 7](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%287%29.png)

**After restart, log back in and verify the hostname is CLIENT1.**

### Screenshot 8

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 8](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%288%29.png)

**Open **Network Connections** (`ncpa.cpl`).**

### Screenshot 9

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 9](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%289%29.png)

**Right-click the Ethernet adapter → **Properties**.**

### Screenshot 10

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 10](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2810%29.png)

**Select **Internet Protocol Version 4 (TCP/IPv4)** → **Properties**.**

### Screenshot 11

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 11](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2811%29.png)

**Ethernet Status showing connection details — click **Properties**.**

### Screenshot 12

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 12](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2812%29.png)

**IPv4 Properties dialog — currently set to DHCP.**

### Screenshot 13

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 13](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2813%29.png)

**Select the static IP option.**

### Screenshot 14

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 14](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2814%29.png)

**IPv4 Properties — ready to enter static IP (currently blank).**

### Screenshot 15

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 15](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2815%29.png)

**Enter the static IP configuration:

```
IP address:        192.168.10.50
Subnet mask:       255.255.255.0
Preferred DNS:     192.168.10.10
```

Click **OK** (red circles highlighting key fields).**

### Screenshot 16

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 16](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2816%29.png)

**Close the properties dialogs.**

### Screenshot 17

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 17](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2817%29.png)

**Open **Command Prompt** and run:

```cmd
ipconfig /all
```

Verify: Host Name = CLIENT1, IPv4 = 192.168.10.50, DNS = 192.168.10.10.**

### Screenshot 18

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 18](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2818%29.png)

**Test connectivity:

```cmd
ping 192.168.10.10
ping 192.168.10.11
```

Both DC1 and DC2 should respond.**

### Screenshot 19

![Step 12 — Rename CLIENT1 & Configure Static IP - Screenshot 19](12-CLIENT1-Rename-And-DNS-Configuration/Rename-And-DNS-Configuration-%20%2819%29.png)

**CLIENT1 network setup complete — all three machines can communicate on the 192.168.10.0/24 network.**

---

## 🔗 Navigation

[⬆️ Back to Top](#)

[📚 Back to Master README](../README.md)
