# Threat Intelligence Summary

## Case Information

Case ID:
PHISH-2024-001

Case Title:
2024-08-29: Phishing Email and Traffic to Fake Webmail Login Page

Analyst:
Jeet Ahirwar

Investigation Date:
19 June 2026

---

# Executive Summary

Threat intelligence enrichment was performed on the indicators extracted during the investigation to assess their reputation and identify potential associations with malicious activity.

Multiple intelligence platforms were consulted to provide broader context and improve confidence in the final assessment.

The findings demonstrated that individual intelligence sources produced varying results. Therefore, evidence correlation was used to determine the final threat classification.

---

# Investigated Indicators

| IOC Type | Value |
|-----------|---------|
| IP Address | 188.127.247.252 |
| Email Address | khz.port@scp.gov.iq |
| Domain | scp.gov.iq |
| Domain | email.procedure.best |
| IP Address | 172.67.202.104 |
| IP Address | 104.21.37.14 |

---

# Intelligence Sources Used

## VirusTotal

Purpose:

Assess reputation using multiple security vendors.

Findings:

- The phishing domain was flagged by 11 out of 91 vendors.
- The originating IP address was flagged by 2 out of 91 vendors.
- Multiple vendors associated the infrastructure with phishing activity.

Assessment:

Malicious activity observed.

---

## AbuseIPDB

Purpose:

Identify community-reported abuse incidents.

Findings:

- Abuse Confidence Score: 0%
- Total Reports: 0
- No public abuse reports identified.

Assessment:

Neutral reputation.

---

## Cisco Talos Intelligence

Purpose:

Assess sender reputation and block list presence.

Findings:

- Sender Reputation: Neutral
- Web Reputation: Neutral
- Not listed on major Talos block lists.

Assessment:

Neutral reputation.

---

## WHOIS Investigation

Purpose:

Gather domain registration context.

Findings:

- WHOIS information was limited.
- Historical hosting activity was observed.
- The phishing infrastructure demonstrated characteristics commonly associated with transient attacker infrastructure.

Assessment:

Suspicious infrastructure.

---

# Cross-Source Correlation

| Source | Result |
|----------|----------|
| VirusTotal (IP) | Malicious Indicators Present |
| VirusTotal (Domain) | Malicious |
| AbuseIPDB | Neutral |
| Cisco Talos | Neutral |
| WHOIS | Suspicious |
| Email Authentication | Failed |
| Network Evidence | Confirmed |

---

# Analyst Assessment

Threat intelligence platforms provided inconsistent reputational results.

This variation highlights an important principle of incident response:

> No single threat intelligence platform should be treated as an absolute source of truth.

Final assessments must be supported by direct evidence and contextual analysis.

---

# Correlation with Investigation Evidence

The threat intelligence findings aligned with evidence collected throughout the investigation.

### Email Analysis

- SPF validation failed.
- DKIM signatures were absent.
- DMARC validation failed.
- Sender behavior appeared suspicious.

### URL Analysis

- The phishing domain was identified and investigated.
- Multiple vendors associated the domain with phishing activity.

### Network Analysis

- Victim interaction with the phishing infrastructure was confirmed.
- Credential harvesting activity was observed.
- HTTP POST requests transmitted authentication data to attacker-controlled infrastructure.

---

# Overall Threat Assessment

Threat Level:
Critical

Confidence Level:
High

Reason:

Although intelligence platforms reported varying reputational outcomes, the direct evidence collected during the investigation confirmed malicious activity.

Credential harvesting behavior was successfully reconstructed through network analysis.

The threat intelligence findings strengthened the confidence of the final classification.

---

# Recommended Actions

- Block identified malicious domains.
- Block associated IP addresses.
- Reset potentially compromised credentials.
- Search historical logs for IOC matches.
- Review email authentication policies.
- Update detection signatures and filtering rules.
- Monitor for recurrence of identified indicators.
- Conduct phishing awareness training.

---

# Lessons Learned

This investigation demonstrated that:

- Reputation scores alone are insufficient for incident classification.
- Threat intelligence must be correlated with evidence.
- Multiple intelligence sources improve confidence.
- Network evidence provides strong validation of malicious activity.
- Context-driven analysis is essential during phishing investigations.

---

# Final Verdict

Threat Intelligence Status:
Completed

Final Threat Classification:
Confirmed Phishing Campaign

Campaign Objective:
Credential Harvesting

Confidence:
High

Case Status:
Closed