# System Security Plan (SSP)
**Organization Name**: SecureTech Solutions  
**System Name**: SecureTech CUI Environment  
**System Owner**: Dylan Nguyen
**Date**: July 28, 2025  

---

## 1. Company Overview
SecureTech Solutions is a fictional small business specializing in providing IT services and cybersecurity consulting to government contractors and small-to-medium enterprises (SMEs). With a team of 25 professionals, SecureTech Solutions offers secure cloud infrastructure management, endpoint protection, and compliance advisory services.

The company’s mission is to empower clients to meet federal cybersecurity requirements and protect sensitive data through tailored, cost-effective solutions. SecureTech Solutions operates in a hybrid cloud environment and handles Controlled Unclassified Information (CUI) on behalf of its clients, making compliance with NIST SP 800-171 a critical component of its operations.

This System Security Plan (SSP) outlines the technical and procedural safeguards implemented by SecureTech Solutions to meet primarily three control families defined in NIST SP 800-171, ensuring the confidentiality, integrity, and availability of CUI within its systems.
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



