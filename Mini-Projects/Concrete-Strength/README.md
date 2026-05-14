# Concrete Compressive Strengvth Predicition

## Project Overview

This project aimed to predict the compressive strength of concrete using machine learning regression models. The dataset contained concrete mix design variables including cement, fly ash, blast furnace slag, water, superplasticizer, coarse aggregate, fine aggregate and curing age in days.
The goal was to build an end-to-end machine learning workflow, starting from data inspection and exploratory data analysis to feature engineering, model development and comparison, hyperparameter tuning, final test evaluation, model interpretation and finally a Power Bi dashboard. 

## Dataset
The dataset was taken from the UCI Machine Learning Repository:
(https://archive.ics.uci.edu/dataset/165/concrete+compressive+strength)

The target variable is "compressive strength" measured in MPa.
The input variables include:
- Cement
- Blast Furnace Slag
- Fly Ash
- Water
- Superplasticizer
- Coarse Aggregate
- Fine Aggregate
- Age

The material properties have units of kg/m³ and age represents the curing age and has units of days.

## Project Workflow

The workflow followed is described below:
1. Data Loading and Initial Inspection
2. Checks for duplicate and missing values
3. Exploratory Data Analysis
4. Feature Engineering
5.  Stratified Train/Test Split
6.  Baseline Model Development
7.  Linear and Regularlised Regression Models
8.  Tree-Based M.L. Models
9.  Hyperparameter Tuning
10. Final Test Set Evaluation
11. Feature Importance Analysis
12. Error and Residual Analysis
13. Confidence Interval Calculation
14. Scenario and Sensitivity Analysis
15. Power BI dashboard


## Feature Engineering

Multiple domain-informed features were created to improve predictive performance.
- Binder Content = Cement + Blast Furnace Slag + Fly Ash
- Water-Cement Ration = Water / Cement
- Water-Binder Content Ratio = Water / Binder Content
- Log Age = log(Age) (for linear models)
- Superplasticizer Present = 1 if present, 0 otherwise
- Superplasticzer-Binder Content Ratio = Superplasticier/Binder-Content

These features were developed due to influence of curing age, binder content, and ratio of water to cement material.

## Models Tested

- Mean Baseline
- Median Baseline
- Age-Based Baselines
- Linear Regression
- Ridge Regression
- SGD Regression
- Decision Tree Regressor
- HistGradientBoostingRegressor
- Tuned HistGradientBoostingRegressor

## Results
The best performing model was the Tuned HistGradientBoostingRegressor, with the final test set performance recorded belowL

| Metric | Value |
|---|---:|
| Test RMSE | 4.38 MPa |
| Test MAE | 2.76 MPa |
| Test MSE | 19.19 MPa² |
| Relative RMSE | 12.31% |
| Relative MAE | 7.75% |
| 95% RMSE Confidence Interval | [3.37, 5.20] MPa |

The final model significantly outperformed the baseline models and the linear regression models. The MAE indicated that, on average, the models predictions were 2.76 MPa away from the true compressive strength.


## Model Interpretation


## Error Analysis

## Scenario Analysis

## Power BI Dashboard



## Limitations


## Future Work

## Tools/Stack Used

## Repo Structure


## Author
