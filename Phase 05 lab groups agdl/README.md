# Phase 05 — Groups & AGDLP

> Implement Microsoft's AGDLP access model: create Global Security Groups per department, create Domain Local Groups per resource, nest the globals inside the locals, assign file share permissions, and verify access from CLIENT1.

---

## The AGDLP Model

```
Accounts  →  Global Groups  →  Domain Local Groups  →  Permissions
  (users)     (by department)   (by resource)            (on folders/shares)
```

**Why AGDLP?**
- Global groups collect users by role/department
- Domain Local groups collect Global groups and are assigned to resources
- Changing who has access only requires moving a user between Global groups — the permissions on the resource never change

---

## Steps

### 01 — Create Global Security Groups
Created one **Global Security Group** per department to collect all users in that department:

| Group Name | Members |
|------------|---------|
| `GG_IT` | All IT staff |
| `GG_HR` | All HR staff |
| `GG_Finance` | All Finance staff |
| `GG_Sales` | All Sales staff |
| `GG_Management` | All managers |

All groups placed in their respective department OUs.

**Screenshots:** `01 — CREATE GLOBAL SECURITY GROUPS/` (11+ images)

---

### 02 — Create Domain Local Groups
Created **Domain Local Security Groups** scoped to specific shared resources:

| Group Name | Purpose |
|------------|---------|
| `DL_Finance_Share_RW` | Read/Write access to Finance share |
| `DL_Finance_Share_RO` | Read-Only access to Finance share |
| `DL_IT_Admin_Share_Full` | Full control of IT admin share |
| `DL_HR_Share_RW` | Read/Write access to HR share |

**Screenshots:** `02-CREATE DOMAIN LOCAL GROUPS/`

---

### 03 — Create Distribution Groups
Created **Distribution Groups** for email list purposes (non-security):

| Group Name | Purpose |
|------------|---------|
| `DL_AllStaff` | Company-wide email distribution |
| `DL_IT_Team` | IT department email list |

> Distribution groups cannot be used for resource permissions — Security groups only.

**Screenshots:** `03-CREATE DISTRIBUTION GROUPS/`

---

### 04 — Apply DL Group to a File Share (AGDLP in Action)
Created a shared folder on DC1 (`\\DC1\FinanceData`) and configured NTFS and share permissions:

1. Created folder `C:\Shares\FinanceData` on DC1
2. Shared it as `\\DC1\FinanceData`
3. Removed `Everyone` from permissions
4. Added `DL_Finance_Share_RW` → **Modify** (NTFS) + **Change** (Share)
5. Added `DL_Finance_Share_RO` → **Read** (NTFS) + **Read** (Share)
6. Nested `GG_Finance` inside `DL_Finance_Share_RW`
7. Tested access from CLIENT1 logged in as a Finance user — access confirmed ✅

**Screenshots:** `04-APPLY DL GROUP TO A FILE SHARE (AGDLP IN ACTION)/`

---

## Key Concepts

- **Global groups** can contain users from the same domain only
- **Domain Local groups** can contain Global groups from any trusted domain — this is what makes AGDLP scale across forests
- Always assign permissions to **Domain Local groups**, never directly to users
- This model minimises permission changes when staff move departments — just change group membership

---

## Tools Used

`Active Directory Users and Computers (ADUC)` · `File Explorer` · `Windows Share Permissions` · `NTFS Permissions`

---

*Previous: [Phase 04 — DNS Configuration](<../Phase 04 lab dns/README.md>) · Next: [Phase 06 — Group Policy](<../Phase 06 lab group policy/README.md>)*
