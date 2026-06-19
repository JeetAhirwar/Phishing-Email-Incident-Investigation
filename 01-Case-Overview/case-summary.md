# Case Summary

## Case Information

Case ID:
PHISH-2024-001

Case Title:
2024-08-29: Phishing Email and Traffic to Fake Webmail Login Page

Analyst:
Jeet Ahirwar

Investigation Date:
19 June 2026

Case Source:
Malware Traffic Analysis

Investigation Type:
Phishing Email Analysis & Network Forensics

Objective:
Investigate a phishing email campaign to identify malicious indicators, understand attacker techniques, reconstruct victim activity, confirm credential harvesting, and document incident response actions.

Current Status:
Investigation Completed

---

## Initial Triage

Severity:
High

Reason:
The email impersonated an account validation request and redirected the victim to a fake webmail login page designed to harvest credentials.

Potential Impact:
Credential Theft

Attack Type:
Phishing

Initial Status:
Under Investigation

---

## Evidence Collection

Evidence Collected:

- Original phishing email archive (.eml.zip)
- Extracted EML file
- Network traffic archive (.pcap.zip)
- Extracted PCAP file
- Screenshots and investigation artifacts

Status:
Evidence preserved successfully.

Next Step:
Extract and analyze email contents.

---

## Email Extraction

The password-protected ZIP archive was extracted successfully.

The original EML evidence was preserved.

A separate analysis copy was created for examination purposes.

Status:
Ready for header analysis.

---

## Network Analysis

Evidence:
2024-08-29-phishing-website-traffic.pcap

Analysis Tool:
Wireshark (Kali Linux)

Total Packets:
895

Status:
PCAP loaded successfully.

---

## Investigation Progress

### Email Investigation

- Email header analysis completed.
- Return-Path analysis completed.
- Sender analysis completed.
- Reply-To analysis completed.
- Subject analysis completed.

### Authentication Analysis

- SPF validation completed.
- DKIM validation completed.
- DMARC validation completed.

### Threat Intelligence

- VirusTotal analysis completed.
- AbuseIPDB analysis completed.
- Cisco Talos analysis completed.
- WHOIS investigation completed.

### Network Forensics

- DNS lookup identified.
- TCP handshake observed.
- HTTP GET request identified.
- HTTP POST request identified.
- HTTP Stream analysis completed.

---

## Key Findings

- SPF validation failed.
- DKIM signatures were absent.
- DMARC validation failed.
- Suspicious Reply-To behavior observed.
- Phishing domain identified:
  email.procedure.best
- Victim accessed the phishing page.
- Victim submitted authentication data.
- Credential harvesting activity confirmed.

---

## Final Classification

Incident Type:
Confirmed Phishing Attack

Severity:
Critical

Attack Objective:
Credential Harvesting

Investigation Outcome:
Successful reconstruction of the phishing campaign from email delivery through credential submission.

Case Status:
Closed

---

## Executive Summary

This investigation analyzed a real-world phishing campaign involving a malicious email that redirected the victim to a fake webmail login page.

Through email header analysis, IOC extraction, threat intelligence enrichment, and network traffic analysis, the phishing infrastructure and victim activity were successfully reconstructed.

The investigation confirmed that the victim interacted with the phishing page and submitted authentication data via an HTTP POST request to attacker-controlled infrastructure.

Based on the collected evidence, the incident was classified as a confirmed credential harvesting attack.