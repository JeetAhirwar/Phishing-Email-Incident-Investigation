# MITRE ATT&CK Mapping

## Case Information

Case ID:
PHISH-2024-001

Case Title:
2024-08-29: Phishing Email and Traffic to Fake Webmail Login Page

Analyst:
Jeet Ahirwar

Investigation Date:
19 June 2026

Framework:
MITRE ATT&CK Enterprise

Version:
ATT&CK Enterprise (Current Version at Time of Investigation)

---

# Objective

The objective of this section is to map the observed attacker behaviors identified during the investigation to the MITRE ATT&CK framework.

This mapping provides a structured understanding of the adversary's tactics and techniques and enables defenders to improve detection and response capabilities.

---

# ATT&CK Mapping Summary

| Tactic | Technique ID | Technique Name | Evidence | Status |
|----------|--------------|-----------------|-----------|----------|
| Initial Access | T1566.002 | Spearphishing Link | Phishing email contained malicious URL | Observed |
| Execution | T1204.001 | User Execution: Malicious Link | Victim clicked phishing link | Observed |
| Command and Control | T1071.001 | Application Layer Protocol: Web Protocols | HTTP GET and POST traffic observed | Observed |
| Credential Access | T1056 | Input Capture | Fake login page harvested credentials | Observed |
| Resource Development | T1583.001 | Acquire Infrastructure: Domains | Phishing domain used | Observed |
| Resource Development | T1583.006 | Acquire Infrastructure: Web Services | Hosting infrastructure utilized | Observed |

---

# Technique Analysis

## T1566.002 – Spearphishing Link

### Tactic

Initial Access

### Description

Adversaries send phishing emails containing malicious links designed to trick users into visiting attacker-controlled infrastructure.

### Evidence

Subject:

```text
Account Validation!! For admin@malware-traffic-analysis.net Only!!
```

Embedded Infrastructure:

```text
email.procedure.best
```

### Finding

The phishing email delivered a malicious URL intended to redirect the victim to a fake login page.

Status:
Observed

---

## T1204.001 – User Execution: Malicious Link

### Tactic

Execution

### Description

Adversaries rely on users to execute malicious actions, such as clicking phishing links.

### Evidence

Observed HTTP GET Request:

```http
GET /management.aspx?good=admin@malware-traffic-analysis.net HTTP/1.1
```

### Finding

The victim interacted with the phishing email and executed the malicious action by accessing the phishing page.

Status:
Observed

---

## T1071.001 – Application Layer Protocol: Web Protocols

### Tactic

Command and Control

### Description

Adversaries use standard web protocols to communicate with malicious infrastructure.

### Evidence

Observed HTTP GET:

```http
GET /management.aspx?good=admin@malware-traffic-analysis.net HTTP/1.1
```

Observed HTTP POST:

```http
POST /management.aspx?good=admin@malware-traffic-analysis.net HTTP/1.1
```

### Finding

The phishing campaign leveraged HTTP traffic to deliver the fake login page and receive authentication data.

Status:
Observed

---

## T1056 – Input Capture

### Tactic

Credential Access

### Description

Adversaries capture user input to obtain credentials.

### Evidence

Packet Number:

```text
703
```

HTTP Stream Analysis:

```text
Authentication data transmitted through HTTP POST requests.
```

### Finding

The phishing infrastructure collected authentication data submitted by the victim.

Status:
Observed

---

## T1583.001 – Acquire Infrastructure: Domains

### Tactic

Resource Development

### Description

Adversaries acquire domains to support malicious operations.

### Evidence

Domain:

```text
email.procedure.best
```

### Finding

The attacker used a dedicated phishing domain to host the credential harvesting page.

Status:
Observed

---

## T1583.006 – Acquire Infrastructure: Web Services

### Tactic

Resource Development

### Description

Adversaries leverage hosting services and infrastructure to support operations.

### Evidence

Resolved Infrastructure:

```text
172.67.202.104
104.21.37.14
```

Originating Mail Infrastructure:

```text
188.127.247.252
```

### Finding

The phishing campaign utilized web-hosted infrastructure to deliver and support credential harvesting operations.

Status:
Observed

---

# ATT&CK Coverage Summary

## Tactics Observed

- Initial Access
- Execution
- Credential Access
- Command and Control
- Resource Development

---

## Techniques Observed

- T1566.002
- T1204.001
- T1071.001
- T1056
- T1583.001
- T1583.006

---

# Analyst Assessment

The phishing campaign demonstrated a relatively straightforward but effective attack chain.

The attacker leveraged social engineering techniques to obtain initial access, relied on user interaction, used standard web protocols to avoid suspicion, and successfully harvested authentication data through attacker-controlled infrastructure.

Mapping these behaviors to the MITRE ATT&CK framework improved understanding of the adversary's methodology and highlighted opportunities for detection and prevention.

---

# Detection Opportunities

- Email gateway detection for phishing URLs.
- Detection of SPF/DKIM/DMARC failures.
- Monitoring DNS requests to suspicious domains.
- Detection of unusual HTTP POST submissions.
- User awareness and phishing simulations.
- Threat intelligence enrichment of identified IOCs.

---

# Final Verdict

MITRE ATT&CK Mapping:
Completed

ATT&CK Coverage:
6 Techniques Across 5 Tactics

Credential Harvesting:
Confirmed

Campaign Classification:
Phishing Campaign

Case Status:
Closed