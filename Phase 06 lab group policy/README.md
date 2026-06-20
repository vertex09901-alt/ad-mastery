# 📋 Phase 06 — Group Policy

> **Open GPMC, create and link GPOs: Base Security Policy, Finance Security Policy, IT Admin Policy, Desktop Policy, Audit Policy, and Loopback Processing for shared PCs. Enforce base policy and test with gpresult.**

**Prerequisites:** Phase 05 completed — groups and users in place.

---
## 📑 Table of Contents

- [Step 1 — Open GPMC & Create Base Security GPO](#step-1-open-gpmc-create-base-security-gpo)
- [Step 2 — GPO: Finance Security Policy](#step-2-gpo:-finance-security-policy)
- [Step 3 — GPO: IT Admin Policy](#step-3-gpo:-it-admin-policy)
- [Step 4 — GPO: Desktop Policy](#step-4-gpo:-desktop-policy)
- [Step 5 — GPO: Audit Policy](#step-5-gpo:-audit-policy)
- [Step 6 — GPO: Loopback Processing for Shared PCs](#step-6-gpo:-loopback-processing-for-shared-pcs)
- [Step 7 — Enforce Base Policy & Test with gpresult](#step-7-enforce-base-policy-test-with-gpresult)

---

## Step 1 — Open GPMC & Create Base Security GPO

Open the Group Policy Management Console (GPMC) from Server Manager → Tools → Group Policy Management. Create and link the **Base Security Policy** GPO to the domain.

**Base GPO Settings:**
- Password Policy: Min 12 chars, complexity enabled, max age 90 days
- Account Lockout: 5 attempts, 30 min lockout, 30 min reset
- Audit Policy: Success/Failure for logon events

### Screenshot 1

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 1](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 2](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 3](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 4](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%284%29.png)

**Continue the configuration (step 4 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 5](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%285%29.png)

**Continue the configuration (step 5 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 6](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%286%29.png)

**Continue the configuration (step 6 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 7](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%287%29.png)

**Continue the configuration (step 7 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 8](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%288%29.png)

**Continue the configuration (step 8 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 9](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%289%29.png)

**Continue the configuration (step 9 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 10](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2810%29.png)

**Continue the configuration (step 10 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 11](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2811%29.png)

**Continue the configuration (step 11 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 12](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2812%29.png)

**Continue the configuration (step 12 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 13](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2813%29.png)

**Continue the configuration (step 13 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 14](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2814%29.png)

**Continue the configuration (step 14 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 15](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2815%29.png)

**Continue the configuration (step 15 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 16](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2816%29.png)

**Continue the configuration (step 16 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 17](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2817%29.png)

**Continue the configuration (step 17 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 18](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2818%29.png)

**Continue the configuration (step 18 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 19](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2819%29.png)

**Continue the configuration (step 19 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 20](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2820%29.png)

**Continue the configuration (step 20 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 21](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2821%29.png)

**Continue the configuration (step 21 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 22

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 22](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2822%29.png)

**Continue the configuration (step 22 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 23

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 23](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2823%29.png)

**Continue the configuration (step 23 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 24

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 24](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2824%29.png)

**Continue the configuration (step 24 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 25

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 25](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2825%29.png)

**Continue the configuration (step 25 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 26

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 26](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2826%29.png)

**Continue the configuration (step 26 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 27

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 27](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2827%29.png)

**Continue the configuration (step 27 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 28

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 28](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2828%29.png)

**Continue the configuration (step 28 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 29

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 29](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2829%29.png)

**Continue the configuration (step 29 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 30

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 30](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2830%29.png)

**Continue the configuration (step 30 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 31

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 31](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2831%29.png)

**Continue the configuration (step 31 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 32

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 32](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2832%29.png)

**Continue the configuration (step 32 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 33

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 33](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2833%29.png)

**Continue the configuration (step 33 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 34

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 34](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2834%29.png)

**Continue the configuration (step 34 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 35

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 35](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2835%29.png)

**Continue the configuration (step 35 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 36

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 36](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2836%29.png)

**Continue the configuration (step 36 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 37

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 37](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2837%29.png)

**Continue the configuration (step 37 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 38

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 38](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2838%29.png)

**Continue the configuration (step 38 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 39

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 39](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2839%29.png)

**Continue the configuration (step 39 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 40

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 40](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2840%29.png)

**Continue the configuration (step 40 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 41

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 41](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2841%29.png)

**Continue the configuration (step 41 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 42

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 42](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2842%29.png)

**Continue the configuration (step 42 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 43

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 43](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2843%29.png)

**Continue the configuration (step 43 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 44

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 44](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2844%29.png)

**Continue the configuration (step 44 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 45

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 45](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2845%29.png)

**Continue the configuration (step 45 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 46

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 46](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2846%29.png)

**Continue the configuration (step 46 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 47

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 47](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2847%29.png)

**Continue the configuration (step 47 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 48

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 48](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2848%29.png)

**Continue the configuration (step 48 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 49

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 49](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2849%29.png)

**Continue the configuration (step 49 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 50

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 50](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2850%29.png)

**Continue the configuration (step 50 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 51

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 51](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2851%29.png)

**Continue the configuration (step 51 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 52

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 52](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2852%29.png)

**Continue the configuration (step 52 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 53

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 53](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2853%29.png)

**Continue the configuration (step 53 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 54

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 54](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2854%29.png)

**Continue the configuration (step 54 of 55) — follow the red arrows/boxes for guidance.**

### Screenshot 55

![Step 1 — Open GPMC & Create Base Security GPO - Screenshot 55](01-OPEN%20GROUP%20POLICY%20MANAGEMENT%20CONSOLE/GROUP%20POLICY%20MANAGEMENT-%20%2855%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 2 — GPO: Finance Security Policy

Create a GPO linked to the Finance OU with department-specific security settings:

- Restrict USB access
- Disable Command Prompt
- Configure Windows Firewall rules
- Enforce screen lock timeout (5 minutes)

### Screenshot 1

![Step 2 — GPO: Finance Security Policy - Screenshot 1](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 2 — GPO: Finance Security Policy - Screenshot 2](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 2 — GPO: Finance Security Policy - Screenshot 3](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 2 — GPO: Finance Security Policy - Screenshot 4](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%284%29.png)

**Continue the configuration (step 4 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 2 — GPO: Finance Security Policy - Screenshot 5](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%285%29.png)

**Continue the configuration (step 5 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 2 — GPO: Finance Security Policy - Screenshot 6](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%286%29.png)

**Continue the configuration (step 6 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 2 — GPO: Finance Security Policy - Screenshot 7](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%287%29.png)

**Continue the configuration (step 7 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 2 — GPO: Finance Security Policy - Screenshot 8](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%288%29.png)

**Continue the configuration (step 8 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 2 — GPO: Finance Security Policy - Screenshot 9](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%289%29.png)

**Continue the configuration (step 9 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 2 — GPO: Finance Security Policy - Screenshot 10](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2810%29.png)

**Continue the configuration (step 10 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 2 — GPO: Finance Security Policy - Screenshot 11](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2811%29.png)

**Continue the configuration (step 11 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 2 — GPO: Finance Security Policy - Screenshot 12](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2812%29.png)

**Continue the configuration (step 12 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 2 — GPO: Finance Security Policy - Screenshot 13](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2813%29.png)

**Continue the configuration (step 13 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 2 — GPO: Finance Security Policy - Screenshot 14](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2814%29.png)

**Continue the configuration (step 14 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 2 — GPO: Finance Security Policy - Screenshot 15](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2815%29.png)

**Continue the configuration (step 15 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 2 — GPO: Finance Security Policy - Screenshot 16](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2816%29.png)

**Continue the configuration (step 16 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 2 — GPO: Finance Security Policy - Screenshot 17](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2817%29.png)

**Continue the configuration (step 17 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 2 — GPO: Finance Security Policy - Screenshot 18](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2818%29.png)

**Continue the configuration (step 18 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 2 — GPO: Finance Security Policy - Screenshot 19](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2819%29.png)

**Continue the configuration (step 19 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 2 — GPO: Finance Security Policy - Screenshot 20](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2820%29.png)

**Continue the configuration (step 20 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 2 — GPO: Finance Security Policy - Screenshot 21](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2821%29.png)

**Continue the configuration (step 21 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 22

![Step 2 — GPO: Finance Security Policy - Screenshot 22](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2822%29.png)

**Continue the configuration (step 22 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 23

![Step 2 — GPO: Finance Security Policy - Screenshot 23](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2823%29.png)

**Continue the configuration (step 23 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 24

![Step 2 — GPO: Finance Security Policy - Screenshot 24](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2824%29.png)

**Continue the configuration (step 24 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 25

![Step 2 — GPO: Finance Security Policy - Screenshot 25](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2825%29.png)

**Continue the configuration (step 25 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 26

![Step 2 — GPO: Finance Security Policy - Screenshot 26](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2826%29.png)

**Continue the configuration (step 26 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 27

![Step 2 — GPO: Finance Security Policy - Screenshot 27](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2827%29.png)

**Continue the configuration (step 27 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 28

![Step 2 — GPO: Finance Security Policy - Screenshot 28](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2828%29.png)

**Continue the configuration (step 28 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 29

![Step 2 — GPO: Finance Security Policy - Screenshot 29](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2829%29.png)

**Continue the configuration (step 29 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 30

![Step 2 — GPO: Finance Security Policy - Screenshot 30](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2830%29.png)

**Continue the configuration (step 30 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 31

![Step 2 — GPO: Finance Security Policy - Screenshot 31](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2831%29.png)

**Continue the configuration (step 31 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 32

![Step 2 — GPO: Finance Security Policy - Screenshot 32](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2832%29.png)

**Continue the configuration (step 32 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 33

![Step 2 — GPO: Finance Security Policy - Screenshot 33](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2833%29.png)

**Continue the configuration (step 33 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 34

![Step 2 — GPO: Finance Security Policy - Screenshot 34](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2834%29.png)

**Continue the configuration (step 34 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 35

![Step 2 — GPO: Finance Security Policy - Screenshot 35](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2835%29.png)

**Continue the configuration (step 35 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 36

![Step 2 — GPO: Finance Security Policy - Screenshot 36](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2836%29.png)

**Continue the configuration (step 36 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 37

![Step 2 — GPO: Finance Security Policy - Screenshot 37](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2837%29.png)

**Continue the configuration (step 37 of 38) — follow the red arrows/boxes for guidance.**

### Screenshot 38

![Step 2 — GPO: Finance Security Policy - Screenshot 38](02-GPO%202%20FINANCE%20SECURITY%20POLICY/SECURITY%20POLICY-%20%2838%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 3 — GPO: IT Admin Policy

Create a GPO for IT administrators with elevated permissions:

- Allow Remote Desktop access
- Enable PowerShell script execution
- Allow access to administrative tools
- Map network drives

### Screenshot 1

![Step 3 — GPO: IT Admin Policy - Screenshot 1](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 3 — GPO: IT Admin Policy - Screenshot 2](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 3 — GPO: IT Admin Policy - Screenshot 3](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 3 — GPO: IT Admin Policy - Screenshot 4](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%284%29.png)

**Continue the configuration (step 4 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 3 — GPO: IT Admin Policy - Screenshot 5](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%285%29.png)

**Continue the configuration (step 5 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 3 — GPO: IT Admin Policy - Screenshot 6](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%286%29.png)

**Continue the configuration (step 6 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 3 — GPO: IT Admin Policy - Screenshot 7](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%287%29.png)

**Continue the configuration (step 7 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 3 — GPO: IT Admin Policy - Screenshot 8](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%288%29.png)

**Continue the configuration (step 8 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 3 — GPO: IT Admin Policy - Screenshot 9](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%289%29.png)

**Continue the configuration (step 9 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 3 — GPO: IT Admin Policy - Screenshot 10](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%2810%29.png)

**Continue the configuration (step 10 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 3 — GPO: IT Admin Policy - Screenshot 11](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%2811%29.png)

**Continue the configuration (step 11 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 3 — GPO: IT Admin Policy - Screenshot 12](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%2812%29.png)

**Continue the configuration (step 12 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 3 — GPO: IT Admin Policy - Screenshot 13](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%2813%29.png)

**Continue the configuration (step 13 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 3 — GPO: IT Admin Policy - Screenshot 14](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%2814%29.png)

**Continue the configuration (step 14 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 3 — GPO: IT Admin Policy - Screenshot 15](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%2815%29.png)

**Continue the configuration (step 15 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 3 — GPO: IT Admin Policy - Screenshot 16](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%2816%29.png)

**Continue the configuration (step 16 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 3 — GPO: IT Admin Policy - Screenshot 17](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%2817%29.png)

**Continue the configuration (step 17 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 3 — GPO: IT Admin Policy - Screenshot 18](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%2818%29.png)

**Continue the configuration (step 18 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 3 — GPO: IT Admin Policy - Screenshot 19](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%2819%29.png)

**Continue the configuration (step 19 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 3 — GPO: IT Admin Policy - Screenshot 20](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%2820%29.png)

**Continue the configuration (step 20 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 3 — GPO: IT Admin Policy - Screenshot 21](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%2821%29.png)

**Continue the configuration (step 21 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 22

![Step 3 — GPO: IT Admin Policy - Screenshot 22](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%2822%29.png)

**Continue the configuration (step 22 of 23) — follow the red arrows/boxes for guidance.**

### Screenshot 23

![Step 3 — GPO: IT Admin Policy - Screenshot 23](03-GPO%203%20IT%20ADMIN%20POLICY/ADMIN%20POLICY-%20%2823%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 4 — GPO: Desktop Policy

Create a GPO for standard desktop customization:

- Set default wallpaper
- Hide desktop icons
- Configure Start menu layout
- Disable unnecessary services

### Screenshot 1

![Step 4 — GPO: Desktop Policy - Screenshot 1](04-GPO%204%20DESKTOP%20POLICY/DESKTOP%20POLICY-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 4 — GPO: Desktop Policy - Screenshot 2](04-GPO%204%20DESKTOP%20POLICY/DESKTOP%20POLICY-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 4 — GPO: Desktop Policy - Screenshot 3](04-GPO%204%20DESKTOP%20POLICY/DESKTOP%20POLICY-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 4 — GPO: Desktop Policy - Screenshot 4](04-GPO%204%20DESKTOP%20POLICY/DESKTOP%20POLICY-%20%284%29.png)

**Continue the configuration (step 4 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 4 — GPO: Desktop Policy - Screenshot 5](04-GPO%204%20DESKTOP%20POLICY/DESKTOP%20POLICY-%20%285%29.png)

**Continue the configuration (step 5 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 4 — GPO: Desktop Policy - Screenshot 6](04-GPO%204%20DESKTOP%20POLICY/DESKTOP%20POLICY-%20%286%29.png)

**Continue the configuration (step 6 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 4 — GPO: Desktop Policy - Screenshot 7](04-GPO%204%20DESKTOP%20POLICY/DESKTOP%20POLICY-%20%287%29.png)

**Continue the configuration (step 7 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 4 — GPO: Desktop Policy - Screenshot 8](04-GPO%204%20DESKTOP%20POLICY/DESKTOP%20POLICY-%20%288%29.png)

**Continue the configuration (step 8 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 4 — GPO: Desktop Policy - Screenshot 9](04-GPO%204%20DESKTOP%20POLICY/DESKTOP%20POLICY-%20%289%29.png)

**Continue the configuration (step 9 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 4 — GPO: Desktop Policy - Screenshot 10](04-GPO%204%20DESKTOP%20POLICY/DESKTOP%20POLICY-%20%2810%29.png)

**Continue the configuration (step 10 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 4 — GPO: Desktop Policy - Screenshot 11](04-GPO%204%20DESKTOP%20POLICY/DESKTOP%20POLICY-%20%2811%29.png)

**Continue the configuration (step 11 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 4 — GPO: Desktop Policy - Screenshot 12](04-GPO%204%20DESKTOP%20POLICY/DESKTOP%20POLICY-%20%2812%29.png)

**Continue the configuration (step 12 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 4 — GPO: Desktop Policy - Screenshot 13](04-GPO%204%20DESKTOP%20POLICY/DESKTOP%20POLICY-%20%2813%29.png)

**Continue the configuration (step 13 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 4 — GPO: Desktop Policy - Screenshot 14](04-GPO%204%20DESKTOP%20POLICY/DESKTOP%20POLICY-%20%2814%29.png)

**Continue the configuration (step 14 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 4 — GPO: Desktop Policy - Screenshot 15](04-GPO%204%20DESKTOP%20POLICY/DESKTOP%20POLICY-%20%2815%29.png)

**Continue the configuration (step 15 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 4 — GPO: Desktop Policy - Screenshot 16](04-GPO%204%20DESKTOP%20POLICY/DESKTOP%20POLICY-%20%2816%29.png)

**Continue the configuration (step 16 of 17) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 4 — GPO: Desktop Policy - Screenshot 17](04-GPO%204%20DESKTOP%20POLICY/DESKTOP%20POLICY-%20%2817%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 5 — GPO: Audit Policy

Create a comprehensive audit GPO to track security events:

**Advanced Audit Policy Configuration:**
- Audit Logon/Logoff (Success + Failure)
- Audit Account Management (Success + Failure)
- Audit Object Access (Success + Failure)
- Audit Policy Change (Success)
- Audit Privilege Use (Success + Failure)

### Screenshot 1

![Step 5 — GPO: Audit Policy - Screenshot 1](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 5 — GPO: Audit Policy - Screenshot 2](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 5 — GPO: Audit Policy - Screenshot 3](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 5 — GPO: Audit Policy - Screenshot 4](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%284%29.png)

**Continue the configuration (step 4 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 5 — GPO: Audit Policy - Screenshot 5](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%285%29.png)

**Continue the configuration (step 5 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 5 — GPO: Audit Policy - Screenshot 6](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%286%29.png)

**Continue the configuration (step 6 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 5 — GPO: Audit Policy - Screenshot 7](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%287%29.png)

**Continue the configuration (step 7 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 5 — GPO: Audit Policy - Screenshot 8](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%288%29.png)

**Continue the configuration (step 8 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 5 — GPO: Audit Policy - Screenshot 9](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%289%29.png)

**Continue the configuration (step 9 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 5 — GPO: Audit Policy - Screenshot 10](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2810%29.png)

**Continue the configuration (step 10 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 5 — GPO: Audit Policy - Screenshot 11](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2811%29.png)

**Continue the configuration (step 11 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 5 — GPO: Audit Policy - Screenshot 12](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2812%29.png)

**Continue the configuration (step 12 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 5 — GPO: Audit Policy - Screenshot 13](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2813%29.png)

**Continue the configuration (step 13 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 5 — GPO: Audit Policy - Screenshot 14](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2814%29.png)

**Continue the configuration (step 14 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 5 — GPO: Audit Policy - Screenshot 15](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2815%29.png)

**Continue the configuration (step 15 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 16

![Step 5 — GPO: Audit Policy - Screenshot 16](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2816%29.png)

**Continue the configuration (step 16 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 17

![Step 5 — GPO: Audit Policy - Screenshot 17](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2817%29.png)

**Continue the configuration (step 17 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 18

![Step 5 — GPO: Audit Policy - Screenshot 18](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2818%29.png)

**Continue the configuration (step 18 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 19

![Step 5 — GPO: Audit Policy - Screenshot 19](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2819%29.png)

**Continue the configuration (step 19 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 20

![Step 5 — GPO: Audit Policy - Screenshot 20](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2820%29.png)

**Continue the configuration (step 20 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 21

![Step 5 — GPO: Audit Policy - Screenshot 21](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2821%29.png)

**Continue the configuration (step 21 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 22

![Step 5 — GPO: Audit Policy - Screenshot 22](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2822%29.png)

**Continue the configuration (step 22 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 23

![Step 5 — GPO: Audit Policy - Screenshot 23](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2823%29.png)

**Continue the configuration (step 23 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 24

![Step 5 — GPO: Audit Policy - Screenshot 24](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2824%29.png)

**Continue the configuration (step 24 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 25

![Step 5 — GPO: Audit Policy - Screenshot 25](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2825%29.png)

**Continue the configuration (step 25 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 26

![Step 5 — GPO: Audit Policy - Screenshot 26](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2826%29.png)

**Continue the configuration (step 26 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 27

![Step 5 — GPO: Audit Policy - Screenshot 27](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2827%29.png)

**Continue the configuration (step 27 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 28

![Step 5 — GPO: Audit Policy - Screenshot 28](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2828%29.png)

**Continue the configuration (step 28 of 29) — follow the red arrows/boxes for guidance.**

### Screenshot 29

![Step 5 — GPO: Audit Policy - Screenshot 29](05-GPO%205%20AUDIT%20POLICY/AUDIT%20POLICY-%20%2829%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 6 — GPO: Loopback Processing for Shared PCs

Configure Loopback Processing in Replace mode for Operations department shared computers. This applies computer-based user settings regardless of which user logs in.

```
Computer Configuration → Policies → Administrative Templates → System → Group Policy
→ Configure user Group Policy loopback processing mode → Enabled (Replace)
```

### Screenshot 1

![Step 6 — GPO: Loopback Processing for Shared PCs - Screenshot 1](06-GPO%206%20LOOPBACK%20(OPERATIONS%20SHARED%20PCS)/LOOPBACK-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 6 — GPO: Loopback Processing for Shared PCs - Screenshot 2](06-GPO%206%20LOOPBACK%20(OPERATIONS%20SHARED%20PCS)/LOOPBACK-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 6 — GPO: Loopback Processing for Shared PCs - Screenshot 3](06-GPO%206%20LOOPBACK%20(OPERATIONS%20SHARED%20PCS)/LOOPBACK-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 6 — GPO: Loopback Processing for Shared PCs - Screenshot 4](06-GPO%206%20LOOPBACK%20(OPERATIONS%20SHARED%20PCS)/LOOPBACK-%20%284%29.png)

**Continue the configuration (step 4 of 11) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 6 — GPO: Loopback Processing for Shared PCs - Screenshot 5](06-GPO%206%20LOOPBACK%20(OPERATIONS%20SHARED%20PCS)/LOOPBACK-%20%285%29.png)

**Continue the configuration (step 5 of 11) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 6 — GPO: Loopback Processing for Shared PCs - Screenshot 6](06-GPO%206%20LOOPBACK%20(OPERATIONS%20SHARED%20PCS)/LOOPBACK-%20%286%29.png)

**Continue the configuration (step 6 of 11) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 6 — GPO: Loopback Processing for Shared PCs - Screenshot 7](06-GPO%206%20LOOPBACK%20(OPERATIONS%20SHARED%20PCS)/LOOPBACK-%20%287%29.png)

**Continue the configuration (step 7 of 11) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 6 — GPO: Loopback Processing for Shared PCs - Screenshot 8](06-GPO%206%20LOOPBACK%20(OPERATIONS%20SHARED%20PCS)/LOOPBACK-%20%288%29.png)

**Continue the configuration (step 8 of 11) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 6 — GPO: Loopback Processing for Shared PCs - Screenshot 9](06-GPO%206%20LOOPBACK%20(OPERATIONS%20SHARED%20PCS)/LOOPBACK-%20%289%29.png)

**Continue the configuration (step 9 of 11) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 6 — GPO: Loopback Processing for Shared PCs - Screenshot 10](06-GPO%206%20LOOPBACK%20(OPERATIONS%20SHARED%20PCS)/LOOPBACK-%20%2810%29.png)

**Continue the configuration (step 10 of 11) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 6 — GPO: Loopback Processing for Shared PCs - Screenshot 11](06-GPO%206%20LOOPBACK%20(OPERATIONS%20SHARED%20PCS)/LOOPBACK-%20%2811%29.png)

**Final result — verify the configuration is complete and working.**

---

## Step 7 — Enforce Base Policy & Test with gpresult

Enforce the Base Security Policy, run `gpupdate /force` on CLIENT1, and verify GPO application:

```cmd
gpupdate /force
gpresult /r
gpresult /h C:\gpresult.html
```

### Screenshot 1

![Step 7 — Enforce Base Policy & Test with gpresult - Screenshot 1](07-ENFORCE%20BASE%20POLICY%20AND%20TEST/ENFORCE-%20%281%29.png)

**Begin the process — open the relevant tool or navigate to the starting point.**

### Screenshot 2

![Step 7 — Enforce Base Policy & Test with gpresult - Screenshot 2](07-ENFORCE%20BASE%20POLICY%20AND%20TEST/ENFORCE-%20%282%29.png)

**Navigate to the required setting or dialog (step 2).**

### Screenshot 3

![Step 7 — Enforce Base Policy & Test with gpresult - Screenshot 3](07-ENFORCE%20BASE%20POLICY%20AND%20TEST/ENFORCE-%20%283%29.png)

**Navigate to the required setting or dialog (step 3).**

### Screenshot 4

![Step 7 — Enforce Base Policy & Test with gpresult - Screenshot 4](07-ENFORCE%20BASE%20POLICY%20AND%20TEST/ENFORCE-%20%284%29.png)

**Continue the configuration (step 4 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 5

![Step 7 — Enforce Base Policy & Test with gpresult - Screenshot 5](07-ENFORCE%20BASE%20POLICY%20AND%20TEST/ENFORCE-%20%285%29.png)

**Continue the configuration (step 5 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 6

![Step 7 — Enforce Base Policy & Test with gpresult - Screenshot 6](07-ENFORCE%20BASE%20POLICY%20AND%20TEST/ENFORCE-%20%286%29.png)

**Continue the configuration (step 6 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 7

![Step 7 — Enforce Base Policy & Test with gpresult - Screenshot 7](07-ENFORCE%20BASE%20POLICY%20AND%20TEST/ENFORCE-%20%287%29.png)

**Continue the configuration (step 7 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 8

![Step 7 — Enforce Base Policy & Test with gpresult - Screenshot 8](07-ENFORCE%20BASE%20POLICY%20AND%20TEST/ENFORCE-%20%288%29.png)

**Continue the configuration (step 8 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 9

![Step 7 — Enforce Base Policy & Test with gpresult - Screenshot 9](07-ENFORCE%20BASE%20POLICY%20AND%20TEST/ENFORCE-%20%289%29.png)

**Continue the configuration (step 9 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 10

![Step 7 — Enforce Base Policy & Test with gpresult - Screenshot 10](07-ENFORCE%20BASE%20POLICY%20AND%20TEST/ENFORCE-%20%2810%29.png)

**Continue the configuration (step 10 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 11

![Step 7 — Enforce Base Policy & Test with gpresult - Screenshot 11](07-ENFORCE%20BASE%20POLICY%20AND%20TEST/ENFORCE-%20%2811%29.png)

**Continue the configuration (step 11 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 12

![Step 7 — Enforce Base Policy & Test with gpresult - Screenshot 12](07-ENFORCE%20BASE%20POLICY%20AND%20TEST/ENFORCE-%20%2812%29.png)

**Continue the configuration (step 12 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 13

![Step 7 — Enforce Base Policy & Test with gpresult - Screenshot 13](07-ENFORCE%20BASE%20POLICY%20AND%20TEST/ENFORCE-%20%2813%29.png)

**Continue the configuration (step 13 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 14

![Step 7 — Enforce Base Policy & Test with gpresult - Screenshot 14](07-ENFORCE%20BASE%20POLICY%20AND%20TEST/ENFORCE-%20%2814%29.png)

**Continue the configuration (step 14 of 15) — follow the red arrows/boxes for guidance.**

### Screenshot 15

![Step 7 — Enforce Base Policy & Test with gpresult - Screenshot 15](07-ENFORCE%20BASE%20POLICY%20AND%20TEST/ENFORCE-%20%2815%29.png)

**Final result — verify the configuration is complete and working.**

---

## 🔗 Navigation

[⬆️ Back to Top](#)

[📚 Back to Master README](../README.md)
