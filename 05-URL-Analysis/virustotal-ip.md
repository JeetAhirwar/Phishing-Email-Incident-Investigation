# VirusTotal IP Analysis

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
VirusTotal

IOC Investigated:
188.127.247.252

---

## Investigation Objective

The objective of this analysis was to assess the reputation of the originating IP address identified during email header analysis and determine whether it had previously been associated with malicious activity.

---

## VirusTotal Lookup Results

IP Address:
188.127.247.252

Detection Ratio:
2/91 security vendors flagged this IP address as malicious.

Malicious Vendors:

- ADMINUSLabs → Malicious
- Fortinet → Phishing

Community Score:
2

Country:
Czech Republic

ASN:
AS6212

AS Owner:
SmartApe OU

Last Analysis Date:
Approximately one month prior to the investigation.

---

## Detection Summary

### Malicious Classifications

- ADMINUSLabs
- Fortinet

### Clean / Unrated Classifications

The majority of vendors classified the IP address as clean or unrated.

VirusTotal did not explicitly provide an exact harmless vote count.

---

## Observation

Although only a small number of vendors flagged the IP address as malicious, the classifications specifically referenced phishing activity.

The IP address was also directly observed within the email headers during the investigation.

This increased confidence that the infrastructure had been used in malicious activity.

---

## Analyst Assessment

Assessment:
Suspicious Infrastructure

Confidence Level:
High

Reason:

Threat intelligence should not rely solely on detection counts.

The investigated IP address was extracted from phishing evidence and independently identified by multiple vendors as malicious.

---

## Correlation with Investigation Findings

### Email Analysis

- Originating IP extracted from Received headers.
- SPF validation failed.
- DMARC validation failed.

### Network Analysis

- Victim communication with phishing infrastructure confirmed.

### Threat Intelligence

- VirusTotal flagged the IP as malicious/phishing.
- AbuseIPDB reported no abuse incidents.
- Cisco Talos classified the IP as neutral.

---

## Risk Assessment

Risk Level:
High

Reason:

The IP address was directly involved in the delivery of the phishing email and was additionally associated with phishing activity by multiple security vendors.

---

## Recommended Actions

- Block communications involving 188.127.247.252.
- Search historical logs for IOC matches.
- Monitor for future activity involving this infrastructure.
- Correlate with additional intelligence sources.
- Investigate related campaigns using the same infrastructure.

---

## Lessons Learned

Low detection counts do not necessarily indicate benign activity.

Threat intelligence must always be interpreted within the context of the investigation.

Direct evidence often provides stronger confidence than reputation scores alone.

---

## Final Verdict

IP Address:
188.127.247.252

VirusTotal Classification:
Malicious Indicators Present

Observed During Investigation:
Yes

Associated with Phishing Activity:
Yes

Analysis Status:
Completed

Case Status:
Closed