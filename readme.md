# 🚨 Fraud Detection Using Machine Learning (XGBoost)

This project implements a **Machine Learning pipeline** to detect fraudulent financial transactions using **XGBoost**.  
It demonstrates an **end-to-end workflow** from data preprocessing to evaluation, with practical recommendations for fraud prevention.  

---

## 📑 Table of Contents
- [📌 Project Overview](#-project-overview)  
- [📂 Dataset Description](#-dataset-description)  
- [⚙️ Data Preprocessing](#️-data-preprocessing)  
- [🔍 Feature Selection](#-feature-selection)  
- [🧠 Model Building](#-model-building)  
- [📊 Evaluation Metrics](#-evaluation-metrics)  
- [💡 Key Insights](#-key-insights)  
- [🛡 Recommendations for Fraud Prevention](#-recommendations-for-fraud-prevention)  
- [📈 Effectiveness Evaluation](#-effectiveness-evaluation)  
- [📦 Requirements](#-requirements)  
- [✍️ Author](#️-author)  

---

## 📌 Project Overview
The goal is to build a **fraud detection model** that identifies suspicious transactions in a financial dataset.  
- Special attention on **imbalanced data**.  
- Focused on **precision & recall**, as fraud detection is **rare but costly**.  

---

## 📂 Dataset Description
**Fields:**  
`step, type, amount, oldbalanceOrg, newbalanceOrig, oldbalanceDest, newbalanceDest, isFraud, isFlaggedFraud`  

- **Dropped:** `nameOrig`, `nameDest` (identifiers)  
- **Target Column:** `isFraud` → (1 = fraud, 0 = genuine)  
- **Class Distribution:** Highly imbalanced (~0.1% fraud)  

---

## ⚙️ Data Preprocessing
- ✅ No missing values  
- ✅ Outliers retained (possible fraud indicators)  
- ✅ Encoded categorical `type` using `LabelEncoder`  
- ✅ Standardized features using `StandardScaler`  
- ✅ Train-test split (80/20)  

---

## 🔍 Feature Selection
**Features Used:**  
`step, type, amount, oldbalanceOrg, newbalanceOrig, oldbalanceDest, newbalanceDest, isFlaggedFraud`  

**Dropped:**  
`nameOrig, nameDest` (irrelevant)  

---

## 🧠 Model Building
- **Algorithm:** `XGBClassifier (XGBoost)`  
- Chosen for handling **imbalanced data & complex feature interactions**  
- Model trained & evaluated with multiple metrics  

---

## 📊 Evaluation Metrics
- **Accuracy:** ~99.8% ⚠️ (misleading for imbalanced data)  
- **Precision (Fraud):** 25%  
- **Recall (Fraud):** 41%  
- **F1-Score (Fraud):** 31%  
- **Visuals:** Confusion Matrix, ROC, PR-Curve  

👉 **Note:** Precision & Recall are more meaningful than accuracy here.  

---

## 💡 Key Insights
- 🔑 Important features: **Transaction Type, Amount, Balance features**  
- 🚩 Fraud concentrated in **large TRANSFER & CASH_OUT transactions**  
- 📉 Model recall is decent but requires improvements for fewer false positives/negatives  

---

## 🛡 Recommendations for Fraud Prevention
- ⚡ **Real-time monitoring** of large/unusual transactions  
- ⛔ **Threshold rules** (block transactions where `amount > balance`)  
- 🔑 **Multi-Factor Authentication (MFA)** for large/first-time transfers  
- 📊 **Behavioral profiling** → user spending patterns  
- 🔄 **Continuous model retraining** with fresh data  
- 🔐 **Secure, real-time analytics infrastructure**  

---

## 📈 Effectiveness Evaluation
- 📊 Track: fraud detection rate, false positives, financial loss  
- 🧪 Use **A/B testing** for fraud prevention measures  
- 🗣 Collect **customer feedback** on usability  
- 🔄 Continuous **dashboard updates & retraining**  

---


## 📦 Requirements
- Python >= 3.7  
- `numpy`, `pandas`, `matplotlib`, `seaborn`  
- `scikit-learn`, `xgboost`  

Install all dependencies via:  
```bash
pip install numpy pandas matplotlib seaborn scikit-learn xgboost
```
---
👤Shivam Parihari<br>
Thanks for visiting❤️

