# 🌐 Phase 04 — DNS Configuration

> **Explore auto-created DNS zones, create reverse lookup zones and PTR records, configure forwarders, create CNAME alias records, set up conditional forwarders, test DNS resolution with nslookup, verify DNS health, and test from CLIENT1.**

**Prerequisites:** Phase 02 completed — AD-integrated DNS running on DC1.

---
## 📑 Table of Contents

- [Step 1 — Open DNS Manager & Explore Auto-Created Zones](#step-1-open-dns-manager-explore-auto-created-zones)
- [Step 2 — Create the Reverse Lookup Zone](#step-2-create-the-reverse-lookup-zone)
- [Step 3 — Create PTR Records](#step-3-create-ptr-records)
- [Step 4 — Configure DNS Forwarders](#step-4-configure-dns-forwarders)
- [Step 5 — Create a CNAME Alias Record](#step-5-create-a-cname-alias-record)
- [Step 6 — Create a Conditional Forwarder](#step-6-create-a-conditional-forwarder)
- [Step 7 — Test DNS with nslookup](#step-7-test-dns-with-nslookup)
- [Step 8 — DNS Health Verification](#step-8-dns-health-verification)
- [Step 9 — Test DNS from CLIENT1](#step-9-test-dns-from-client1)

---

## Step 1 — Open DNS Manager & Explore Auto-Created Zones

Open DNS Manager from Server Manager → Tools → DNS. Explore the Forward Lookup Zone for `vertex.local` and view auto-created records (SOA, NS, A records for DC1).

### Screenshot 1

![Step 1 — Open DNS Manager & Explore Auto-Created Zones - Screenshot 1](01-OPEN%20DNS%20MANAGER%20AND%20EXPLORE%20WHAT%20WAS%20AUTO-CREATED/DNS%20MANAGER-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 1 — Open DNS Manager & Explore Auto-Created Zones - Screenshot 2](01-OPEN%20DNS%20MANAGER%20AND%20EXPLORE%20WHAT%20WAS%20AUTO-CREATED/DNS%20MANAGER-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 1 — Open DNS Manager & Explore Auto-Created Zones - Screenshot 3](01-OPEN%20DNS%20MANAGER%20AND%20EXPLORE%20WHAT%20WAS%20AUTO-CREATED/DNS%20MANAGER-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 1 — Open DNS Manager & Explore Auto-Created Zones - Screenshot 4](01-OPEN%20DNS%20MANAGER%20AND%20EXPLORE%20WHAT%20WAS%20AUTO-CREATED/DNS%20MANAGER-%20%284%29.png)

**Continue the configuration (step 4 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 1 — Open DNS Manager & Explore Auto-Created Zones - Screenshot 5](01-OPEN%20DNS%20MANAGER%20AND%20EXPLORE%20WHAT%20WAS%20AUTO-CREATED/DNS%20MANAGER-%20%285%29.png)

**Continue the configuration (step 5 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 1 — Open DNS Manager & Explore Auto-Created Zones - Screenshot 6](01-OPEN%20DNS%20MANAGER%20AND%20EXPLORE%20WHAT%20WAS%20AUTO-CREATED/DNS%20MANAGER-%20%286%29.png)

**Continue the configuration (step 6 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 1 — Open DNS Manager & Explore Auto-Created Zones - Screenshot 7](01-OPEN%20DNS%20MANAGER%20AND%20EXPLORE%20WHAT%20WAS%20AUTO-CREATED/DNS%20MANAGER-%20%287%29.png)

**Continue the configuration (step 7 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 1 — Open DNS Manager & Explore Auto-Created Zones - Screenshot 8](01-OPEN%20DNS%20MANAGER%20AND%20EXPLORE%20WHAT%20WAS%20AUTO-CREATED/DNS%20MANAGER-%20%288%29.png)

**Continue the configuration (step 8 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 1 — Open DNS Manager & Explore Auto-Created Zones - Screenshot 9](01-OPEN%20DNS%20MANAGER%20AND%20EXPLORE%20WHAT%20WAS%20AUTO-CREATED/DNS%20MANAGER-%20%289%29.png)

**Continue the configuration (step 9 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 1 — Open DNS Manager & Explore Auto-Created Zones - Screenshot 10](01-OPEN%20DNS%20MANAGER%20AND%20EXPLORE%20WHAT%20WAS%20AUTO-CREATED/DNS%20MANAGER-%20%2810%29.png)

**Continue the configuration (step 10 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 1 — Open DNS Manager & Explore Auto-Created Zones - Screenshot 11](01-OPEN%20DNS%20MANAGER%20AND%20EXPLORE%20WHAT%20WAS%20AUTO-CREATED/DNS%20MANAGER-%20%2811%29.png)

**Continue the configuration (step 11 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 1 — Open DNS Manager & Explore Auto-Created Zones - Screenshot 12](01-OPEN%20DNS%20MANAGER%20AND%20EXPLORE%20WHAT%20WAS%20AUTO-CREATED/DNS%20MANAGER-%20%2812%29.png)

**Continue the configuration (step 12 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 1 — Open DNS Manager & Explore Auto-Created Zones - Screenshot 13](01-OPEN%20DNS%20MANAGER%20AND%20EXPLORE%20WHAT%20WAS%20AUTO-CREATED/DNS%20MANAGER-%20%2813%29.png)

**Continue the configuration (step 13 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 1 — Open DNS Manager & Explore Auto-Created Zones - Screenshot 14](01-OPEN%20DNS%20MANAGER%20AND%20EXPLORE%20WHAT%20WAS%20AUTO-CREATED/DNS%20MANAGER-%20%2814%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 2 — Create the Reverse Lookup Zone

Create a reverse lookup zone for the `192.168.10.x` subnet to enable PTR (pointer) record lookups — translating IPs back to hostnames.

```
Zone Type: Primary Zone
Replication: All DNS servers in vertex.local
Network ID: 192.168.10
```

### Screenshot 1

![Step 2 — Create the Reverse Lookup Zone - Screenshot 1](02-CREATE%20THE%20REVERSE%20LOOKUP%20ZONE/REVERSE%20LOOKUP%20ZONE-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 2 — Create the Reverse Lookup Zone - Screenshot 2](02-CREATE%20THE%20REVERSE%20LOOKUP%20ZONE/REVERSE%20LOOKUP%20ZONE-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 2 — Create the Reverse Lookup Zone - Screenshot 3](02-CREATE%20THE%20REVERSE%20LOOKUP%20ZONE/REVERSE%20LOOKUP%20ZONE-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 2 — Create the Reverse Lookup Zone - Screenshot 4](02-CREATE%20THE%20REVERSE%20LOOKUP%20ZONE/REVERSE%20LOOKUP%20ZONE-%20%284%29.png)

**Continue the configuration (step 4 of 12) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 2 — Create the Reverse Lookup Zone - Screenshot 5](02-CREATE%20THE%20REVERSE%20LOOKUP%20ZONE/REVERSE%20LOOKUP%20ZONE-%20%285%29.png)

**Continue the configuration (step 5 of 12) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 2 — Create the Reverse Lookup Zone - Screenshot 6](02-CREATE%20THE%20REVERSE%20LOOKUP%20ZONE/REVERSE%20LOOKUP%20ZONE-%20%286%29.png)

**Continue the configuration (step 6 of 12) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 2 — Create the Reverse Lookup Zone - Screenshot 7](02-CREATE%20THE%20REVERSE%20LOOKUP%20ZONE/REVERSE%20LOOKUP%20ZONE-%20%287%29.png)

**Continue the configuration (step 7 of 12) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 2 — Create the Reverse Lookup Zone - Screenshot 8](02-CREATE%20THE%20REVERSE%20LOOKUP%20ZONE/REVERSE%20LOOKUP%20ZONE-%20%288%29.png)

**Continue the configuration (step 8 of 12) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 2 — Create the Reverse Lookup Zone - Screenshot 9](02-CREATE%20THE%20REVERSE%20LOOKUP%20ZONE/REVERSE%20LOOKUP%20ZONE-%20%289%29.png)

**Continue the configuration (step 9 of 12) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 2 — Create the Reverse Lookup Zone - Screenshot 10](02-CREATE%20THE%20REVERSE%20LOOKUP%20ZONE/REVERSE%20LOOKUP%20ZONE-%20%2810%29.png)

**Continue the configuration (step 10 of 12) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 2 — Create the Reverse Lookup Zone - Screenshot 11](02-CREATE%20THE%20REVERSE%20LOOKUP%20ZONE/REVERSE%20LOOKUP%20ZONE-%20%2811%29.png)

**Continue the configuration (step 11 of 12) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 2 — Create the Reverse Lookup Zone - Screenshot 12](02-CREATE%20THE%20REVERSE%20LOOKUP%20ZONE/REVERSE%20LOOKUP%20ZONE-%20%2812%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 3 — Create PTR Records

Create PTR records in the reverse lookup zone for DC1 (192.168.10.10), DC2 (192.168.10.11), and CLIENT1 (192.168.10.50).

### Screenshot 1

![Step 3 — Create PTR Records - Screenshot 1](03-Create-PTR-Records/PTR-Records-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 3 — Create PTR Records - Screenshot 2](03-Create-PTR-Records/PTR-Records-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 3 — Create PTR Records - Screenshot 3](03-Create-PTR-Records/PTR-Records-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 3 — Create PTR Records - Screenshot 4](03-Create-PTR-Records/PTR-Records-%20%284%29.png)

**Continue the configuration (step 4 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 3 — Create PTR Records - Screenshot 5](03-Create-PTR-Records/PTR-Records-%20%285%29.png)

**Continue the configuration (step 5 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 3 — Create PTR Records - Screenshot 6](03-Create-PTR-Records/PTR-Records-%20%286%29.png)

**Continue the configuration (step 6 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 3 — Create PTR Records - Screenshot 7](03-Create-PTR-Records/PTR-Records-%20%287%29.png)

**Continue the configuration (step 7 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 3 — Create PTR Records - Screenshot 8](03-Create-PTR-Records/PTR-Records-%20%288%29.png)

**Continue the configuration (step 8 of 9) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 3 — Create PTR Records - Screenshot 9](03-Create-PTR-Records/PTR-Records-%20%289%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 4 — Configure DNS Forwarders

Configure DNS forwarders to resolve external (internet) names. Add public DNS servers:

```
8.8.8.8      (Google DNS)
8.8.4.4      (Google DNS Secondary)
1.1.1.1      (Cloudflare DNS)
```

### Screenshot 1

![Step 4 — Configure DNS Forwarders - Screenshot 1](04-CONFIGURE%20FORWARDERS/CONFIGURE%20FORWARDERS-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 4 — Configure DNS Forwarders - Screenshot 2](04-CONFIGURE%20FORWARDERS/CONFIGURE%20FORWARDERS-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 4 — Configure DNS Forwarders - Screenshot 3](04-CONFIGURE%20FORWARDERS/CONFIGURE%20FORWARDERS-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 4 — Configure DNS Forwarders - Screenshot 4](04-CONFIGURE%20FORWARDERS/CONFIGURE%20FORWARDERS-%20%284%29.png)

**Continue the configuration (step 4 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 4 — Configure DNS Forwarders - Screenshot 5](04-CONFIGURE%20FORWARDERS/CONFIGURE%20FORWARDERS-%20%285%29.png)

**Continue the configuration (step 5 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 4 — Configure DNS Forwarders - Screenshot 6](04-CONFIGURE%20FORWARDERS/CONFIGURE%20FORWARDERS-%20%286%29.png)

**Continue the configuration (step 6 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 4 — Configure DNS Forwarders - Screenshot 7](04-CONFIGURE%20FORWARDERS/CONFIGURE%20FORWARDERS-%20%287%29.png)

**Continue the configuration (step 7 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 4 — Configure DNS Forwarders - Screenshot 8](04-CONFIGURE%20FORWARDERS/CONFIGURE%20FORWARDERS-%20%288%29.png)

**Continue the configuration (step 8 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 4 — Configure DNS Forwarders - Screenshot 9](04-CONFIGURE%20FORWARDERS/CONFIGURE%20FORWARDERS-%20%289%29.png)

**Continue the configuration (step 9 of 10) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 4 — Configure DNS Forwarders - Screenshot 10](04-CONFIGURE%20FORWARDERS/CONFIGURE%20FORWARDERS-%20%2810%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 5 — Create a CNAME Alias Record

Create a CNAME (Canonical Name) record to create an alias for a server. For example, `intranet.vertex.local` → `DC1.vertex.local`.

### Screenshot 1

![Step 5 — Create a CNAME Alias Record - Screenshot 1](05-CREATE%20A%20CNAME%20ALIAS%20RECORD/CNAME-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 5 — Create a CNAME Alias Record - Screenshot 2](05-CREATE%20A%20CNAME%20ALIAS%20RECORD/CNAME-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 5 — Create a CNAME Alias Record - Screenshot 3](05-CREATE%20A%20CNAME%20ALIAS%20RECORD/CNAME-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 5 — Create a CNAME Alias Record - Screenshot 4](05-CREATE%20A%20CNAME%20ALIAS%20RECORD/CNAME-%20%284%29.png)

**Continue the configuration (step 4 of 5) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 5 — Create a CNAME Alias Record - Screenshot 5](05-CREATE%20A%20CNAME%20ALIAS%20RECORD/CNAME-%20%285%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 6 — Create a Conditional Forwarder

Create a conditional forwarder to forward DNS queries for a specific domain to designated DNS servers. Useful for multi-forest environments.

### Screenshot 1

![Step 6 — Create a Conditional Forwarder - Screenshot 1](06-CREATE%20A%20CONDITIONAL%20FORWARDER/CONDITIONAL%20FORWARDER-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 6 — Create a Conditional Forwarder - Screenshot 2](06-CREATE%20A%20CONDITIONAL%20FORWARDER/CONDITIONAL%20FORWARDER-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 6 — Create a Conditional Forwarder - Screenshot 3](06-CREATE%20A%20CONDITIONAL%20FORWARDER/CONDITIONAL%20FORWARDER-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 6 — Create a Conditional Forwarder - Screenshot 4](06-CREATE%20A%20CONDITIONAL%20FORWARDER/CONDITIONAL%20FORWARDER-%20%284%29.png)

**Continue the configuration (step 4 of 7) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 6 — Create a Conditional Forwarder - Screenshot 5](06-CREATE%20A%20CONDITIONAL%20FORWARDER/CONDITIONAL%20FORWARDER-%20%285%29.png)

**Continue the configuration (step 5 of 7) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 6 — Create a Conditional Forwarder - Screenshot 6](06-CREATE%20A%20CONDITIONAL%20FORWARDER/CONDITIONAL%20FORWARDER-%20%286%29.png)

**Continue the configuration (step 6 of 7) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 6 — Create a Conditional Forwarder - Screenshot 7](06-CREATE%20A%20CONDITIONAL%20FORWARDER/CONDITIONAL%20FORWARDER-%20%287%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 7 — Test DNS with nslookup

Verify all DNS records work correctly using `nslookup`:

```cmd
nslookup DC1.vertex.local
nslookup DC2.vertex.local
nslookup vertex.local
nslookup 192.168.10.10
nslookup 192.168.10.11
```

### Screenshot 1

![Step 7 — Test DNS with nslookup - Screenshot 1](07-TEST%20ALL%20DNS%20WITH%20NSLOOKUP/NSLOOKUP-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 7 — Test DNS with nslookup - Screenshot 2](07-TEST%20ALL%20DNS%20WITH%20NSLOOKUP/NSLOOKUP-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 7 — Test DNS with nslookup - Screenshot 3](07-TEST%20ALL%20DNS%20WITH%20NSLOOKUP/NSLOOKUP-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 7 — Test DNS with nslookup - Screenshot 4](07-TEST%20ALL%20DNS%20WITH%20NSLOOKUP/NSLOOKUP-%20%284%29.png)

**Continue the configuration (step 4 of 7) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 7 — Test DNS with nslookup - Screenshot 5](07-TEST%20ALL%20DNS%20WITH%20NSLOOKUP/NSLOOKUP-%20%285%29.png)

**Continue the configuration (step 5 of 7) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 7 — Test DNS with nslookup - Screenshot 6](07-TEST%20ALL%20DNS%20WITH%20NSLOOKUP/NSLOOKUP-%20%286%29.png)

**Continue the configuration (step 6 of 7) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 7 — Test DNS with nslookup - Screenshot 7](07-TEST%20ALL%20DNS%20WITH%20NSLOOKUP/NSLOOKUP-%20%287%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 8 — DNS Health Verification

Run DNS diagnostic commands to verify DNS health:

```cmd
dcdiag /test:dns
nslookup -type=SOA vertex.local
nslookup -type=NS vertex.local
```

### Screenshot 1

![Step 8 — DNS Health Verification - Screenshot 1](08-DNS-Health-Verification/Health-Verification-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 8 — DNS Health Verification - Screenshot 2](08-DNS-Health-Verification/Health-Verification-%20%282%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 9 — Test DNS from CLIENT1

Log into CLIENT1 and verify it can resolve all domain names:

```cmd
nslookup vertex.local
nslookup DC1.vertex.local
nslookup DC2.vertex.local
ipconfig /all
```

### Screenshot 1

![Step 9 — Test DNS from CLIENT1 - Screenshot 1](09-TEST%20DNS%20FROM%20CLIENT1/TEST%20DNS-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 9 — Test DNS from CLIENT1 - Screenshot 2](09-TEST%20DNS%20FROM%20CLIENT1/TEST%20DNS-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 9 — Test DNS from CLIENT1 - Screenshot 3](09-TEST%20DNS%20FROM%20CLIENT1/TEST%20DNS-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 9 — Test DNS from CLIENT1 - Screenshot 4](09-TEST%20DNS%20FROM%20CLIENT1/TEST%20DNS-%20%284%29.png)

**Continue the configuration (step 4 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 9 — Test DNS from CLIENT1 - Screenshot 5](09-TEST%20DNS%20FROM%20CLIENT1/TEST%20DNS-%20%285%29.png)

**Continue the configuration (step 5 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 9 — Test DNS from CLIENT1 - Screenshot 6](09-TEST%20DNS%20FROM%20CLIENT1/TEST%20DNS-%20%286%29.png)

**Continue the configuration (step 6 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 9 — Test DNS from CLIENT1 - Screenshot 7](09-TEST%20DNS%20FROM%20CLIENT1/TEST%20DNS-%20%287%29.png)

**Continue the configuration (step 7 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 9 — Test DNS from CLIENT1 - Screenshot 8](09-TEST%20DNS%20FROM%20CLIENT1/TEST%20DNS-%20%288%29.png)

**Continue the configuration (step 8 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 9 — Test DNS from CLIENT1 - Screenshot 9](09-TEST%20DNS%20FROM%20CLIENT1/TEST%20DNS-%20%289%29.png)

**Continue the configuration (step 9 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 9 — Test DNS from CLIENT1 - Screenshot 10](09-TEST%20DNS%20FROM%20CLIENT1/TEST%20DNS-%20%2810%29.png)

**Continue the configuration (step 10 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 9 — Test DNS from CLIENT1 - Screenshot 11](09-TEST%20DNS%20FROM%20CLIENT1/TEST%20DNS-%20%2811%29.png)

**Continue the configuration (step 11 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 9 — Test DNS from CLIENT1 - Screenshot 12](09-TEST%20DNS%20FROM%20CLIENT1/TEST%20DNS-%20%2812%29.png)

**Continue the configuration (step 12 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 9 — Test DNS from CLIENT1 - Screenshot 13](09-TEST%20DNS%20FROM%20CLIENT1/TEST%20DNS-%20%2813%29.png)

**Continue the configuration (step 13 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 9 — Test DNS from CLIENT1 - Screenshot 14](09-TEST%20DNS%20FROM%20CLIENT1/TEST%20DNS-%20%2814%29.png)

**Final result — verify the configuration is complete and working.**

---

## 🔗 Navigation

[⬆️ Back to Top](#)

[📚 Back to Master README](../README.md)
