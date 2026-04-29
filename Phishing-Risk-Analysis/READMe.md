# Human Risk Factor: Phishing Simulation & Quantitative Risk Analysis
**Status:** Completed | **Category:** Risk Management & Security Advisory  
**Consultant:** Samuel Adeoluwa Okunribido  
**Frameworks:** NIST 800-53, ISO 27001, PCI-DSS v4.0

---

## 1. Executive Summary
This advisory engagement analyzed the resilience of a 2,000-employee workforce against sophisticated phishing vectors. Testing revealed a **Critical Risk** profile, specifically within authority-based social engineering (Campaign B), which yielded a **30% credential theft rate**.

Financial modeling projects an **Annualized Loss Expectancy (ALE) of $652.5 Million** if current control gaps remain unaddressed. The implementation of Adaptive MFA is identified as the highest-impact remediation, offering an exceptional ROI of **724,175%**.

---

## 2. Engagement Parameters

### **Scope & Methodology**
The assessment utilized three phishing archetypes to measure the "Human Firewall":
* **Campaign A (Urgency):** External notification requiring immediate action.
* **Campaign B (Authority):** Simulated internal communication from executive leadership.
* **Campaign C (Financial):** Benefit-themed solicitation.

### **Risk Quantification Logic**
We utilized the industry-standard **ALE = SLE × ARO** model to provide a business-centric view of vulnerability impact, moving beyond simple "click rates" to actual financial exposure.

---

## 3. Performance Metrics & Vulnerability Analysis

| Metric | Campaign A | Campaign B | Campaign C |
| :--- | :--- | :--- | :--- |
| **Open Rate** | 20% | 40% | 25% |
| **Click-Through Rate** | 10% | 35% | 15% |
| **Credential Submission** | 5% | 30% | 10% |
| **Severity** | Medium | **CRITICAL** | High |

> **Analyst Note:** The high success of Campaign B (Authority) indicates a significant cultural vulnerability regarding internal verification protocols.

---

## 4. Financial Exposure & The Business Case

| Risk Metric | Value | Industry Benchmark | Variance |
| :--- | :--- | :--- | :--- |
| **Projected Breaches** | 150 / Year | 85 / Year | +76% |
| **Annualized Loss (ALE)** | **$652.5M** | $285M | +128% |
| **MFA Implementation ROI** | **724,175%** | 350% | Exceptional |

---

## 5. Strategic Remediation Roadmap

### **Phase 1: Immediate Technical Controls (Q2 2026)**
* **Control:** Deploy Adaptive Multi-Factor Authentication (MFA).
* **Mapping:** NIST 800-53 (IA-2), PCI-DSS (Req. 8.3).
* **Expected Impact:** 99% reduction in credential-based breach success.

### **Phase 2: Administrative Governance (Q3 2026)**
* **Control:** Just-in-Time (JIT) Security Awareness Training.
* **Mapping:** ISO 27001 (A.7.2.2), NIST CSF (PR.AT-1).
* **Expected Impact:** Reduction in human susceptibility and click-through rates.

### **Phase 3: Defensive Engineering (Q4 2026)**
* **Control:** DMARC/SPF/DKIM Hardening & Advanced Email Filtering.
* **Mapping:** CIS Control 9.

---

## 6. Compliance Gap Analysis

| Framework | Requirement | Status | Gap Identified |
| :--- | :--- | :--- | :--- |
| **NIST 800-53** | AT-2 (Awareness) | ⚠️ Partial | Training frequency does not match current threat velocity. |
| **PCI-DSS v4.0** | Req 8.3 (MFA) | ❌ Fail | Lack of MFA for administrative and sensitive access. |
| **ISO 27001** | A.12.6.1 (Vuln) | ❌ Fail | High susceptibility to social engineering threats. |

---

## ⚖️ Professional Disclaimer
Financial projections are based on industry-standard cost-per-record breach data (IBM/Ponemon). Remediation ROI is calculated based on expected control effectiveness against validated simulation success rates.
