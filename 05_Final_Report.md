# 🛡️ Final Project Report: NIST SP 800-171 Assessment Simulation

**Project Title**: SecureTech SSP & Control Assessment  
**Author**: Dylan Nguyen  
**Date**: July 28, 2025  
**Scope**: Access Control (AC), Awareness and Training (AT), Audit and Accountability (AU)

---

## 📌 1. Project Overview

This project simulates a partial NIST SP 800-171 assessment for a fictional company, **SecureTech Solutions**, which provides IT and cybersecurity services to government contractors. The goal was to demonstrate how to document and assess selected control families within a System Security Plan (SSP), and to identify areas for improvement using a Plan of Action and Milestones (POA&M).

---

## 🎯 2. Scope

The assessment focused on the following three control families:

- **Access Control (AC)**
- **Awareness and Training (AT)**
- **Audit and Accountability (AU)**

These families were selected to demonstrate a representative sample of technical, procedural, and human-centric controls.

---

## 🧪 3. Methodology

The assessment followed the structure of NIST SP 800-171 Rev. 2 and included:

- Reviewing SSP implementation statements for each control
- Assigning implementation scores (0 = Not Implemented, 10 = Intermediate, 20 = Fully Implemented)
- Documenting weaknesses and planned remediation in a POA&M

---

## 🔍 4. Key Findings

### ✅ Access Control (AC)
| Control | Description | Status | Notes |
|---------|-------------|--------|-------|
| AC-1 | Access Control Policy | ⚠️ Partial | Some departments have not adopted the latest policy |
| AC-2 | Account Management | ⚠️ Partial | Terminated accounts remained active beyond 30 days |
| AC-3 | Access Enforcement | ✅ Implemented | RBAC enforced across systems |
| AC-4 | Information Flow Enforcement | ✅ Implemented | VLANs and firewall rules in place |

### ⚠️ Awareness and Training (AT)
| Control | Description | Status | Notes |
|---------|-------------|--------|-------|
| AT-1 | Security Awareness Training | ❌ Not Implemented | Training occurs every 10 years instead of annually |
| AT-2 | Role-Based Training | ❌ Not Implemented | No specialized training for admins or developers |

### ⚠️ Audit and Accountability (AU)
| Control | Description | Status | Notes |
|---------|-------------|--------|-------|
| AU-1 | Audit Policy | ⚠️ Partial | Some systems excluded from audit scope |
| AU-2 | Event Logging | ⚠️ Partial | Mobile device logs not consistently captured |
| AU-3 | Audit Record Content | ✅ Implemented | Logs include required metadata |

---

## 🛠️ 5. POA&M Summary

| Control | Weakness | Planned Action | Target Date | Status |
|---------|----------|----------------|-------------|--------|
| AC-1 | Policy not adopted org-wide | Re-distribute and train on updated policy | 2025-08-15 | Planned |
| AC-2 | Terminated accounts remain active | Automate deactivation in Azure AD | 2025-08-20 | In Progress |
| AT-1 | Training not annual | Update policy and schedule annual training | 2025-08-10 | Planned |
| AT-2 | No role-based training | Develop secure config/coding training | 2025-08-25 | Not Started |
| AU-1 | Incomplete audit scope | Expand audit coverage to all systems | 2025-08-18 | Planned |
| AU-2 | Missing mobile logs | Integrate mobile logging into SIEM | 2025-08-22 | Planned |

---

## ✅ 6. Conclusion

This simulation demonstrates how to document and assess selected NIST SP 800-171 controls in a structured and actionable way. While some controls were fully implemented, others revealed gaps in policy enforcement, training, and audit coverage. The POA&M provides a clear roadmap for remediation and continuous improvement.

This project serves as a portfolio-ready example of compliance documentation, risk identification, and control assessment aligned with federal cybersecurity standards.
