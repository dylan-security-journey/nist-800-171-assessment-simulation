# 🛡️ Final Project Report: NIST SP 800-171 Assessment Simulation

**Project Title**: SecureTech Solutions – System Security Plan (SSP) and Assessment  
**Author**: Dylan Nguyen  
**Date**: July 28, 2025  
**Repository**: `nist-800-171-assessment-simulation`

---

## 📌 Project Overview

SecureTech Solutions is a fictional small business that provides IT and cybersecurity services to government contractors and SMEs. This project simulates the creation and evaluation of a System Security Plan (SSP) for SecureTech's Controlled Unclassified Information (CUI) environment, in alignment with **NIST SP 800-171 Rev. 2**.

The project includes:
- A detailed SSP narrative
- A control-by-control assessment score sheet
- A Plan of Action and Milestones (POA&M)
- A final report summarizing the findings

---

## 🧪 Methodology

The assessment followed the 14 control families and 110 requirements defined in NIST SP 800-171. Each control was evaluated using a 3-tier scoring system:

| Score | Meaning |
|-------|---------|
| 1     | Basic implementation or ad hoc |
| 2     | Documented and partially optimized |
| 3     | Fully implemented and mature |

Artifacts created:
- `02_SecureTech_SSP_Template.md`: Narrative SSP
- `03_Assessment_Score_Sheet.xlsx`: Control-by-control scoring
- `04_POAM.md`: Remediation plan for gaps

---

## 🔍 Key Findings

- **Total Controls Evaluated**: 31 (subset of 110 for simulation)
- **Fully Implemented (Score 3)**: 3
- **Partially Implemented (Score 1)**: 1
- **Not Implemented (Score 0)**: 0
- **Total Score**: 38 / 93
- **Implementation Rate**: 76%

---

## 🧱 POA&M Summary

The following controls were identified as **not implemented** and added to the POA&M:

| Control ID | Control Name                     | Weakness Description                        | Target Date  | Status       |
|------------|----------------------------------|---------------------------------------------|--------------|--------------|
| CM-3       | Configuration Change             | No formal change control process            | 2025-08-15   | In Progress  |
| CM-6       | Configuration Settings           | No baseline enforcement                     | 2025-08-20   | Planned      |
| IR-4       | Incident Handling                | No documented incident handling procedures  | 2025-08-25   | Not Started  |
| PM-9       | Risk Assessment                  | No formal risk assessment process           | 2025-08-28   | Not Started  |

See full POA&M: [`04_POAM.md`](04_POAM.md)

---

## ✅ Conclusion

This simulation demonstrates a structured approach to NIST SP 800-171 compliance for a fictional organization. By documenting the SSP, scoring implementation maturity, and identifying remediation actions, SecureTech Solutions has a clear roadmap for improving its cybersecurity posture.

This project can serve as a portfolio piece for cybersecurity professionals preparing for roles in compliance, GRC, or federal contracting.

---

**Next Steps**:
- Complete POA&M remediation tasks
- Expand assessment to all 110 controls
- Conduct internal audit and update SSP quarterly
