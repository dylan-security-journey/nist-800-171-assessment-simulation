# System Security Plan (SSP)
**Organization Name**: SecureTech Solutions  
**System Name**: SecureTech CUI Environment  
**System Owner**: Dylan Nguyen
**Date**: July 28, 2025  

---

## 1. Company Overview
SecureTech Solutions is a fictional small business specializing in providing IT services and cybersecurity consulting to government contractors and small-to-medium enterprises (SMEs). With a team of 25 professionals, SecureTech Solutions offers secure cloud infrastructure management, endpoint protection, and compliance advisory services.

The company’s mission is to empower clients to meet federal cybersecurity requirements and protect sensitive data through tailored, cost-effective solutions. SecureTech Solutions operates in a hybrid cloud environment and handles Controlled Unclassified Information (CUI) on behalf of its clients, making compliance with NIST SP 800-171 a critical component of its operations.

This System Security Plan (SSP) outlines the technical and procedural safeguards implemented by SecureTech Solutions to meet the 110 security requirements defined in NIST SP 800-171, ensuring the confidentiality, integrity, and availability of CUI within its systems.
---

## 2. System Boundary Description
SecureTech Solutions operates a hybrid IT environment designed to support secure handling of Controlled Unclassified Information (CUI). The system boundary includes the following components:

### 🔧 Hardware
- 25 employee laptops (Windows 11 Pro, BitLocker enabled)
- 2 physical servers (used for local backup and internal services)
- Network switches and firewalls (Cisco Meraki)
- Secure mobile devices (company-issued smartphones with MDM)

### 🧠 Software
- Microsoft 365 (Exchange, SharePoint, OneDrive)
- Endpoint protection: CrowdStrike Falcon
- SIEM: Splunk Cloud
- Ticketing system: Jira Service Management
- VPN: Cisco AnyConnect

### 🌐 Network Components
- Internal LAN segmented by VLANs (Admin, Users, Guests)
- Cloud-hosted services via Microsoft Azure
- Encrypted VPN access for remote employees
- Firewall rules enforcing least privilege access

### 🔒 Security Boundaries
- All CUI is stored in encrypted containers within SharePoint and OneDrive
- Access to CUI is restricted via role-based access controls (RBAC)
- Remote access requires MFA and VPN
- Network monitoring and logging are centralized in Splunk
---

## 3. Control Families


## 3.1 Access Control (AC)

- **AC-1: Access Control Policy and Procedures**  
  SecureTech maintains documented access control policies that define user roles and responsibilities. Policies are reviewed annually, but some departments have not acknowledged or adopted the latest version.

- **AC-2: Account Management**
  - User accounts are managed via Azure Active Directory with automated provisioning and deactivation workflows. However, some terminated accounts were found to remain active beyond 30 days.

- **AC-3: Access Enforcement**  
  Role-based access controls (RBAC) are enforced across all systems, including SharePoint and internal servers.

- **AC-4: Information Flow Enforcement**  
  Firewall rules and VLAN segmentation restrict data flow between departments.

---

## 3.2 Awareness and Training (AT)

- **AT-1: Security Awareness Training Policy**  
  All employees receive once every ten years cybersecurity awareness training, although the policy states training should occur annually.

- **AT-2: Role-Based Training**  
  System administrators and developers don't have specialized training on secure system configuration and coding practices, despite being listed as a requirement in the internal training policy.

---

## 3.3 Audit and Accountability (AU)

- **AU-1: Audit Policy and Procedures**  
  Audit policies are documented and reviewed quarterly, but recent audits revealed that some systems were not included in the review scope.

- **AU-2: Event Logging**  
  Security events are logged using Splunk Cloud and retained for 12 months. However, logs from mobile devices are not consistently captured.

- **AU-3: Content of Audit Records**  
  Logs include timestamps, user IDs, event types, and source IP addresses.

---

## 3.4 Configuration Management (CM)

- **CM-1: Configuration Management Policy**  
  SecureTech maintains a baseline configuration for all systems, but enforcement of these baselines is inconsistent across departments.

- **CM-2: Configuration Change Control**  
  Changes are tracked via Jira and require approval before deployment. However, emergency changes are sometimes implemented without formal documentation.

---

## 3.5 Identification and Authentication (IA)

- **IA-1: Identification Policy**  
  Unique user IDs are assigned to all personnel.

- **IA-2: Authentication Mechanisms**  
  Multi-factor authentication (MFA) is enforced for all remote access.

---

## 3.6 Incident Response (IR)

- **IR-1: Incident Response Policy**  
  SecureTech has a documented incident response plan reviewed annually.

- **IR-2: Incident Reporting**  
  Employees report incidents via a dedicated email and ticketing system.

---

## 3.7 Maintenance (MA)

- **MA-1: Maintenance Policy**  
  Maintenance activities are scheduled and logged.

- **MA-2: Remote Maintenance**  
  Remote maintenance is conducted over encrypted VPN connections.

---

## 3.8 Media Protection (MP)

- **MP-1: Media Protection Policy**  
  All removable media must be encrypted.

- **MP-2: Media Sanitization**  
  Media is sanitized using DoD-approved tools before disposal.

---

## 3.9 Physical Protection (PE)

- **PE-1: Physical Security Policy**  
  Access to server rooms is restricted via badge readers.

- **PE-2: Escort Policy**  
  Visitors are escorted at all times within secure areas.

---

## 3.10 Personnel Security (PS)

- **PS-1: Personnel Screening**  
  Background checks are conducted for all new hires.

- **PS-2: Termination Procedures**  
  Access is revoked immediately upon employee termination.

---

## 3.11 Risk Assessment (RA)

- **RA-1: Risk Assessment Policy**  
  Annual risk assessments are conducted using NIST guidelines.

- **RA-2: Vulnerability Scanning**  
  Systems are scanned monthly using Nessus.

---

## 3.12 Security Assessment (CA)

- **CA-1: Security Control Assessment**  
  Controls are assessed annually by internal audit.

- **CA-2: Plan of Action and Milestones (POA&M)**  
  Gaps are documented and tracked in a POA&M spreadsheet.

---

## 3.13 System and Communications Protection (SC)

- **SC-1: System Protection Policy**  
  All systems are hardened according to CIS benchmarks.

- **SC-2: Encryption of Data in Transit**  
  TLS 1.2+ is used for all data transmissions.

---

## 3.14 System and Information Integrity (SI)

- **SI-1: Integrity Policy**  
  Antivirus and endpoint protection are deployed on all devices.

- **SI-2: Flaw Remediation**  
  Patches are applied within 7 days of release for critical vulnerabilities.

---

## 4. Appendices

## Appendix A: Acronyms

- CUI: Controlled Unclassified Information  
- SSP: System Security Plan  
- POA&M: Plan of Action and Milestones  
- MFA: Multi-Factor Authentication  
- RBAC: Role-Based Access Control  
- SIEM: Security Information and Event Management  
- VPN: Virtual Private Network  
- AD: Active Directory  
- IR: Incident Response  

## Appendix B: References

- NIST SP 800-171 Rev. 2 – Protecting Controlled Unclassified Information in Nonfederal Systems  
- NIST SP 800-171A – Assessment Guide for NIST 800-171  
- CIS Benchmarks – System Hardening Guidelines  
- Microsoft Azure Security Documentation  
- Splunk Cloud SIEM Documentation  



