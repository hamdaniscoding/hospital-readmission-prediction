# Hospital Readmission Prediction

## Overview

This project predicts whether a patient will be readmitted to the hospital within 30 days using Logistic Regression with L2 regularization.

## Problem Statement

Hospital readmissions can increase healthcare costs and resource utilization. The objective of this project is to use patient information to predict the risk of 30-day hospital readmission.

## Dataset

The project uses the Diabetes 130-US Hospitals dataset.

The main dataset used is:

`diabetic_data.csv`

The target variable is `readmitted`.

For this project:

- `<30` → 1 (readmitted within 30 days)
- Other values → 0 (not readmitted within 30 days)

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

The following steps were performed:

1. Loaded the dataset
2. Explored the data
3. Handled missing values
4. Selected relevant features
5. Encoded categorical variables
6. Scaled numerical variables
7. Split the data into training and testing sets
8. Trained a Logistic Regression model
9. Used L2 regularization
10. Generated predictions
11. Evaluated the model using multiple metrics
12. Analyzed false positives and false negatives

## Model

Logistic Regression with L2 regularization was used for classification.

The dataset was divided into:

- 80% Training data
- 20% Testing data

A stratified split with `random_state=42` was used.

## Evaluation

The model was evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- Confusion Matrix
- ROC Curve

ROC-AUC was used as the primary evaluation metric.

The actual results are available in the Jupyter Notebook.

## False Positives and False Negatives

### False Negative

A false negative occurs when the model predicts that a patient will not be readmitted, but the patient is actually readmitted within 30 days.

In a healthcare setting, this could mean that a high-risk patient does not receive additional follow-up or preventive intervention.

### False Positive

A false positive occurs when the model predicts that a patient will be readmitted, but the patient is not readmitted.

This could lead to unnecessary monitoring, follow-up, or use of healthcare resources.

The appropriate balance between false positives and false negatives depends on the clinical context and the cost of the intervention.

## Limitations

- The dataset may not contain all relevant clinical information.
- The model is a relatively simple baseline model.
- Dataset characteristics may not represent all hospitals or patient populations.
- The model should not be used directly for clinical decision-making without further validation.

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Google Colab
- Jupyter Notebook

## Files

```text
hospital-readmission-prediction/
│
├── hospital_readmission_prediction.ipynb
├── README.md
└── requirements.txt
