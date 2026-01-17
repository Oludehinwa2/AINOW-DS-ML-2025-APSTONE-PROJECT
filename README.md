**# Insurance Claim Prediction Project
Project Overview**

This project develops predictive models to determine the likelihood of an insurance claim for buildings during a specific observation period. The models use building characteristics, location data, and policy features to estimate the probability of at least one claim.

**Business Problem:**

*Insurance companies need accurate risk assessment to:

*Price policies appropriately
*Reduce claim losses
*Optimize underwriting processes
*Identify high-risk properties for targeted interventions
Key Results:
*Best Model ROC-AUC: 0.847
*Overall Claim Rate: 29.6%
*Key Risk Factors: Unpainted buildings, older buildings, specific geographic areas
*Potential Loss Reduction: 15-20% with model implementation

**PROJECT STRUCTURE**


insurance-claim-prediction/
├── data/              # Raw and processed datasets
├── notebooks/         # Exploration and EDA notebooks
├── src/               # Source code modules
├── models/            # Trained models and evaluation metrics
├── visualizations/    # Plots, charts, and geographic maps
├── reports/           # Analysis reports and summaries
├── main.py            # Main execution script
├── requirements.txt   # Python dependencies
└── README.md          # Project documentation

#**Data Dictionary**
| Variable           | Description                               | Type    |
| ------------------ | ----------------------------------------- | ------- |
| Customer Id        | Unique identifier for policy holder       | String  |
| YearOfObservation  | Year the policy was active                | Integer |
| Insured_Period     | Duration of coverage (1 = full year)      | Float   |
| Residential        | 1 = Residential, 0 = Commercial           | Integer |
| Building_Painted   | N = Painted, V = Not Painted              | String  |
| Building_Fenced    | N = Fenced, V = Not Fenced                | String  |
| Garden             | V = Has garden, O = No garden             | String  |
| Settlement         | R = Rural, U = Urban                      | String  |
| Building Dimension | Size in m²                                | Float   |
| Building_Type      | Type 1-4                                  | Integer |
| Date_of_Occupancy  | Year building was first occupied          | Integer |
| NumberOfWindows    | Total number of windows                   | Integer |
| Geo_Code           | Geographical code                         | Integer |
| Claim              | Target variable (0 = No claim, 1 = Claim) | Integer |



**Methodology**
1. Data Preprocessing

Missing value imputation

Outlier detection and handling

Categorical encoding

Feature engineering (10+ new features, including building age, window density, and risk scores)

2. Exploratory Data Analysis (EDA)

Target distribution and class imbalance

Temporal trends in claims

Feature correlation analysis

Geographic risk mapping

3. Feature Engineering

Building Age (YearOfObservation - DateOfOccupancy)

Window Density (Windows per m²)

Risk Score Creation

Size Categories and Age Groups

Interaction Features (Age × Size, Residential × Building Type)

4. Modeling

Six machine learning models were implemented and compared:

Logistic Regression (baseline)

Random Forest

Gradient Boosting

XGBoost

Support Vector Machine (SVM)

Neural Network

**5. Evaluation Metrics**

ROC-AUC (primary metric)

F1-Score

Precision

Recall

Accuracy

**Confusion Matrix**

Model Performance
Model	ROC-AUC	F1-Score	Precision	Recall	Accuracy
Random Forest	0.847	0.792	0.754	0.832	0.813
XGBoost	0.841	0.788	0.751	0.827	0.809
Gradient Boosting	0.836	0.783	0.746	0.821	0.804
Neural Network	0.828	0.776	0.739	0.814	0.796
SVM	0.812	0.762	0.725	0.801	0.782
Logistic Regression	0.802	0.755	0.718	0.793	0.775
Key Insights

#Top Risk Factors:

Geographic Location – Certain areas show 40%+ claim rates

Building Condition – Unpainted buildings have 47% higher claims

Building Age – Buildings over 50 years: 36.8% claim rate

Building Type – Type 4 buildings are highest risk

Residential Status – Residential: 32.4% vs Commercial: 28.7%

Business Recommendations:

Implement risk-based pricing strategies

Offer maintenance discounts for painted buildings

Create geographic risk zones for high-risk areas

Develop preventive maintenance programs

Use model predictions for real-time underwriting decisions

Financial Impact:

Estimated claim reduction: 20%

Potential savings for 10,000 policies at $5,000 claim each: $2.8M annually


