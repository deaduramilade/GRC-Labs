# Web Application Security Assessment & Risk Analysis
**Project:** Legacy E-Commerce & Administrative Portal Security Audit  
**Frameworks:** OWASP Top 10 (2021), NIST SP 800-53, PCI-DSS v4.0  
**Consultant:** Samuel Adeoluwa Okunribido  

---

## 1. Executive Summary
A comprehensive security assessment was conducted on the organization’s web application environment to evaluate the effectiveness of existing security controls. The assessment identified systemic vulnerabilities, including **Broken Access Control (A01)**, **Cryptographic Failures (A02)**, and **Injection (A03)**. 

These flaws indicate a critical breakdown in the Secure Development Lifecycle (SDLC) and pose a significant threat to data integrity and regulatory compliance. Quantitative risk analysis indicates substantial potential financial exposure due to unauthenticated administrative access and plaintext credential transmission. 

> **Key Recommendation:** Immediate remediation of high-severity findings and the integration of automated security testing into the CI/CD pipeline are required to mitigate identified business risks.

---

## 2. Engagement Parameters

### **Project Scope & Limitations**
The scope of this assessment was restricted to the **Legacy E-Commerce Environment (172.16.13.129)**. Testing was conducted within a time-boxed window to identify high-impact vulnerabilities. Out-of-scope activities included Denial of Service (DoS) testing, social engineering, and physical security assessments.

### **Operational Assumptions**
* The target environment is assumed to be a representative mirror of the organization’s legacy production stack.
* Internal security controls (WAF, IDS/IPS) were evaluated in their current state without prior tuning for this engagement.

### **Professional Disclaimer**
This report is provided for **risk management and security advisory purposes only**. All identified vulnerabilities were validated via Proof of Concept (PoC) in a non-destructive manner to ensure continuous service availability.

---

## 3. Methodology & Framework Alignment
This assessment utilized the **NIST Cybersecurity Framework (CSF)** "Detect" and "Protect" functions, mapped against the **OWASP Top 10 (2021)** for technical validation.

### **Technical Assessment Stack**
* **Nmap:** Infrastructure service enumeration and service discovery.
* **Burp Suite Professional:** Intercepting proxy for traffic analysis, session manipulation, and manual injection.
* **Kali Linux:** Standardized attack platform for controlled vulnerability validation.

---

## 4. Vulnerability Analysis & Risk Quantification

### **4.1 A01: Broken Access Control**
* **Observation:** The administrative interface (`/bodgeit/admin.jsp`) was accessible without valid authentication tokens.
* **GRC Impact:** Failure to meet **NIST SP 800-53 (AC-2)** Access Management requirements.
* **Risk:** Critical. Unauthorized actors can perform administrative functions, leading to complete system compromise.

<details>
<summary><b>Click to View Technical Evidence (PoC)</b></summary>

#### **Evidence: Unauthorized Admin Access**
![Admin Access Screenshot](link-to-your-image-here.png)
*Observation: Direct URL navigation bypassed all authentication checks, exposing the administrative console.*
</details>

### **4.2 A02: Cryptographic Failures**
* **Observation:** User credentials transmitted via HTTP Basic Authentication using Base64 encoding without TLS encryption.
* **GRC Impact:** Non-compliance with **PCI-DSS (Req. 4.1)** and **GDPR** data protection principles.
* **Risk:** High. Facilitates credential harvesting via Man-in-the-Middle (MitM) attacks.

### **4.3 A03: Injection (SQLi)**
* **Observation:** Search functionality vulnerable to SQL Injection via tautology payloads (`' OR 1=1 --`).
* **GRC Impact:** Breach of **CIS Control 16** (Application Software Security).
* **Risk:** High. Potential for unauthorized database exfiltration and loss of data integrity.

<details>
<summary><b>Click to View Technical Evidence (PoC)</b></summary>

#### **Evidence: SQL Injection Validation**
![SQLi Screenshot](link-to-your-image-here.png)
*Observation: Payload execution resulted in the return of the full product database, bypassing search filters.*
</details>

---

## 5. Strategic Remediation Roadmap

| Phase | Action Item | Control Mapping | Priority |
| :--- | :--- | :--- | :--- |
| **Immediate** | Enforce TLS 1.3 for all authenticated traffic. | NIST CSF PR.DS-2 | Critical |
| **Short-Term** | Implement Parameterized Queries / Prepared Statements. | OWASP ASVS | High |
| **Short-Term** | Enforce Server-Side Role-Based Access Control (RBAC). | NIST 800-53 AC-3 | High |
| **Long-Term** | Integrate DAST/SAST into the CI/CD Pipeline. | ISO 27001 A.14.2 | Medium |

---

## 6. Compliance Gap Analysis
| Framework | Status | Gap Identified |
| :--- | :--- | :--- |
| **PCI-DSS v4.0** | ❌ Non-Compliant | Requirement 4.1: Plaintext transmission of CHD. |
| **NIST 800-53** | ⚠️ Partial | Control AC-2: Insufficient session management. |
| **OWASP Top 10** | ❌ Failed | Multiple violations across Top 3 categories. |
