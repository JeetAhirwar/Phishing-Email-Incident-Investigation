# Investigation Notes

## Case Information

Case ID:
PHISH-2024-001

Case Title:
2024-08-29: Phishing Email and Traffic to Fake Webmail Login Page

Analyst:
Jeet Ahirwar

Investigation Date:
19 June 2026

Source:
Malware Traffic Analysis

---

# Evidence Source Notes

All evidence used during this investigation was obtained from publicly available security research resources provided by Malware Traffic Analysis.

Source Website:
https://www.malware-traffic-analysis.net/

Evidence Collected:

- Phishing email archive (.eml.zip)
- Network traffic archive (.pcap.zip)

Purpose:

The evidence was used exclusively for educational and defensive cybersecurity analysis.

---

# ZIP Archive Notes

The downloaded evidence archives were password protected.

Reason:

Password protection prevents accidental execution of malicious content and encourages controlled analysis.

Status:

ZIP archives extracted successfully.

---

# Evidence Handling Notes

- Original evidence files were preserved.
- Working copies were created for analysis activities.
- Original evidence remained unmodified.
- Evidence integrity was maintained throughout the investigation.
- Analysis activities were documented continuously.

---

# Analysis Environment

Operating Systems:

- Windows
- Kali Linux

Primary Analysis Tools:

- Wireshark
- VirusTotal
- AbuseIPDB
- Cisco Talos Intelligence
- WHOIS Lookup
- Text Editor (EML Header Review)

---

# Investigation Observations

## Email Analysis

Initial review identified several suspicious indicators:

- Urgent account validation theme.
- Government-related sender domain.
- Suspicious Reply-To behavior.
- Authentication failures.

---

## Threat Intelligence

Threat intelligence sources provided varying levels of confidence.

Observation:

No single intelligence source should be treated as absolute truth.

Analyst decisions should be based on evidence correlation and investigation context.

---

## Network Analysis

The victim activity was successfully reconstructed.

Observed sequence:

Email Delivery
↓
Phishing Link Access
↓
DNS Resolution
↓
TCP Session Establishment
↓
HTTP GET Request
↓
Fake Login Page Display
↓
HTTP POST Submission
↓
Credential Harvesting Confirmation

---

# Lessons Learned

This investigation demonstrated that:

- Email authentication failures are strong indicators of phishing activity.
- Context-driven analysis is more effective than relying solely on reputation scores.
- Network traffic analysis can validate phishing success.
- Threat intelligence enrichment improves confidence in findings.
- Evidence preservation is essential during investigations.

---

# Analyst Reflections

This project provided practical experience in:

- Email security investigations
- Threat intelligence analysis
- IOC enrichment
- Network forensics
- Wireshark investigations
- MITRE ATT&CK mapping
- Incident documentation

The investigation successfully reconstructed a real-world phishing campaign from initial delivery through credential harvesting.

---

# Final Notes

Case Status:
Closed

Investigation Status:
Completed

Severity:
Critical

Attack Objective:
Credential Harvesting

Project Type:
Educational Defensive Investigation