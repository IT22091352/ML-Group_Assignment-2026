# Machine Learning for IoT Intrusion Detection 🛡️

A comparative study of tree-based Machine Learning algorithms (XGBoost, LightGBM, Random Forest, and Decision Tree) to accurately detect and classify network traffic anomalies and cyber-attacks in IoT environments.

## 📌 Project Overview
The rapid proliferation of Internet of Things (IoT) devices has increased the attack surface for malicious actors. This project addresses the critical need for a robust, automated Intrusion Detection System (IDS). By applying Supervised Machine Learning techniques to network flow metrics, we developed models capable of autonomously distinguishing between benign traffic and 33 distinct types of cyber-attacks (e.g., DDoS, Mirai botnets, Reconnaissance).

## 📊 Dataset
**Dataset Used:** [CICIoT2023](https://www.kaggle.com/datasets/himadri07/ciciot2023)  
*Published by the Canadian Institute for Cybersecurity.*

* **Context:** Generated using a realistic topology of 105 IoT devices while various cyber-attacks were actively executed.
* **Sample Size Used:** * Training Set: 1,000,000 records
    * Validation Set: 200,000 records
    * Testing Set: 300,000 records
* **Target Variable:** 34 distinct classes (1 Benign + 33 Attack types).

## 🛠️ Methodology & Preprocessing
To ensure optimal model performance, the following preprocessing pipeline was implemented:
1.  **Data Cleansing:** Replaced unstable `Infinity` values with `NaN` and dropped missing values.
2.  **Encoding:** Applied `LabelEncoder` for the 34 textual target labels.
3.  **Scaling:** Utilized `RobustScaler` to manage extreme numerical spikes (outliers) typical in DDoS volumetric floods.
4.  **Class Balancing (Hybrid Approach):** To combat extreme class imbalance without exceeding hardware memory constraints:
    * **Undersampled** majority attack classes to 15,000 records each.
    * **Oversampled** minority classes using **SMOTE** up to 15,000 records.
    * *Result:* A perfectly balanced training dataset of 510,000 rows.

## 🚀 Algorithms Implemented
Four tree-based algorithms were chosen for their ability to find non-linear, complex decision boundaries in large tabular datasets:

1.  **XGBoost (Extreme Gradient Boosting):** High predictive power with GPU acceleration.
2.  **LightGBM:** Exceptionally fast, leaf-wise tree growth.
3.  **Random Forest:** Ensemble method to counter variance and overfitting.
4.  **Decision Tree:** Highly interpretable baseline model.

## 🏆 Results & Comparative Performance
Models were evaluated on a strictly unseen test dataset of 300,000 records.

| Algorithm | Overall Accuracy | Weighted F1-Score | Macro F1-Score |
| :--- | :--- | :--- | :--- |
| **XGBoost** | **99.37%** | **99.37%** | **~82.00%** |
| **LightGBM** | 99.35% | 99.35% | 81.24% |
| **Random Forest** | 99.34% | 99.29% | 75.00% |
| **Decision Tree** | 96.78% | 97.79% | 72.22% |

*The hybrid SMOTE + Undersampling data-level fix drastically improved the ensemble models' ability to classify rare minority attacks, pushing XGBoost to a superior 82.00% Macro F1-Score.*

## 🎥 Project Demonstration
**Watch our presentation and real-time model verification here:** ▶️ [Insert YouTube Link Here]

## 👥 Group Members
* **Vitharana K.V.C.D** (IT22091352) - XGBoost Implementation & Pipeline Design
* **Buddhima I.K.N** (IT22133472) - Decision Tree Implementation & Visualizations
* **Ranepura L.K** (IT22298430) - Random Forest Implementation & Version Control
* **Karunadasa M.S.T** (IT22007056) - LightGBM Implementation & Class Balancing

---
*This project was completed as part of the IT4060 - Machine Learning module at the Sri Lanka Institute of Information Technology (SLIIT).*
