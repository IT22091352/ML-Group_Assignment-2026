# IoT Network Intrusion Detection System using XGBoost 🛡️

## 📌 Project Overview
This project implements a robust Machine Learning-based Intrusion Detection System (IDS) designed specifically for Internet of Things (IoT) networks. Utilizing the **Extreme Gradient Boosting (XGBoost)** algorithm, the model analyzes network traffic features to classify data packets as either normal (`BenignTraffic`) or one of 33 distinct cyber-attacks. 

This project was developed as part of our Final Year Machine Learning Assignment to demonstrate the practical application of supervised learning in modern cybersecurity.

## 📊 Dataset: CICIoT2023
The project utilizes the **Canadian Institute for Cybersecurity Internet of Things 2023 (CICIoT2023)** dataset. This is a comprehensive, modern dataset generated from a realistic IoT testbed.
* **Total Classes:** 34 (1 Benign + 33 Attack types)
* **Attack Categories:** DDoS, DoS, Reconnaissance, Web-based (XSS, SQLi), Brute Force, Mirai, and Spoofing.
* **Features:** 47 extracted network flow metrics (e.g., flow duration, packet rates, header lengths).
