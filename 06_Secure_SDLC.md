# Secure SDLC — SecureTech SSP Assessment Simulation

This document shows how the NIST SP 800-171 assessment artifacts in this repo map into a lightweight **Secure-SDLC** with explicit **release gates**.

## Phases & Gates

### 1) Planning
**Activities**
- Define CUI boundary and data flows (what systems store/process/transmit CUI)
- Identify stakeholders + RACI; establish risk register
- Select in-scope controls: **AC, AT, AU, CM** (others out of scope for this sim)

**Gate P1 — Scope Approved**
- [ ] Boundary & assets documented
- [ ] Stakeholders & roles confirmed
- [ ] Risk register created with initial risks

**Artifacts**: `02_SecureTech_SSP.md` (boundary, roles), `05_Final_Report.md` (risk summary)

---

### 2) Requirements / Analysis
**Activities**
- Derive implementable **security requirements** from 800-171 controls
- Create **traceability** from control → requirement → test → evidence

**Gate A1 — Requirements Traced**
- [ ] Each in-scope control mapped to at least one requirement
- [ ] Each requirement has a planned verification method

**Artifacts**: `08_Requirements_Traceability.md`

---

### 3) Design
**Activities**
- Architecture diagram + **IAM role model**
- Log sources, retention, and parsing schema
- Baseline configuration list (CM)
- **Threat model** (STRIDE) with top risks + mitigations

**Gate D1 — Design Reviewed**
- [ ] Threat model reviewed; top risks assigned to POA&M items
- [ ] Logging & IAM design meet requirements
- [ ] Baseline configs documented

**Artifacts**: `07_Threat_Model.md`, `04_POA&M.md` (linked items)

---

### 4) Implementation
**Activities**
- Implement/Configure: account lifecycle, MFA (if in scope), log forwarding, baseline templates
- Add **security automation** (SAST/secrets) in CI

**Gate I1 — Build Clean**
- [ ] CI runs security checks with no high-severity findings
- [ ] Implementation reviewed (4-eyes)
- [ ] Evidence captured

**Artifacts**: `.github/workflows/security.yml`, `/evidence/*`

---

### 5) Verification / Testing
**Activities**
- Execute test cases for AC/AT/AU/CM
- Capture screenshots, logs, or reports as **evidence**

**Gate V1 — Tests Passing**
- [ ] All planned tests pass (or risk accepted)
- [ ] Findings logged in POA&M with owners/dates

**Artifacts**: `09_Test_Plan.md`, `/evidence/*`, `04_POA&M.md`

---

### 6) Deployment & Maintenance
**Activities**
- Release checklist (change control, rollback, monitoring on)
- Operational metrics + continuous monitoring cadence

**Gate M1 — Operate & Monitor**
- [ ] Dashboards/metrics updated
- [ ] Next periodic reviews scheduled (access review, log review, baseline drift)

**Artifacts**: `04_POA&M.md`, `05_Final_Report.md`, `metrics.md` (optional)

---

## RACI (Abbrev.)
| Activity                          | Responsible      | Accountable       | Consulted             | Informed         |
|----------------------------------|------------------|-------------------|-----------------------|------------------|
| Control scoping / Planning       | Compliance Officer | CISO (sim)      | IT Admin, Audit Lead  | Stakeholders     |
| IAM design / AC controls         | IT Admin          | CISO (sim)        | Security Engineer     | Audit Lead       |
| Logging / AU controls            | Security Engineer | CISO (sim)        | IT Admin              | Audit Lead       |
| Training / AT controls           | Training Coord.   | HR Manager        | Compliance Officer    | All Staff        |
| Baselines / CM controls          | Config Manager    | CISO (sim)        | Security Engineer     | Audit Lead       |

---

## SDLC ↔ 800-171 Control Examples
- **AC-2 Account Management**: Analysis → Design (roles & lifecycle) → Impl (de-provision) → Verify (T-AC2-01) → Maintain (monthly reviews)
- **AU-2 Event Logging**: Design (schema/retention) → Impl (forwarders) → Verify (T-AU2-02) → Maintain (log reviews)
- **AT-2 Role-Based Training**: Plan (matrix) → Impl (assign courses) → Verify (T-AT2-01) → Maintain (annual cadence)
- **CM-1/CM-2 Baselines**: Design (baseline) → Impl (enforce) → Verify (T-CM2-01) → Maintain (drift monitoring)

---

## KPIs / Continuous Monitoring (suggested)
- % terminated accounts disabled < 1h (target ≥ 95%)
- % log sources forwarding required fields (target 100%)
- Training completion rate by role (target ≥ 98% by due date)
- Mean time to remediate baseline drift (target < 7 days)
