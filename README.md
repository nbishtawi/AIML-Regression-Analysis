# Used Car Regression Analysis Project

## Overview
This project applies regression analysis to explore the relationship between predictors and rental prices. The notebook demonstrates data cleaning, feature engineering, hypothesis testing, regression modeling, and evaluation using multiple performance metrics.

---

## Dataset
- File: `used_cars_data.csv`
- Variables: mix of categorical and numerical predictors
- Target: `Price`
- Preprocessing: unit parsing, missing value imputation, categorical encoding

---

## Methodology
1) Data Preparation  
- Cleaned and standardized features  
- Converted categorical variables to numerical via encoding  
- Train/test split applied  

2) Modeling  
- Two linear regression models tested on different feature sets (Set 1 vs. Set 2)  

3) Evaluation Metrics  
- RMSE (Root Mean Squared Error)  
- MAE (Mean Absolute Error)  
- R² and Adjusted R²  
- MAPE (Mean Absolute Percentage Error)  

---

## Feature Sets
- Target in both models: `Price_log`
- Set 1 (df2 → X): applied log transforms to a first list of skewed numeric columns (`dist_cols`), then one-hot encoded categoricals; features are all columns except `Price_log` → `X = df2.drop(['Price_log'], axis=1)`
- Set 2 (df4 → X2): applied an alternate set of log transforms (`dist_cols2`), then one-hot encoded categoricals; features are all columns except `Price_log` → `X2 = df4.drop(['Price_log'], axis=1)`
- In short: same algorithm (linear regression), different feature engineering choices; Set 2 uses a slightly different set of log-transformed numeric variables.

---

## Results

### Model 1 (Set 1)
- Train: RMSE = 0.1575, MAE = 0.1186, R² = 0.9545, Adj. R² = 0.9494, MAPE = 5.90%  
- Test:  RMSE = 0.2435, MAE = 0.1486, R² = 0.8855, Adj. R² = 0.8746, MAPE = 7.46%

### Model 2 (Set 2)
- Train: RMSE = 0.1561, MAE = 0.1191, R² = 0.9546, Adj. R² = 0.9495, MAPE = 5.64%  
- Test:  RMSE = 0.2481, MAE = 0.1515, R² = 0.8804, Adj. R² = 0.8685, MAPE = 7.61%

Observations: both models explain ~95% of variance on the training set and ~88% on the test set. MAPE indicates average prediction error of ~6–8%. Set 2 is very close to Set 1 but slightly worse on the test set.

---

## Repository Structure
AIML-Regression-Analysis/
├── Regression Analysis Project.ipynb # Main notebook with code and results
├── used_cars_data.csv # Dataset
└── README.md # Project documentation

