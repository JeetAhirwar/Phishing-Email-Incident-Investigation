# Phishing Email Analysis & Incident Investigation

## Overview

This project presents an end-to-end investigation of a real-world phishing campaign using publicly available evidence from Malware Traffic Analysis. The investigation follows the workflow of a SOC Analyst and Digital Forensics & Incident Response (DFIR) practitioner by analyzing phishing emails, validating email authentication mechanisms, extracting Indicators of Compromise (IOCs), performing threat intelligence enrichment, reconstructing victim activity through network traffic analysis, and confirming credential harvesting.

The objective of this project was to simulate a real phishing investigation and document findings using industry-standard methodologies and tools.

---

## Case Information

| Attribute | Details |
|------------|-----------|
| Case ID | PHISH-2024-001 |
| Analyst | Jeet Ahirwar |
| Investigation Date | June 2026 |
| Evidence Source | Malware Traffic Analysis |
| Case Title | 2024-08-29: Phishing Email and Traffic to Fake Webmail Login Page |
| Severity | Critical |
| Attack Objective | Credential Harvesting |
| Investigation Type | Email Security Investigation & Network Forensics |

---

## Investigation Objectives

- Analyze a real phishing email sample.
- Perform email header analysis.
- Validate SPF, DKIM, and DMARC authentication mechanisms.
- Extract and document Indicators of Compromise (IOCs).
- Investigate phishing domains and attacker infrastructure.
- Enrich IOCs using threat intelligence platforms.
- Analyze network traffic using Wireshark.
- Reconstruct victim activity from PCAP evidence.
- Confirm credential harvesting attempts.
- Map attacker behavior to the MITRE ATT&CK Framework.
- Develop an executive incident report with recommendations.

---

## Investigation Methodology

```text
Evidence Collection
        ↓
Email Header Analysis
        ↓
SPF / DKIM / DMARC Validation
        ↓
IOC Extraction
        ↓
Threat Intelligence Enrichment
        ↓
Network Traffic Analysis
        ↓
Victim Activity Reconstruction
        ↓
Credential Harvesting Confirmation
        ↓
MITRE ATT&CK Mapping
        ↓
Incident Reporting
```

---

## Tools & Technologies Used

### Email Analysis

- Raw EML Analysis
- Email Header Examination
- SPF Validation
- DKIM Validation
- DMARC Validation

### Threat Intelligence

- VirusTotal
- AbuseIPDB
- Cisco Talos Intelligence
- WHOIS Lookup

### Network Forensics

- Wireshark
- HTTP Stream Analysis
- DNS Analysis
- TCP Session Analysis
- HTTP GET/POST Investigation

### Frameworks & Methodologies

- MITRE ATT&CK Framework
- Incident Response Lifecycle
- Evidence Preservation Principles

### Operating Systems

- Kali Linux
- Windows

---

## Key Findings

### Email Authentication Failures

- SPF validation failed.
- DKIM signatures were absent.
- DMARC validation failed.
- DMARC quarantine policy was triggered.

### Social Engineering Indicators

- Urgent account validation theme.
- Victim email embedded in subject line.
- Suspicious Reply-To behavior.

### Threat Intelligence Findings

- Phishing domain flagged by multiple security vendors.
- Originating infrastructure linked to phishing activity.
- Multiple intelligence platforms were correlated to improve confidence.

### Network Findings

- DNS lookup for phishing domain observed.
- TCP three-way handshake established.
- HTTP GET request loaded the fake login page.
- HTTP POST request submitted victim authentication data.
- Credential harvesting activity confirmed.

---

## Indicators of Compromise (IOCs)

| Type | Value |
|--------|---------|
| Email Address | khz.port@scp.gov.iq |
| Sender Domain | scp.gov.iq |
| Phishing Domain | email.procedure.best |
| Originating IP | 188.127.247.252 |
| Infrastructure IP | 172.67.202.104 |
| Infrastructure IP | 104.21.37.14 |

---

## MITRE ATT&CK Mapping

| Technique ID | Technique |
|--------------|------------|
| T1566.002 | Spearphishing Link |
| T1204.001 | User Execution: Malicious Link |
| T1071.001 | Application Layer Protocol: Web Protocols |
| T1056 | Input Capture |
| T1583.001 | Acquire Infrastructure: Domains |
| T1583.006 | Acquire Infrastructure: Web Services |

---

## Incident Timeline

```text
Phishing Email Delivered
        ↓
Victim Opened Email
        ↓
Victim Clicked Phishing Link
        ↓
DNS Lookup Performed
        ↓
TCP Connection Established
        ↓
HTTP GET Request Sent
        ↓
Fake Login Page Loaded
        ↓
Victim Submitted Credentials
        ↓
HTTP POST Request Sent
        ↓
Credential Harvesting Confirmed
```

---

## Project Structure

```text
Phishing-Email-Incident-Investigation/
│
├── README.md
├── 01-Case-Overview/
├── 02-Evidence/
├── 03-Email-Headers/
├── 04-IOCs/
├── 05-URL-Analysis/
├── 06-Network-Analysis/
├── 07-MITRE-Mapping/
├── 08-Incident-Report/
├── 09-Incident-Timeline/
├── Screenshots/
└── Samples/
```

---

## Skills Demonstrated

- Email Security Investigation
- Phishing Analysis
- Threat Intelligence Analysis
- IOC Extraction & Enrichment
- Network Traffic Analysis
- Wireshark Packet Analysis
- HTTP Stream Investigation
- Incident Response Documentation
- MITRE ATT&CK Mapping
- Analytical Thinking
- Technical Reporting

---

## Final Verdict

The investigated phishing campaign successfully leveraged social engineering techniques to direct the victim to a fake webmail login page. Through email analysis, threat intelligence correlation, and network forensic investigation, the campaign was confirmed to be a credential harvesting attack.

The investigation validated malicious activity through multiple independent evidence sources and reconstructed the victim's actions from email delivery to credential submission.

**Incident Classification:** Confirmed Phishing Attack

**Severity:** Critical

**Attack Objective:** Credential Harvesting

---

## Disclaimer

This project was conducted solely for educational, research, and defensive cybersecurity purposes.

No malware was executed during this investigation. All evidence used in this project was obtained from publicly available security research sources and analyzed in an isolated environment.

---

## Author

**Jeet Ahirwar**

Aspiring SOC Analyst | Incident Response Enthusiast | Cybersecurity Learner

- LinkedIn: https://www.linkedin.com/in/jeetahirwar/
- GitHub: https://github.com/JeetAhirwar