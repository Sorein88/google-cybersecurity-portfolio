# **🔐 Project: PW AI Auditor – Intelligent Password Security Analysis**

**Focus:** Cybersecurity Automation & Adversarial Simulation  
**Author:** **Sandra Weiß** | **Core Tool:** **Python / AI-driven Dictionary Attacks**

---

## **📝 Project Overview**
The **PW AI Auditor** is a dual-layered security tool designed to evaluate password strength from both a mathematical and an adversarial perspective. Unlike standard testers, it doesn't just check for complexity—it simulates how an AI-driven attacker would attempt to crack the password using pattern recognition and common dictionary variants.

---

## **🚀 Key Features**

### **Layer 1: Mathematical Strength Audit**
* Uses the **zxcvbn** library and custom regex patterns to calculate entropy.
* Analyzes length, character variety, and common sequences.
* Provides a **Brute-Force Estimate** (Time-to-crack).

### **Layer 2: AI-Driven Adversarial Testing**
* Simulates an **AI Password Guesser** that recognizes common "human" patterns (e.g., replacing 'a' with '@').
* Checks against a high-frequency **Common Pattern Dictionary**.
* **Result:** Identifies passwords that look "strong" to a machine but are easily guessable by a smart attacker.

### **Layer 3: Automated Hardening Recommendations**
* Suggests **hardened versions** of weak passwords.
* Provides a detailed **Vulnerability Report** for each analyzed input.

---

## **🛠️ Technical Toolkit**
* **Language:** **Python**
* **Security Libraries:** **zxcvbn** (Dropbox's strength estimator)
* **Core Logic:** **Regular Expressions (Regex)**, **Adversarial Pattern Matching**
* **Concepts:** **Entropy**, **Brute-Force Mitigation**, **Dictionary Attacks**

---

## **💡 Why this matters for SOC Teams**
This project demonstrates:
* Ability to build **custom security tools** for internal audits.
* Understanding of the **attacker's mindset** (Adversarial Thinking).
* Proficiency in **Python scripting** to automate security assessments.