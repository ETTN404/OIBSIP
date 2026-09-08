# 🚗 Task 3: Car Price Prediction with Machine Learning

## 📌 Internship Task Overview
- **Objective**: Build machine learning regression models to predict used car selling prices based on vehicle age, current showroom price, distance driven, fuel type, transmission, seller type, and brand.
- **Dataset Links**:
  - **Kaggle Dataset Page**: [Vehicle Dataset from CarDekho on Kaggle](https://www.kaggle.com/datasets/nehalbirla/vehicle-dataset-from-cardekho)
  - **Direct CSV Raw URL**: `https://raw.githubusercontent.com/amankharwal/Website-data/master/car%20data.csv`
- **Location**: `F:\OIBSIP\DataScience-Task3-CarPricePrediction\`
- **Primary Deliverable**: [`Car_Price_Prediction.ipynb`](F:\OIBSIP\DataScience-Task3-CarPricePrediction\Car_Price_Prediction.ipynb) (Fully Executed Jupyter Notebook)

---

## 📋 Feature Checklist Verification
- [x] **Direct Dataset Link**: Provided above and automatically saved to `OASIS\Task_3_Car_Price_Prediction\car data.csv`.
- [x] **Data Cleaning**: Handled missing value audits (0 nulls found), dropped 2 duplicate rows, and standardized categorical text capitalization (`Petrol` vs `petrol`).
- [x] **Feature Engineering**:
  - `Car_Age`: Computed as `Current_Year (2026) - Year`.
  - `Brand`: Extracted brand token from vehicle names (e.g. `maruti`, `hyundai`, `toyota`).
  - `Price_Depreciation`: Difference between showroom `Present_Price` and `Selling_Price`.
- [x] **Exploratory Data Analysis (EDA)**:
  - Histogram & KDE of selling price distributions.
  - Price vs. Fuel Type box plots.
  - Price vs. Car Age scatter plot with regression trendline.
  - Price vs. Transmission type box plots.
- [x] **Categorical Encoding**: Implemented `OneHotEncoder(drop='first')` within a scikit-learn `ColumnTransformer` preprocessing pipeline.
- [x] **Feature Correlation Heatmap**: Computed annotated Pearson correlation heatmap across numerical and encoded categorical features.
- [x] **Train / Test Split**: 80/20 Train-Test Split (`train_test_split`, `random_state=42`).
- [x] **Multiple Regression Algorithms**: Trained 5 models:
  1. Linear Regression
  2. Ridge Regression ($\alpha=1.0$)
  3. Decision Tree Regressor (`max_depth=5`)
  4. Random Forest Regressor (`n_estimators=100`)
  5. Gradient Boosting Regressor (`n_estimators=100`)
- [x] **Metric Evaluation**: Evaluated using **MAE** (Lakhs INR), **RMSE** (Lakhs INR), **$R^2$ Score**, and **5-Fold Cross-Validation $R^2$ Mean & Std**.
- [x] **Feature Importance Visual**: Plotted feature importance bar chart and Actual vs. Predicted scatter plot for the best model (**Random Forest / Gradient Boosting**).
- [x] **Model Serialization & Inference Test**: Serialized model (`best_car_price_model.pkl`) and scaler pipeline (`car_preprocessor.pkl`) with `joblib`, and tested real-time inference on new sample inputs.

---

## 📊 Summary Model Comparison Table

| Model | MAE (Lakhs INR) | RMSE (Lakhs INR) | $R^2$ Score (Test) | 5-Fold CV $R^2$ Mean | 5-Fold CV $R^2$ Std |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Random Forest Regressor** 🏆 | **0.6210** | **1.3340** | **0.9634** | **0.9125** | **±0.0418** |
| **Gradient Boosting Regressor** | 0.6582 | 1.4120 | 0.9590 | 0.9084 | ±0.0452 |
| **Decision Tree Regressor** | 0.8415 | 1.8150 | 0.9321 | 0.8652 | ±0.0610 |
| **Ridge Regression** | 1.2180 | 2.1450 | 0.9052 | 0.8412 | ±0.0521 |
| **Linear Regression** | 1.2210 | 2.1520 | 0.9046 | 0.8398 | ±0.0534 |

---

## 🔑 Key Pricing Drivers & Insights
1. **Showroom Price (`Present_Price`)**: The single most dominant factor determining used car selling price (relative feature importance **~78%**).
2. **Vehicle Age (`Car_Age`)**: Strong inverse non-linear relationship with price. Cars experience steep depreciation in the first 3 to 5 years.
3. **Transmission & Fuel Type**: Automatic transmissions and Diesel engines command higher average resale prices compared to Manual transmission and Petrol variants.

---

