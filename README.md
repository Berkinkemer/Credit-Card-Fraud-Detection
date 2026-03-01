# 💳 Credit Card Fraud Detection with Machine Learning

This project aims to detect fraudulent credit card transactions using machine learning algorithms. Different models were trained on a highly imbalanced dataset, and the most suitable solution is presented by comparing their performances.

## 📌 Project Summary
Credit card fraud is one of the most significant problems in the financial sector. In this project:
* A highly imbalanced dataset, where only **0.17%** of transactions are fraudulent, was analyzed.
* **SMOTE** (Synthetic Minority Over-sampling Technique) was applied to prevent data leakage and enable the model to learn the minority class.
* Powerful Ensemble models such as **Random Forest** and **XGBoost** were trained and optimized based on **Recall, Precision, and F1-Score** metrics instead of accuracy.

## 🛠️ Technologies Used
* **Language:** Python
* **Data Processing & Analysis:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn, XGBoost, Imbalanced-Learn
* **Visualization:** Matplotlib, Seaborn

## 📂 Dataset
The dataset used was obtained from [Kaggle - Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud/data). 
Due to security reasons, original features are hidden via PCA (V1, V2, ... V28). Only `Time` and `Amount` features are left in their original form.

*(Note: The dataset is not uploaded to this repository due to its size. To run the project, you must download the data and add it to the `data/raw/` folder.)*

## 🚀 Project Steps & Methodology

### 1. Data Preprocessing
* **Scaling:** The `Time` and `Amount` columns were scaled using **RobustScaler** as it is resilient to outliers.
* **Data Splitting:** Data was split into **80% Training** and **20% Test** sets; `stratify=y` was used to ensure the class balance is reflected equally in both sets.
* **Imbalance Solution (SMOTE):** Synthetic data was generated to close the massive gap between "Normal Transaction" and "Fraud" classes in the training set.

### 2. Model Performances
Since the primary goal in financial fraud projects is not to miss fraudsters, the focus was placed on the **Recall** success of the models.

**Random Forest Performance:**
* **Recall:** 0.82 (Caught 82% of fraudsters)
* **Precision:** 0.85 (Gave false alarms for only 14 normal transactions)
* **AUC Score:** 0.974

**XGBoost Performance (Winner):**
* **Recall:** 0.86 (Caught 86% of fraudsters!)
* **Precision:** 0.72
* **AUC Score:** 0.978



## 📊 Important Features (Feature Importance)
Feature importance analysis was performed to take the model's decisions out of being a "Black Box." The model paid the most attention to the **V14, V12, and V4** features while detecting fraud.



## 💡 Conclusion and Business Logic
In real-world banking scenarios, the cost of overlooking a fraud is much higher than the cost of an "Your transaction is suspicious, did you do it?" SMS sent to the customer. For this reason, the **XGBoost model with a higher Recall value (0.86)** was chosen as the most suitable solution for this problem.

---
*Developer: Berkin*
