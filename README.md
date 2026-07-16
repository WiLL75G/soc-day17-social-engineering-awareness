# Social Engineering Analysis and Security Awareness

Documenting the attacks no firewall stops. Five social engineering types broken down, two attack scripts analysed, and a training guide written for the people who actually have to spot them.

## At a Glance

| Field | Detail |
| --- | --- |
| Work Type | Social engineering analysis and awareness material |
| Attack Types Documented | 5 |
| Attacks Analysed | Spoofed PayPal phishing email, IT support vishing script |
| Deliverable | 6 module security awareness training guide |
| Target Layer | Human, email, phone, physical media, social media |
| Framework | MITRE ATT&CK |

## What This Is

Every technical control in a SOC assumes the attacker has to break in. Social engineering asks someone to open the door.

An employee who types their password into a convincing page has defeated the firewall, the SIEM, and the EDR simultaneously, and none of them logged anything wrong. The credentials were valid. The login was legitimate. The control worked exactly as designed.

This lab documents the attacks that work that way, and produces the only control that addresses them, which is teaching people what they look like.

Scope stated plainly: this is analysis and awareness material, not a live phishing campaign against real users. No employees were tested. What it demonstrates is the breakdown of the techniques and the ability to write for a non technical audience.

## Attack Type Documentation

Five core social engineering types documented, each with red flags, detection method, and MITRE mapping.

The common thread across all five is that they do not attack systems, they attack states of mind. Urgency removes the pause where someone would think. Authority makes questioning feel rude. Fear makes compliance feel like safety.

An analyst who only knows the technical half of the attack surface is protecting half of it.

## Phishing Analysis, Spoofed PayPal

A real world phishing template spoofing PayPal was broken down using the SLAM method: Sender, Links, Attachments, Message.

Seven indicators identified, including the spoofed sender domain, the mismatched Reply-To, and urgency language.

Full five step anatomy mapped from lure to credential harvest.

Three things carry the analysis:

The Reply-To is the most reliable single indicator in the header. The attacker needs the victim to see PayPal and needs the reply to reach them. The From can lie freely. The Reply-To has to be true, so it is the field that gives them up.

The urgency is engineering, not decoration. "24 hours" exists to remove the gap where someone would check. The deadline is not a threat, it is a mechanism.

Missing SPF and DKIM confirms the mail never came from the domain it claims. It is the difference between a suspicious email and a proven forgery.

## Vishing Analysis, Fake IT Support Call

A vishing script impersonating IT support was analysed. Five indicators identified, including the unsolicited call, the password request, and OTP harvesting.

One rule carries this entire section. Nobody legitimate ever needs your OTP. Not IT, not the bank, not the vendor. The code exists specifically to prove the caller is not you, so a request for it is always an account takeover in progress. There is no exception, which makes it the cleanest rule to teach.

Vishing is harder to catch than phishing, and the reason is evidentiary. A phishing email leaves headers, a domain, an IP, a hash. A phone call leaves a memory. There is nothing for the SOC to analyse afterwards and nothing to hunt on, so the defence has to live entirely in the person answering.

Callback verification is the control. Hang up, call the number you already have, not the one you were given. It costs thirty seconds and it defeats the technique completely.

## Awareness Training Guide

A six module training guide was produced for a non technical audience.

Module 1, six golden rules of security.

Module 2, the SLAM method for spotting phishing.

Module 3, phone call verification protocol.

Module 4, four real scenarios with the correct response to each.

Module 5, incident reporting procedure.

Module 6, quick reference card.

Module 4 is the one that works. People do not retain a definition of pretexting. They retain the story about the call that came at 4:55 on a Friday. Scenario based training survives contact with a real attack because it gets recalled as recognition rather than recall.

Module 5 matters more than it looks. Most people who spot a phish do not report it, because reporting is vague and they are not certain enough to feel it is worth the fuss. A clear reporting path removes that hesitation, and hesitation is what gives an attacker the hour they need.

Writing security material for people who do not work in security is its own skill. The failure mode is not being wrong, it is being technically correct and unread.

## MITRE ATT&CK Mapping

| Technique | ID | Attack Type |
| --- | --- | --- |
| Phishing, spearphishing link | T1566.002 | Phishing email |
| Masquerading, match legitimate name | T1036.005 | Spoofed PayPal sender |
| Acquire infrastructure, domains | T1583.001 | Malicious domain |
| Input capture, web portal capture | T1056.003 | Credential harvesting page |
| Phishing for information | T1598 | Vishing and pretexting |
| Replication through removable media | T1091 | USB baiting |

Mapping note: these are the techniques the documented attacks use. This is analysis of attack tradecraft, not observation of an intrusion.

## Analyst Findings

Five social engineering types documented with red flags and detection method for each.

Phishing template confirmed malicious on seven indicators, including spoofed domain and attacker controlled Reply-To.

Vishing script confirmed as an account takeover attempt on the OTP request alone.

Six module awareness guide produced covering all five attack types.

The human layer carries the highest residual risk in the organisation, because it is the only attack surface no technical control fully covers.

## Recommended Response

Enforce SPF, DKIM, and DMARC, which stops the spoofing half of this at delivery rather than relying on the recipient.

Adopt a callback verification policy for all inbound IT support calls. Never verify using a number the caller provided.

Make the reporting path one action, and make sure nobody is ever made to feel stupid for reporting a false alarm. The moment reporting has a social cost, it stops happening.

Run scenario based awareness training rather than annual slide decks.

Feed reported phishing back into gateway rules so the human layer becomes a detection source rather than just a target.

## What This Lab Demonstrates

Documenting attack tradecraft that leaves no technical artefact to hunt.

Applying the SLAM method to a phishing sample and reaching a verdict on header evidence.

Reading a vishing script for the manipulation mechanics, not just the ask.

Knowing why vishing resists detection and where the only viable control sits.

Writing security material a non technical audience will actually read and remember.

Mapping social engineering tradecraft to MITRE ATT&CK.

Recognising the human layer as an attack surface with its own discipline rather than a training checkbox.

## Repository Structure

```
social-engineering-security-awareness-lab/
├── README.md
└── reports/
    ├── attack_types.md
    ├── phishing_analysis.md
    └── security_awareness_training.md
```

---

[![LinkedIn](https://img.shields.io/badge/LinkedIn-WilliamInCyber)](https://linkedin.com/in/WilliamInCyber)
[![X](https://img.shields.io/badge/X-WilliamInCyber-black?style=flat&logo=x)](https://x.com/WilliamInCyber)
