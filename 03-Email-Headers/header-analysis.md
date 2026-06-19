# Email Header Analysis

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
Malware Traffic Analysis

---

## Evidence Source

File Name:
2024-08-29-phishing-email-0415-UTC.eml

Analysis Copy:
03-Email-Headers/analysis-copy.eml

Status:
Analyzed

---

## Email Subject Analysis

Subject:
Account Validation!! For admin@malware-traffic-analysis.net Only!!

### Observation

The subject line attempts to create urgency and exclusivity by implying that immediate action is required specifically for the intended recipient.

### Social Engineering Indicators

- Use of urgency ("Account Validation!!")
- Exclusivity ("Only!!")
- Victim email address embedded in subject
- Encourages immediate action

### Finding

The subject line employs urgency and exclusivity techniques commonly associated with phishing campaigns.

---

## Sender Analysis

Return-Path:
khz.port@scp.gov.iq

From:
SupportDesk <khz.port@scp.gov.iq>

### Observation

The sender claims to represent a support desk using the domain:

scp.gov.iq

The email content relates to account validation for an unrelated recipient domain.

There is no apparent business relationship between the sender domain and the intended recipient.

### Finding

The sender domain does not align with the email content and appears suspicious.

---

## Reply-To Analysis

Reply-To:
admin@malware-traffic-analysis.net

### Observation

The Reply-To field references the victim's own email address.

Typically, the Reply-To address points to the sender or support mailbox.

Using the recipient address as Reply-To is unusual and may indicate automated phishing template generation.

### Finding

The Reply-To field references the victim email address, which is abnormal and may indicate automated phishing template generation.

---

## Authentication Header Evidence

Authentication-Results:

dkim=none

dmarc=fail reason="No valid SPF, No valid DKIM"

spf=fail (domain of khz.port@scp.gov.iq does not designate 188.127.247.252 as permitted sender)

### Observation

The Authentication-Results header provided direct evidence that the message failed multiple authentication checks.

### Finding

The combined authentication failures significantly increased confidence that the email was fraudulent.

---

## Authentication Analysis

### DKIM Analysis

DKIM Result:

dkim=none

#### What is DKIM?

DomainKeys Identified Mail (DKIM) is an email authentication mechanism that uses digital signatures to verify that the email originated from an authorized sender and was not modified during transit.

#### Observation

No DKIM signature was present within the email headers.

Government-related domains commonly implement DKIM to enhance trust and authenticity.

#### Finding

No DKIM signature was present, reducing trust in sender authenticity.

---

### SPF Analysis

SPF Result:

spf=fail

Domain:
scp.gov.iq

Originating IP:
188.127.247.252

Authentication Details:

The domain scp.gov.iq does not designate 188.127.247.252 as a permitted sender.

#### What is SPF?

Sender Policy Framework (SPF) specifies which mail servers are authorized to send email on behalf of a domain.

#### Observation

The email originated from an IP address that was not included in the sender domain's SPF records.

#### Meaning

The email was sent from an unauthorized server.

#### Finding

SPF validation failed because the originating IP was not authorized to send mail on behalf of scp.gov.iq.

---

### DMARC Analysis

DMARC Result:

dmarc=fail

Policy:
quarantine

Reason:
No valid SPF and no valid DKIM.

#### What is DMARC?

Domain-based Message Authentication, Reporting, and Conformance (DMARC) defines how receiving mail servers should handle emails that fail SPF and DKIM validation.

#### Observation

The domain owner configured a quarantine policy for authentication failures.

The investigated email failed DMARC validation.

#### Meaning

The email should have been quarantined according to the sender domain's policy.

#### Finding

The email failed DMARC validation and should have been quarantined according to domain policy.

---

## Received Header Analysis

Received:

from s940027.srvape.com (188.127.247.252)

for admin@malware-traffic-analysis.net

Timestamp:
Thu, 29 Aug 2024 04:15:53 UTC

### Observation

The server responsible for transmitting the email was identified as:

s940027.srvape.com

IP Address:

188.127.247.252

### Finding

The originating mail server was not authorized to send email on behalf of the claimed domain.

---

## Sender Reputation Assessment

Assessment Criteria:

- Sender domain mismatch
- Failed SPF validation
- Missing DKIM signature
- Failed DMARC validation
- Suspicious Reply-To behavior

Assessment Result:

Sender Trustworthiness:
Low

Confidence Level:
High

### Finding

The sender could not be considered trustworthy based on the observed authentication failures and contextual inconsistencies.

---

## Header-Derived Indicators of Compromise (IOCs)

| IOC Type | Value | Reason | Severity |
|-----------|---------|---------|-----------|
| IP Address | 188.127.247.252 | Originating mail server | High |
| Email Address | khz.port@scp.gov.iq | Suspicious sender | High |
| Domain | scp.gov.iq | Claimed sender domain | Medium |

---

## Technical Summary

| Category | Result |
|-----------|----------|
| Return-Path | khz.port@scp.gov.iq |
| From | SupportDesk <khz.port@scp.gov.iq> |
| Reply-To | admin@malware-traffic-analysis.net |
| SPF | Fail |
| DKIM | None |
| DMARC | Fail |
| DMARC Policy | Quarantine |
| Originating IP | 188.127.247.252 |
| Sender Trustworthiness | Low |
| Social Engineering | Observed |
| Overall Risk | High |

---

## Confidence Assessment

Analyst Confidence:
High

Reason:

Multiple independent indicators supported the phishing classification, including authentication failures, suspicious sender behavior, social engineering indicators, and unauthorized sender infrastructure.

---

## Analyst Conclusion

The email was determined to be a phishing attempt.

The investigation identified multiple indicators of malicious activity, including SPF failure, absence of DKIM signatures, DMARC failure, suspicious Reply-To behavior, and the use of social engineering techniques within the subject line.

The originating server (188.127.247.252) was not authorized to send emails on behalf of the claimed domain.

Based on these findings, the email was classified as malicious and designed to harvest user credentials.

---

## Final Verdict

Classification:
Confirmed Phishing Email

Risk Level:
Critical

Attack Objective:
Credential Harvesting

Recommended Response:

- Quarantine the phishing email.
- Block the originating IP address (188.127.247.252).
- Block the phishing domain (email.procedure.best).
- Investigate related emails across the environment.
- Search logs for communication involving identified IOCs.
- Reset potentially compromised credentials.
- Notify affected users.
- Review email authentication policies.
- Conduct phishing awareness training.

Case Status:
Closed