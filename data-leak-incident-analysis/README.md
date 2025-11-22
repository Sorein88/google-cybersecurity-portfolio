# Data Leak Incident Analysis

## Project Overview
This project analyzes a data leak incident where internal company documents were accidentally shared publicly. The analysis applies the NIST SP 800-53 AC-6 control (Principle of Least Privilege) to identify issues, provide recommendations, and justify security improvements.

## Scenario
A sales manager granted team members access to an internal folder containing unreleased product information and customer analytics. After a meeting, access was not revoked. A sales representative accidentally shared the entire folder with a business partner, who then posted it on social media.

## Skills Demonstrated
- Incident analysis and root cause identification
- Application of NIST SP 800-53 security controls
- Understanding of Principle of Least Privilege (PoLP)
- Risk assessment and mitigation recommendations
- Security policy documentation

## Key Findings
- **Primary Issue:** Violation of least privilege - excessive access granted and not revoked
- **Contributing Factor:** Human error in sharing wrong link
- **Impact:** Confidential data publicly exposed

## Recommendations Implemented
1. **Role-based access control:** Restrict access based on job function
2. **Automatic access revocation:** Time-based access expiration to eliminate manual management dependency

## Tools & Frameworks Used
- NIST Cybersecurity Framework (CSF)
- NIST SP 800-53: AC-6 (Least Privilege Control)

## Date Completed
November 2025

## Certification
Part of Google Cybersecurity Professional Certificate - Course 5: Assets, Threats, and Vulnerabilities
