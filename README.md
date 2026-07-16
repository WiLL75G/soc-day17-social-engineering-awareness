# SOC Tier 1 Incident Report: Social Engineering & Security Awareness Lab

---

## Incident Summary

- **Incident Type:** Social Engineering Simulation & Security Awareness Assessment
- **Severity:** High (Human Attack Vector No Technical Control Can Block)
- **Detection Method:** Phishing Analysis + Vishing Script Review + Attack Documentation
- **Tools Used:** MXToolbox, Manual Header Analysis, MITRE ATT&CK Framework
- **Status:** Complete Awareness Training Material Delivered

---

## Executive Summary

A social engineering security awareness lab was conducted to document real attack techniques targeting human behaviour rather than technical systems. Five social engineering attack types were analysed and documented. Two attack simulations were performed a spoofed PayPal phishing email and a vishing IT support call script. A full security awareness training guide was produced for employee education. MITRE ATT&CK techniques were mapped across all attack types.

---

## Affected System

- **Target:** Human layer employees and end users
- **Attack Surface:** Email, phone, physical media, social media
- **Organisation:** Nexus Corp SOC
- **Scope:** All employees with system or data access
- **Risk Level:** Critical no technical control fully mitigates human error

---

## Investigation Methodology

---

### 1. Social Engineering Attack Type Documentation

- Documented 5 core social engineering attack types used by real attackers
- Mapped each attack type to MITRE ATT&CK techniques
- Identified red flags and detection methods for each attack
- Built a SOC detection summary table across all 5 attack types

#### SOC Observations:

- Social engineering exploits psychology urgency, authority, and fear are the primary weapons
- No firewall or SIEM can stop an employee from handing over credentials voluntarily
- SOC analysts must understand attack techniques to build effective detection and awareness programs

---

### 2. Phishing Email Analysis Spoofed PayPal

- Analysed a real-world phishing email template spoofing PayPal
- Applied the SLAM method Sender, Links, Attachments, Message
- Identified 7 phishing indicators including spoofed domain, mismatched Reply-To, and urgency language
- Mapped the full 5 step attack anatomy from lure to credential harvest
- Documented SOC response actions for phishing incidents

#### SOC Observations:

- The Reply-To field is the most reliable phishing indicator it reveals the real attacker address
- Urgency language bypasses critical thinking "24 hours" is a deliberate pressure tactic
- SPF/DKIM absence confirms the email was not sent from the legitimate domain

---

### 3. Vishing Attack Analysis Fake IT Support Call

- Analysed a real world vishing script impersonating IT support
- Identified 5 vishing indicators including unsolicited call, password request, and OTP harvesting
- Documented the verification protocol employees must follow
- Documented SOC response actions for vishing incidents

#### SOC Observations:

- Requesting an OTP code over the phone is always an account takeover attempt no exceptions
- Vishing attacks are harder to detect than phishing they leave no digital footprint
- A callback verification policy is the strongest defence against vishing

---

### 4. Security Awareness Training Material Built

- Built a complete 6 module security awareness training guide for Nexus Corp employees
- Module 1 — The 6 Golden Rules of Security
- Module 2 — SLAM Method for phishing detection
- Module 3 — Phone call verification protocol
- Module 4 — 4 real attack scenarios with correct responses
- Module 5 — Incident reporting procedure
- Module 6 — Security quick reference card

#### SOC Observations:

- Security awareness training is the most cost effective security control in any organisation
- Real scenario based training is more effective than theory employees remember stories
- A clear reporting process removes the barrier to reporting suspicious activity

---

## MITRE ATT&CK Mapping

| Technique ID | Technique | Attack Type |
|---|---|---|
| T1566.001 | Phishing: Spearphishing Link | Phishing Email |
| T1036.005 | Masquerading | Spoofed PayPal Sender |
| T1583.001 | Acquire Infrastructure: Domains | Malicious Domain |
| T1056.003 | Input Capture: Web Portal Capture | Credential Harvesting |
| T1598 | Phishing for Information | Vishing + Pretexting |
| T1091 | Replication Through Removable Media | Baiting USB Drop |

---

## SOC Analyst Findings

- 5 social engineering attack types documented with red flags and detection methods
- Phishing email confirmed malicious 7 indicators identified including spoofed domain and malicious Reply-To
- Vishing script confirmed attack OTP harvesting attempt identified
- Security awareness training guide produced covering all 5 attack types
- Human layer identified as the highest-risk attack surface in the organisation

---

## SOC Analyst Response

- Documented all 5 social engineering attack types for SOC reference
- Produced phishing analysis report for analyst training
- Produced vishing analysis with verification protocol for employees
- Delivered 6 module security awareness training guide to Nexus Corp
- Recommended DMARC/DKIM/SPF implementation to prevent email spoofing
- Recommended callback verification policy for all IT support calls
- Recommended mandatory annual security awareness training for all staff

---

## Analyst Insight

Social engineering is the most underestimated attack vector in cybersecurity. Every technical control firewalls, SIEMs, EDR can be bypassed in seconds if an employee hands over their credentials voluntarily. A SOC analyst who only understands technical threats is only protecting half the attack surface. The human layer requires a different discipline empathy, communication, and education. Building security awareness is just as important as building detection rules.

---

## Learning Outcome

- Document and analyse all 5 core social engineering attack types
- Apply the SLAM method to identify phishing indicators
- Analyse a real vishing attack script and identify manipulation tactics
- Map social engineering techniques to MITRE ATT&CK framework
- Build a professional security awareness training program
- Understand why human behaviour is the highest risk attack surface
- Produce SOC response recommendations for human layer attacks

---

## Repository Structure

```
social-engineering-security-awareness-lab/
├── README.md
├── reports/
│   ├── attack_types.md
│   ├── phishing_analysis.md
│   └── security_awareness_training.md

```

---

## Conclusion

This lab demonstrates a complete social engineering awareness and analysis workflow. Five attack types were documented, two attack simulations were analysed, and a full 6 module security awareness training guide was produced. MITRE ATT&CK techniques were mapped across all attack types. This project proves that a SOC analyst understands threats beyond the technical layer and can build the human defences that no firewall can provide.
