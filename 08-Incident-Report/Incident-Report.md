# Incident Report

## Executive Summary

A phishing email investigation was conducted using publicly available evidence obtained from Malware Traffic Analysis.

The investigation involved email header analysis, threat intelligence enrichment, network traffic analysis, and MITRE ATT&CK mapping to determine the nature and impact of the incident.

The phishing campaign redirected the victim to a fake webmail login page designed to harvest authentication credentials.

Network evidence confirmed that the victim accessed the phishing infrastructure and submitted authentication data to attacker-controlled systems.

The incident was classified as a successful credential harvesting attack.

---

# Case Information

Case ID:
PHISH-2024-001

Case Title:
2024-08-29: Phishing Email and Traffic to Fake Webmail Login Page

Analyst:
Jeet Ahirwar

Investigation Date:
19 June 2026

Evidence Source:
Malware Traffic Analysis

Incident Type:
Phishing

Severity:
Critical

Attack Objective:
Credential Harvesting

Case Status:
Closed

---

# Scope of Investigation

The investigation included:

- Email evidence analysis
- Header examination
- SPF validation
- DKIM validation
- DMARC validation
- IOC extraction
- Threat intelligence enrichment
- VirusTotal analysis
- AbuseIPDB analysis
- Cisco Talos analysis
- WHOIS investigation
- DNS analysis
- HTTP GET analysis
- HTTP POST analysis
- HTTP stream reconstruction
- MITRE ATT&CK mapping
- Incident timeline reconstruction

The investigation excluded:

- Endpoint forensics
- Memory analysis
- Malware execution
- Disk forensics
- Host artifact collection

---

# Evidence Reviewed

| Evidence ID | Description |
|-------------|-------------|
| EV-001 | Original phishing email archive (.eml.zip) |
| EV-002 | Extracted phishing email (.eml) |
| EV-003 | Analysis copy of EML |
| EV-004 | Original PCAP archive (.pcap.zip) |
| EV-005 | Extracted PCAP evidence |
| EV-006 | HTTP Stream evidence |

---

# Investigation Methodology

```text
Evidence Collection
        ↓
Email Header Analysis
        ↓
Authentication Validation
        ↓
IOC Extraction
        ↓
Threat Intelligence Enrichment
        ↓
Network Traffic Analysis
        ↓
Victim Activity Reconstruction
        ↓
MITRE ATT&CK Mapping
        ↓
Incident Reporting
```

---

# Key Findings

## Email Findings

- Suspicious sender identified.
- Reply-To behavior appeared abnormal.
- Subject line used urgency and exclusivity techniques.

---

## Authentication Findings

- SPF validation failed.
- DKIM signatures were absent.
- DMARC validation failed.
- DMARC quarantine policy applied.

---

## Threat Intelligence Findings

- VirusTotal identified the phishing domain as malicious.
- The originating IP showed limited vendor detections.
- AbuseIPDB reported no public abuse reports.
- Cisco Talos reported neutral reputation.
- WHOIS information was limited.

---

## Network Findings

- DNS lookups to phishing infrastructure confirmed.
- TCP communication established.
- Victim accessed the phishing page.
- HTTP GET request identified.
- HTTP POST request identified.
- Credential harvesting confirmed.

---

# Indicators of Compromise (IOCs)

| IOC Type | Value |
|-----------|---------|
| Email Address | khz.port@scp.gov.iq |
| Domain | scp.gov.iq |
| Domain | email.procedure.best |
| IP Address | 188.127.247.252 |
| IP Address | 172.67.202.104 |
| IP Address | 104.21.37.14 |

---

# MITRE ATT&CK Summary

| Technique ID | Technique |
|--------------|------------|
| T1566.002 | Spearphishing Link |
| T1204.001 | User Execution |
| T1071.001 | Application Layer Protocol: Web Protocols |
| T1056 | Input Capture |
| T1583.001 | Acquire Infrastructure: Domains |
| T1583.006 | Acquire Infrastructure: Web Services |

---

# Impact Assessment

Potential Impact:

- Credential compromise
- Unauthorized account access
- Lateral movement opportunities
- Data exposure risks
- Business disruption

Observed Impact:

Victim authentication data was transmitted to attacker-controlled infrastructure.

Credential harvesting activity was successfully confirmed.

Impact Severity:
Critical

---

# Recommendations

## Immediate Actions

- Reset potentially compromised credentials.
- Investigate affected accounts.
- Review authentication logs.
- Block identified domains and IP addresses.

---

## Short-Term Improvements

- Update email filtering policies.
- Enhance phishing detection capabilities.
- Monitor DNS and proxy logs.
- Deploy IOC-based detection rules.

---

## Long-Term Improvements

- Implement phishing awareness training.
- Strengthen email authentication controls.
- Conduct regular phishing simulations.
- Establish phishing response playbooks.

---

# Analyst Assessment

The investigation successfully reconstructed the complete attack lifecycle from phishing email delivery to credential submission.

Although reputation platforms produced mixed results, direct evidence collected from email and network artifacts confirmed malicious activity.

The investigation demonstrated the importance of correlating multiple evidence sources rather than relying solely on threat intelligence scores.

Confidence Level:
High

---

# Final Verdict

Incident Classification:
Confirmed Phishing Attack

Attack Objective:
Credential Harvesting

Attack Success:
Successful

Severity:
Critical

Analyst Confidence:
High

Case Status:
Closed

Investigation Outcome:
Credential harvesting activity successfully confirmed through evidence correlation and network reconstruction.