# 💳 Credit Card Fraud Detection

### Link to download dataset: https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

### A Machine Learning project to detect fraudulent credit card transactions using Under-Sampling and Logistic Regression.

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat&logo=python)
![Library](https://img.shields.io/badge/Library-Scikit--Learn-orange?style=flat&logo=scikit-learn)
![Status](https://img.shields.io/badge/Status-Completed-green)

## 📌 Project Overview
Fraud detection is the classic "Needle in a Haystack" problem. In this dataset, only **0.17%** of transactions are fraudulent. Standard models often fail here because they simply guess "Legitimate" for everything and achieve high accuracy but zero utility.

I built a model that focuses on **Recall** (catching the thieves) by balancing the dataset and applying feature scaling.

## 📂 Dataset
The dataset is obtained from [Kaggle: Credit Card Fraud Detection](https://www.kaggle.com/mlg-ulb/creditcardfraud).

*   **Transactions:** 284,807
*   **Frauds:** 492
*   **Features:** Time, Amount, and V1-V28 (Anonymized features resulting from PCA transformation).
<img width="1026" height="585" alt="Transaction amount by class" src="https://github.com/user-attachments/assets/86da4eb5-e31e-4e65-adb4-d658254b4d00" />

## ⚙️ Data Preprocessing
1.  **Scaling:** The `Amount` column was highly skewed (some transactions were $0, others $25,000). I applied `StandardScaler` to normalize it.
2.  **Addressing Class Imbalance:**
    *   I used **Under-Sampling** to create a balanced sub-dataset.
    *   Selected all 492 Fraud cases.
    *   Randomly selected 492 Non-Fraud cases.
    *   Result: A 50/50 split dataset (984 rows total) for fair training.

## 🤖 Model Performance
**Algorithm:** Logistic Regression

**Results on Test Set:**
*   **Accuracy:** ~94%
*   **Recall (Fraud):** ~94% (The model successfully identified 93 out of ~98 fraud cases in the test batch).

**Algorithm:** Random Forest Classifier

**Results on Test Set:**
*   **Accuracy:** ~93%
*   **Recall (Fraud):** ~92%

**Confusion Matrix:**
<img width="505" height="470" alt="Confusion matrix for Random Forest Classifier" src="https://github.com/user-attachments/assets/7594749e-f088-4920-8c4a-510535ad621a" />
<img width="505" height="470" alt="Confusion matrix for Logistic Regression" src="https://github.com/user-attachments/assets/71efd834-3a71-425e-924a-727b6cf890ad" />

The model prioritizes **minimizing False Negatives** (missing a fraud), as this is the most costly error for a bank.

## 🚀 How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/JusChillin96/Credit-Card-Fraud-detection.git
