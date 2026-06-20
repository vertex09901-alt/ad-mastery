# 🎟️ Phase 09 — Kerberos Authentication

> **Observe Kerberos tickets with klist, manage SPNs (Service Principal Names), verify time synchronization (critical for Kerberos), enable AES-256 encryption on important accounts, configure Kerberos Constrained Delegation, and review Kerberos events in Event Viewer.**

**Prerequisites:** Phase 08 completed — secure admin accounts configured.

---
## 📑 Table of Contents

- [Step 1 — Observe Kerberos Tickets with klist](#step-1-observe-kerberos-tickets-with-klist)
- [Step 2 — Manage SPNs (Service Principal Names)](#step-2-manage-spns-service-principal-names)
- [Step 3 — Verify Time Synchronization](#step-3-verify-time-synchronization)
- [Step 4 — Enable AES-256 Encryption](#step-4-enable-aes-256-encryption)
- [Step 5 — Configure Kerberos Constrained Delegation](#step-5-configure-kerberos-constrained-delegation)
- [Step 6 — Review Kerberos Events](#step-6-review-kerberos-events)

---

## Step 1 — Observe Kerberos Tickets with klist

Use the `klist` command to view cached Kerberos tickets:

```cmd
klist
klist tickets
klist tgt
```

Observe TGT (Ticket Granting Ticket) and service tickets.

### Screenshot 1

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 1](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 2](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 3](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 4](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%284%29.png)

**Continue the configuration (step 4 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 5](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%285%29.png)

**Continue the configuration (step 5 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 6](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%286%29.png)

**Continue the configuration (step 6 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 7](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%287%29.png)

**Continue the configuration (step 7 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 8](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%288%29.png)

**Continue the configuration (step 8 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 9](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%289%29.png)

**Continue the configuration (step 9 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 10](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%2810%29.png)

**Continue the configuration (step 10 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 11](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%2811%29.png)

**Continue the configuration (step 11 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 12](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%2812%29.png)

**Continue the configuration (step 12 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 13](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%2813%29.png)

**Continue the configuration (step 13 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 14](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%2814%29.png)

**Continue the configuration (step 14 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 15](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%2815%29.png)

**Continue the configuration (step 15 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 16](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%2816%29.png)

**Continue the configuration (step 16 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 17](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%2817%29.png)

**Continue the configuration (step 17 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 18](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%2818%29.png)

**Continue the configuration (step 18 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 19](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%2819%29.png)

**Continue the configuration (step 19 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 20](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%2820%29.png)

**Continue the configuration (step 20 of 21) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 1 — Observe Kerberos Tickets with klist - Screenshot 21](01-OBSERVE%20KERBEROS%20TICKETS%20WITH%20KLIST/KLIST-%20%2821%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 2 — Manage SPNs (Service Principal Names)

Register and query SPNs for service accounts:

```cmd
setspn -L DC1
setspn -Q */*
setspn -S HTTP/webapp.vertex.local serviceaccount
```

### Screenshot 1

![Step 2 — Manage SPNs (Service Principal Names) - Screenshot 1](02-MANAGE%20SPNs%20(SERVICE%20PRINCIPAL%20NAMES)/SPNs-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 2 — Manage SPNs (Service Principal Names) - Screenshot 2](02-MANAGE%20SPNs%20(SERVICE%20PRINCIPAL%20NAMES)/SPNs-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 2 — Manage SPNs (Service Principal Names) - Screenshot 3](02-MANAGE%20SPNs%20(SERVICE%20PRINCIPAL%20NAMES)/SPNs-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 2 — Manage SPNs (Service Principal Names) - Screenshot 4](02-MANAGE%20SPNs%20(SERVICE%20PRINCIPAL%20NAMES)/SPNs-%20%284%29.png)

**Continue the configuration (step 4 of 18) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 2 — Manage SPNs (Service Principal Names) - Screenshot 5](02-MANAGE%20SPNs%20(SERVICE%20PRINCIPAL%20NAMES)/SPNs-%20%285%29.png)

**Continue the configuration (step 5 of 18) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 2 — Manage SPNs (Service Principal Names) - Screenshot 6](02-MANAGE%20SPNs%20(SERVICE%20PRINCIPAL%20NAMES)/SPNs-%20%286%29.png)

**Continue the configuration (step 6 of 18) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 2 — Manage SPNs (Service Principal Names) - Screenshot 7](02-MANAGE%20SPNs%20(SERVICE%20PRINCIPAL%20NAMES)/SPNs-%20%287%29.png)

**Continue the configuration (step 7 of 18) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 2 — Manage SPNs (Service Principal Names) - Screenshot 8](02-MANAGE%20SPNs%20(SERVICE%20PRINCIPAL%20NAMES)/SPNs-%20%288%29.png)

**Continue the configuration (step 8 of 18) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 2 — Manage SPNs (Service Principal Names) - Screenshot 9](02-MANAGE%20SPNs%20(SERVICE%20PRINCIPAL%20NAMES)/SPNs-%20%289%29.png)

**Continue the configuration (step 9 of 18) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 2 — Manage SPNs (Service Principal Names) - Screenshot 10](02-MANAGE%20SPNs%20(SERVICE%20PRINCIPAL%20NAMES)/SPNs-%20%2810%29.png)

**Continue the configuration (step 10 of 18) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 2 — Manage SPNs (Service Principal Names) - Screenshot 11](02-MANAGE%20SPNs%20(SERVICE%20PRINCIPAL%20NAMES)/SPNs-%20%2811%29.png)

**Continue the configuration (step 11 of 18) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 2 — Manage SPNs (Service Principal Names) - Screenshot 12](02-MANAGE%20SPNs%20(SERVICE%20PRINCIPAL%20NAMES)/SPNs-%20%2812%29.png)

**Continue the configuration (step 12 of 18) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 2 — Manage SPNs (Service Principal Names) - Screenshot 13](02-MANAGE%20SPNs%20(SERVICE%20PRINCIPAL%20NAMES)/SPNs-%20%2813%29.png)

**Continue the configuration (step 13 of 18) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 2 — Manage SPNs (Service Principal Names) - Screenshot 14](02-MANAGE%20SPNs%20(SERVICE%20PRINCIPAL%20NAMES)/SPNs-%20%2814%29.png)

**Continue the configuration (step 14 of 18) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 2 — Manage SPNs (Service Principal Names) - Screenshot 15](02-MANAGE%20SPNs%20(SERVICE%20PRINCIPAL%20NAMES)/SPNs-%20%2815%29.png)

**Continue the configuration (step 15 of 18) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 2 — Manage SPNs (Service Principal Names) - Screenshot 16](02-MANAGE%20SPNs%20(SERVICE%20PRINCIPAL%20NAMES)/SPNs-%20%2816%29.png)

**Continue the configuration (step 16 of 18) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 2 — Manage SPNs (Service Principal Names) - Screenshot 17](02-MANAGE%20SPNs%20(SERVICE%20PRINCIPAL%20NAMES)/SPNs-%20%2817%29.png)

**Continue the configuration (step 17 of 18) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 2 — Manage SPNs (Service Principal Names) - Screenshot 18](02-MANAGE%20SPNs%20(SERVICE%20PRINCIPAL%20NAMES)/SPNs-%20%2818%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 3 — Verify Time Synchronization

Kerberos requires clocks to be within 5 minutes. Verify NTP sync:

```cmd
w32tm /query /status
w32tm /query /source
w32tm /resync
```

### Screenshot 1

![Step 3 — Verify Time Synchronization - Screenshot 1](03-VERIFY%20TIME%20SYNCHRONIZATION/SYNCHRONIZATION-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 3 — Verify Time Synchronization - Screenshot 2](03-VERIFY%20TIME%20SYNCHRONIZATION/SYNCHRONIZATION-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 3 — Verify Time Synchronization - Screenshot 3](03-VERIFY%20TIME%20SYNCHRONIZATION/SYNCHRONIZATION-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 3 — Verify Time Synchronization - Screenshot 4](03-VERIFY%20TIME%20SYNCHRONIZATION/SYNCHRONIZATION-%20%284%29.png)

**Continue the configuration (step 4 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 3 — Verify Time Synchronization - Screenshot 5](03-VERIFY%20TIME%20SYNCHRONIZATION/SYNCHRONIZATION-%20%285%29.png)

**Continue the configuration (step 5 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 3 — Verify Time Synchronization - Screenshot 6](03-VERIFY%20TIME%20SYNCHRONIZATION/SYNCHRONIZATION-%20%286%29.png)

**Continue the configuration (step 6 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 3 — Verify Time Synchronization - Screenshot 7](03-VERIFY%20TIME%20SYNCHRONIZATION/SYNCHRONIZATION-%20%287%29.png)

**Continue the configuration (step 7 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 3 — Verify Time Synchronization - Screenshot 8](03-VERIFY%20TIME%20SYNCHRONIZATION/SYNCHRONIZATION-%20%288%29.png)

**Continue the configuration (step 8 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 3 — Verify Time Synchronization - Screenshot 9](03-VERIFY%20TIME%20SYNCHRONIZATION/SYNCHRONIZATION-%20%289%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 4 — Enable AES-256 Encryption

Enable AES-256 encryption on important accounts for stronger Kerberos security. In ADUC → account properties → Account Options → check:

- ✅ This account supports Kerberos AES 128-bit encryption
- ✅ This account supports Kerberos AES 256-bit encryption

### Screenshot 1

![Step 4 — Enable AES-256 Encryption - Screenshot 1](04-ENABLE%20AES%20ENCRYPTION%20ON%20IMPORTANT%20ACCOUNTS/AES%20ENCRYPTION%20-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 4 — Enable AES-256 Encryption - Screenshot 2](04-ENABLE%20AES%20ENCRYPTION%20ON%20IMPORTANT%20ACCOUNTS/AES%20ENCRYPTION%20-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 4 — Enable AES-256 Encryption - Screenshot 3](04-ENABLE%20AES%20ENCRYPTION%20ON%20IMPORTANT%20ACCOUNTS/AES%20ENCRYPTION%20-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 4 — Enable AES-256 Encryption - Screenshot 4](04-ENABLE%20AES%20ENCRYPTION%20ON%20IMPORTANT%20ACCOUNTS/AES%20ENCRYPTION%20-%20%284%29.png)

**Continue the configuration (step 4 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 4 — Enable AES-256 Encryption - Screenshot 5](04-ENABLE%20AES%20ENCRYPTION%20ON%20IMPORTANT%20ACCOUNTS/AES%20ENCRYPTION%20-%20%285%29.png)

**Continue the configuration (step 5 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 4 — Enable AES-256 Encryption - Screenshot 6](04-ENABLE%20AES%20ENCRYPTION%20ON%20IMPORTANT%20ACCOUNTS/AES%20ENCRYPTION%20-%20%286%29.png)

**Continue the configuration (step 6 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 4 — Enable AES-256 Encryption - Screenshot 7](04-ENABLE%20AES%20ENCRYPTION%20ON%20IMPORTANT%20ACCOUNTS/AES%20ENCRYPTION%20-%20%287%29.png)

**Continue the configuration (step 7 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 4 — Enable AES-256 Encryption - Screenshot 8](04-ENABLE%20AES%20ENCRYPTION%20ON%20IMPORTANT%20ACCOUNTS/AES%20ENCRYPTION%20-%20%288%29.png)

**Continue the configuration (step 8 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 4 — Enable AES-256 Encryption - Screenshot 9](04-ENABLE%20AES%20ENCRYPTION%20ON%20IMPORTANT%20ACCOUNTS/AES%20ENCRYPTION%20-%20%289%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 5 — Configure Kerberos Constrained Delegation

Set up Kerberos Constrained Delegation for service accounts to delegate authentication only to specific services:

```
Service Account Properties → Delegation tab
→ Trust this user for delegation to specified services only
→ Use Kerberos only
→ Add the target service SPN
```

### Screenshot 1

![Step 5 — Configure Kerberos Constrained Delegation - Screenshot 1](05-CONFIGURE%20KERBEROS%20CONSTRAINED%20DELEGATION/DELEGATION-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 5 — Configure Kerberos Constrained Delegation - Screenshot 2](05-CONFIGURE%20KERBEROS%20CONSTRAINED%20DELEGATION/DELEGATION-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 5 — Configure Kerberos Constrained Delegation - Screenshot 3](05-CONFIGURE%20KERBEROS%20CONSTRAINED%20DELEGATION/DELEGATION-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 5 — Configure Kerberos Constrained Delegation - Screenshot 4](05-CONFIGURE%20KERBEROS%20CONSTRAINED%20DELEGATION/DELEGATION-%20%284%29.png)

**Continue the configuration (step 4 of 13) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 5 — Configure Kerberos Constrained Delegation - Screenshot 5](05-CONFIGURE%20KERBEROS%20CONSTRAINED%20DELEGATION/DELEGATION-%20%285%29.png)

**Continue the configuration (step 5 of 13) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 5 — Configure Kerberos Constrained Delegation - Screenshot 6](05-CONFIGURE%20KERBEROS%20CONSTRAINED%20DELEGATION/DELEGATION-%20%286%29.png)

**Continue the configuration (step 6 of 13) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 5 — Configure Kerberos Constrained Delegation - Screenshot 7](05-CONFIGURE%20KERBEROS%20CONSTRAINED%20DELEGATION/DELEGATION-%20%287%29.png)

**Continue the configuration (step 7 of 13) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 5 — Configure Kerberos Constrained Delegation - Screenshot 8](05-CONFIGURE%20KERBEROS%20CONSTRAINED%20DELEGATION/DELEGATION-%20%288%29.png)

**Continue the configuration (step 8 of 13) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 5 — Configure Kerberos Constrained Delegation - Screenshot 9](05-CONFIGURE%20KERBEROS%20CONSTRAINED%20DELEGATION/DELEGATION-%20%289%29.png)

**Continue the configuration (step 9 of 13) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 5 — Configure Kerberos Constrained Delegation - Screenshot 10](05-CONFIGURE%20KERBEROS%20CONSTRAINED%20DELEGATION/DELEGATION-%20%2810%29.png)

**Continue the configuration (step 10 of 13) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 5 — Configure Kerberos Constrained Delegation - Screenshot 11](05-CONFIGURE%20KERBEROS%20CONSTRAINED%20DELEGATION/DELEGATION-%20%2811%29.png)

**Continue the configuration (step 11 of 13) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 5 — Configure Kerberos Constrained Delegation - Screenshot 12](05-CONFIGURE%20KERBEROS%20CONSTRAINED%20DELEGATION/DELEGATION-%20%2812%29.png)

**Continue the configuration (step 12 of 13) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 5 — Configure Kerberos Constrained Delegation - Screenshot 13](05-CONFIGURE%20KERBEROS%20CONSTRAINED%20DELEGATION/DELEGATION-%20%2813%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 6 — Review Kerberos Events

Open **Event Viewer → Windows Logs → Security** and filter for Kerberos events:

- Event ID 4768 — TGT Request (AS-REQ)
- Event ID 4769 — Service Ticket Request (TGS-REQ)
- Event ID 4771 — Kerberos Pre-Authentication Failed

### Screenshot 1

![Step 6 — Review Kerberos Events - Screenshot 1](06-LOOK%20AT%20KERBEROS%20EVENTS%20IN%20EVENT%20VIEWER/EVENT%20VIEWER-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 6 — Review Kerberos Events - Screenshot 2](06-LOOK%20AT%20KERBEROS%20EVENTS%20IN%20EVENT%20VIEWER/EVENT%20VIEWER-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 6 — Review Kerberos Events - Screenshot 3](06-LOOK%20AT%20KERBEROS%20EVENTS%20IN%20EVENT%20VIEWER/EVENT%20VIEWER-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 6 — Review Kerberos Events - Screenshot 4](06-LOOK%20AT%20KERBEROS%20EVENTS%20IN%20EVENT%20VIEWER/EVENT%20VIEWER-%20%284%29.png)

**Final result — verify the configuration is complete and working.**

---

## 🔗 Navigation

[⬆️ Back to Top](#)

[📚 Back to Master README](../README.md)
