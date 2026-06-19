# Network Analysis Summary

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
2024-08-29-phishing-website-traffic.pcap

Analysis Tool:
Wireshark (Kali Linux)

---

## Investigation Objective

The objective of the network analysis was to reconstruct the victim's interaction with the phishing infrastructure and determine whether credential harvesting activity occurred.

---

## Evidence Overview

Evidence File:
2024-08-29-phishing-website-traffic.pcap

Total Packets:
895

Analysis Environment:
Kali Linux

Tool Used:
Wireshark

---

# Network Investigation Findings

## DNS Resolution

Observed Activity:

The victim system initiated DNS queries to resolve the phishing domain.

Queried Domain:

```text
email.procedure.best
```

Resolved Infrastructure:

```text
172.67.202.104
104.21.37.14
```

Finding:

Victim infrastructure successfully resolved the phishing domain.

Status:
Confirmed

---

## TCP Session Analysis

Observed Activity:

A TCP three-way handshake was established prior to HTTP communication.

Observed Sequence:

```text
SYN
↓
SYN, ACK
↓
ACK
```

Finding:

Communication between the victim and phishing server was successfully established.

Status:
Confirmed

---

## HTTP GET Analysis

Observed Request:

```http
GET /management.aspx?good=admin@malware-traffic-analysis.net HTTP/1.1
```

Host:

```http
email.procedure.best
```

Finding:

The victim accessed the phishing webpage distributed through the phishing email.

Status:
Confirmed

---

## HTTP POST Analysis

Observed Request:

```http
POST /management.aspx?good=admin@malware-traffic-analysis.net HTTP/1.1
```

Packet Number:

```text
703
```

Finding:

Authentication data was submitted to attacker-controlled infrastructure.

Status:
Confirmed

---

## HTTP Stream Analysis

Analysis Method:

```text
Follow HTTP Stream
```

Observation:

The transmitted authentication data appeared encoded or obfuscated before submission.

Finding:

Credential harvesting activity was successfully reconstructed.

Status:
Confirmed

---

# Victim Activity Reconstruction

```text
Phishing Email Delivered
        ↓
Victim Opened Email
        ↓
Victim Clicked Embedded Link
        ↓
DNS Lookup Performed
        ↓
TCP Connection Established
        ↓
Fake Login Page Loaded
        ↓
Victim Entered Credentials
        ↓
HTTP POST Request Sent
        ↓
Credential Harvesting Confirmed
```

---

# Indicators Observed During Network Analysis

| Type | Value |
|--------|---------|
| Domain | email.procedure.best |
| IP Address | 172.67.202.104 |
| IP Address | 104.21.37.14 |
| Victim IP | 10.8.29.128 |
| DNS Server | 10.8.29.2 |

---

# MITRE ATT&CK Correlation

| Technique ID | Technique |
|--------------|------------|
| T1566.002 | Spearphishing Link |
| T1204.001 | User Execution |
| T1071.001 | Application Layer Protocol: Web Protocols |
| T1056 | Input Capture |

---

# Analyst Assessment

The network evidence provided direct visibility into the victim's actions following receipt of the phishing email.

Unlike investigations limited to email analysis alone, the PCAP evidence enabled full reconstruction of the attack sequence and confirmed successful credential harvesting.

Confidence Level:
High

---

# Risk Assessment

Risk Level:
Critical

Reason:

The investigation confirmed that the victim interacted with the phishing infrastructure and transmitted authentication data to attacker-controlled systems.

This represented a successful phishing incident resulting in credential compromise.

---

# Recommended Actions

- Reset potentially compromised credentials.
- Investigate affected user accounts.
- Review authentication logs.
- Search proxy and DNS logs for IOC matches.
- Block identified domains and IP addresses.
- Monitor for unauthorized access attempts.
- Conduct phishing awareness training.
- Enhance email authentication and filtering controls.

---

# Network Analysis Outcome

DNS Resolution:
Confirmed

TCP Connectivity:
Confirmed

Victim Link Click:
Confirmed

Phishing Page Access:
Confirmed

Credential Submission:
Confirmed

Credential Harvesting:
Confirmed

Analysis Status:
Completed

Case Status:
Closed