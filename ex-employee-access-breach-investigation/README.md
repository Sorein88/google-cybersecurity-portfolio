# Ex-Employee Access Breach Investigation

## Project Overview
Investigation of an unauthorized access incident where a former contractor with expired credentials accessed sensitive payroll systems four years after contract termination. This analysis identifies critical failures in the user deprovisioning process and provides actionable security recommendations.

## Scenario
A security team discovered suspicious access to the company's payroll systems. Investigation revealed that a user account belonging to a contractor whose contract ended in 2019 was still active with administrative privileges and was used to access sensitive systems in 2023.

## Investigation Details

**Timeline:**
- Contract ended: 2019
- Unauthorized access detected: October 3, 2023
- Gap: 4 years of unrevoked access

**User Profile:**
- Name: Robert Taylor Jr.
- Role: Former contractor (Legal/Administrator access)
- Access level: Administrative privileges to payroll systems
- Source IP: 152.207.255.255

## Skills Demonstrated
- Security incident investigation
- Access control analysis
- Identification of deprovisioning failures
- Risk assessment (insider threat detection)
- Security policy recommendations
- Understanding of principle of least privilege
- Knowledge of authentication controls (MFA)

## Key Findings

**Critical Security Flaw:**
Failure in user deprovisioning process allowed a contractor account with administrative privileges to remain active for 4 years post-contract termination, creating significant insider threat risk.

**Root Causes:**
1. No automated account expiration policy
2. Lack of regular access reviews
3. Missing offboarding procedures for contractors
4. No monitoring of dormant privileged accounts

## Recommendations Implemented

**Technical/Operational Controls:**
- Implement automatic account expiration after 30 days of inactivity or contract termination
- Enable Multi-Factor Authentication (MFA) for all accounts to prevent unauthorized credential use

**Managerial/Administrative Controls:**
- Restrict contractor access to minimum necessary business resources (principle of least privilege)
- Establish formal offboarding procedures
- Conduct quarterly access reviews for privileged accounts
- Separate contractor accounts from employee accounts with different lifecycle policies

## Security Impact

**Before:**
- Dormant privileged accounts remained active indefinitely
- No differentiation between employee and contractor access lifecycle
- Potential for unauthorized access by former personnel

**After:**
- Automated deprovisioning reduces attack surface
- MFA prevents compromised credential exploitation
- Regular audits identify and remove unnecessary access
- Clear contractor access policies reduce risk

## Frameworks & Standards Applied
- **NIST SP 800-53:** AC-2 (Account Management), AC-6 (Least Privilege)
- **Principle of Least Privilege**
- **Defense in Depth:** Multiple layers of access controls
- **User Lifecycle Management:** Provisioning → Monitoring → Deprovisioning

## Tools & Concepts Used
- Access control logs analysis
- User account auditing
- Authentication mechanisms (MFA)
- Authorization policy review
- IP address tracking

## Date Completed
November 2025

## Certification
Part of Google Cybersecurity Professional Certificate - Course 5: Assets, Threats, and Vulnerabilities

## Lessons Learned
This investigation highlights the critical importance of:
- Automated deprovisioning processes
- Regular access reviews, especially for privileged accounts
- Treating contractor and employee accounts differently in lifecycle management
- Layered security controls (MFA) to prevent credential-based attacks
- Proactive monitoring of dormant accounts
