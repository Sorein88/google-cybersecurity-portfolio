\# \*\*🛡️ Project Sentinel-Grid: AI-Driven Threat Detection for KRITIS\*\*



\[cite\_start]\*\*Focus:\*\* Industrial Control System (ICS) Security \& Behavioral Anomaly Detection \[cite: 74, 75]  

\[cite\_start]\*\*Lead Developer:\*\* \*\*Sandra Weiß\*\* \[cite: 76] | \[cite\_start]\*\*Date:\*\* \*\*December 2025\*\* \[cite: 77]



---



\## \*\*📝 Project Overview\*\*

\[cite\_start]\*\*Sentinel-Grid\*\* is a proactive security framework designed to protect \*\*critical infrastructure\*\* (such as power grids and industrial turbines) from sophisticated \*\*cyber-physical attacks\*\*\[cite: 74]. \[cite\_start]By using \*\*Unsupervised Machine Learning (Isolation Forest)\*\*, the system establishes a \*\*behavioral baseline\*\* and detects anomalies that traditional signature-based systems might miss\[cite: 75, 92, 93].



---



\## \*\*🚀 Key Features \& Phases\*\*



\### \*\*Phase 1: Establishing the Operational Baseline\*\*

\[cite\_start]I used \*\*Python (Pandas, NumPy)\*\* to simulate real-time sensor data from a \*\*Siemens turbine\*\*\[cite: 78, 79, 80]. \[cite\_start]The AI was trained to recognize a \*\*"normal" vibration frequency (~50Hz)\*\* and automatically flag \*\*high-frequency hacks (~120Hz)\*\*\[cite: 85, 86, 87, 88].

\* \[cite\_start]\*\*Result:\*\* Real-time visualization of \*\*cyber-physical anomalies\*\*\[cite: 104, 109].



\### \*\*Phase 2: Temporal Correlation \& Trend Analysis\*\*

\[cite\_start]To reduce \*\*false alarms (False Positives)\*\*, I implemented a \*\*stricter model\*\* (reducing contamination to 0.5%) and a \*\*10-point rolling mean trend analysis\*\*\[cite: 168, 169, 176, 177]. 

\* \[cite\_start]\*\*Efficiency:\*\* Successfully reduced initial alert noise from \*\*500 potential anomalies\*\* down to \*\*48 critical, smart alerts\*\*\[cite: 173, 174, 175, 184].



\### \*\*Phase 3: Adversarial Stress Testing (Red Teaming)\*\*

\[cite\_start]I simulated two high-risk attack scenarios to test the defense mechanisms\[cite: 186]:

1\.  \[cite\_start]\*\*Replay Attack:\*\* Injecting "perfect" historical data to hide an ongoing crisis from the operator\[cite: 208, 215, 223, 224].

2\.  \[cite\_start]\*\*Man-in-the-Middle (MITM) Bias Injection:\*\* Subtly nudging sensor readings (\*\*+15V bias\*\*) to mask a failing transformer\[cite: 225, 228, 233, 234].



---



\## \*\*🛠️ Technical Toolkit\*\*

\* \[cite\_start]\*\*Language:\*\* \*\*Python\*\* \[cite: 79]

\* \[cite\_start]\*\*Machine Learning:\*\* \*\*Scikit-learn (Isolation Forest)\*\* \[cite: 82, 93]

\* \[cite\_start]\*\*Data Analysis:\*\* \*\*Pandas\*\*, \*\*NumPy\*\* \[cite: 79, 80]

\* \[cite\_start]\*\*Visualization:\*\* \*\*Matplotlib\*\* \[cite: 81]

\* \[cite\_start]\*\*Frameworks:\*\* \*\*KRITIS Security Standards\*\*, \*\*ICS Behavioral Analysis\*\* \[cite: 74, 75]



---



\## \*\*💡 Why this matters for SOC Teams\*\*

This project demonstrates my ability to:

\* \[cite\_start]Identify vulnerabilities in \*\*Industrial Control Systems (ICS)\*\*\[cite: 75].

\* \[cite\_start]Implement \*\*Adversarial Stress Testing\*\* (\*\*Red Teaming\*\*)\[cite: 186].

\* \[cite\_start]Apply \*\*AI and Data Science\*\* to solve complex security challenges in \*\*real-time\*\*\[cite: 149, 158].

