# Verification & Test Plan — AC / AT / AU / CM

## Scope & Environment
- Environment: lab or simulated prod with IdP, servers, SIEM.
- Evidence location: `/evidence/<TestID>/` (screenshots, logs, exports).

---

## Test Cases

### T-AC2-01 — Terminated Account Disabled within 1 Hour
- **Control:** AC-2
- **Objective:** Ensure leaver de-provisioning blocks access promptly.
- **Pre-reqs:** Test user `temp.user` with access to web and SSH.
- **Steps:**
  1. Create `temp.user`; verify login works.
  2. Terminate `temp.user` in HR/IdP at T0.
  3. Attempt login (web + SSH) at T0+30m and T0+60m.
- **Expected:** All logins denied by ≤ 1h; SIEM shows `DISABLED/TERMINATED` reason.
- **Evidence:** Screenshot of failed auth; SIEM events; deprovision job log.
- **Status:** In Progress

---

### T-AT2-01 — Role-Based Training Completion
- **Control:** AT-2
- **Objective:** Verify training assignment and completion recording by role.
- **Steps:**
  1. In training matrix, pick role "SysAdmin".
  2. Assign “Secure Admin 101” course; mark due date.
  3. Complete course in LMS (or simulate).
  4. Export completion record.
- **Expected:** Record shows user, role, course, completion date ≤ due date.
- **Evidence:** Matrix screenshot + LMS export.
- **Status:** Planned

---

### T-AU2-02 — Auth Events Reach SIEM with Required Fields
- **Control:** AU-2 (also AU-6 retention implicitly)
- **Objective:** Validate logging pipeline and field integrity.
- **Steps:**
  1. Generate 3 failed SSH logins from IP A, then 1 success.
  2. In SIEM, search last 5 minutes for host.
  3. Verify fields: `timestamp, user, src_ip, action(FAILED/SUCCESS), host`.
- **Expected:** All 4 events present with correct fields & timestamps.
- **Evidence:** SIEM query + raw event JSON.
- **Status:** Complete

---

### T-CM2-01 — Baseline Drift Detection & Ticketing
- **Control:** CM-2
- **Objective:** Show config drift triggers alert and ticket.
- **Steps:**
  1. Change SSH config (e.g., PermitRootLogin from `no` → `yes`).
  2. Run baseline check (script/tool).
  3. Confirm alert and ticket with host, diff, time.
  4. Revert change; confirm ticket closure.
- **Expected:** Drift detected within monitoring interval; ticket created and closed with fix.
- **Evidence:** Diff report, alert screenshot, ticket log.
- **Status:** Planned

---

## Acceptance Criteria
- All **High** controls (AC-2, AU-2) pass; **Medium** (CM-2, AT-2) have remediation plan.
- Evidence stored and linked in the traceability matrix and POA&M.

## Post-Test Actions
- Log failures as POA&M items with owner and date.
- Update `05_Final_Report.md` with results and next steps.
