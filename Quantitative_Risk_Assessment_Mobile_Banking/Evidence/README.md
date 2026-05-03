[← Back to GRC Portfolio](../README.md)

# Quantitative Cyber Risk Assessment & Remediation Roadmap: "SecureMobile"

**Strategic Focus:** Financial Risk Quantification (ALE), Control ROI, and NIST/PCI Alignment  
**Consultant:** Samuel Okunribido  

---

## 1. Executive Summary
This assessment evaluates the financial exposure of the "SecureMobile" platform. The analysis identified an **Annualized Loss Expectancy (ALE) of $35M**. By implementing the recommended GRC controls, the organization can achieve a **77% risk reduction** with an aggregate **ROI of 3,600%**.

## 2. Risk Quantification Matrix
| Vulnerability | Single Loss (SLE) | Frequency (ARO) | Annual Risk (ALE) | NIST CSF Mapping |
| :--- | :--- | :--- | :--- | :--- |
| **Database Injection** | $125,000,000 | 0.25 | **$31,250,000** | PR.DS-01 (Data Integrity) |
| **Session Hijacking** | $7,500,000 | 0.40 | **$3,000,000** | PR.AC-01 (Access Control) |
| **API Auth Bypass** | $5,000,000 | 0.15 | **$750,000** | PR.AC-03 (API Security) |

## 3. Remediation & Financial Justification (ROI)
The following controls are prioritized based on their ability to mitigate the highest financial risks.

* **Web Application Firewall (WAF):** Mitigates Database Injection. Cost: $150k | Risk Reduction: $23.4M | **ROI: 13,292%**
* **MFA Enhancement:** Mitigates Session Hijacking. Cost: $200k | Risk Reduction: $2.8M | **ROI: 1,139%**

## 4. Engagement Evidence & Documentation
* [Download Full Detailed Report (PDF)](./Reports/Lab_3b_Risk_Quantification.pdf)
* **Risk Heat Map:** ![Heat Map](./Evidence/risk_map.png)

---
*Disclaimer: This is a professional risk advisory deliverable. Financial figures are based on industry-standard record valuation ($250/record).*
