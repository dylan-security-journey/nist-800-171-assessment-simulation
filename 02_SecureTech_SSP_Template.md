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

### 📊 Diagram 

!SecureTech Network Diagram
---

## 3. Control Families

### 3.1 Access Control (AC)
- AC-1: [Implementation Details]
- AC-2: [Implementation Details]
...

### 3.2 Awareness and Training (AT)
- AT-1: [Implementation Details]
- AT-2: [Implementation Details]
...

### 3.3 Audit and Accountability (AU)
- AU-1: [Implementation Details]
- AU-2: [Implementation Details]
...

### 3.4 Configuration Management (CM)
- CM-1: [Implementation Details]
- CM-2: [Implementation Details]
...

### 3.5 Identification and Authentication (IA)
- IA-1: [Implementation Details]
- IA-2: [Implementation Details]
...

### 3.6 Incident Response (IR)
- IR-1: [Implementation Details]
- IR-2: [Implementation Details]
...

### 3.7 Maintenance (MA)
- MA-1: [Implementation Details]
- MA-2: [Implementation Details]
...

### 3.8 Media Protection (MP)
- MP-1: [Implementation Details]
- MP-2: [Implementation Details]
...

### 3.9 Personnel Security (PS)
- PS-1: [Implementation Details]
- PS-2: [Implementation Details]
...

### 3.10 Physical Protection (PE)
- PE-1: [Implementation Details]
- PE-2: [Implementation Details]
...

### 3.11 Risk Assessment (RA)
- RA-1: [Implementation Details]
- RA-2: [Implementation Details]
...

### 3.12 Security Assessment (CA)
- CA-1: [Implementation Details]
- CA-2: [Implementation Details]
...

### 3.13 System and Communications Protection (SC)
- SC-1: [Implementation Details]
- SC-2: [Implementation Details]
...

### 3.14 System and Information Integrity (SI)
- SI-1: [Implementation Details]
- SI-2: [Implementation Details]
...

---

## 4. Appendices
- Appendix A: Acronyms
- Appendix B: References
- Appendix C: Diagrams

