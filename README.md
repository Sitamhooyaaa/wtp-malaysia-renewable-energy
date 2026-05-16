# 🌱 Predicting Willingness to Pay for Renewable Energy in Malaysia

![Python](https://img.shields.io/badge/Python-3.x-blue) ![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange) ![Status](https://img.shields.io/badge/Status-Completed-green)

## 📌 Project Overview

This project predicts whether a Malaysian consumer is willing to pay an additional charge on their electricity bill to support renewable energy initiatives. Using survey data collected from three East Coast Malaysian states, I built and evaluated multiple machine learning classification models to identify key drivers of willingness to pay (WTP).

This project is directly relevant to Malaysia's national energy transition agenda and provides actionable insights for energy policymakers and utility companies like **Tenaga Nasional Berhad (TNB)**.

---

## 🎯 Problem Statement

Malaysia is transitioning toward renewable energy. A critical challenge is understanding **who is willing to pay more** for clean energy and **what drives that willingness**. This model helps answer:

> *"Given a Malaysian consumer's demographic, financial, and knowledge profile — will they agree to pay an additional charge for renewable energy?"*

---

## 📊 Dataset

| Property | Details |
|----------|---------|
| Source | Survey data (Kaggle) |
| States Covered | Terengganu, Pahang, Kelantan |
| Total Respondents | 713 |
| Original Features | 60 columns |
| Final Features Used | 29 columns |
| Target Variable | `wtp` (YES = 1, NO = 0) |
| Class Distribution | 60% YES, 40% NO |

---

## 🔧 Tech Stack

- **Python 3.x**
- **Pandas** — data manipulation
- **NumPy** — numerical operations
- **Matplotlib & Seaborn** — data visualization
- **Scikit-learn** — ML models and evaluation
- **XGBoost** — gradient boosting model
- **Jupyter Notebook** — development environment

---

## 🚀 Project Workflow

```
Raw Data (713 rows, 60 columns)
        ↓
Data Cleaning
• Dropped 7 columns with >40% missing values
• Filled income columns with 0 (domain logic)
• Filled demographic columns with median
• Removed data leakage columns (model outputs)
        ↓
Exploratory Data Analysis (EDA)
• Distribution analysis
• WTP by state, gender, knowledge, income
• Correlation heatmap
        ↓
Feature Engineering & Encoding
• Ordinal encoding for confidence levels
• Label encoding for categorical variables
• Preserved original dataframe integrity
        ↓
Model Training & Evaluation
• Logistic Regression (baseline)
• Random Forest
• XGBoost
        ↓
Model Training & Evaluation
- Logistic Regression (baseline)
- Random Forest
- XGBoost
        ↓
Model Optimization
- Cross Validation (5-Fold) — true accuracy: 66.62%
- Hyperparameter Tuning (GridSearchCV)
- L1 Regularization — eliminated 15 irrelevant features
        ↓
Final Model Selection & Insights
```

---

## 📈 EDA Key Findings

### 1. Confidence is Everything
Respondents who were **confident** in their WTP decision were significantly more likely to say YES. This was the strongest pattern found in the entire dataset.

### 2. Knowledge Helps But Isn't Enough
Awareness of the Renewable Energy Fund showed weak positive correlation with WTP. Both informed and uninformed respondents showed similar YES/NO ratios — suggesting awareness campaigns alone are insufficient.

### 3. Income is Less Important Than Expected
Median income for YES and NO groups was nearly identical (~RM2,000). WTP is not purely driven by financial capacity.

### 4. Electricity Bill Amount Doesn't Predict WTP
Respondents with high electricity bills were not more likely to say YES — suggesting price sensitivity exists even among high consumers.

---

## 🤖 Model Results

| Logistic Regression (baseline) | 74.83% | 0.74 | 0.56 | 0.75 | 0.87 |
| Random Forest | 74.83% | 0.77 | 0.53 | 0.74 | 0.90 |
| XGBoost | 69.23% | 0.63 | 0.56 | 0.73 | 0.78 |
| **Optimized Logistic Regression** | **77.62%** | 0.86 | 0.53 | 0.75 | 0.94 |

### ✅ Final Model: Optimized Logistic Regression (77.62%)
- Hyperparameter tuning via GridSearchCV improved accuracy by +2.79%
- Best parameters: C=0.1, penalty=L1, solver=liblinear
- L1 regularization automatically eliminated 15 irrelevant features
- Selected for superior explainability — critical for policy-making contexts
- Cross validation confirmed true accuracy: 66.62% (5-fold average)
---

## 🔑 Top Predictive Features

| Feature | Coefficient | Direction |
|---------|------------|-----------|
| Confidence in WTP | +0.686 | ↑ More likely YES |
| Knowledge of RE Fund | +0.247 | ↑ More likely YES |
| State | -0.233 | ↓ Varies by state |
| Elderly household members | -0.180 | ↓ More likely NO |
| Income quartile | +0.147 | ↑ More likely YES |

---

## 💡 Business Recommendations for TNB

1. **Build public confidence first** — The biggest lever is trust in renewable energy programs, not just awareness. Communication strategies should emphasize reliability, transparency, and outcomes.

2. **State-specific strategies needed** — WTP varies by state. Targeted regional campaigns will be more effective than a one-size-fits-all approach.

3. **Target working-age households** — Elderly households show higher resistance. Programs should be designed with younger household decision-makers in mind.

4. **Don't assume high bill payers will pay more** — Price sensitivity exists across all electricity consumption levels. Pricing strategy should be carefully structured.

5. **Knowledge campaigns are necessary but not sufficient** — Pair awareness with confidence-building initiatives such as pilot programs, testimonials, and visible renewable energy outcomes.

---

## 📁 Repository Structure

```
wtp-malaysia-renewable-energy/
│
├── wtp_malaysia_analysis.ipynb   # Main Jupyter Notebook
├── wtp-data.xlsx                 # Dataset
├── wtp-variable.csv              # Variable descriptions
└── README.md                     # Project documentation
```

---

## 👤 Author

**Muhammad Aqil Bin Mohd Nor**
- 📧 m.aqilmn@gmail.com
- 💼 [LinkedIn](http://www.linkedin.com/in/muhammad-aqil-mn)
- 🐙 [GitHub](https://github.com/Sitamhooyaaa)

---

## 📝 Notes

This is Project 1 of my Data Analytics → AI/ML Engineering learning journey. Built as part of an intensive self-directed study program focused on becoming a professional ML Engineer.
