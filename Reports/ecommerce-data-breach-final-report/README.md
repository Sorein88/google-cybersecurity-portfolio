# E-Commerce Data Breach Investigation & Final Report

## Project Overview
Complete incident response case study documenting a data breach affecting 50,000 customer records. Investigated forced browsing vulnerability in e-commerce web application, analyzed web server logs to confirm data exfiltration, coordinated customer notification, and provided remediation recommendations. Estimated financial impact: $100,000.

## Scenario
An attacker exploited a web application vulnerability to perform a forced browsing attack, systematically accessing customer purchase confirmation pages by manipulating URL parameters. The breach resulted in theft of customer PII and financial data, followed by a ransom demand that escalated from $25,000 to $50,000.

## Incident Timeline

**December 22, 2022 - 3:13 PM PT (Initial Contact)**
- Employee received first ransom email ($25,000 demand)
- Email incorrectly dismissed as spam
- ⚠️ Missed opportunity for early detection

**December 28, 2022 - 7:20 PM PT (Incident Confirmed)**
- Unauthorized access to customer PII and financial data
- Attacker had been actively exfiltrating data

**December 28, 2022 - Later Same Day (Escalation)**
- Second ransom email received with sample of stolen data
- Ransom increased to $50,000
- Security team notified and investigation initiated

**December 28-31, 2022 (Investigation & Response)**
- Root cause analysis conducted
- Web application vulnerability identified
- Log analysis confirmed scope of breach
- Response and remediation actions implemented

## Skills Demonstrated
- Incident response coordination
- Web application security analysis
- Log analysis and forensics
- Vulnerability assessment
- Root cause analysis
- Financial impact assessment
- Executive-level reporting
- Crisis management (ransom situation)
- Customer communication strategy
- Remediation planning
- Evidence collection and preservation

## Investigation Details

### Root Cause Analysis

**Vulnerability Type:** Forced Browsing (Insecure Direct Object Reference - IDOR)

**Attack Method:**
- Attacker accessed customer purchase confirmation pages
- Modified order number in URL string (e.g., `/order/12345` → `/order/12346`)
- No authentication check on order access
- Sequential access to thousands of order confirmations

**Technical Details:**
- Single log source showing exceptionally high volume of requests
- Sequential pattern in customer order numbers accessed
- Clear evidence of automated data collection
- Thousands of purchase confirmation pages accessed

### Impact Assessment

**Affected Records:** ~50,000 customer records

**Data Types Compromised:**
- Personal Identifiable Information (PII)
- Financial information
- Purchase history

**Financial Impact:** $100,000
- Direct incident response costs
- Customer notification expenses
- Identity protection services
- Potential revenue loss
- Regulatory fines (potential)

## Response & Remediation Actions

### Immediate Response
✅ Security team mobilized on-site
✅ Vulnerability identified and patched
✅ Web server logs analyzed for full scope
✅ Evidence preserved for potential law enforcement involvement

### Customer Communication
✅ Collaborated with Public Relations department
✅ Disclosed breach to affected customers
✅ Offered free identity protection services to all 50,000 customers

### Technical Remediation
✅ Fixed insecure direct object reference vulnerability
✅ Implemented authentication checks on order access
✅ Enhanced logging and monitoring

## Recommendations to Prevent Recurrence

### Proactive Security Measures
1. **Routine Vulnerability Scanning**
   - Regular automated scans of web applications
   - Annual penetration testing by third-party security firms
   - Code security reviews before deployment

2. **Access Control Implementation**
   - **Allowlisting:** Restrict access to specified URL sets, automatically block requests outside defined ranges
   - **Authentication enforcement:** Ensure only authenticated users can access sensitive content
   - **Authorization validation:** Verify user owns the resource they're accessing (order belongs to logged-in user)

3. **Enhanced Monitoring**
   - Implement anomaly detection for unusual access patterns
   - Alert on high-volume sequential access attempts
   - Real-time SIEM correlation rules

### Process Improvements
- Security awareness training (recognizing ransom emails)
- Incident response procedure updates
- Regular security assessments

## Security Frameworks & Standards Applied
- **NIST Incident Response Lifecycle:** Preparation → Detection → Analysis → Containment → Eradication → Recovery → Post-Incident
- **OWASP Top 10:** A01:2021 - Broken Access Control (IDOR vulnerability)
- **Chain of Custody:** Evidence preservation through log analysis
- **Business Continuity:** Customer notification and reputation management

## Key Lessons Learned

**Detection Failures:**
- Initial ransom email dismissed as spam - security awareness gap
- 6-day window between first contact and incident confirmation
- Need for better email threat intelligence and user training

**Investigation Success:**
- Clear log evidence enabled rapid root cause identification
- Single log source pattern made attack obvious
- Preserved evidence supports potential legal action

**Response Effectiveness:**
- Quick mobilization prevented further damage
- Coordinated customer communication maintained trust
- Offered remediation (identity protection) demonstrated accountability

## Tools & Techniques Used
- Web server log analysis
- Access pattern correlation
- Vulnerability assessment
- IDOR (Insecure Direct Object Reference) identification
- Timeline reconstruction
- Financial impact modeling
- Executive reporting

## Incident Status
✅ **CLOSED** - Investigation complete, remediation implemented, customers notified

## Date Completed
November 2025

## Certification
Part of Google Cybersecurity Professional Certificate - Course 6: Sound the Alarm - Detection and Response

## Additional Context
This case study demonstrates the critical importance of:
- Proper access control implementation in web applications
- User security awareness training
- Timely incident response to ransom communications
- Comprehensive log analysis for attack pattern identification
- Balancing technical response with business communication needs
