# Incident Timeline

## Case Information

Case ID:
PHISH-2024-001

Case Title:
2024-08-29: Phishing Email and Traffic to Fake Webmail Login Page

Analyst:
Jeet Ahirwar

Investigation Date:
19 June 2026

Incident Type:
Phishing

Severity:
Critical

Attack Objective:
Credential Harvesting

Case Status:
Closed

---

# Timeline Objective

The objective of this timeline is to reconstruct the sequence of events that occurred during the phishing campaign based on evidence collected throughout the investigation.

The timeline was developed using email artifacts, threat intelligence findings, and network traffic evidence.

---

# Incident Timeline

## Stage 1 – Phishing Email Delivery

### Event

The phishing email was successfully delivered to the victim.

### Evidence

Email Subject:

```text
Account Validation!! For admin@malware-traffic-analysis.net Only!!
```

Sender:

```text
SupportDesk <khz.port@scp.gov.iq>
```

### Status

Observed

---

## Stage 2 – Initial Email Review

### Event

Initial analysis identified suspicious characteristics.

### Evidence

- Suspicious sender domain
- Suspicious Reply-To behavior
- Urgent subject line
- Authentication failures

### Status

Observed

---

## Stage 3 – Authentication Validation

### Event

Email authentication mechanisms were evaluated.

### Evidence

SPF:

```text
Fail
```

DKIM:

```text
None
```

DMARC:

```text
Fail (Policy: Quarantine)
```

### Status

Observed

---

## Stage 4 – IOC Extraction

### Event

Indicators of Compromise were extracted from email evidence.

### Extracted Indicators

```text
188.127.247.252
khz.port@scp.gov.iq
scp.gov.iq
email.procedure.best
```

### Status

Observed

---

## Stage 5 – Threat Intelligence Enrichment

### Event

Threat intelligence platforms were used to enrich extracted indicators.

### Findings

- VirusTotal identified malicious indicators.
- AbuseIPDB reported no public abuse records.
- Cisco Talos reported neutral reputation.
- WHOIS information was limited.

### Status

Observed

---

## Stage 6 – DNS Resolution

### Event

The victim system attempted to resolve the phishing domain.

### Evidence

DNS Query:

```dns
A email.procedure.best
```

Resolved IP Addresses:

```text
172.67.202.104
104.21.37.14
```

### Status

Confirmed

---

## Stage 7 – TCP Connection Establishment

### Event

The victim system established communication with phishing infrastructure.

### Evidence

Observed Sequence:

```text
SYN
↓
SYN, ACK
↓
ACK
```

### Status

Confirmed

---

## Stage 8 – Fake Login Page Access

### Event

The victim accessed the phishing webpage.

### Evidence

HTTP GET Request:

```http
GET /management.aspx?good=admin@malware-traffic-analysis.net HTTP/1.1
```

Host:

```http
email.procedure.best
```

### Status

Confirmed

---

## Stage 9 – Credential Submission

### Event

The victim submitted authentication data.

### Evidence

HTTP POST Request:

```http
POST /management.aspx?good=admin@malware-traffic-analysis.net HTTP/1.1
```

Packet Number:

```text
703
```

### Status

Confirmed

---

## Stage 10 – Credential Harvesting

### Event

Authentication data was transmitted to attacker-controlled infrastructure.

### Evidence

Follow HTTP Stream analysis identified encoded or obfuscated form data associated with the submitted credentials.

### Status

Confirmed

---

# Attack Flow Visualization

```text
Phishing Email Delivered
        ↓
Initial Triage Performed
        ↓
Authentication Failures Identified
        ↓
IOCs Extracted
        ↓
Threat Intelligence Enrichment
        ↓
DNS Resolution
        ↓
TCP Session Established
        ↓
HTTP GET Request
        ↓
Fake Login Page Loaded
        ↓
Victim Submitted Credentials
        ↓
HTTP POST Request
        ↓
Credential Harvesting Confirmed
```

---

# Timeline Summary

| Stage | Activity | Status |
|---------|-----------|----------|
| 1 | Email Delivery | Observed |
| 2 | Initial Triage | Observed |
| 3 | Authentication Validation | Observed |
| 4 | IOC Extraction | Observed |
| 5 | Threat Intelligence | Observed |
| 6 | DNS Resolution | Confirmed |
| 7 | TCP Handshake | Confirmed |
| 8 | HTTP GET | Confirmed |
| 9 | HTTP POST | Confirmed |
| 10 | Credential Harvesting | Confirmed |

---

# Analyst Assessment

The timeline reconstruction demonstrated the complete lifecycle of the phishing campaign.

The investigation successfully correlated email evidence, threat intelligence findings, and network artifacts to reconstruct the victim's actions.

Unlike investigations limited to email analysis alone, this investigation confirmed that the phishing campaign progressed beyond delivery and resulted in successful credential harvesting.

Confidence Level:
High

---

# Final Verdict

Timeline Reconstruction:
Completed

Victim Interaction:
Confirmed

Credential Submission:
Confirmed

Credential Harvesting:
Confirmed

Incident Classification:
Confirmed Phishing Attack

Severity:
Critical

Attack Objective:
Credential Harvesting

Case Status:
Closed