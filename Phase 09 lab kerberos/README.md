# Phase 09 — Kerberos Authentication

> Observe Kerberos ticket flow using klist, manage Service Principal Names, verify time synchronisation, enforce AES encryption, configure constrained delegation, and inspect Kerberos events in Event Viewer.

---

## How Kerberos Works (Quick Reference)

```
1. Client → KDC (AS-REQ): "I'm jsmith, give me a TGT"
2. KDC → Client (AS-REP): Here's your TGT (encrypted with krbtgt key)
3. Client → KDC (TGS-REQ): "I want to access \\DC1\Finance, here's my TGT"
4. KDC → Client (TGS-REP): Here's a Service Ticket for that share
5. Client → Service (AP-REQ): Here's my Service Ticket
6. Service → Client (AP-REP): Authenticated ✅
```

Domain: `vertex.local` · KDC: DC1 (PDC Emulator holds the master krbtgt key)

---

## Steps

### 01 — Observe Kerberos Tickets with klist
Logged into CLIENT1 as a domain user and ran:

```cmd
klist
klist tickets
```

Observed:
- **TGT (Ticket Granting Ticket)** — issued by KDC, valid for 10 hours (default), proves identity
- **Service Tickets** — one per service accessed (file shares, DC LDAP, etc.)
- Ticket encryption type (RC4 vs AES256)
- Expiry and renewal times

Also used `klist purge` to clear tickets and force re-authentication, observing new tickets being issued.

**Screenshots:** `01-OBSERVE KERBEROS TICKETS WITH KLIST/` (21 images)

---

### 02 — Manage SPNs (Service Principal Names)
SPNs are how Kerberos identifies services. Used `setspn` to list, add, and verify SPNs:

```cmd
setspn -L DC1                    # List all SPNs on DC1
setspn -Q */*                    # Query all SPNs in the domain
setspn -S HTTP/webserver.vertex.local DC1   # Register an HTTP SPN
setspn -D HTTP/webserver.vertex.local DC1   # Remove SPN (cleanup)
```

Identified duplicate SPNs (a common misconfiguration that breaks Kerberos authentication for services).

**Screenshots:** `02-MANAGE SPNs (SERVICE PRINCIPAL NAMES)/` (18 images)

---

### 03 — Verify Time Synchronisation
Kerberos has a strict **5-minute clock skew tolerance** — if clocks are more than 5 minutes apart, authentication fails with `KRB_AP_ERR_SKEW`.

Verified the NTP hierarchy:
- DC1 (PDC Emulator) → synchronises to an external NTP source (`time.windows.com`)
- DC2 → synchronises to DC1
- CLIENT1 → synchronises to DC1

```cmd
w32tm /query /status           # Check current time sync status
w32tm /query /peers            # Check NTP peers
w32tm /resync /force           # Force an immediate sync
```

**Screenshots:** `03-VERIFY TIME SYNCHRONIZATION/` (9 images)

---

### 04 — Enable AES Encryption on Important Accounts
Updated privileged accounts and service accounts to use **AES-256** encryption instead of the weaker RC4 (NTLM-compatible) encryption:

In ADUC → Account tab → Account options:
- ✅ `This account supports Kerberos AES 128 bit encryption`
- ✅ `This account supports Kerberos AES 256 bit encryption`
- ❌ (Optionally) unchecked `Use DES encryption types for this account`

After enabling, verified tickets showed `Etype: AES-256-CTS-HMAC-SHA1-96` in `klist`.

**Screenshots:** `04-ENABLE AES ENCRYPTION ON IMPORTANT ACCOUNTS/` (9 images)

---

### 05 — Configure Kerberos Constrained Delegation
Configured **Constrained Delegation** for a service account (`svc_web`) to allow it to request Kerberos tickets on behalf of users, but only to specific services:

In ADUC → svc_web → Delegation tab:
- Selected: **Trust this user for delegation to specified services only**
- Added: `HTTP/webserver.vertex.local`

This simulates how a web application can access a backend SQL server *as the logged-in user* without exposing that user's credentials.

**Screenshots:** `05-CONFIGURE KERBEROS CONSTRAINED DELEGATION/` (13 images)

---

### 06 — Look at Kerberos Events in Event Viewer
Filtered **Security** event log on DC1 for Kerberos-specific events:

| Event ID | Description |
|----------|-------------|
| 4768 | Kerberos TGT requested (AS-REQ) |
| 4769 | Kerberos service ticket requested (TGS-REQ) |
| 4770 | Kerberos service ticket renewed |
| 4771 | Kerberos pre-authentication failed |
| 4772 | Kerberos authentication ticket request failed |

Observed live TGT and TGS requests as users logged in and accessed resources.

**Screenshots:** `06-LOOK AT KERBEROS EVENTS IN EVENT VIEWER/` (4 images)

---

## Key Concepts

- **TGT** is your "day pass" — presented to the KDC to get service tickets without re-entering your password
- **SPNs** map service names to AD accounts — if an SPN is missing or duplicated, Kerberos falls back to NTLM (or fails entirely)
- **RC4 (NTLM-compat)** Kerberos tickets are vulnerable to **Kerberoasting** — AES tickets are not
- **Constrained delegation** is safer than unconstrained delegation (which allows impersonation to *any* service)
- Clock skew is the #1 cause of mysterious Kerberos failures in new environments

---

## Tools Used

`klist` · `setspn` · `w32tm` · `Active Directory Users and Computers` · `Event Viewer`

---

*Previous: [Phase 08 — AD Security](<../Phase 08 lab ad security/README.md>) · Next: [Phase 10 — LDAP](<../Phase 10 lab ldap/README.md>)*
