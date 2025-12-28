# 🔐 Project: PW AI Auditor – Intelligent Password Security Analysis

**Focus:** Cybersecurity Automation & Adversarial Simulation  
**Author:** Sandra Weiß  
**Core Tools:** Python, AI-driven Pattern Recognition, Dictionary Attack Simulation  
**Date:** 2025

---

## 📝 Project Overview

The **PW AI Auditor** is a dual-layered security tool designed to evaluate password strength from both a **mathematical** and an **adversarial** perspective. 

Unlike standard password testers that only check for complexity (length, special characters, numbers), **PW AI Auditor simulates how an AI-driven attacker would attempt to crack passwords** using pattern recognition and common dictionary variants.

**The Problem:**  
Traditional password strength meters give false confidence. A password like `P@ssw0rd2024!` appears "strong" (length, special chars, numbers) but is trivially crackable by attackers using:
- Dictionary attacks with common substitutions (`@` for `a`, `0` for `o`)
- Predictable patterns (year appended, common word + numbers)
- AI-powered password guessers trained on breach datasets

**PW AI Auditor exposes these vulnerabilities BEFORE attackers exploit them.**

---

## 🚀 Key Features & Implementation Layers

### Layer 1: Mathematical Strength Audit

**Objective:** Calculate objective password strength using entropy and brute-force resistance.

**Implementation:**
- **zxcvbn library** (Dropbox's industry-standard strength estimator) analyzes:
  - Password length
  - Character variety (uppercase, lowercase, numbers, symbols)
  - Common sequences (`123`, `qwerty`, repeated characters)
- **Custom regex patterns** detect weak structures:
  - Sequential characters (`abcd`, `1234`)
  - Keyboard patterns (`qwerty`, `asdfgh`)
  - Common substitutions (`@` for `a`, `$` for `s`)
- **Entropy calculation** determines randomness vs predictability
- **Brute-Force Time Estimate** shows realistic crack time

**Output Example:**
```
Password: MyP@ssw0rd123
Mathematical Strength: WEAK
Entropy: 42 bits
Estimated Crack Time: 3.2 hours (GPU cluster)
Vulnerability: Dictionary word + common substitutions + predictable number sequence
```

---

### Layer 2: AI-Driven Adversarial Testing

**Objective:** Simulate how a smart attacker with AI tools would approach cracking this password.

**The Adversarial Mindset:**  
Modern password crackers don't just brute-force - they use:
- **Pattern recognition** (humans use predictable substitutions)
- **Contextual guessing** (company name + year, personal info)
- **Trained models** on billions of leaked passwords

**Implementation:**
- **AI Password Guesser Module** recognizes common "human" patterns:
  - Base dictionary word + substitutions (`password` → `P@ssw0rd`)
  - Appended numbers (birth years, current year, sequential counting)
  - Capitalization patterns (first letter capital, all caps)
- **High-Frequency Pattern Dictionary** contains:
  - Top 10,000 most common passwords from breach data
  - Common word variations with substitutions
  - Industry-specific terms (company names, tech jargon)

**Detection Logic:**
```python
# Example: Detecting substitution patterns
if base_word in common_dictionary:
    if contains_common_substitutions(password):
        flag_as_vulnerable("Dictionary word with predictable substitutions")
```

**Result:** Identifies passwords that **appear strong to traditional meters** but are **easily guessable by intelligent attackers**.

**Output Example:**
```
Password: C0mpany2024!
Adversarial Assessment: HIGH RISK
Pattern Detected: Company name + current year + common symbol
Attack Probability: 87% (AI guesser would crack in top 1000 attempts)
Recommendation: Avoid company-related terms, years, and predictable patterns
```

---

### Layer 3: Automated Hardening Recommendations

**Objective:** Don't just flag weaknesses - provide actionable fixes.

**Implementation:**
- Analyzes detected vulnerabilities
- Suggests **hardened alternatives** that maintain memorability while increasing security
- Generates **detailed vulnerability reports** for audit documentation

**Example Hardening:**
```
Original Password: Summer2024!
Vulnerabilities:
  - Season name (common dictionary word)
  - Current year (predictable)
  - Single symbol at end (pattern)

Hardened Alternative: $umM3r_t!M3_70x
Changes:
  - Mixed case disrupts pattern recognition
  - Substitutions less predictable (@→3, i→!)
  - Added randomness with underscores and hex notation
  - Still memorable (phonetic similarity to original)

New Strength: STRONG
Entropy: 68 bits
Estimated Crack Time: 847 years (GPU cluster)
```

---

## 🛠️ Technical Stack

**Programming:**
- **Python** (core language)
- **Regular Expressions (Regex)** for pattern matching
- **zxcvbn library** (Dropbox's password strength estimator)

**Security Concepts:**
- **Entropy Analysis** (measuring password randomness)
- **Brute-Force Mitigation** (time-to-crack calculations)
- **Dictionary Attacks** (common word + variation testing)
- **Adversarial Simulation** (thinking like an attacker)

**Attack Simulation Techniques:**
- Substitution pattern recognition (`@` for `a`, `0` for `o`, `$` for `s`)
- Sequential number detection (years, counting patterns)
- Common word dictionary matching
- Contextual pattern analysis (company names, personal info)

---

## 💡 Key Insights & Strategic Value

### Why This Matters for SOC Teams:

**1. Proactive Vulnerability Detection**  
Instead of waiting for passwords to be compromised in breaches, identify weak authentication BEFORE attackers do. This tool enables **internal security audits** to catch risky passwords across employee accounts.

**2. Adversarial Thinking**  
Traditional password policies focus on complexity rules ("must have 1 uppercase, 1 number, 1 symbol"). **This tool thinks like an attacker** - recognizing that `P@ssw0rd1!` satisfies all rules but is still trivially crackable.

**3. Automation for Scale**  
Manual password audits are impractical for organizations with hundreds/thousands of users. **PW AI Auditor can batch-process credential databases** and flag high-risk accounts for mandatory resets.

**4. User Education**  
The vulnerability reports generate clear, actionable feedback for non-technical users:
- "Your password uses a dictionary word" (not vague "weak password")
- "Attackers would crack this in 3 hours using AI tools" (concrete threat)
- "Here's a stronger alternative" (solution, not just criticism)

---

## 🎯 Real-World Use Cases

**Internal Security Audits:**  
HR onboarding includes password strength check - new employees receive hardening recommendations before account activation

**Post-Breach Credential Rotation:**  
After a breach, audit all user passwords to identify those vulnerable to similar attack patterns

**Compliance Requirements:**  
Demonstrate adherence to password security standards (NIST 800-63B, PCI DSS) with automated strength verification

**Developer Tools:**  
Integrate into CI/CD pipelines to prevent developers from hardcoding weak credentials in repositories

---

## 🎓 Academic Foundation

This project was developed alongside coursework from:
- **CompTIA Security+** (2025) - Authentication & Access Control
- **IBM Cybersecurity Analyst Professional Certificate** (2025) - Threat Modeling
- **TryHackMe SOC Level 1** (2025) - Adversarial Thinking & Red Team Techniques

---

## 🔮 Future Development Roadmap

**1. Breach Database Integration**  
Cross-reference passwords against HaveIBeenPwned API to flag previously compromised credentials

**2. Context-Aware Analysis**  
Incorporate user metadata (username, email, company name) to detect personalized weak patterns

**3. Multi-Language Support**  
Expand dictionary attack simulation to non-English languages and regional patterns

**4. Real-Time API**  
Deploy as microservice for live password validation during account creation/password resets

---

## 📫 Connect

**Portfolio:** [github.com/Sorein88/google-cybersecurity-portfolio](https://github.com/Sorein88/google-cybersecurity-portfolio)  
**LinkedIn:** [linkedin.com/in/sandra-weiss-cy](https://linkedin.com/in/sandra-weiss-cy)  
**Email:** weiss_sandra@mein.gmx

---

**This project demonstrates my ability to build practical security automation tools that combine technical depth (Python, regex, entropy analysis) with adversarial thinking - essential skills for proactive threat mitigation in SOC environments.**
