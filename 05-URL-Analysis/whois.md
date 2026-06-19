# WHOIS Analysis

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
WHOIS / DomainTools

Domain Investigated:
email.procedure.best

---

## Investigation Objective

The objective of this analysis was to obtain registration and ownership context related to the phishing domain identified during the investigation.

WHOIS information can help analysts understand domain age, hosting patterns, registrar details, and identify characteristics commonly associated with malicious infrastructure.

---

## WHOIS Investigation Results

Investigated Domain:
procedure.best

WHOIS Status:
WHOIS record not available.

Registration Status:
The domain was not actively registered at the time of analysis.

---

## Historical Infrastructure Findings

IP History:
2 changes across 2 unique IP addresses over approximately 1 year.

Hosting History:
5 changes across 4 unique name servers over approximately 7 years.

---

## Observation

Limited WHOIS information was available for the investigated domain.

Although ownership details could not be retrieved, historical hosting records indicated multiple infrastructure changes over time.

Frequent hosting changes are often observed in malicious campaigns attempting to evade detection.

---

## Analyst Assessment

Assessment:
Suspicious Infrastructure

Confidence Level:
Medium

Reason:

The absence of detailed WHOIS information does not prove malicious intent.

However, combined with the phishing evidence and historical hosting activity, the domain exhibited characteristics commonly associated with attacker-controlled infrastructure.

---

## Correlation with Investigation Findings

### Email Analysis

- The phishing email redirected victims to:
  
  email.procedure.best

---

### Threat Intelligence

- VirusTotal classified the domain as malicious.
- Multiple vendors categorized the domain as phishing infrastructure.

---

### Network Analysis

- DNS lookups resolved the phishing domain.
- Victim interaction with the domain was confirmed.
- Credential harvesting activity was observed.

---

## Risk Assessment

Risk Level:
High

Reason:

The investigated domain was directly involved in a confirmed credential harvesting campaign.

The combination of limited registration transparency and observed malicious activity increased the overall risk assessment.

---

## Recommended Actions

- Block access to the identified domain.
- Monitor DNS logs for future occurrences.
- Search historical logs for related activity.
- Investigate associated infrastructure.
- Update threat intelligence feeds and block lists.

---

## Lessons Learned

WHOIS investigations provide contextual information rather than definitive evidence.

Limited registration details should not be interpreted as proof of malicious activity.

Analysts should combine WHOIS findings with technical evidence and threat intelligence before reaching conclusions.

---

## Final Verdict

Investigated Domain:
procedure.best

WHOIS Transparency:
Limited

Observed During Investigation:
Yes

Associated with Credential Harvesting:
Yes

Infrastructure Assessment:
Suspicious

Analysis Status:
Completed

Case Status:
Closed