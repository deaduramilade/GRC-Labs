# Novalink Governance Lab – Custom GRC Engineering Exercise  
**Lab Title:** Governance in a Borderless World: Building a Secure Operating Model for Novalink  
## **Company Scenario**  
Novalink is a fast-growing fintech SaaS startup providing cross-border payment infrastructure and compliance automation tools. The company operates in 12 countries, serves 450+ financial institutions, and processes sensitive payment and KYC data.  
Due to rapid growth and recent regulatory scrutiny (including NDPR, GDPR, and PCI DSS requirements), the leadership team has asked the GRC team to design and document a robust Information Security Governance Operating Model.  
## **Lab Objectives**  
1. **Design** a modern security governance structure suitable for a borderless fintech company.  
2. **Create** key governance artifacts (org chart, RACI, charter).  
3. **Perform** a practical technical validation exercise (using Nessus and Kali Linux) to test governance controls in a simulated environment.  
   
### Phase 1: Information Security Governance Structure (Org Chart)  
**Task:** Design a reporting structure that ensures independence for the security function while maintaining alignment with business goals.  
- **Board of Directors / Risk Committee:** Ultimate oversight.  
- **Chief Executive Officer (CEO):** Overall executive accountability.  
- **Chief Information Security Officer (CISO):** Reports directly to the CEO (to avoid conflict of interest with the CTO/IT).  
- **Information Security Steering Committee (ISSC):** Cross-functional advisory body.  
- **CISO Direct Reports:**  
- **Head of GRC:** Manages compliance (PCI DSS, GDPR), audits, and vendor risk.  
- **Head of Security Operations (SecOps):** Manages monitoring, incident response, and vulnerability management.  
- **Head of Product Security (AppSec):** Integrates security into the SDLC.  
### Phase 2: Information Security Steering Committee (ISSC) Charter  
**Task:** Draft the charter to mandate cross-departmental security collaboration.  
- **Purpose:** To align Novalink’s security strategy with business objectives and ensure adequate resource allocation for risk mitigation.  
- **Core Members:** CISO (Chair), CTO, CFO, Chief Legal/Privacy Officer, and VP of Product.  
- **Meeting Frequency:** Quarterly, or ad-hoc during critical security incidents.  
- **Key Responsibilities:** Reviewing major risk assessments, approving the annual security budget, and signing off on core security policies.  
###    
### Phase 3: RACI Matrix for Core Security Operations  
**Task:** Develop a RACI (Responsible, Accountable, Consulted, Informed) matrix to eliminate ambiguity in security responsibilities.  
| | | | | | |  
|-|-|-|-|-|-|  
| **Activity / Domain** | **CISO** | **GRC Team** | **SecOps Team** | **Engineering/DevOps** | **ISSC** |   
| **Policy Creation & Update** | A | R | C | C | I |   
| **Vulnerability Scanning** | A | I | R | C | I |   
| **Patching & Remediation** | A | C | I | R | I |   
| **Compliance Audits (PCI DSS)** | A | R | C | C | I |   
###    
###    
### Phase 4: High-Level Security Policies & Baseline Alignment  
**Task:** Identify the core policies Novalink must implement to satisfy its regulatory requirements (GDPR, NDPR, PCI DSS).  
- **Information Security Policy:** The overarching mandate.  
- **Access Control Policy:** Enforcing Least Privilege and Role-Based Access Control (RBAC).  
- **Vulnerability Management Policy:** Mandating regular scanning (e.g., Nessus) and strict SLAs for patching critical flaws.  
- **Secure Software Development Life Cycle (SSDLC) Policy:** Mandating code reviews, input validation, and OWASP Top 10 mitigation.  
### Phase 5: Technical Practical Validation (Nessus & Kali Linux)  
**Objective:** Validate governance controls through hands-on vulnerability scanning and penetration testing in a controlled lab environment.  
**Lab Environment:**  
- **Attacker/Scanner:** Kali Linux VM  
- **Vulnerability Scanner:** Tenable Nessus (Installed on Kali or running alongside it)  
- **Target:** OWASP Broken Web Applications (BWA) VM (representing a poorly governed legacy system in the Novalink environment).  
**Task 1: Automated Vulnerability Assessment (Nessus)**  
1. Launch Nessus and run a **Basic Network Scan** against the Target IP (<TARGET_IP>).  
2. Review the scan results to identify missing patches, open ports, and default configurations.  
3. **Governance Tie-in:** Export the Nessus executive summary. Document how these findings violate Novalink’s *Vulnerability Management Policy* and highlight the failure of the  *Asset Management* controls.  
**Task 2: Asset Discovery & Service Enumeration (Kali/Nmap)**  
Bash  
nmap -sV -sC -O -p- -oA novalink_initial_scan <TARGET_IP>  
   
- Compare the Nmap output with the Nessus scan to verify the attack surface.  
**Task 3: Application Vulnerability Validation (OWASP Top 10)**  
Browse to http://<TARGET_IP> and navigate to **DVWA (Damn Vulnerable Web App)**.  
1. **Test Injection (OWASP A03:2021 - Injection):** * Navigate to the Command Injection module in DVWA.  
- Input 127.0.0.1; cat /etc/passwd to validate if OS commands can be executed.  
2. **Test Broken Access Control / Default Credentials (OWASP A01:2021):**  
- Attempt to log in using default administrative credentials (e.g., admin / password).  
**Task 4: Mapping Findings to Governance Failures**  
Document how the technical findings map to governance gaps:  
- *Command Injection Success:* Represents a failure in the **Secure SDLC Policy** (lack of input validation and developer training).  
- *Default Credentials:* Represents a direct violation of the **Access Control Policy** and PCI DSS Requirement 8 (Identify and authenticate access to system components).  
- *Nessus Critical Findings:* Demonstrates a breakdown in the **Patch Management SLAs**.  
**Deliverable for Phase 5:**  
- A PDF of the Nessus Scan Summary.  
- Screenshots of the Nmap scan and the successful DVWA injection test.  
- A "Remediation & Governance Action Plan" memo addressed to the ISSC outlining the policy gaps that allowed these technical vulnerabilities to exist.  
   
