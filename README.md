# Customer-Churn-Prediction-Risk-Segmentation-Dashboard

# Overview

Customer churn has a direct impact on recurring revenue in subscription-based businesses.
This project builds an end-to-end customer churn prediction system and translates model outputs into actionable risk segments, visualized through a Power BI dashboard for business decision-making.

The focus is not only on model performance, but on interpretability, business relevance, and deployable insights.

# Dataset

Source: Telco Customer Churn Dataset (Kaggle)

Type: Customer-level subscription data

Features include:

Demographics

Contract and billing information

Service usage

Target variable: Churn (Yes / No)

# Project Structure
Customer-Churn/
│
├── data/
│   ├── raw/
│   │   └── Telco-Customer-Churn.csv
│   └── processed/
│       └── churn_scored_customers.csv
│
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_preprocessing.ipynb
│   ├── 03_modeling.ipynb
│
├── dashboard/
│   └── churn_dashboard.pbix
│
├── src/
│   ├── preprocessing.py
│   ├── modeling.py
│   └── evaluation.py
│
└── README.md


Each notebook is fully independent and reproducible.

# Methodology
1. Exploratory Data Analysis (EDA)

Identified class imbalance in churn

Observed strong churn patterns related to:

Customer tenure

Contract type

Monthly charges

Detected and handled data quality issues in TotalCharges

2. Data Preprocessing

Dropped non-informative identifiers

Encoded categorical variables

Scaled numerical features

Used stratified train–test split to preserve churn distribution

3. Modeling

Logistic Regression

Used as a baseline for interpretability

Coefficient analysis to explain churn drivers

Random Forest

Captured non-linear relationships

Improved recall and ROC–AUC

Threshold tuning

Optimized for recall to reduce missed churners

4. Risk Segmentation

Predicted churn probabilities were converted into business-friendly risk tiers:

High Risk

Medium Risk

Low Risk

This enables targeted retention strategies rather than generic actions.

# Evaluation Metrics

Recall (Churn = 1)

ROC–AUC

Confusion Matrix

Accuracy was not used as the primary metric due to class imbalance.

# Power BI Dashboard

The Power BI dashboard consumes the processed, scored dataset and provides:

Executive overview of churn and risk levels

Key churn drivers (contract type, tenure, charges)

Customer risk segmentation for targeted action

All modeling logic is handled in Python; Power BI is used strictly for visualization and communication.

# Key Insights

Customers with short tenure and month-to-month contracts have the highest churn risk

Higher monthly charges correlate with increased churn probability

Risk-based segmentation allows focused retention efforts with controlled cost

Business Recommendation

Target high-risk customers identified by the model with proactive retention strategies (discounts, contract upgrades, service improvements) to reduce churn while minimizing unnecessary outreach.

# Tools & Technologies

Python (Pandas, NumPy, Scikit-learn)

Jupyter Notebook

Power BI Desktop

Git / GitHub

Future Improvements

SHAP-based model explainability

Uplift modeling for retention strategy evaluation

Deployment as an interactive web application

Author

Vedashri
MSc Data Science
