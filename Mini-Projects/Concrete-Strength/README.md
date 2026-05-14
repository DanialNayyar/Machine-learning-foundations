# Concrete Compressive Strengvth Predicition

## Project Overview

This project aimed to predict the compressive strength of concrete using machine learning regression models. The dataset contained concrete mix design variables including cement, fly ash, blast furnace slag, water, superplasticizer, coarse aggregate, fine aggregate and curing age in days.
The goal was to build an end-to-end machine learning workflow, starting from data inspection and exploratory data analysis to feature engineering, model development and comparison, hyperparameter tuning, final test evaluation, model interpretation and finally a Power Bi dashboard. 

## Key Result

**Best model:** Tuned HistGradientBoostingRegressor  
**Final test RMSE:** 4.38 MPa  
**Final test MAE:** 2.76 MPa  
**Relative MAE:** 7.75%


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

Permutation importance was used to determine the most important features for the final model. `Age` was the most important feature followed by water based ratios and binder related features. This agrees with the understanding of concrete engineering. Compressive strength is strongly affected by curing age and the balance between water and cement materials. 
The top features after `Age` are `Water-Cement Ratio`, `Water-Binder Content Ratio`, and `Cement` as well.

## Error Analysis
The final model's residuals were analused on the test set.

Some key observations:
- The actual vs predicted plot displayed a clear diagonal trend.
- Residuals were generally centered around zero, i.e. the model's predictions were not severely overpredicted or underpredicted.
- The largest errors wre inspected using important features i.e. age, water-binder ratio, water-cement ratio etc.

## Scenario Analysis
Scenario analysis was performed to inspect how the final model might respond to chages in key input variables. Two scenarios were tested:
1. Variation of curing age whilst the typical concrete mix is held constant.
2. Variation of water content (recalculatig water-cement and water-binder content ratios)

The behaviour seen agreed with concrete mix theory. The model predicted that that compressive strength increases with curing age and decreases with water content increasing.

The plots do not constitute as direct proof but rather can be interpreted as model behaviour.

## Power BI Dashboard

A Power BI dashboard was developed to visualise the final results. The dashboard includes:
- Model performance overview
- Final test metrics
- Training vs Cross-Validation error comparison
- Actual vs Predicted Values
- Residual Error Distribution
- Largest Prediction Errors
- Feature Importance
- Scenario Analysis

### Page 1: Model Performance Overview

![Model Performance Overview](Dashboard/Page%201%20-%20Model%20Performance.png)

### Page 2: Error Analysis

![Error Analysis](Dashboard/Page%202%20-%20Error%20Analysis.png)

### Page 3: Feature Importance and Scenario Analysis

![Feature Importance and Scenario Analysis](dashboard/page_3.png)


## Limitations
This project did have some limitations that more than likely affected the final outcome.
Some limitations include:
- Small size of the dataset.
- Identical mix designs have different target values, likely an experimental variation.
- Feature engineering was performed before the final split. However, it should be noted that the engineered features were domain-informed and carried out row-wise.
- The final model was evaluated on a test (held-out).
- Scenario analysis showed model behaviour not proof.

## Future Work
- Testing additional ensemble methods such XGBoost or LightGBM.
- Streamlit app for interactive predictions.
- Creating a stricter end-to-end pipeline where feature engineering is carried out within a custom transformer.
- Compare model predictions against empirical concrete strength equations.

## Tools/Stack Used
- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-Learn
- SciPy
- Power Bi
- Google Colab

## Repo Structure


## Author
Danial Nayyar
