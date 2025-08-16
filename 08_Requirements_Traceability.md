# Requirements & Traceability Matrix

Trace from **NIST SP 800-171 controls → actionable requirements → SDLC phase → test & evidence**.

| Control | Requirement (plain English) | SDLC Phase | Evidence / Artifact | Test ID | Status |
|---|---|---|---|---|---|
| **AC-1** Access Control Policy | Document and annually review an AC policy; all depts acknowledge | Planning → Maintain | `02_SSP.md`, policy excerpt, sign-off list | T-POL-01 | Planned |
| **AC-2** Account Management | JML process; disable terminated accounts ≤1 hour; monthly recertification | Analysis → Impl → Verify → Maintain | Runbook, deprovision script logs, access review record | **T-AC2-01** | In Progress |
| **AT-1** Security Awareness Policy | Formal security awareness policy reviewed at least annually | Planning → Maintain | Policy doc + approval record | T-POL-02 | Planned |
| **AT-2** Role-Based Training | Role matrix; engineers complete secure-coding/admin training yearly | Planning → Impl → Maintain | `training_matrix.csv`, LMS screenshot | **T-AT2-01** | Planned |
| **AU-1** Audit & Accountability Policy | Audit policy defines sources, fields, retention, review cadence | Design → Maintain | Logging standard, review calendar | T-POL-03 | Planned |
| **AU-2** Event Logging | SSH/web auth successes/failures sent to SIEM with user/IP/time | Design → Impl → Verify → Maintain | Agent config; SIEM sample event | **T-AU2-02** | Complete |
| **CM-1/CM-2** Configuration Management | Baseline configs documented; drift detected and ticketed | Design → Impl → Verify → Maintain | `baseline.yml`, drift report | **T-CM2-01** | Planned |

**Link to POA&M:** Each open requirement has a matching POA&M row with owner and due date.
