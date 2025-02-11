# Credit Card Fraud Transaction Detection System 🚀

## 📌 Overview

This repository contains the implementation of a **Credit Card Fraud Detection System** using **Machine Learning techniques** to identify fraudulent transactions. The project leverages **data mining, feature engineering, and classification algorithms** to enhance fraud detection accuracy. The dataset, provided by **Vesta Corp. via Kaggle**, includes both **transactional** and **identity** information, requiring advanced preprocessing techniques.

## 🔍 Problem Statement

Financial fraud is a persistent challenge in digital transactions. This project focuses on:

- Evaluating the impact of **data preprocessing, PCA-based feature selection, and class balancing (SMOTE, weight balancing)**
- Implementing and comparing **Logistic Regression, XGBoost, and LightGBM** models to detect fraudulent transactions
- Assessing model performance using **accuracy, precision, recall, F1-score, and confusion matrices** to optimize fraud detection strategies

## 📊 Dataset

The dataset consists of two parts: **Transaction** and **Identity**, joined via `TransactionID`.

- **Transaction Dataset** (~507k samples)  
  - Features: `TransactionDT`, `TransactionAMT`, `ProductCD`, `card1-card6`, `addr`, `dist`, `emaildomain`, `C1-C14`, `D1-D15`, `M1-M9`, `Vxxx` (total: 392 features)

- **Identity Dataset** (~144k samples)  
  - Features: `DeviceType`, `DeviceInfo`, `id01-id38` (total: 40 features)

## 🛠️ Methodology

### **1️⃣ Data Preprocessing**
- **Scaling Numerical Features**: Min-max normalization to standardize values  
- **Handling Missing Data**: Removing features with 80%+ missing values and applying mean imputation  
- **Encoding Categorical Features**: Converting categorical values for ML compatibility  

### **2️⃣ Feature Selection**
- **Principal Component Analysis (PCA)** applied to reduce dimensionality and redundancy  
- **Correlation Analysis** used to retain essential transaction features  

### **3️⃣ Handling Class Imbalance**
- **SMOTE (Synthetic Minority Over-sampling Technique)** to balance fraudulent and non-fraudulent transactions  
- **Weight Balancing** within **XGBoost** and **LightGBM** to improve fraud detection  

### **4️⃣ Model Training & Evaluation**
Three models were trained and evaluated under different balancing techniques:

| Model | No Balancing | Weight Balanced | SMOTE Balanced |
|--------|------------|----------------|---------------|
| **Logistic Regression** | ✅ | ❌ | ✅ |
| **XGBoost** | ✅ | ✅ | ✅ |
| **LightGBM** | ✅ | ✅ | ✅ |

### **5️⃣ Evaluation Metrics**
- **Accuracy Score**
- **Confusion Matrix**
- **Precision, Recall, and F1-Score**
- **Frequent Misclassification Analysis**

## 🏆 Key Findings

- **LightGBM emerged as the top performer**, excelling with **weight balancing** for fraud detection.
- **PCA-based feature selection** helped **reduce redundancy**, improving computational efficiency.
- **Weight balancing outperformed SMOTE** in enhancing precision-recall tradeoffs.
- **Higher recall is prioritized** to flag more fraudulent transactions while maintaining fair precision.
