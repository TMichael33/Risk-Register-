# Project 1: Enterprise Qualitative Risk Register & Mitigation Strategy

##  Executive Overview
This project demonstrates the design and implementation of a Qualitative Risk Register for a mock FinTech startup ("Apex Payments"). The organization is scaling rapidly, processing credit card transactions, and adopting cloud-native infrastructure. The objective of this risk assessment is to identify core operational, technical, and compliance threats, analyze their inherent risk levels, and establish structured risk treatment plans to lower residual risk to acceptable thresholds.

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

<table width="100%">
  <thead>
    <tr>
      <th width="8%">Risk ID</th>
      <th width="25%">Threat Scenario</th>
      <th width="8%">Inherent L</th>
      <th width="8%">Inherent I</th>
      <th width="10%">Inherent Score</th>
      <th width="25%">Compensating / Implemented Controls</th>
      <th width="8%">Residual L</th>
      <th width="8%">Residual I</th>
      <th width="10%">Residual Score</th>
      <th width="15%">Risk Treatment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>RSK-01</b></td>
      <td><b>Ransomware / Malware Attack</b><br>Phishing email compromises an internal employee workstation, spreading to corporate shares.</td>
      <td align="center">4</td>
      <td align="center">5</td>
      <td align="center" bgcolor="#ffcccc"><b>20 (Critical)</b></td>
      <td>• Enforced corporate-wide MFA via Entra ID.<br>• Implemented weekly automated endpoint isolation via EDR.<br>• Isolated immutable cloud backups.</td>
      <td align="center">2</td>
      <td align="center">4</td>
      <td align="center" bgcolor="#fff2cc"><b>8 (Medium)</b></td>
      <td><b>Mitigate</b><br>(Reduce risk through active defense)</td>
    </tr>
    <tr>
      <td><b>RSK-02</b></td>
      <td><b>Insider Threat / Data Leakage</b><br>Disgruntled employee exfiltrates sensitive customer financial records via a personal cloud drive.</td>
      <td align="center">3</td>
      <td align="center">5</td>
      <td align="center" bgcolor="#ffcccc"><b>15 (Critical)</b></td>
      <td>• Implemented Role-Based Access Control (RBAC) / Least Privilege.<br>• Configured Data Loss Prevention (DLP) blocks for external domains.</td>
      <td align="center">2</td>
      <td align="center">3</td>
      <td align="center" bgcolor="#fff2cc"><b>6 (Medium)</b></td>
      <td><b>Mitigate</b><br>(Restrict data movement)</td>
    </tr>
  </tbody>
</table>
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
