# Project 1: Enterprise Qualitative Risk Register & Mitigation Strategy

##  Executive Overview
This project demonstrates the design and implementation of a Qualitative Risk Register for a mock FinTech startup ("Apex Payments"). The organization is scaling rapidly, processing credit card transactions, and adopting cloud-native infrastructure. The objective of this assessment is to identify core operational, technical, and compliance threats, analyze their inherent risk levels, and establish structured risk treatment plans to lower residual risk to acceptable thresholds.

---

##  Risk Scoring Methodology
Risks are evaluated using a standard **5x5 Qualitative Matrix** across two variables: **Likelihood** (Probability of occurrence) and **Impact** (Severity of financial, operational, or reputational damage).

*   **Risk Score** = $\text{Likelihood} \times \text{Impact}$ (Scale of 1 to 25)
*   **Inherent Risk:** The risk level *before* any security controls are applied.
*   **Residual Risk:** The remaining risk level *after* current controls are successfully implemented.

### Scoring Tiers:
*   🔴 **Critical (15–25):** Requires immediate executive attention and automated controls.
*   🟡 **Medium (6–14):** Requires continuous monitoring and documented procedures.
*   🟢 **Low (1–5):** Acceptable risk; managed through routine operational logs.

---

##  Enterprise Risk Register

| Risk ID | Threat Scenario | Inherent L | Inherent I | Inherent Score | Compensating / Implemented Controls | Residual L | Residual I | Residual Score | Risk Treatment |
| :--- | :--- | :---: | :---: | :---: | :--- | :---: | :---: | :---: | :--- |
| **RSK-01** | **Ransomware / Malware Attack** <br> Phishing email compromises an internal employee workstation, spreading to corporate shares. | 4 | 5 | **20 (Critical)** | • Enforced corporate-wide MFA via Entra ID. <br>• Implemented weekly automated endpoint isolation via EDR. <br>• Isolated immutable cloud backups. | 2 | 4 | **8 (Medium)** | **Mitigate** (Reduce risk through active defense) |
| **RSK-02** | **Insider Threat / Data Leakage** <br> Disgruntled employee exfiltrates sensitive customer financial records via a personal cloud drive. | 3 | 5 | **15 (Critical)** | • Implemented Role-Based Access Control (RBAC) / Least Privilege. <br>• Configured Data Loss Prevention (DLP) blocks for external domains. | 2 | 3 | **6 (Medium)** | **Mitigate** (Restrict data movement permissions) |
| **RSK-03** | **Unpatched Vulnerability Exploitation** <br> Threat actor exploits a known critical vulnerability in an internet-facing web server. | 4 | 4 | **16 (Critical)** | • Established a strict 14-day SLA patching window for Critical CVEs. <br>• Deployed a Web Application Firewall (WAF). | 2 | 3 | **6 (Medium)** | **Mitigate** (Automate vulnerability patching lifecycle) |
| **RSK-04** | **Third-Party Vendor Breach** <br> A critical cloud-based HR/Payroll platform experiences a data breach exposing PII. | 3 | 4 | **12 (Medium)** | • Mandatory SOC 2 Type II review prior to onboarding. <br>• Annual vendor security questionnaire and scoring evaluations. | 2 | 4 | **8 (Medium)** | **Transfer** (Add contractual indemnification clauses) |
| **RSK-05** | **Shadow AI Data Leakage** <br> Engineering team inputs proprietary source code into an unapproved public AI tool. | 4 | 3 | **12 (Medium)** | • Enacted an Enterprise AI Acceptable Use Policy. <br>• Configured CASB (Cloud Access Security Broker) filters to block public AI URLs. | 2 | 3 | **6 (Medium)** | **Mitigate** (Employee training + technical URL blocks) |

---

##  Visualizing the Risk Matrix
Below is the qualitative mapping mapping our identified corporate risks from their raw, inherent state down to their treated, residual state.

```text
INHERENT RISK HEATMAP                     RESIDUAL RISK HEATMAP
   5 | [   ] [   ] [   ] [01 ] [02 ]         5 | [   ] [   ] [   ] [   ] [   ]
I  4 | [   ] [   ] [   ] [03 ] [   ]      I  4 | [   ] [   ] [   ] [01 ] [04 ]
M  3 | [   ] [   ] [   ] [04 ] [05 ]      M  3 | [   ] [   ] [   ] [02 ] [03 ] [05 ]
P  2 | [   ] [   ] [   ] [   ] [   ]      P  2 | [   ] [   ] [   ] [   ] [   ]
   1 | [   ] [   ] [   ] [   ] [   ]         1 | [   ] [   ] [   ] [   ] [   ]
     -------------------------               -------------------------
       1     2     3     4     5               1     2     3     4     5
             LIKELIHOOD                              LIKELIHOOD
```

## Key Insights & Business Alignment

1. The Reality of Residual Risk: As a GRC analyst, I recognize that zero risk does not exist. Even with top-tier EDR and MFA, a clever ransomware strain can still execute (RSK-01 drops from a 20 down to an 8, but it does not hit 0). The goal is bringing the threat down below the company's Risk Appetite Threshold.

2. Addressing Modern Paradigms: RSK-05 directly targets the modern challenge of Shadow AI. By pairing policy training with a technical CASB control, the company protects its intellectual property without stopping innovation.

3. Framework Allignments: The controls selected above directly map back to NIST CSF 2.0 (PR.AC-1: Identity Management) and NIST 800-53 (SI-2: Flaw Remediation), making this risk register audit-ready for standard compliance verification frameworks.
