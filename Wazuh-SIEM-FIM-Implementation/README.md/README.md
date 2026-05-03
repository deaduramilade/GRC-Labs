# Technical Assessment & Control Evidence

## 📝 Document Overview
This directory contains the formal professional deliverable titled: **"Security Control Validation Report: Centralised Logging and File Integrity Monitoring (FIM) Deployment"**.

### **Scope of Assessment**
* **In-Scope:** Wazuh Management Plane (Ubuntu 24 Pro) and monitored Kali Purple endpoint.
* **Control Validation:** Testing the effectiveness of FIM triggers upon unauthorised file modifications in `/var/ossec/etc/`.

### **Key Technical Observations**
1.  **Integrity Validation:** Successfully generated Level 7 security alerts upon system configuration changes.
2.  **Cryptographic Handshake:** Validated the registration process using unique cryptographic keys to prevent rogue agent injection.
3.  **Remediation Insight:** Identified SHA1 deprecation issues within the Ubuntu 24 Pro environment and provided a technical roadmap for repository signature updates.

## 📊 Evidence of Control Effectiveness
The following artifacts prove the implementation of the controls:
1.  **Control Matrix:** Located in the main PDF report.
2.  **SIEM Dashboard Logs:** Real-time telemetry showing "Who, What, and When" of file changes.

---
**Disclaimer:** This report is based on a point-in-time assessment. Continuous monitoring is required to maintain the security posture described.
