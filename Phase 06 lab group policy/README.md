# Phase 06 — Group Policy Management

> Create, link, and test multiple Group Policy Objects covering password security, desktop restrictions, IT admin access, audit logging, and loopback processing for shared workstations.

---

## Steps

### 01 — Open Group Policy Management Console
Opened the **Group Policy Management Console (GPMC)** from Server Manager → Tools. Explored the default GPOs:
- `Default Domain Policy` — domain-wide settings (applied to all objects)
- `Default Domain Controllers Policy` — DC-specific security settings

Explored GPO precedence (LSDOU): Local → Site → Domain → OU

**Screenshots:** `01-OPEN GROUP POLICY MANAGEMENT CONSOLE/` (10+ images)

---

### 02 — GPO 2: Finance Security Policy
Created and linked a GPO to the `Finance` OU enforcing additional security restrictions:

- **Account Lockout:** Lock after 3 failed attempts, 30-minute lockout duration
- **Interactive Logon:** Display legal notice before logon
- **Removable Storage:** Block write access to USB drives
- **Audit:** Log all logon events

**Screenshots:** `02-GPO 2 FINANCE SECURITY POLICY/`

---

### 03 — GPO 3: IT Admin Policy
Created a GPO for the `IT` OU granting IT admins elevated capabilities:

- **Remote Desktop:** Allow RDP connections from IT OU accounts
- **Windows Firewall:** Allow specific management ports
- **Script execution:** Enabled PowerShell script execution policy

**Screenshots:** `03-GPO 3 IT ADMIN POLICY/`

---

### 04 — GPO 4: Desktop Policy
Created a standardised desktop policy linked to `Workstations` OU:

- **Wallpaper:** Set corporate wallpaper (non-changeable)
- **Control Panel:** Restrict access for non-admin users
- **Taskbar:** Remove specific items
- **Start Menu:** Remove "Run" and "Shutdown" for standard users

**Screenshots:** `04-GPO 4 DESKTOP POLICY/`

---

### 05 — GPO 5: Audit Policy
Created a comprehensive audit GPO linked at the domain level:

Audit categories configured:
- ✅ Account Logon Events
- ✅ Account Management
- ✅ Directory Service Access
- ✅ Logon Events
- ✅ Object Access
- ✅ Policy Change
- ✅ Privilege Use
- ✅ System Events

**Screenshots:** `05-GPO 5 AUDIT POLICY/`

---

### 06 — GPO 6: Loopback (Operations Shared PCs)
Configured **Loopback Processing** for shared workstations in the `Operations` OU. In Loopback mode, user settings from the *computer's* GPO apply instead of the user's own GPO — ensuring that shared kiosk-style PCs always apply restrictive settings regardless of which user logs in.

Modes:
- **Replace** — only computer-linked user settings apply (most restrictive)
- **Merge** — computer-linked user settings merge with user's own (overriding conflicts)

**Screenshots:** `06-GPO 6 LOOPBACK (OPERATIONS SHARED PCS)/`

---

### 07 — Enforce Base Policy & Test
- Set `Default Domain Policy` to **Enforced** to prevent lower-level GPOs from blocking it
- Ran `gpupdate /force` on CLIENT1
- Ran `gpresult /r` on CLIENT1 to verify which GPOs applied
- Verified wallpaper changed, Control Panel restrictions active, audit events appearing in Event Viewer

**Screenshots:** `07-ENFORCE BASE POLICY AND TEST/`

---

## Key Concepts

- **LSDOU order:** Local → Site → Domain → OU (later wins unless Enforced/Block Inheritance)
- **Enforced GPOs** cannot be blocked by child OUs — use for baseline security
- **Block Inheritance** on an OU blocks all parent GPOs (except Enforced ones)
- `gpupdate /force` immediately pulls the latest policy without waiting for the 90-minute refresh
- `gpresult /r` shows the **Resultant Set of Policy (RSoP)** — which GPOs actually applied and which won conflicts
- **Loopback processing** is essential for shared PCs, kiosks, and terminal servers

---

## Tools Used

`Group Policy Management Console (GPMC)` · `Group Policy Object Editor` · `gpupdate` · `gpresult` · `Event Viewer`

---

*Previous: [Phase 05 — Groups & AGDLP](<../Phase 05 lab groups agdl/README.md>) · Next: [Phase 07 — Domain Controllers & FSMO](<../Phase 07 lab domaincontrollers fsmo/README.md>)*
