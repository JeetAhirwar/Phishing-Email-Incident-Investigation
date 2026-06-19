# VirusTotal Domain Analysis

## Case Information

Case ID:
PHISH-2024-001

Case Title:
2024-08-29: Phishing Email and Traffic to Fake Webmail Login Page

Analyst:
Jeet Ahirwar

Investigation Date:
19 June 2026

Evidence Source:
VirusTotal

Domain Investigated:
email.procedure.best

---

## Investigation Objective

The objective of this analysis was to assess the reputation of the phishing domain identified during the investigation and determine whether it had previously been associated with malicious activity.

---

## VirusTotal Lookup Results

Domain:
email.procedure.best

Detection Ratio:
11/91 security vendors flagged this domain as malicious.

Community Score:
11

Registrar:
Sav.com, LLC

Creation Date:
Approximately 1 year prior to the investigation.

Last Analysis Date:
Approximately 2 months prior to the investigation.

Threat Category:
Phishing

---

## Detection Summary

### Malicious Vendors

- ADMINUSLabs
- BitDefender
- CyRadar
- G-Data
- Lionic
- Webroot
- alphaMountain.ai
- CRDF
- Fortinet
- Kaspersky
- Sophos

### Suspicious Vendors

- Forcepoint ThreatSeeker

---

## Observation

Unlike the originating IP address, the phishing domain demonstrated strong consensus among security vendors.

Multiple independent detection engines associated the domain with phishing activity.

This significantly increased confidence that the domain had been used to facilitate credential theft campaigns.

---

## Analyst Assessment

Assessment:
Malicious Domain

Confidence Level:
High

Reason:

The domain was:

- Embedded within the phishing email.
- Accessed by the victim during the investigation.
- Associated with credential harvesting activity.
- Flagged by multiple independent security vendors.

---

## Correlation with Investigation Findings

### Email Analysis

The phishing email redirected the victim to:

email.procedure.best

---

### Network Analysis

DNS requests resolved the phishing domain.

Observed IP addresses:

- 172.67.202.104
- 104.21.37.14

Victim interaction with the phishing infrastructure was confirmed.

HTTP GET requests loaded the fake login page.

HTTP POST requests transmitted authentication data.

---

### Threat Intelligence

VirusTotal identified the domain as malicious.

Multiple vendors specifically categorized the domain as phishing infrastructure.

---

## Risk Assessment

Risk Level:
Critical

Reason:

The investigated domain hosted the credential harvesting page used during the phishing campaign.

Victim interaction with the infrastructure was directly observed through network evidence.

---

## Recommended Actions

- Block access to email.procedure.best.
- Search historical logs for communications involving this domain.
- Review proxy and DNS logs for IOC matches.
- Update email security filters.
- Investigate related domains and infrastructure.
- Reset potentially compromised credentials.

---

## Lessons Learned

Threat intelligence enrichment can rapidly identify known malicious infrastructure.

Domains associated with phishing campaigns often exhibit stronger detection consensus than individual IP addresses.

Reputation findings become significantly more valuable when combined with direct evidence.

---

## Final Verdict

Domain:
email.procedure.best

VirusTotal Classification:
Malicious

Threat Category:
Phishing

Observed During Investigation:
Yes

Associated with Credential Harvesting:
Yes

Confidence:
High

Analysis Status:
Completed

Case Status:
Closed