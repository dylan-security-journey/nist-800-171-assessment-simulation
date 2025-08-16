# Threat Model — SecureTech (STRIDE)

**Scope:** Systems handling Controlled Unclassified Information (CUI) for SecureTech.  
**Assumption:** Identity provider (IdP) supports MFA (if OOS, marked as recommendation).  
**In-scope controls:** AC, AT, AU, CM (others referenced where helpful).

## System & Data Flow (DFD — conceptual)

[External User] --(HTTPS)--> [Web/App] --(SQL)--> [DB (CUI)]
| |
+--(Auth)--> [IdP/MFA] +--(Syslog/Agent)--> [SIEM/Log Store]
[Admin] --(SSH/RDP)--> [Servers] --config--> [Baseline/CM Tool]

**Trust Boundaries:** Internet ↔ Edge; App ↔ DB; Admin network; Logging pipeline.

## Assets
- CUI in DB and backups
- Credentials, tokens, API keys
- Audit logs and security events
- Baseline configuration definitions

## Actors
- External users, internal employees/admins
- Adversaries (external), malicious insiders
- Automation (CI/CD, agents)

## STRIDE Table (top items)

| STRIDE | Threat Example | Likelihood | Impact | Control Mapping | SDLC Phase | Mitigation/Evidence |
|---|---|---:|---:|---|---|---|
| **S** | Stale/terminated account used to access CUI | M | H | **AC-2** | Analysis→Impl→Verify | Joiner/Mover/Leaver process; T-AC2-01 evidence |
| **T** | Config tampering on servers | M | H | **CM-2** | Design→Impl→Maintain | Baseline + drift detection; T-CM2-01 |
| **R** | Missing audit logs enable repudiation | M | M | **AU-2, AU-6** | Design→Verify→Maintain | Log schema + retention; T-AU2-02 |
| **I** | Excessive privilege/role creep | L | H | **AC-6** (note), AC-2 | Analysis→Design | Role model + quarterly access review |
| **D** | CUI exposure via weak segmentation | L | H | **AC-3/AC-4** (note) | Design | Network/role segmentation, SSP diagram |
| **E** | No MFA for admin access | M | H | **IA-2** (OOS; recommend) | Design→Impl | Enforce MFA; evidence from IdP policy |

> **Notes:** Controls marked “note” or “OOS” are outside the strict sim scope but are recommended for completeness.

## Top Risks & POA&M Links
1. **Terminated accounts remain active** → POA&M AC-2-R1 (owner: IT Admin, due: 2025-08-20)  
2. **Inconsistent device logging** → POA&M AU-2-R1 (owner: Security Engineer, due: 2025-08-25)  
3. **Baseline not enforced** → POA&M CM-2-R1 (owner: Config Manager, due: 2025-08-28)

## Residual Risk
After planned mitigations, residual risk primarily from privileged access and third-party integrations; track via quarterly reviews and POA&M status.

## References
- `02_SecureTech_SSP.md` (boundary, roles)
- `04_POA&M.md` (actions, owners, dates)
- `09_Test_Plan.md` (verification)
