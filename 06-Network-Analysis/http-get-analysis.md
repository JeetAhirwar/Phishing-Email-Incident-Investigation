# HTTP GET Analysis

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

The objective of this analysis was to determine whether the victim accessed the phishing website embedded within the email and to reconstruct the initial stages of the attack using network evidence.

---

## Evidence Overview

Evidence File:
2024-08-29-phishing-website-traffic.pcap

Total Packets:
895

Filter Applied:

```wireshark
http
```

Purpose:

Identify HTTP communications associated with the phishing activity.

---

## DNS Analysis

### DNS Query

Source IP:
10.8.29.128

Destination DNS Server:
10.8.29.2

Query:

```dns
A email.procedure.best
```

### Observation

The victim system attempted to resolve the phishing domain embedded within the email.

---

### DNS Response

Resolved Domain:

```text
email.procedure.best
```

Resolved IP Addresses:

```text
172.67.202.104
104.21.37.14
```

### Finding

The phishing domain successfully resolved to attacker-controlled infrastructure.

---

## TCP Session Establishment

The following packets were observed before the HTTP communication:

```text
SYN
SYN, ACK
ACK
```

### Observation

A TCP three-way handshake was successfully completed between the victim and the phishing infrastructure.

### Finding

The successful handshake confirmed that communication with the phishing server was established.

---

## HTTP GET Request Analysis

Observed Packet:

Packet Number:
6

HTTP Request:

```http
GET /management.aspx?good=admin@malware-traffic-analysis.net HTTP/1.1
```

Host:

```http
Host: email.procedure.best
```

Destination IP:

```text
172.67.202.104
```

---

## Observation

The victim system requested the phishing webpage hosted at:

```text
email.procedure.best
```

The URL contained the victim email address as a parameter:

```text
admin@malware-traffic-analysis.net
```

This behavior is commonly observed in phishing kits designed to personalize login pages and increase legitimacy.

---

## Social Engineering Assessment

The phishing page attempted to appear relevant to the intended victim by embedding the recipient's email address within the request.

This technique can increase user trust and improve the likelihood of credential submission.

---

## Analyst Findings

Evidence confirmed that the victim interacted with the phishing link distributed through the email.

The HTTP GET request represented the stage at which the fake login page was delivered to the victim.

---

## Correlation with Investigation Findings

### Email Analysis

- Phishing email identified.
- Suspicious account validation theme observed.

### DNS Analysis

- Victim resolved the phishing domain.

### Network Analysis

- TCP session established.
- HTTP GET request retrieved the fake login page.

---

## Risk Assessment

Risk Level:
Critical

Reason:

Victim interaction with attacker infrastructure was successfully confirmed through network evidence.

---

## Recommended Actions

- Block access to email.procedure.best.
- Search proxy logs for similar requests.
- Investigate other users who may have accessed the same URL.
- Review email gateway logs for related campaigns.

---

## Lessons Learned

HTTP GET requests often represent the initial point of victim interaction during phishing campaigns.

Reconstructing these requests enables analysts to validate whether phishing attempts progressed beyond email delivery.

---

## Final Verdict

Victim Link Click:
Confirmed

Phishing Page Access:
Confirmed

Infrastructure Contact:
Confirmed

Credential Harvesting Stage:
Pre-Submission

Analysis Status:
Completed

Case Status:
Closed