# Phase 04 — DNS Configuration

> Configure enterprise DNS on DC1: explore what AD auto-created, build a reverse lookup zone, add PTR records, configure external forwarders, create CNAME aliases, set up a conditional forwarder, and verify everything with `nslookup` from both DC1 and CLIENT1.

---

## Steps

### 01 — Open DNS Manager & Explore Auto-Created Records
AD DS automatically created several DNS records during domain promotion. Explored:
- `vertex.local` Forward Lookup Zone
- `_msdcs.vertex.local` zone (used for DC locator SRV records)
- SOA, NS, A records and SRV records for Kerberos and LDAP

![DNS Manager — AD DS and DNS roles visible in Server Manager](<01-OPEN DNS MANAGER AND EXPLORE WHAT WAS AUTO-CREATED/DNS MANAGER- (1).png>)

---

### 02 — Create the Reverse Lookup Zone
Created a **Reverse Lookup Zone** for the `192.168.x.x` subnet to allow IP-to-hostname resolution (PTR lookups). Configured as an Active Directory-integrated zone for automatic replication to DC2.

**Screenshots:** `02-CREATE THE REVERSE LOOKUP ZONE/`

---

### 03 — Create PTR Records
Added **PTR (Pointer) records** for DC1, DC2, and CLIENT1 in the reverse lookup zone, enabling `nslookup` reverse queries like:
```
nslookup 192.168.1.10
```

**Screenshots:** `03-Create-PTR-Records/`

---

### 04 — Configure Forwarders
Configured **DNS Forwarders** to send external DNS queries (anything outside `vertex.local`) to an upstream DNS resolver:
- Primary: `8.8.8.8` (Google DNS)
- Secondary: `8.8.4.4`

This allows domain-joined machines to resolve internet names through the DC's DNS server.

**Screenshots:** `04-CONFIGURE FORWARDERS/` (10 images)

---

### 05 — Create a CNAME Alias Record
Created a **CNAME record** to alias a friendly name to a server's A record:

```
webserver.vertex.local → DC1.vertex.local
```

This simulates how a file server, web server, or application server might be referenced by a service name rather than a hostname.

**Screenshots:** `05-CREATE A CNAME ALIAS RECORD/`

---

### 06 — Create a Conditional Forwarder
Created a **Conditional Forwarder** to forward DNS queries for a specific external domain to a specific DNS server. This simulates a scenario where two corporate domains need to resolve each other's names (e.g., after a merger).

**Screenshots:** `06-CREATE A CONDITIONAL FORWARDER/`

---

### 07 — Test All DNS with NSLOOKUP
Used `nslookup` on DC1 to verify every DNS configuration:

```cmd
nslookup dc1.vertex.local          # Forward A record
nslookup 192.168.1.10              # Reverse PTR record
nslookup webserver.vertex.local    # CNAME alias
nslookup google.com                # External via forwarder
```

**Screenshots:** `07-TEST ALL DNS WITH NSLOOKUP/`

---

### 08 — DNS Health Verification
Ran `dcdiag /test:dns` to check for DNS errors across the domain and verified:
- All SRV records present
- Both DC1 and DC2 registering correctly
- No DNS delegation errors

**Screenshots:** `08-DNS-Health-Verification/`

---

### 09 — Test DNS from CLIENT1
Ran `nslookup` from CLIENT1's command prompt to confirm:
- CLIENT1 correctly queries DC1 for DNS
- Domain names resolve from the workstation perspective

**Screenshots:** `09-TEST DNS FROM CLIENT1/`

---

## Key Concepts

- **AD-integrated zones** replicate via AD replication, not standard zone transfers
- **Reverse lookup zones** are optional but essential for troubleshooting and some AD features
- **Forwarders** prevent DNS queries from failing for external names — always configure them
- **SRV records** are how clients locate domain controllers, Kerberos KDCs, and LDAP servers — never manually delete them
- `dcdiag /test:dns` is the go-to tool for diagnosing DNS issues in AD environments

---

## Tools Used

`DNS Manager` · `nslookup` · `dcdiag` · `PowerShell`

---

*Previous: [Phase 03 — Users & Computers](<../Phase 03 lab users computers/README.md>) · Next: [Phase 05 — Groups & AGDLP](<../Phase 05 lab groups agdl/README.md>)*
