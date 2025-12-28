# 🔐 Project: AI-Powered Phishing URL Detection System

**Focus:** Machine Learning Classifier & Predictive Security  
**Author:** Sandra Weiß  
**Accuracy:** 96.88%  
**Date:** December 2025  
**Academic Foundation:** CompTIA Security+, IBM Cybersecurity Analyst, TryHackMe SOC Level 1 (2025)

---

## 📝 Project Overview

The **AI-Powered Phishing URL Detection System** is a high-performance machine learning classifier designed to identify malicious URLs before users interact with them.

**The Problem:**  
Traditional URL blacklists are reactive - they only catch known phishing sites AFTER they've been reported. **Modern phishing campaigns use disposable domains that exist for hours before being taken down**, making blacklists ineffective against zero-day threats.

**The Solution:**  
Instead of relying on blacklists, this system **analyzes behavioral characteristics of URLs** to detect phishing patterns, enabling proactive detection of threats that have never been seen before.

By analyzing **32 distinct security features** from a dataset of **11,000+ URLs**, the system differentiates between legitimate websites and phishing attempts with **96.88% accuracy**.

---

## 🚀 Key Development Phases

### Phase 1: Feature Engineering & Exploratory Data Analysis

**Objective:** Identify which URL characteristics reliably indicate phishing attempts.

**Implementation:**  
Developed a custom feature extraction engine analyzing:

**Structural Features:**
- URL length (phishing URLs average 54+ characters due to obfuscation)
- Number of dots/subdomains (attackers use complex subdomains like `secure.login.paypal-verify.com`)
- Special characters (`@` for credential theft, `-` for typosquatting)

**Security Indicators:**
- Protocol analysis (HTTP vs HTTPS - **but** attackers increasingly use SSL certificates)
- IP-based URLs (`http://192.168.1.1/admin` bypasses domain reputation)
- Suspicious keywords (`login`, `verify`, `update`, `banking`, `secure`)

**Adversarial Patterns:**
- Digit insertion in domain names (typosquatting: `paypa1.com` instead of `paypal.com`)
- Hyphenated domains (`amazon-security.com`)
- Abnormally long URLs (obfuscation tactic)

**Dataset:**
- **11,054 URLs** (4,897 phishing, 6,157 legitimate)
- **32 security features** per URL
- Source: Kaggle Phishing URL Dataset

**Result:** A robust feature set that serves as the foundation for behavioral detection, catching threats that signature-based systems miss.

---

### Phase 2: Model Training, Evaluation & Algorithm Comparison

**Objective:** Identify the most effective machine learning architecture for phishing detection.

**Models Tested:**
- **Random Forest:** 96.88% accuracy ✅ (Selected)
- **Neural Networks (MLP):** 96.56%
- **SVM:** 95.61%
- **Gradient Boosting:** 95.39%
- **Logistic Regression:** 93.22%

**Why Random Forest Won:**

**1. Highest Accuracy (96.88%)**  
Outperformed all other algorithms on the test set

**2. Low False Positive Rate (3.89%)**  
Critical for production - we can't block legitimate sites. Only 38 safe URLs per 1,000 flagged incorrectly.

**3. Feature Interpretability**  
Can explain WHY a URL was flagged (essential for SOC analyst trust)

**4. Robustness to Adversarial Attacks**  
Tested against "Red Team" scenarios (see Phase 3) - detected sophisticated evasion attempts

---

### Phase 3: Adversarial Testing (Red Team Simulation)

**Objective:** Test if the model can detect sophisticated attackers who intentionally evade detection.

#### **Attack Scenario 1: SSL Certificate Deception**

**Attacker Strategy:**
- Purchase legitimate SSL certificate (HTTPS = ✅)
- Use SEO manipulation to fake traffic stats (Traffic = ✅)
- Hide malicious links behind legitimate-looking anchor text (AnchorURL = ❌)

**Detection Result:**  
```
🛡 ABGEWEHRT! Die KI hat den Braten trotz Tarnung gerochen. 
Vorhersage: PHISHING (69.0% Sicherheit)
```

**Why It Worked:** The model recognized that **legitimate sites don't have mismatched anchor URLs**, even if other signals look clean. This demonstrates **pattern recognition beyond simple rule-matching**.

#### **Attack Scenario 2: Typosquatting**

**Attacker Strategy:**
- Register `paypa1.com` (digit substitution)
- Everything else appears legitimate (SSL, proper structure)

**Detection Features:**
- `AbnormalURL` flag (digit in domain name)
- `AgeofDomain` (new registration)
- `WebsiteTraffic` (low traffic despite "recognizable" brand)

**Result:** Successfully flagged as phishing despite visual similarity to legitimate site.

#### **Attack Scenario 3: Subdomain Hijacking**

**Attacker Strategy:**
- Compromise legitimate subdomain: `shop.amazon-secure.net`
- Use hyphen to appear official

**Detection Features:**
- `SubDomains` (suspicious nested structure)
- `PrefixSuffix-` (hyphen indicator)
- Combined with HTTPS check

**Result:** Model caught the structural anomaly even though the base domain looked legitimate.

---

### Phase 4: Explainable AI (XAI) - Feature Importance Analysis

**Objective:** Understand WHICH features the AI relies on most, enabling analyst trust and model refinement.

**Top 10 Most Important Features:**

1. **HTTPS** - Presence of valid SSL certificate
2. **AnchorURL** - Do links point to the claimed domain?
3. **WebsiteTraffic** - Legitimate sites have established traffic patterns
4. **PrefixSuffix-** - Hyphens common in phishing domains
5. **AgeofDomain** - Newly registered domains (red flag)
6. **DNSRecording** - Proper DNS configuration
7. **SubDomains** - Excessive subdomains indicate obfuscation
8. **PageRank** - Legitimate sites have SEO presence
9. **GoogleIndex** - Is the site indexed by Google?
10. **LinksPointingToPage** - Backlink profile analysis

**Visualization:** Generated bar chart showing relative feature importance, enabling security analysts to understand model decisions.

---

### Phase 5: Interactive Web Application & Deployment

**Objective:** Make the model accessible to non-technical users through an intuitive interface.

**Implementation:**

**Streamlit Web App:**
- **Input:** User pastes suspicious URL
- **Processing:** Feature extraction + ML prediction in real-time
- **Output:** Risk assessment (Safe ✅ / Phishing ⚠️) with confidence score

**Example Output:**
```
URL: https://paypal-secure-login.com
Result: ⚠ PHISHING (71.00% Sicherheit)
Reason: Suspicious keywords + hyphenated domain
```

**Deployment:**
- **Model Export:** Serialized trained model using `joblib` for production use
- **Cloud Deployment:** Deployed via Localtunnel for external accessibility
- **API-Ready:** Can be integrated into browser extensions, email filters, or SOC ticketing systems

---

## 🛠️ Technical Stack

**Programming & Data Science:**
- **Python** (primary language)
- **Pandas, NumPy** (data manipulation & feature engineering)
- **Scikit-Learn** (Random Forest, SVM, MLP, Gradient Boosting)
- **Joblib** (model serialization)
- **Matplotlib, Seaborn** (data visualization)

**Machine Learning Techniques:**
- **Supervised Learning** (trained on labeled phishing/legitimate dataset)
- **Ensemble Methods** (Random Forest: 100 decision trees)
- **Feature Engineering** (32 custom security indicators)
- **Cross-Validation** (80/20 train-test split)

**Deployment & Interface:**
- **Streamlit** (interactive web application)
- **Localtunnel** (cloud deployment for testing)
- **Regex** (pattern matching for URL analysis)

---

## 💡 Key Insights & Strategic Value

### Why This Matters for SOC Teams:

**1. Zero-Day Phishing Detection**  
Doesn't rely on blacklists - detects NEW phishing sites by behavioral analysis

**2. Reduced False Positives (3.89%)**  
Low false positive rate means analysts aren't overwhelmed with false alarms - only 38 legitimate sites per 1,000 flagged incorrectly

**3. Explainable Decisions**  
Feature importance analysis enables analysts to understand WHY a URL was flagged, building trust in AI-assisted triage

**4. Automated Triage**  
Can process thousands of URLs per minute, freeing analysts to focus on confirmed threats instead of manual URL inspection

**5. Integration-Ready**  
Serialized model can be deployed in:
- Email security gateways (block phishing before delivery)
- Browser extensions (warn users in real-time)
- SIEM correlation rules (enrich threat intelligence)
- SOC ticketing systems (auto-categorize phishing reports)

---

## 🎯 Real-World Use Cases

**Email Security Gateway Integration:**  
Scan all inbound email links before delivery - block phishing attempts in real-time

**Browser Extension:**  
Warn users when they're about to visit a suspicious site (similar to Google Safe Browsing, but with behavioral analysis)

**SOC Incident Response:**  
Analysts receive phishing report → paste URL into tool → instant risk assessment → prioritize investigation

**Security Awareness Training:**  
Demonstrate to employees HOW attackers craft convincing phishing URLs (typosquatting, SSL deception, keyword manipulation)

---

## 🎓 Academic Foundation

This project was developed alongside coursework from:
- **CompTIA Security+** (2025) - Threat Analysis & Detection
- **IBM Cybersecurity Analyst Professional Certificate** (2025) - Machine Learning for Security
- **TryHackMe SOC Level 1** (2025) - Phishing Analysis & Email Security

---

## 🔮 Future Development Roadmap

**1. Real-Time Threat Intelligence Integration**  
Cross-reference predictions with HaveIBeenPwned API to flag URLs from known breach datasets

**2. Multi-Language Phishing Detection**  
Expand keyword dictionary to detect non-English phishing campaigns (German, French, Spanish)

**3. Deep Learning Enhancement**  
Test LSTM/Transformer models for sequential pattern recognition in URL structure

**4. Browser Extension Deployment**  
Package model as Chrome/Firefox extension for consumer-facing protection

**5. SIEM Integration**  
Build API connector for Splunk/Sentinel to enrich security alerts with URL risk scores

---

## 📫 Connect

**Portfolio:** [github.com/Sorein88/google-cybersecurity-portfolio](https://github.com/Sorein88/google-cybersecurity-portfolio)  
**LinkedIn:** [linkedin.com/in/sandra-weiss-cy](https://linkedin.com/in/sandra-weiss-cy)  
**Email:** weiss_sandra@mein.gmx

---

**This project demonstrates my ability to build production-ready security automation tools that combine machine learning expertise with operational security thinking - essential skills for modern SOC environments facing evolving phishing threats.**
