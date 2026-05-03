# Security Control Validation: Centralised Logging & File Integrity Monitoring (FIM)

## 📌 Executive Summary
This project demonstrates the operationalisation of a centralized risk monitoring environment using the **Wazuh Open-Source XDR/SIEM**. By deploying a Manager-Agent architecture, I established continuous visibility into unauthorised file modifications—bridging the gap between high-level compliance policies and technical enforcement.

## 🛡️ GRC Framework Alignment
This implementation directly satisfies specific technical controls within the following global standards:
* **PCI DSS v4.0 (Req 11.5):** Deployment of FIM to detect unauthorised changes to critical system and financial files.
* **ISO/IEC 27001:2022 (A.8.15 & A.8.16):** Logging, monitoring, and event management requirements.
* **NIST CSF v2.0 (PR.DS-01):** Ensuring data integrity is maintained through continuous monitoring.

## ⚙️ Technical Environment
* **Security Platform:** Wazuh Indexer, Server, & Dashboard.
* **Operating Systems:** Ubuntu 24 Pro (Manager) & Kali Purple (Monitored Endpoint).
* **Key Feature:** Cryptographic agent authentication for secure asset onboarding.

## 📂 Project Structure
* `Reports/`: Contains the full Technical Security Assessment & Control Validation Report.
* `Evidence/`: Technical screenshots of dashboard alerts and configuration files.

---
*Developed by Samuel Okunribido – GRC Engineering Portfolio*
