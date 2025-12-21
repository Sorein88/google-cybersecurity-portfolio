# Post-Incident Report: E-Commerce Data Breach

## Executive Summary
Led the investigation into a major data breach affecting 50,000 customer records. The root cause was identified as a web application vulnerability.

## Technical Root Cause
* **Vulnerability:** Forced Browsing / IDOR (Insecure Direct Object Reference).
* **Classification:** OWASP Top 10.
* **Evidence:** Log forensics revealed unauthorized GET requests accessing sequential user IDs.

## Mitigation & Lessons Learned
* Coordinated a customer notification strategy for 50k users.
* Estimated financial impact: $100,000.
* Recommended implementation of session-based access controls and automated vulnerability scanning.