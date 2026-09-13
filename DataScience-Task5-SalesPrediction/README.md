# 📊 Task 5: Sales Prediction Using Python & Machine Learning

## 📌 Internship Task Overview
- **Objective**: Build machine learning regression models to predict product sales based on advertising budget spend across TV, Radio, and Newspaper channels.
- **Location**: `F:\OIBSIP\DataScience-Task5-SalesPrediction\`
- **Primary Deliverable**: `F:\OIBSIP\DataScience-Task5-SalesPrediction\Task_5_Sales_Prediction.ipynb` (Fully Executed Jupyter Notebook)

---

## 📋 Feature Checklist Verification
- [x] **Dataset Sourcing & Loading**: Loaded classic Advertising.csv dataset (200 records: TV, Radio, Newspaper, Sales).
- [x] **Data Inspection & EDA**: Verified shape ( \\times 4$), data types, missing value audit (0 nulls), descriptive statistics, and generated pairwise scatter matrix (sns.pairplot).
- [x] **Individual Channel Scatter Plots**: Created individual scatter plots with fitted linear regression trendlines (sns.regplot) for Sales vs. TV, Sales vs. Radio, and Sales vs. Newspaper.
- [x] **Correlation Heatmap**: Computed Pearson correlation heatmap visualizing correlations ({TV, Sales} = 0.782$, {Radio, Sales} = 0.576$, {Newspaper, Sales} = 0.228$).
- [x] **Train / Test Split**: 80/20 Split (	rain_test_split, 
andom_state=42).
- [x] **Regression Algorithms Trained**:
  1. Baseline Linear Regression
  2. Polynomial Regression (Degree=2 interaction features + Linear Regression)
  3. Random Forest Regressor (
_estimators=100)
  4. Decision Tree Regressor (max_depth=4)
- [x] **Metrics Evaluated**: MAE, RMSE, ^2$ Score, and 5-Fold Cross-Validation ^2$ Mean & Std.
- [x] **Residual Plot Analysis**: Plotted Residuals ({true} - y_{pred}$) vs Predicted Sales and Residual Histogram/KDE normality check to confirm homoscedasticity.
- [x] **Channel Impact Interpretation**: Interpreted linear regression coefficients and Random Forest relative feature importances:
  - **TV Spend** is the primary driver of overall sales volume (relative feature importance **~63% - 82%**).
  - **Radio Spend** yields the highest marginal return per dollar spent ($\\beta = +0.189$).
  - **Newspaper Spend** has near-zero net predictive impact ($\\beta = +0.003$) when TV and Radio spend are controlled for.
- [x] **Model Serialization & Live Inference**: Saved best model (est_sales_model.pkl) with joblib and tested real-time sales estimation on sample advertising budgets.

---

## 📊 Summary Model Performance Comparison

| Model | MAE (1000s units) | RMSE (1000s units) | ^2$ Score (Test) | 5-Fold CV ^2$ Mean | 5-Fold CV ^2$ Std |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Polynomial Regression (Deg 2)** 🏆 | **0.5182** | **0.6841** | **0.9835** | **0.9712** | **±0.0115** |
| **Random Forest Regressor** | 0.6215 | 0.8240 | 0.9761 | 0.9654 | ±0.0142 |
| **Decision Tree Regressor** | 0.9120 | 1.2150 | 0.9480 | 0.9210 | ±0.0210 |
| **Linear Regression (Baseline)** | 1.4608 | 1.7815 | 0.8994 | 0.8872 | ±0.0245 |

---
