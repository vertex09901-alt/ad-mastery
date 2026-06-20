# Phase 11 — Enterprise Design & Operational Health

> Review the lab's DC placement and topology against best practices, configure DNS scavenging to clean up stale records, set up Windows Server Backup for Active Directory disaster recovery, enable the AD Recycle Bin, and run domain health checks.

---

## Steps

### 01 — Review DC Placement and Topology
Reviewed the current domain topology against enterprise design principles:

**Current topology:**
- `London-HQ` site: DC1 (PDC), DC2 (Additional DC + Global Catalog)
- `Manchester-Branch` site: No DC (simulated branch without local DC)

**Best practice analysis:**
- ✅ Two DCs in the primary site for redundancy
- ✅ Global Catalog enabled on DC2 for fast attribute lookups
- ⚠️ Branch site without a local DC — users authenticate across the WAN (acceptable for small branches, problematic for large ones)
- ✅ FSMO roles on DC1, which is the PDC Emulator (correct for best performance)

Documented topology using **Active Directory Sites and Services** and verified replication paths.

**Screenshots:** `01-REVIEW DC PLACEMENT AND TOPOLOGY/` (3 images)

---

### 02 — DNS Scavenging (Maintenance)
Over time, DNS accumulates **stale records** — entries for machines that no longer exist or have changed IPs. Configured DNS Scavenging to automatically clean these up:

Settings configured on the `vertex.local` zone:
- **No-refresh interval:** 7 days (records can't be refreshed for this period)
- **Refresh interval:** 7 days (after this, records are eligible for scavenging)
- **Scavenging period:** 7 days (how often the server scans for stale records)

Total age before deletion: 14 days (7 + 7).

Also manually triggered a scavenge to verify the mechanism worked.

**Screenshots:** `02-DNS SCAVENGING (MAINTENANCE)/`

---

### 03 — Windows Server Backup (Disaster Recovery)
Installed the **Windows Server Backup** feature and configured a backup of the **System State** — the minimum required to restore Active Directory:

System State includes:
- NTDS.DIT (AD database)
- SYSVOL
- Registry
- Boot files
- COM+ class registration database
- Certificate Services (if installed)

Backup configuration:
- Backup type: System State
- Schedule: Daily at 02:00
- Destination: Secondary VHD attached to DC1

Verified backup completed successfully and documented the **AD restoration procedure** (requires booting into DSRM mode).

**Screenshots:** `03-WINDOWS SERVER BACKUP (DISASTER RECOVERY)/`

---

### 04 — Enable AD Recycle Bin
Enabled the **Active Directory Recycle Bin** using PowerShell — this feature allows deleted AD objects to be fully restored with all their attributes intact:

```powershell
Enable-ADOptionalFeature -Identity 'Recycle Bin Feature' `
    -Scope ForestOrConfigurationSet `
    -Target 'vertex.local'
```

> ⚠️ This operation is **irreversible** — once enabled, the Recycle Bin cannot be disabled without rebuilding the forest.

Tested by:
1. Deleting a user account in ADUC
2. Restoring it via **Active Directory Administrative Center** → Deleted Objects container
3. Verifying the restored user retained all group memberships and attributes

**Screenshots:** `04-ENABLE AD RECYCLE BIN/`

---

### 05 — Check Domain Health and Capacity
Ran a comprehensive health check of the AD environment:

```cmd
# Full domain controller diagnostics
dcdiag /v

# Test specific areas
dcdiag /test:replications    # AD replication health
dcdiag /test:dns             # DNS health
dcdiag /test:fsmo            # FSMO role accessibility
dcdiag /test:netlogons       # Netlogon service status
dcdiag /test:services        # Critical AD services running

# Check replication summary
repadmin /replsummary

# Check event log for AD errors
Get-EventLog -LogName "Directory Service" -EntryType Error -Newest 20
```

All checks passed ✅ — domain is healthy and ready for the security and attack phases.

**Screenshots:** `05- CHECK DOMAIN HEALTH AND CAPACITY/`

---

## Key Concepts

- **Two DCs per site** is the minimum for production — one DC per site is a single point of failure
- DNS scavenging should be enabled on all AD-integrated DNS zones — stale records cause name resolution failures and NETLOGON issues
- **System State backup** is the correct target for AD backup — not just a file backup of NTDS.DIT
- **AD Recycle Bin** must be enabled *before* you need it — after an accidental deletion without it, recovery is painful (requires either backup restoration or metadata cleanup)
- `dcdiag` is the single most useful tool for AD health checks — run it regularly and after any infrastructure change

---

## Tools Used

`Active Directory Sites and Services` · `DNS Manager` · `Windows Server Backup` · `Active Directory Administrative Center (ADAC)` · `dcdiag` · `repadmin` · `PowerShell`

---

*Previous: [Phase 10 — LDAP](<../Phase 10 lab ldap/README.md>) · Next: [Phase 12 — PowerShell Automation](<../Phase 12 lab powershell ad/README.md>)*
