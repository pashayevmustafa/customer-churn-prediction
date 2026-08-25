# Customer Churn Prediction

End-to-end machine learning solution for predicting customer churn and supporting proactive customer retention strategies.

---

## Business Problem

Customer churn is a major challenge for subscription-based businesses.

The goal of this project is to identify customers with a high probability of churn so that businesses can proactively target them with retention campaigns.

The solution can support:

- Customer retention
- Targeted marketing campaigns
- Customer segmentation
- Risk-based prioritization
- Proactive customer engagement

---

## Project Objective

Build a machine learning classification model that predicts whether a customer is likely to churn.

The project focuses not only on predictive performance but also on:

- Model interpretability
- Risk-oriented evaluation
- Threshold optimization
- Business decision-making

---

## Dataset

The project uses the Telco Customer Churn dataset.

Dataset characteristics:

- 7,043 customers
- Demographic information
- Customer account information
- Services used
- Contract information
- Payment information
- Customer tenure

Target variable:

`Churn`

| Value | Meaning |
|---|---|
| 0 | Customer stays |
| 1 | Customer churns |

---

# Machine Learning Pipeline

```text
Raw Data
    |
    v
Exploratory Data Analysis
    |
    v
Data Cleaning
    |
    v
Feature Engineering
    |
    v
Train/Test Split
    |
    v
Preprocessing
    |
    v
Baseline Models
    |
    v
Hyperparameter Optimization
    |
    v
Final CatBoost Model
    |
    v
Model Evaluation
    |
    v
Threshold Optimization
    |
    v
SHAP Explainability

Models

The following models were evaluated:

Logistic Regression
Random Forest
XGBoost
LightGBM
CatBoost

CatBoost was selected as the final model and optimized using Optuna.

Hyperparameter Optimization

Optuna was used to optimize the CatBoost model.

Optimized parameters included:

Number of iterations
Tree depth
Learning rate
L2 regularization
Random strength
Border count

The optimization objective was to maximize ROC-AUC.

Model Evaluation

The model was evaluated using both machine learning and risk-modeling metrics:

ROC-AUC
Gini
Recall
Precision
F1 Score
KS Statistic

Gini was calculated as:

Gini = 2 × ROC-AUC − 1
Final Model Performance
Metric	Score
ROC-AUC	0.840
Gini	0.679
Recall	0.805
Precision	0.494
F1 Score	0.612

The model demonstrates good ranking performance while maintaining high recall for identifying customers at risk of churn.

Threshold Optimization

The default classification threshold of 0.5 was evaluated against alternative thresholds.

The objective was to find a threshold that provides a practical balance between:

Recall
Precision
F1 Score

This allows the model to be adapted to different business strategies.

For example, a retention campaign may prioritize recall because missing a customer who is likely to churn can be more costly than contacting an additional low-risk customer.

Risk-Oriented Evaluation

The project also includes KS analysis to evaluate the separation between churned and retained customers.

This approach is particularly relevant for financial and risk analytics applications.

Model Explainability

SHAP was used to understand how individual features influence model predictions.

The analysis provides:

Global feature importance
Direction and magnitude of feature impact
Individual customer explanations
SHAP Summary

Feature Importance

ROC Curve

Confusion Matrix

Threshold Optimization

KS Curve

Key Business Insights

The analysis demonstrates that customer churn is strongly influenced by factors such as:

Contract type
Customer tenure
Payment method
Monthly charges
Internet service
Customer service and account characteristics

Customers with shorter contracts and certain payment/service combinations tend to demonstrate higher churn risk.

These insights can be used to prioritize retention campaigns.

Technologies
Python
Pandas
NumPy
Scikit-learn
CatBoost
XGBoost
LightGBM
Optuna
SHAP
Matplotlib
Seaborn
SciPy
Joblib
Project Structure
customer-churn-prediction/

├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   ├── 01_EDA.ipynb
│   ├── 02_Preprocessing.ipynb
│   ├── 03_Modeling.ipynb
│   ├── 04_Optuna_Tuning.ipynb
│   ├── 05_Model_Evaluation.ipynb
│   └── 06_SHAP_Analysis.ipynb
│
├── models/
│
├── images/
│
├── requirements.txt
└── README.md
Future Improvements

Possible extensions include:

Cross-validation
MLflow experiment tracking
FastAPI deployment
Docker containerization
Automated retraining pipeline
Customer-level churn scoring API
Integration with CRM and retention systems
Author
Mustafa Pashayev

Risk Data Analyst | Python | SQL | Power BI | Machine Learning | Risk Analytics

[LINKEDIN](https://www.linkedin.com/in/mustafa-pashayev-859059293/)

