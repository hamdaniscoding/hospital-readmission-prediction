# Machine Learning Case Studies

This repository contains two Machine Learning case studies developed as part of academic coursework. The projects demonstrate the application of supervised learning techniques to healthcare and financial transaction problems.

---

# 📌 Case Study 1: Hospital Readmission Prediction

## Overview

The objective of this project is to predict whether a patient will be readmitted to the hospital within 30 days using patient-related information.

The project uses **Logistic Regression with L2 regularization** as the classification algorithm.

## Dataset

The project uses the **Diabetes 130-US Hospitals Dataset**.

Main dataset:

`diabetic_data.csv`

The `readmitted` column is used as the target variable.

The target is converted into a binary classification problem:

- `<30` → `1` (Readmitted within 30 days)
- Other values → `0` (Not readmitted within 30 days)

## Features Used

The model uses a small set of patient-related features:

- Age
- Gender
- Time in hospital
- Number of laboratory procedures
- Number of procedures
- Number of medications
- Number of outpatient visits
- Number of emergency visits
- Number of inpatient visits

## Methodology

The following workflow was used:

1. Load the dataset
2. Explore the dataset
3. Handle missing values
4. Convert the target variable into binary form
5. Select relevant features
6. Encode categorical variables
7. Scale numerical features
8. Split the data into training and testing sets
9. Train Logistic Regression with L2 regularization
10. Generate predictions
11. Evaluate model performance

## Model

**Algorithm:** Logistic Regression

**Regularization:** L2

The dataset is divided into:

- 80% Training Data
- 20% Testing Data

A stratified split with `random_state=42` is used.

## Evaluation

The model is evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC
- Confusion Matrix
- ROC Curve

ROC-AUC is used as the primary evaluation metric.

## False Positives vs False Negatives

### False Negative

A false negative occurs when the model predicts that a patient will **not** be readmitted, but the patient is actually readmitted within 30 days.

In a healthcare setting, this could result in a high-risk patient not receiving additional follow-up or preventive intervention.

### False Positive

A false positive occurs when the model predicts that a patient **will** be readmitted, but the patient is not actually readmitted.

This could lead to unnecessary monitoring, follow-up, and healthcare resource utilization.

The appropriate balance between false positives and false negatives depends on the clinical context and the cost of the intervention.

## Limitations

- The dataset may not contain all relevant clinical information.
- Logistic Regression is a relatively simple baseline model.
- Dataset characteristics may not represent every hospital or patient population.
- The model requires further validation before any real-world clinical application.

> **Note:** This project is intended for educational purposes and should not be used directly for clinical decision-making.

---

# 📌 Case Study 2: Credit Card Fraud Detection

## Overview

The objective of this project is to identify potentially fraudulent credit card transactions using Machine Learning.

The project uses **XGBoost** for classification and **SMOTE** to handle the highly imbalanced nature of fraud detection datasets.

## Dataset

A small **synthetically generated transaction dataset** is used for this project.

The dataset contains legitimate and fraudulent transactions with a strong class imbalance.

The synthetic dataset is generated directly inside the Jupyter Notebook for educational purposes.

## Features Used

The model uses transaction-related features such as:

- Transaction amount
- Transaction hour
- Account age
- Number of previous transactions
- Transactions in the last 24 hours
- Distance from home
- Device changes
- Failed attempts
- International transaction
- New device

## Methodology

The following workflow was used:

1. Generate a synthetic transaction dataset
2. Analyze the class imbalance
3. Separate features and target
4. Split the dataset into training and testing sets
5. Apply SMOTE to the training data
6. Train an XGBoost classifier
7. Generate fraud probabilities
8. Evaluate model performance
9. Tune the classification decision threshold
10. Analyze feature importance

## Model

**Algorithm:** XGBoost

XGBoost is a tree-based gradient boosting algorithm suitable for classification tasks.

## Handling Class Imbalance

Fraudulent transactions usually represent a small percentage of all transactions.

**SMOTE (Synthetic Minority Oversampling Technique)** is applied to the training data to increase the representation of the minority fraud class.

SMOTE is applied only to the training data so that the test set remains representative of unseen transactions.

## Evaluation

The model is evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC
- Confusion Matrix
- ROC Curve

## Decision Threshold Tuning

The default classification threshold of `0.50` is not necessarily optimal for an imbalanced fraud detection problem.

Multiple thresholds are evaluated to examine the relationship between:

- Precision
- Recall
- F1-Score
- False Positives
- False Negatives

The threshold producing the highest F1-score is selected for the final demonstration.

## Feature Importance

XGBoost feature importance scores are used to identify which transaction features contributed most to the model's predictions.

Feature importance indicates the features that were most useful to the trained model. It does not establish a causal relationship.

## False Positives vs False Negatives

### False Positive

A legitimate transaction is incorrectly classified as fraudulent.

Possible consequences include:

- Legitimate transactions being declined
- Additional verification being required
- Customer inconvenience
- Additional fraud-review workload

### False Negative

A fraudulent transaction is incorrectly classified as legitimate.

Possible consequences include:

- Fraudulent transactions going undetected
- Financial losses
- Increased investigation and recovery costs

The appropriate threshold depends on the relative costs of missed fraud and false alarms.

## Limitations

- The dataset is synthetically generated.
- Synthetic transactions do not perfectly represent real-world financial behavior.
- The model has not been validated on real banking transaction data.
- Feature importance does not imply causation.
- Further testing and validation would be required for real-world deployment.

> **Note:** This project is intended for educational purposes and does not represent a real financial fraud detection system.

---

# 🛠️ Technologies Used

Both projects were developed using Python and the following libraries:

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Imbalanced-learn
- Matplotlib
- Seaborn
- Google Colab
- Jupyter Notebook

---

# 📂 Repository Structure

```text
Machine-Learning-Case-Studies/
│
├── Hospital-Readmission-Prediction/
│   └── mle_1.ipynb
│
├── Credit-Card-Fraud-Detection/
│   └── credit_card_fraud_detection.ipynb
│
└── README.md
