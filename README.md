# Stay-In-School-India

📊 Education Dropout Rate Analysis & Forecasting (2019–2025)
📌 Overview
This project analyzes India’s school dropout rates using UDISE+ (Unified District Information System for Education Plus) data from 2019 to 2024, builds a Power BI dashboard for insights, and uses Machine Learning (XGBoost) to forecast 2025 dropout rates.

The project helps education policymakers, NGOs, and government planners to:

Track multi-year dropout trends,
Measure gender disparities,
Identify high-risk states,
Forecast dropout rates for proactive interventions

📂 Dataset
Source: UDISE+ – Ministry of Education, Govt. of India
Years Covered: 2019–2024
Key Columns:
State,
Level (Primary / Upper Primary / Secondary),
Gender,
Academic Year,
Dropout Rate (%),

🛠 Data Cleaning & Preparation (Power BI Power Query)
Steps Performed:
Loaded Raw Dataset into Power BI Power Query.
Filtered Relevant Years → kept only 2020–21 & 2023–24 for improvement analysis.
Created Two Copies:

Copy 1 → 2020–21 (renamed dropout column → DropoutRate_2020_21)

Copy 2 → 2023–24 (renamed dropout column → DropoutRate_2023_24)

Merged Tables on State + Level.

Calculated Improvement:

Improvement = DropoutRate_2020_21 – DropoutRate_2023_24
Positive → improvement

Negative → worsening trend

Removed Unnecessary Columns (academic year, blanks, metadata).

📈 Dashboard Insights (Power BI)
Key metrics from the report
:

Overall Avg Dropout Rate: 7.06%

Highest Dropout Rate: 32.6% (Meghalaya, Secondary)

Lowest Dropout Rate: 0.10% (Andaman & Nicobar Islands, Gujarat)

Gender Gap: Boys 7.6% vs Girls 6.5%

Top 3 High Dropout States: Meghalaya, Bihar, Assam

Top 3 States with Improvement: Tripura, Nagaland, Mizoram

Top 3 States with Worsening: Bihar, Ladakh, Rajasthan

Visuals Included:

Dropout rate by academic year

Dropout rate by level & gender

State-wise dropout trends

Improvement/Worsening charts

🤖 Machine Learning (Python)
Objective:
Predict 2025 dropout rates using historical trends & lag features.

Steps:
Feature Engineering:

Created Lag1 & Lag2 dropout rates per State × Level × Gender

Encoded categorical variables

Train-Test Split: Train ≤ 2022, validate on 2023

Models Tried:

Baseline: RandomForestRegressor (R² = 0.714)

Advanced: XGBoostRegressor (R² improved to 0.705 after tuning)

Best Parameters:

{'subsample': 1.0, 'n_estimators': 200, 'max_depth': 4,
 'learning_rate': 0.1, 'gamma': 0.2, 'colsample_bytree': 0.6}
Evaluation Metrics:

MAE = 2.57

RMSE = 3.67

R² = 0.705

Prediction:

Generated 2025 predictions for all combinations

Saved as predicted_dropout_rate_2025.csv

🔮 Forecast for 2025
Used tuned XGBoost model

Predictions available by:

State

Gender

Level

Integrated results into Power BI for visualization.

📊 Tools & Technologies
Data Cleaning: Power BI Power Query

Dashboarding: Power BI Desktop

Machine Learning: Python (pandas, scikit-learn, xgboost)

Visualization: Matplotlib, Power BI
