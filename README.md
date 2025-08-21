# fraud-detection-model

---

# Fraud Detection in Financial Transactions

This project analyzes financial transaction data and applies **machine learning models** to detect fraudulent transactions. It combines **Exploratory Data Analysis (EDA)** with **predictive modeling** to uncover fraud patterns and build a classification system.

---

## 📌 Project Overview

Fraud detection is a critical problem for banks, payment gateways, and fintech platforms. This project uses a large transactional dataset to:

* Explore and visualize transaction distributions.
* Identify fraud-prone transaction types.
* Compare flagged vs. actual fraudulent cases.
* Apply **machine learning models** to classify fraud vs. non-fraud transactions.
* Evaluate models using accuracy, precision, recall, and F1-score.

---

## 📂 Dataset

The project uses the dataset **Fraud.csv**. Key features include:

* **step** → unit of time (1 step = 1 hour; total 744 steps = 30 days).
* **type** → transaction type (CASH-IN, CASH-OUT, DEBIT, PAYMENT, TRANSFER).
* **amount** → transaction amount.
* **nameOrig** → sender ID.
* **oldbalanceOrg / newbalanceOrig** → sender’s balance before/after transaction.
* **nameDest** → receiver ID.
* **oldbalanceDest / newbalanceDest** → receiver’s balance before/after transaction.
* **isFraud** → whether the transaction is fraudulent.
* **isFlaggedFraud** → flagged suspicious transactions (e.g., transfers > 200,000).


---

## 🔍 Analysis & Modeling Workflow

### 1. **Exploratory Data Analysis (EDA)**

* Dataset overview: shape, data types, missing values, duplicates.
* Transaction type distribution.
* Fraud detection analysis:

  * Number of fraudulent transactions.
  * Cross-tab between fraud and flagged fraud.
  * Types of fraudulent transactions (**TRANSFER** & **CASH\_OUT**).
  * Min/Max fraudulent transaction amounts.
* Fraudulent balance inconsistencies.

### 2. **Feature Engineering**

* Encoded categorical features (`type`).
* Created new features such as **balance differences**.
* Handled class imbalance with **oversampling/undersampling**.

### 3. **Machine Learning Models**

Models applied include:

* **Logistic Regression**
* **Decision Trees**
* **Random Forests**
* **XGBoost**

### 4. **Model Evaluation**

Evaluated using:

* Accuracy
* Precision
* Recall (important for fraud detection)
* F1-score
* Confusion Matrix

---

## 📊 Key Insights

* Fraud is **rare but highly concentrated** in **TRANSFER** and **CASH\_OUT** types.
* Business rules flag large transactions but fail to capture many fraudulent ones.
* **XGBoost and Random Forest** performed the best, with higher recall compared to simpler models.
* **Recall was prioritized** to minimize false negatives (frauds missed).

---

## 🚀 Work to do

* Deploy the best model as a **REST API** for real-time fraud detection.
* Integrate with **streaming pipelines (Kafka/Spark)** for live monitoring.
* Apply **deep learning models** (LSTM/Autoencoders) for anomaly detection.
* Experiment with **cost-sensitive learning** to handle fraud vs. non-fraud imbalance.

