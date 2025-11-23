# Phishing Alert Investigation & Escalation

## Project Overview
Investigation and triage of a medium-severity security alert (Ticket A-2703) involving a phishing email with malicious attachment. Successfully identified multiple phishing indicators, confirmed malware download through threat intelligence analysis, and escalated to Level-Two SOC analyst for incident response.

## Scenario
A security system generated an alert: "SERVER-MAIL Phishing attempt possible download of malware." An employee received a suspicious email claiming to be from "Def Communications" regarding a job application, which contained a password-protected executable attachment.

## Investigation Process

### Initial Alert Details
- **Ticket ID:** A-2703
- **Alert Message:** SERVER-MAIL Phishing attempt possible download of malware
- **Severity:** Medium (initial classification)
- **Date/Time:** Wednesday, July 20, 2022, 09:30:14 AM
- **Affected User:** hr@inergy.com

### Phishing Indicators Identified

**Email Header Anomalies:**
- Sender name: "Def Communications"
- Sender email: 76tguyhh6tgftrt7tg.su (suspicious TLD)
- Sender IP: 114.114.114.114
- Email signature: "Clyde West" (inconsistent with sender name)

**Content Red Flags:**
- Subject line typo: "Infrastructure **Egnieer** role"
- Grammatical errors: "I am writing **for to** express my interest"
- Generic greeting: "Dear HR at Ingergy"
- Password-protected attachment (common social engineering tactic)

**Malicious Attachment:**
- Filename: bfsvc.exe (executable disguised as resume)
- Password: paradise10789 (provided in email body)
- File hash: 54e6ea47eb04634d3e87fd7787e2136ccfbcc80ade34f246a12cf93bab527f6b
- **Status: CONFIRMED MALICIOUS** via threat intelligence database

### User Actions
❌ Employee downloaded the attachment
❌ Employee opened the malicious file
⚠️ Malware executed on affected machine

## Skills Demonstrated
- Security alert triage and analysis
- Phishing email investigation
- Threat intelligence utilization (file hash verification)
- Indicator of Compromise (IoC) identification
- Escalation decision-making
- Security documentation and reporting
- Email header analysis
- Malware identification
- Risk assessment (severity vs. actual impact)

## Key Findings & Decision Rationale

**Critical Factors:**
1. **Confirmed malware execution** - not just attempted delivery
2. **Known malicious file** - verified against threat intelligence
3. **Successful user interaction** - both download AND execution occurred
4. **Initial severity underestimated** - Medium classification didn't reflect actual impact

**Escalation Justification:**
Despite medium severity rating, the confirmed download and execution of known malware required immediate escalation to Level-Two SOC analyst for:
- Malware containment procedures
- Host isolation and forensic analysis
- Potential lateral movement investigation
- Incident response coordination

## Action Taken
**Ticket Status:** ✅ Escalated to Level-Two SOC Analyst

**Ticket Comments Provided:**
Documented all phishing indicators, user actions, malware confirmation, and rationale for escalation to ensure smooth handoff to L2 analyst.

## Security Concepts Applied
- **NIST Incident Response Lifecycle:** Detection → Analysis phase
- **Alert Triage:** Assessing severity vs. actual impact
- **Threat Intelligence:** Leveraging external sources for IoC verification
- **Defense in Depth:** Multiple detection layers (email gateway, endpoint protection)
- **Chain of Custody:** Documenting evidence (file hash, timestamps, user actions)

## Tools & Techniques Used
- Security Information and Event Management (SIEM)
- Threat intelligence databases (file hash lookup)
- Email header analysis
- Malware analysis (file hash verification)
- Ticketing system documentation

## Outcome
Successfully identified and escalated a confirmed malware infection, enabling rapid incident response and containment before potential lateral movement or data exfiltration could occur.

## Date Completed
November 2025

## Certification
Part of Google Cybersecurity Professional Certificate - Course 6: Sound the Alarm - Detection and Response

## Lessons Learned
- Alert severity ratings should be validated against actual impact
- File hash verification is critical for confirming threats
- Multiple phishing indicators increase confidence in threat assessment
- Clear documentation enables effective escalation and handoff
- Social engineering tactics (password-protected files) bypass some technical controls
