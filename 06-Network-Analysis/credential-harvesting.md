# Credential Harvesting Analysis

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

The objective of this analysis was to determine whether the victim submitted authentication data to the phishing infrastructure and to confirm whether credential harvesting activity occurred.

---

## Evidence Overview

Evidence File:
2024-08-29-phishing-website-traffic.pcap

Total Packets:
895

Filter Applied:

```wireshark
http.request.method == "POST"
```

Purpose:

Identify HTTP POST requests associated with credential submission.

---

## HTTP POST Request Analysis

Observed Packet:

Packet Number:
703

HTTP Request:

```http
POST /management.aspx?good=admin@malware-traffic-analysis.net HTTP/1.1
```

Source IP:

```text
10.8.29.128
```

Destination IP:

```text
172.67.202.104
```

Host:

```http
Host: email.procedure.best
```

Content-Type:

```http
application/x-www-form-urlencoded
```

Origin:

```http
Origin: http://email.procedure.best
```

Referer:

```http
Referer: http://email.procedure.best/management.aspx?good=admin@malware-traffic-analysis.net
```

---

## Follow HTTP Stream Analysis

Analysis Method:

```text
Right Click Packet 703
↓
Follow
↓
HTTP Stream
```

Observation:

The HTTP stream contained encoded form data transmitted from the victim to the phishing infrastructure.

The submitted data was not directly visible in plaintext and appeared to be encoded or obfuscated prior to transmission.

Example Stream Fragment:

```text
JVrYh...
QGQ...
FBQ0X...
```

---

## Credential Submission Assessment

Observation:

The victim successfully submitted authentication data through the phishing form.

The phishing kit appeared to implement client-side encoding or obfuscation before transmitting captured credentials.

Possible Explanations:

- Base64 encoding
- Custom client-side encoding
- JavaScript obfuscation
- Simple data transformation techniques

---

## Analyst Findings

Evidence confirmed that the victim interacted with the phishing page and transmitted authentication data to attacker-controlled infrastructure.

Although the credentials were not directly observable in plaintext, the HTTP POST request and corresponding HTTP stream confirmed successful credential submission.

---

## Correlation with Investigation Findings

### Email Analysis

- Phishing email identified.
- Social engineering indicators observed.

### HTTP GET Analysis

- Victim accessed the phishing login page.
- Fake login page delivery confirmed.

### HTTP POST Analysis

- Authentication data submitted.
- Communication with attacker infrastructure confirmed.

---

## Attack Chain Reconstruction

```text
Phishing Email Delivered
        ↓
Victim Opened Email
        ↓
Victim Clicked Link
        ↓
DNS Resolution
        ↓
TCP Connection Established
        ↓
HTTP GET Request
        ↓
Fake Login Page Displayed
        ↓
Victim Entered Credentials
        ↓
HTTP POST Request Sent
        ↓
Credential Harvesting Confirmed
```

---

## MITRE ATT&CK Correlation

| Technique ID | Technique |
|--------------|------------|
| T1566.002 | Spearphishing Link |
| T1204.001 | User Execution |
| T1071.001 | Application Layer Protocol: Web Protocols |
| T1056 | Input Capture |

---

## Risk Assessment

Risk Level:
Critical

Reason:

The investigation successfully reconstructed the complete phishing workflow and confirmed that authentication data was transmitted to attacker-controlled infrastructure.

This represented a successful credential harvesting event.

---

## Recommended Actions

- Reset potentially compromised credentials.
- Investigate affected accounts.
- Review authentication logs.
- Search proxy logs for similar POST requests.
- Monitor for unauthorized account activity.
- Block identified phishing infrastructure.
- Conduct phishing awareness training.

---

## Lessons Learned

HTTP POST analysis provides critical evidence during phishing investigations.

Credential theft may still be confirmed even when credentials are encoded or obfuscated.

Network traffic reconstruction can validate attack success beyond email analysis alone.

---

## Final Verdict

Victim Credential Submission:
Confirmed

Credential Harvesting:
Confirmed

Credential Visibility:
Encoded / Obfuscated

Attack Success:
Successful

Severity:
Critical

Analysis Status:
Completed

Case Status:
Closed