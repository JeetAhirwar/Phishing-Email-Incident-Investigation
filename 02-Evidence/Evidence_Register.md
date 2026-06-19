# Evidence Register

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

## Evidence Inventory

| Evidence ID | File Name | Description | Status |
|------------|------------|-------------|----------|
| EV-001 | 2024-08-29-phishing-email-0415-UTC.eml.zip | Original phishing email archive | Downloaded |
| EV-002 | 2024-08-29-phishing-email-0415-UTC.eml | Extracted phishing email evidence | Preserved |
| EV-003 | analysis-copy.eml | Working copy created for analysis | Analyzed |
| EV-004 | 2024-08-29-phishing-website-traffic.pcap.zip | Original network traffic archive | Downloaded |
| EV-005 | 2024-08-29-phishing-website-traffic.pcap | Extracted PCAP evidence | Preserved |
| EV-006 | Wireshark HTTP Stream | Credential harvesting evidence extracted from PCAP | Analyzed |

---

## Evidence Metadata

### EV-001

File Name:
2024-08-29-phishing-email-0415-UTC.eml.zip

Description:
Original phishing email archive obtained from Malware Traffic Analysis.

File Size:
1.64 KB (1,686 bytes)

Date Downloaded:
Friday, 19 June 2026, 06:05:43 PM

Status:
Preserved

---

### EV-002

File Name:
2024-08-29-phishing-email-0415-UTC.eml

Description:
Extracted email evidence used to identify sender information and authentication failures.

Source:
EV-001

Status:
Preserved

---

### EV-003

File Name:
analysis-copy.eml

Description:
Analysis copy created to preserve original evidence integrity.

Purpose:
Header analysis and email investigation.

Source:
EV-002

Status:
Analyzed

---

### EV-004

File Name:
2024-08-29-phishing-website-traffic.pcap.zip

Description:
Original network traffic archive obtained from Malware Traffic Analysis.

Source:
Malware Traffic Analysis

Status:
Preserved

---

### EV-005

File Name:
2024-08-29-phishing-website-traffic.pcap

Description:
Extracted network capture used for forensic analysis.

Analysis Tool:
Wireshark (Kali Linux)

Total Packets:
895

Source:
EV-004

Status:
Analyzed

---

### EV-006

Evidence Name:
Wireshark HTTP Stream

Description:
HTTP POST stream confirming credential harvesting activity.

Packet Number:
703

Analysis Method:
Follow HTTP Stream

Source:
EV-005

Status:
Analyzed

---

## Chain of Custody Notes

- Original evidence files were preserved and not modified during the investigation.
- Separate working copies were created for analysis purposes.
- Network evidence was analyzed using Wireshark in an isolated environment.
- All findings were documented throughout the investigation process.
- Evidence integrity was maintained from acquisition through reporting.

---

## Final Evidence Status

Evidence Collection:
Completed

Evidence Preservation:
Maintained

Evidence Analysis:
Completed

Case Status:
Closed