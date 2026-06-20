# 🔒 Phase 08 — AD Security Hardening

> **Implement admin tiering (Tier 0/1/2 accounts), delegate password reset to Helpdesk, deploy LAPS for local admin passwords, configure Protected Users group, create Fine-Grained Password Policies (PSOs), and verify security audit events.**

**Prerequisites:** Phase 06 completed — GPOs in place for baseline security.

---
## 📑 Table of Contents

- [Step 1 — Implement Admin Tiering](#step-1-implement-admin-tiering)
- [Step 2 — Delegate Password Reset to Helpdesk](#step-2-delegate-password-reset-to-helpdesk)
- [Step 3 — Deploy LAPS](#step-3-deploy-laps)
- [Step 4 — Configure Protected Users Group](#step-4-configure-protected-users-group)
- [Step 5 — Create Fine-Grained Password Policies](#step-5-create-fine-grained-password-policies)
- [Step 6 — Verify Security Audit Events](#step-6-verify-security-audit-events)

---

## Step 1 — Implement Admin Tiering

Create tiered admin accounts following Microsoft's Enterprise Access Model:

```
Tier 0 — Domain Controllers & AD infrastructure
Tier 1 — Server administration
Tier 2 — Workstation & end-user support
```

Create separate admin accounts for each tier (e.g., `t0-admin`, `t1-admin`, `t2-admin`).

### Screenshot 1

![Step 1 — Implement Admin Tiering - Screenshot 1](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 1 — Implement Admin Tiering - Screenshot 2](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 1 — Implement Admin Tiering - Screenshot 3](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 1 — Implement Admin Tiering - Screenshot 4](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%284%29.png)

**Continue the configuration (step 4 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 1 — Implement Admin Tiering - Screenshot 5](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%285%29.png)

**Continue the configuration (step 5 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 1 — Implement Admin Tiering - Screenshot 6](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%286%29.png)

**Continue the configuration (step 6 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 1 — Implement Admin Tiering - Screenshot 7](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%287%29.png)

**Continue the configuration (step 7 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 1 — Implement Admin Tiering - Screenshot 8](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%288%29.png)

**Continue the configuration (step 8 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 1 — Implement Admin Tiering - Screenshot 9](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%289%29.png)

**Continue the configuration (step 9 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 1 — Implement Admin Tiering - Screenshot 10](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2810%29.png)

**Continue the configuration (step 10 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 1 — Implement Admin Tiering - Screenshot 11](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2811%29.png)

**Continue the configuration (step 11 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 1 — Implement Admin Tiering - Screenshot 12](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2812%29.png)

**Continue the configuration (step 12 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 1 — Implement Admin Tiering - Screenshot 13](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2813%29.png)

**Continue the configuration (step 13 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 1 — Implement Admin Tiering - Screenshot 14](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2814%29.png)

**Continue the configuration (step 14 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 1 — Implement Admin Tiering - Screenshot 15](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2815%29.png)

**Continue the configuration (step 15 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 1 — Implement Admin Tiering - Screenshot 16](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2816%29.png)

**Continue the configuration (step 16 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 1 — Implement Admin Tiering - Screenshot 17](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2817%29.png)

**Continue the configuration (step 17 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 1 — Implement Admin Tiering - Screenshot 18](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2818%29.png)

**Continue the configuration (step 18 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 1 — Implement Admin Tiering - Screenshot 19](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2819%29.png)

**Continue the configuration (step 19 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 1 — Implement Admin Tiering - Screenshot 20](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2820%29.png)

**Continue the configuration (step 20 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 1 — Implement Admin Tiering - Screenshot 21](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2821%29.png)

**Continue the configuration (step 21 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 22

![Step 1 — Implement Admin Tiering - Screenshot 22](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2822%29.png)

**Continue the configuration (step 22 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 23

![Step 1 — Implement Admin Tiering - Screenshot 23](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2823%29.png)

**Continue the configuration (step 23 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 24

![Step 1 — Implement Admin Tiering - Screenshot 24](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2824%29.png)

**Continue the configuration (step 24 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 25

![Step 1 — Implement Admin Tiering - Screenshot 25](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2825%29.png)

**Continue the configuration (step 25 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 26

![Step 1 — Implement Admin Tiering - Screenshot 26](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2826%29.png)

**Continue the configuration (step 26 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 27

![Step 1 — Implement Admin Tiering - Screenshot 27](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2827%29.png)

**Continue the configuration (step 27 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 28

![Step 1 — Implement Admin Tiering - Screenshot 28](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2828%29.png)

**Continue the configuration (step 28 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 29

![Step 1 — Implement Admin Tiering - Screenshot 29](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2829%29.png)

**Continue the configuration (step 29 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 30

![Step 1 — Implement Admin Tiering - Screenshot 30](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2830%29.png)

**Continue the configuration (step 30 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 31

![Step 1 — Implement Admin Tiering - Screenshot 31](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2831%29.png)

**Continue the configuration (step 31 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 32

![Step 1 — Implement Admin Tiering - Screenshot 32](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2832%29.png)

**Continue the configuration (step 32 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 33

![Step 1 — Implement Admin Tiering - Screenshot 33](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2833%29.png)

**Continue the configuration (step 33 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 34

![Step 1 — Implement Admin Tiering - Screenshot 34](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2834%29.png)

**Continue the configuration (step 34 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 35

![Step 1 — Implement Admin Tiering - Screenshot 35](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2835%29.png)

**Continue the configuration (step 35 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 36

![Step 1 — Implement Admin Tiering - Screenshot 36](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2836%29.png)

**Continue the configuration (step 36 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 37

![Step 1 — Implement Admin Tiering - Screenshot 37](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2837%29.png)

**Continue the configuration (step 37 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 38

![Step 1 — Implement Admin Tiering - Screenshot 38](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2838%29.png)

**Continue the configuration (step 38 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 39

![Step 1 — Implement Admin Tiering - Screenshot 39](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2839%29.png)

**Continue the configuration (step 39 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 40

![Step 1 — Implement Admin Tiering - Screenshot 40](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2840%29.png)

**Continue the configuration (step 40 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 41

![Step 1 — Implement Admin Tiering - Screenshot 41](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2841%29.png)

**Continue the configuration (step 41 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 42

![Step 1 — Implement Admin Tiering - Screenshot 42](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2842%29.png)

**Continue the configuration (step 42 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 43

![Step 1 — Implement Admin Tiering - Screenshot 43](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2843%29.png)

**Continue the configuration (step 43 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 44

![Step 1 — Implement Admin Tiering - Screenshot 44](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2844%29.png)

**Continue the configuration (step 44 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 45

![Step 1 — Implement Admin Tiering - Screenshot 45](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2845%29.png)

**Continue the configuration (step 45 of 46) — follow the red arrows/boxes for guidance.**

### Screenshot 46

![Step 1 — Implement Admin Tiering - Screenshot 46](01-TIERING%20ADMIN%20ACCOUNTS/TIERING%20ADMIN%20ACCOUNTS-%20%2846%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 2 — Delegate Password Reset to Helpdesk

Use the Delegation of Control Wizard to grant the Helpdesk group permission to reset user passwords in specific OUs — without giving them full admin rights.

### Screenshot 1

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 1](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 2](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 3](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 4](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%284%29.png)

**Continue the configuration (step 4 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 5](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%285%29.png)

**Continue the configuration (step 5 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 6](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%286%29.png)

**Continue the configuration (step 6 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 7](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%287%29.png)

**Continue the configuration (step 7 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 8](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%288%29.png)

**Continue the configuration (step 8 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 9](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%289%29.png)

**Continue the configuration (step 9 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 10](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2810%29.png)

**Continue the configuration (step 10 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 11](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2811%29.png)

**Continue the configuration (step 11 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 12](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2812%29.png)

**Continue the configuration (step 12 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 13](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2813%29.png)

**Continue the configuration (step 13 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 14](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2814%29.png)

**Continue the configuration (step 14 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 15](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2815%29.png)

**Continue the configuration (step 15 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 16](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2816%29.png)

**Continue the configuration (step 16 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 17](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2817%29.png)

**Continue the configuration (step 17 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 18](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2818%29.png)

**Continue the configuration (step 18 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 19](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2819%29.png)

**Continue the configuration (step 19 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 20](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2820%29.png)

**Continue the configuration (step 20 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 21](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2821%29.png)

**Continue the configuration (step 21 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 22

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 22](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2822%29.png)

**Continue the configuration (step 22 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 23

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 23](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2823%29.png)

**Continue the configuration (step 23 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 24

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 24](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2824%29.png)

**Continue the configuration (step 24 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 25

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 25](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2825%29.png)

**Continue the configuration (step 25 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 26

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 26](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2826%29.png)

**Continue the configuration (step 26 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 27

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 27](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2827%29.png)

**Continue the configuration (step 27 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 28

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 28](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2828%29.png)

**Continue the configuration (step 28 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 29

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 29](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2829%29.png)

**Continue the configuration (step 29 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 30

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 30](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2830%29.png)

**Continue the configuration (step 30 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 31

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 31](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2831%29.png)

**Continue the configuration (step 31 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 32

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 32](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2832%29.png)

**Continue the configuration (step 32 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 33

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 33](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2833%29.png)

**Continue the configuration (step 33 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 34

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 34](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2834%29.png)

**Continue the configuration (step 34 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 35

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 35](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2835%29.png)

**Continue the configuration (step 35 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 36

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 36](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2836%29.png)

**Continue the configuration (step 36 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 37

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 37](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2837%29.png)

**Continue the configuration (step 37 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 38

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 38](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2838%29.png)

**Continue the configuration (step 38 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 39

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 39](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2839%29.png)

**Continue the configuration (step 39 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 40

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 40](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2840%29.png)

**Continue the configuration (step 40 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 41

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 41](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2841%29.png)

**Continue the configuration (step 41 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 42

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 42](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2842%29.png)

**Continue the configuration (step 42 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 43

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 43](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2843%29.png)

**Continue the configuration (step 43 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 44

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 44](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2844%29.png)

**Continue the configuration (step 44 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 45

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 45](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2845%29.png)

**Continue the configuration (step 45 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 46

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 46](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2846%29.png)

**Continue the configuration (step 46 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 47

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 47](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2847%29.png)

**Continue the configuration (step 47 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 48

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 48](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2848%29.png)

**Continue the configuration (step 48 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 49

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 49](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2849%29.png)

**Continue the configuration (step 49 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 50

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 50](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2850%29.png)

**Continue the configuration (step 50 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 51

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 51](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2851%29.png)

**Continue the configuration (step 51 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 52

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 52](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2852%29.png)

**Continue the configuration (step 52 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 53

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 53](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2853%29.png)

**Continue the configuration (step 53 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 54

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 54](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2854%29.png)

**Continue the configuration (step 54 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 55

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 55](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2855%29.png)

**Continue the configuration (step 55 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 56

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 56](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2856%29.png)

**Continue the configuration (step 56 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 57

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 57](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2857%29.png)

**Continue the configuration (step 57 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 58

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 58](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2858%29.png)

**Continue the configuration (step 58 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 59

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 59](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2859%29.png)

**Continue the configuration (step 59 of 60) — follow the red arrows/boxes for guidance.**

### Screenshot 60

![Step 2 — Delegate Password Reset to Helpdesk - Screenshot 60](02-DELEGATE%20PASSWORD%20RESET%20TO%20HELPDESK/DELEGATE%20PASSWORD-%20%2860%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 3 — Deploy LAPS

Install and configure LAPS (Local Administrator Password Solution) to automatically manage and rotate local admin passwords on domain-joined computers:

```powershell
# Extend AD Schema for LAPS
Update-LapsADSchema

# Configure LAPS via GPO
# Enable LAPS, set password complexity, rotation schedule
```

### Screenshot 1

![Step 3 — Deploy LAPS - Screenshot 1](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 3 — Deploy LAPS - Screenshot 2](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 3 — Deploy LAPS - Screenshot 3](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 3 — Deploy LAPS - Screenshot 4](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%284%29.png)

**Continue the configuration (step 4 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 3 — Deploy LAPS - Screenshot 5](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%285%29.png)

**Continue the configuration (step 5 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 3 — Deploy LAPS - Screenshot 6](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%286%29.png)

**Continue the configuration (step 6 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 3 — Deploy LAPS - Screenshot 7](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%287%29.png)

**Continue the configuration (step 7 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 3 — Deploy LAPS - Screenshot 8](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%288%29.png)

**Continue the configuration (step 8 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 3 — Deploy LAPS - Screenshot 9](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%289%29.png)

**Continue the configuration (step 9 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 3 — Deploy LAPS - Screenshot 10](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2810%29.png)

**Continue the configuration (step 10 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 3 — Deploy LAPS - Screenshot 11](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2811%29.png)

**Continue the configuration (step 11 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 3 — Deploy LAPS - Screenshot 12](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2812%29.png)

**Continue the configuration (step 12 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 3 — Deploy LAPS - Screenshot 13](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2813%29.png)

**Continue the configuration (step 13 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 3 — Deploy LAPS - Screenshot 14](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2814%29.png)

**Continue the configuration (step 14 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 3 — Deploy LAPS - Screenshot 15](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2815%29.png)

**Continue the configuration (step 15 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 3 — Deploy LAPS - Screenshot 16](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2816%29.png)

**Continue the configuration (step 16 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 3 — Deploy LAPS - Screenshot 17](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2817%29.png)

**Continue the configuration (step 17 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 3 — Deploy LAPS - Screenshot 18](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2818%29.png)

**Continue the configuration (step 18 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 3 — Deploy LAPS - Screenshot 19](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2819%29.png)

**Continue the configuration (step 19 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 3 — Deploy LAPS - Screenshot 20](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2820%29.png)

**Continue the configuration (step 20 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 3 — Deploy LAPS - Screenshot 21](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2821%29.png)

**Continue the configuration (step 21 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 22

![Step 3 — Deploy LAPS - Screenshot 22](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2822%29.png)

**Continue the configuration (step 22 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 23

![Step 3 — Deploy LAPS - Screenshot 23](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2823%29.png)

**Continue the configuration (step 23 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 24

![Step 3 — Deploy LAPS - Screenshot 24](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2824%29.png)

**Continue the configuration (step 24 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 25

![Step 3 — Deploy LAPS - Screenshot 25](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2825%29.png)

**Continue the configuration (step 25 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 26

![Step 3 — Deploy LAPS - Screenshot 26](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2826%29.png)

**Continue the configuration (step 26 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 27

![Step 3 — Deploy LAPS - Screenshot 27](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2827%29.png)

**Continue the configuration (step 27 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 28

![Step 3 — Deploy LAPS - Screenshot 28](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2828%29.png)

**Continue the configuration (step 28 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 29

![Step 3 — Deploy LAPS - Screenshot 29](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2829%29.png)

**Continue the configuration (step 29 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 30

![Step 3 — Deploy LAPS - Screenshot 30](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2830%29.png)

**Continue the configuration (step 30 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 31

![Step 3 — Deploy LAPS - Screenshot 31](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2831%29.png)

**Continue the configuration (step 31 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 32

![Step 3 — Deploy LAPS - Screenshot 32](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2832%29.png)

**Continue the configuration (step 32 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 33

![Step 3 — Deploy LAPS - Screenshot 33](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2833%29.png)

**Continue the configuration (step 33 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 34

![Step 3 — Deploy LAPS - Screenshot 34](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2834%29.png)

**Continue the configuration (step 34 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 35

![Step 3 — Deploy LAPS - Screenshot 35](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2835%29.png)

**Continue the configuration (step 35 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 36

![Step 3 — Deploy LAPS - Screenshot 36](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2836%29.png)

**Continue the configuration (step 36 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 37

![Step 3 — Deploy LAPS - Screenshot 37](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2837%29.png)

**Continue the configuration (step 37 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 38

![Step 3 — Deploy LAPS - Screenshot 38](03-LAPS%20(LOCAL%20ADMINISTRATOR%20PASSWORD%20SOLUTION)/LAPS-%20%2838%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 4 — Configure Protected Users Group

Add high-privilege accounts to the **Protected Users** security group. Members get additional Kerberos protections:

- No NTLM authentication
- No DES or RC4 encryption
- No delegation
- TGT lifetime limited to 4 hours

### Screenshot 1

![Step 4 — Configure Protected Users Group - Screenshot 1](04-PROTECTED%20USERS%20GROUP/PROTECTED%20USERS-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 4 — Configure Protected Users Group - Screenshot 2](04-PROTECTED%20USERS%20GROUP/PROTECTED%20USERS-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 4 — Configure Protected Users Group - Screenshot 3](04-PROTECTED%20USERS%20GROUP/PROTECTED%20USERS-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 4 — Configure Protected Users Group - Screenshot 4](04-PROTECTED%20USERS%20GROUP/PROTECTED%20USERS-%20%284%29.png)

**Continue the configuration (step 4 of 5) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 4 — Configure Protected Users Group - Screenshot 5](04-PROTECTED%20USERS%20GROUP/PROTECTED%20USERS-%20%285%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 5 — Create Fine-Grained Password Policies

Create Password Settings Objects (PSOs) to apply different password policies to different groups:

```powershell
New-ADFineGrainedPasswordPolicy -Name 'AdminPasswordPolicy' `
    -Precedence 10 `
    -MinPasswordLength 16 `
    -MaxPasswordAge '30.00:00:00' `
    -PasswordHistoryCount 24 `
    -ComplexityEnabled $true `
    -LockoutThreshold 3
```

### Screenshot 1

![Step 5 — Create Fine-Grained Password Policies - Screenshot 1](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 5 — Create Fine-Grained Password Policies - Screenshot 2](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 5 — Create Fine-Grained Password Policies - Screenshot 3](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 5 — Create Fine-Grained Password Policies - Screenshot 4](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%284%29.png)

**Continue the configuration (step 4 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 5 — Create Fine-Grained Password Policies - Screenshot 5](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%285%29.png)

**Continue the configuration (step 5 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 5 — Create Fine-Grained Password Policies - Screenshot 6](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%286%29.png)

**Continue the configuration (step 6 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 5 — Create Fine-Grained Password Policies - Screenshot 7](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%287%29.png)

**Continue the configuration (step 7 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 5 — Create Fine-Grained Password Policies - Screenshot 8](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%288%29.png)

**Continue the configuration (step 8 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 5 — Create Fine-Grained Password Policies - Screenshot 9](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%289%29.png)

**Continue the configuration (step 9 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 5 — Create Fine-Grained Password Policies - Screenshot 10](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%2810%29.png)

**Continue the configuration (step 10 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 5 — Create Fine-Grained Password Policies - Screenshot 11](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%2811%29.png)

**Continue the configuration (step 11 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 5 — Create Fine-Grained Password Policies - Screenshot 12](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%2812%29.png)

**Continue the configuration (step 12 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 5 — Create Fine-Grained Password Policies - Screenshot 13](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%2813%29.png)

**Continue the configuration (step 13 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 5 — Create Fine-Grained Password Policies - Screenshot 14](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%2814%29.png)

**Continue the configuration (step 14 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 5 — Create Fine-Grained Password Policies - Screenshot 15](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%2815%29.png)

**Continue the configuration (step 15 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 5 — Create Fine-Grained Password Policies - Screenshot 16](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%2816%29.png)

**Continue the configuration (step 16 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 5 — Create Fine-Grained Password Policies - Screenshot 17](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%2817%29.png)

**Continue the configuration (step 17 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 5 — Create Fine-Grained Password Policies - Screenshot 18](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%2818%29.png)

**Continue the configuration (step 18 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 5 — Create Fine-Grained Password Policies - Screenshot 19](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%2819%29.png)

**Continue the configuration (step 19 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 5 — Create Fine-Grained Password Policies - Screenshot 20](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%2820%29.png)

**Continue the configuration (step 20 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 5 — Create Fine-Grained Password Policies - Screenshot 21](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%2821%29.png)

**Continue the configuration (step 21 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 22

![Step 5 — Create Fine-Grained Password Policies - Screenshot 22](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%2822%29.png)

**Continue the configuration (step 22 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 23

![Step 5 — Create Fine-Grained Password Policies - Screenshot 23](05-FINE-GRAINED%20PASSWORD%20POLICIES%20(PSO)/%28PSO%29-%20%2823%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 6 — Verify Security Audit Events

Open **Event Viewer → Windows Logs → Security** to verify audit events are being logged correctly. Check for:

- Event ID 4624 — Successful logon
- Event ID 4625 — Failed logon
- Event ID 4720 — User account created
- Event ID 4732 — Member added to security group

### Screenshot 1

![Step 6 — Verify Security Audit Events - Screenshot 1](06-SECURITY%20AUDIT%20EVENT%20VERIFICATION/SECURITY%20AUDIT-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 6 — Verify Security Audit Events - Screenshot 2](06-SECURITY%20AUDIT%20EVENT%20VERIFICATION/SECURITY%20AUDIT-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 6 — Verify Security Audit Events - Screenshot 3](06-SECURITY%20AUDIT%20EVENT%20VERIFICATION/SECURITY%20AUDIT-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 6 — Verify Security Audit Events - Screenshot 4](06-SECURITY%20AUDIT%20EVENT%20VERIFICATION/SECURITY%20AUDIT-%20%284%29.png)

**Continue the configuration (step 4 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 6 — Verify Security Audit Events - Screenshot 5](06-SECURITY%20AUDIT%20EVENT%20VERIFICATION/SECURITY%20AUDIT-%20%285%29.png)

**Continue the configuration (step 5 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 6 — Verify Security Audit Events - Screenshot 6](06-SECURITY%20AUDIT%20EVENT%20VERIFICATION/SECURITY%20AUDIT-%20%286%29.png)

**Continue the configuration (step 6 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 6 — Verify Security Audit Events - Screenshot 7](06-SECURITY%20AUDIT%20EVENT%20VERIFICATION/SECURITY%20AUDIT-%20%287%29.png)

**Continue the configuration (step 7 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 6 — Verify Security Audit Events - Screenshot 8](06-SECURITY%20AUDIT%20EVENT%20VERIFICATION/SECURITY%20AUDIT-%20%288%29.png)

**Continue the configuration (step 8 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 6 — Verify Security Audit Events - Screenshot 9](06-SECURITY%20AUDIT%20EVENT%20VERIFICATION/SECURITY%20AUDIT-%20%289%29.png)

**Continue the configuration (step 9 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 6 — Verify Security Audit Events - Screenshot 10](06-SECURITY%20AUDIT%20EVENT%20VERIFICATION/SECURITY%20AUDIT-%20%2810%29.png)

**Continue the configuration (step 10 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 6 — Verify Security Audit Events - Screenshot 11](06-SECURITY%20AUDIT%20EVENT%20VERIFICATION/SECURITY%20AUDIT-%20%2811%29.png)

**Continue the configuration (step 11 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 6 — Verify Security Audit Events - Screenshot 12](06-SECURITY%20AUDIT%20EVENT%20VERIFICATION/SECURITY%20AUDIT-%20%2812%29.png)

**Continue the configuration (step 12 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 6 — Verify Security Audit Events - Screenshot 13](06-SECURITY%20AUDIT%20EVENT%20VERIFICATION/SECURITY%20AUDIT-%20%2813%29.png)

**Continue the configuration (step 13 of 14) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 6 — Verify Security Audit Events - Screenshot 14](06-SECURITY%20AUDIT%20EVENT%20VERIFICATION/SECURITY%20AUDIT-%20%2814%29.png)

**Final result — verify the configuration is complete and working.**

---

## 🔗 Navigation

[⬆️ Back to Top](#)

[📚 Back to Master README](../README.md)
