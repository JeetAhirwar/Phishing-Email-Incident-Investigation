# Indicator of Compromise (IOC) Analysis

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

# IOC Summary

Indicators of Compromise (IOCs) were extracted from the phishing email headers, phishing infrastructure, and network traffic analysis.

These indicators were enriched using threat intelligence platforms to assess maliciousness and support incident classification.

---

## IOC Inventory

| IOC ID | IOC Type | Value | Source | Severity | Status |
|----------|------------|---------|----------|------------|----------|
| IOC-001 | IP Address | 188.127.247.252 | Email Headers | High | Confirmed |
| IOC-002 | Email Address | khz.port@scp.gov.iq | Email Headers | High | Confirmed |
| IOC-003 | Domain | scp.gov.iq | Email Headers | Medium | Observed |
| IOC-004 | Domain | email.procedure.best | Phishing URL | Critical | Confirmed |
| IOC-005 | IP Address | 172.67.202.104 | DNS Resolution | High | Confirmed |
| IOC-006 | IP Address | 104.21.37.14 | DNS Resolution | High | Confirmed |

---

## IOC-001

IOC Type:
IP Address

Value:
188.127.247.252

Source:
Received Header Analysis

Description:
Originating mail server responsible for delivering the phishing email.

Severity:
High

Recommended Action:
Block and investigate any communication involving this IP address.

---

## IOC-002

IOC Type:
Email Address

Value:
khz.port@scp.gov.iq

Source:
From / Return-Path

Description:
Suspicious sender email address used in the phishing campaign.

Severity:
High

Recommended Action:
Block and investigate similar sender activity.

---

## IOC-003

IOC Type:
Domain

Value:
scp.gov.iq

Source:
Sender Domain

Description:
Claimed sender domain observed in email headers.

Observation:
The domain failed authentication validation checks.

Severity:
Medium

Recommended Action:
Monitor for additional spoofing attempts involving this domain.

---

## IOC-004

IOC Type:
Domain

Value:
email.procedure.best

Source:
Phishing URL

Description:
Domain hosting the fake webmail login page.

Severity:
Critical

Recommended Action:
Block domain access and investigate historical communications.

---

## IOC-005

IOC Type:
IP Address

Value:
172.67.202.104

Source:
DNS Response

Description:
Resolved IP address associated with the phishing domain.

Severity:
High

Recommended Action:
Block and monitor network activity involving this IP.

---

## IOC-006

IOC Type:
IP Address

Value:
104.21.37.14

Source:
DNS Response

Description:
Additional resolved IP address associated with the phishing domain.

Severity:
High

Recommended Action:
Block and monitor network activity involving this IP.

---

## IOC Correlation

The extracted indicators were observed across multiple evidence sources:

### Email Evidence

- Suspicious sender address identified.
- Sender domain observed.
- Originating mail server extracted.

### URL Analysis

- Phishing domain identified.

### Network Evidence

- DNS resolutions captured.
- Victim communication with attacker infrastructure confirmed.

---

## IOC Confidence Assessment

Confidence Level:
High

Reason:

The indicators were extracted directly from evidence and corroborated through multiple stages of the investigation, including header analysis, DNS analysis, and network traffic analysis.

---

## Recommended Defensive Actions

- Block identified malicious domains.
- Block associated IP addresses.
- Search historical logs for IOC matches.
- Monitor for future occurrences.
- Update email filtering rules.
- Conduct phishing awareness training.

---

## Final IOC Assessment

Total IOCs Identified:
6

Critical IOCs:
1

High Severity IOCs:
4

Medium Severity IOCs:
1

IOC Analysis Status:
Completed

Case Status:
Closed