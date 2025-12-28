
🛡️ Project Sentinel-Grid: AI-Driven Threat Detection for KRITIS
Focus: Industrial Control System (ICS) Security & Behavioral Anomaly Detection
Lead Developer: Sandra Weiß
Date: December 2025
Academic Foundation: Johns Hopkins University - AI for Industrial Control Systems Security (Dec 2025)

📝 Project Overview
Sentinel-Grid is a proactive security framework designed to protect critical infrastructure (power grids, industrial turbines, energy systems) from sophisticated cyber-physical attacks.
Traditional security systems rely on threshold detection ("alarm if voltage > 280V"), which leaves KRITIS vulnerable to sub-threshold attacks - malicious activity that stays within "safe" limits but aims to cause long-term damage or grid instability.
Sentinel-Grid shifts from reactive rules to proactive behavioral analysis. Using Unsupervised Machine Learning (Isolation Forest), the system learns the "normal operational footprint" of industrial systems and identifies anomalies that signature-based detection would miss.

🚀 Key Features & Implementation Phases
Phase 1: Establishing the Operational Baseline
Using Python (Pandas, NumPy, Scikit-Learn), I simulated real-time sensor data from a Siemens turbine to establish behavioral patterns.
The Challenge:
Traditional security would only flag obvious attacks (e.g., frequency spike to 300Hz). But sophisticated attackers operate in the "gray zone" - raising turbine frequency from 50Hz to 65Hz, which stays within threshold limits but degrades equipment over time.
The Solution:
The Isolation Forest model learns what "normal" looks like for this specific turbine at this specific time of day, enabling detection of statistically significant deviations rather than just threshold violations.
Result: Real-time visualization of cyber-physical anomalies, catching threats traditional systems miss.

Phase 2: Temporal Correlation & Trend Analysis
Problem: Initial model flagged too many alerts (500+ potential anomalies), creating alarm fatigue for SOC operators.
Solution:

Stricter contamination rate (0.5% instead of 5%) to focus only on critical threats
10-point rolling mean to give the AI "short-term memory" - comparing current state against recent trends, not just static baselines

Result:

Reduced alerts from 500 → 48 (90% reduction in false positives)
Maintained high detection accuracy by focusing on temporal anomalies (sudden changes in trend) rather than isolated data points

This approach mirrors how experienced SOC analysts work - they don't just look at individual logs, they recognize when patterns shift.

Phase 3: Adversarial Stress Testing (Red Teaming)
To validate the model, I simulated two sophisticated attack scenarios that real-world adversaries use:
Test 1: Replay Attack
Attack Method: Intercept 50 points of "perfect" normal data and replay it during a crisis, hiding actual volatility from operators (similar to Stuxnet tactics).
Detection Result: The AI flagged the "seams" where live data transitioned to recorded loops - catching the deception even though all values stayed within safe thresholds.
Test 2: Man-in-the-Middle (MITM) Bias Injection
Attack Method: Inject a constant +15V bias into sensor readings, causing controllers to overcompensate and slowly damage transformers while appearing "normal."
Detection Result: The AI identified sustained statistical drift - the raw data pulled away from the rolling mean too quickly, triggering alerts even though no single reading violated thresholds.


🛠️ Technical Stack
Programming & Data Science:

Python (primary language)
Pandas, NumPy (data manipulation & analysis)
Scikit-Learn (Isolation Forest implementation)
Matplotlib (real-time visualization)

Machine Learning Approach:

Unsupervised Learning (no labeled attack data required)
Isolation Forest (anomaly detection optimized for "few and different" patterns)
Feature Engineering (rolling mean for temporal context)

Security Frameworks:

KRITIS Security Standards (German critical infrastructure protection)
ICS/OT Behavioral Analysis
Adversarial Testing (Red Team methodology)

Dataset:

Real-world power grid telemetry (Voltage, Current, Frequency)
Kaggle: Power System Multiclass Anomaly Data


💡 Key Insights & Strategic Value
Why This Matters for SOC Teams:
1. Generalizable Threat Detection
Both attack types (Replay, MITM) triggered similar anomaly signatures, proving the model generalizes the concept of "normalcy" rather than memorizing specific attack patterns. This enables zero-day attack detection without needing historical examples.
2. Trend-Based Detection > Threshold-Based
Traditional systems missed both attacks because values stayed within 180V-280V "safe zone." Sentinel-Grid caught them by analyzing temporal correlation - how data points relate to each other over time, not just static limits.
3. Operational Efficiency (Alarm Fatigue Reduction)
By tuning the contamination rate and implementing rolling mean analysis, the system acts as an AI copilot for analysts - surfacing only the most critical threats and reducing noise by 90%.
4. Real-World Applicability
This project demonstrates capability in:

ICS/OT Security (specialized, high-demand skill)
Adversarial Thinking (Red Team methodology)
ML for Security (applying AI to solve real operational problems)
KRITIS Protection (directly relevant to energy sector roles)


🎓 Academic Foundation
This project was developed alongside coursework from:

Johns Hopkins University: Artificial Intelligence for Industrial Control Systems Security (Dec 2024)
IBM Cybersecurity Analyst Professional Certificate (2025)
CompTIA Security+ (Dec 2025)


🔮 Future Development Roadmap
1. Multi-Variate Analysis
Correlate Voltage + Frequency + Current simultaneously for richer behavioral patterns
2. Explainable AI (XAI)
Implement SHAP values to show analysts why specific anomalies were flagged (building trust in AI decisions)
3. Edge Deployment
Optimize model for real-time inference on Siemens Scalance or Simatic hardware for production OT environments
4. Extended Attack Scenarios
Test against coordinated attacks, time-delay exploits, and advanced persistent threats (APTs)

📫 Connect
Portfolio: github.com/Sorein88/google-cybersecurity-portfolio
LinkedIn: linkedin.com/in/sandra-weiss-cy
Email: weiss_sandra@mein.gmx

This project demonstrates my ability to bridge technical depth (Python, ML, data analysis) with operational security thinking (threat modeling, red teaming, SOC workflow optimization) - essential skills for protecting critical infrastructure in an increasingly hostile threat landscape.
