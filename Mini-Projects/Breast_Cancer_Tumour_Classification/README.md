# Breast Cancer Tumour Classification with Classical Machine Learning

## Overview

This project developed and evaluated classical machine learning models to classify breast tumors as either malignant or bening using numerical characteristics. The data used was from the sklearn dataset library. 

The primary objective was to prioritise identification of malignant tumors. In the context of cancers, a malignant tumor being misdiagnosed as a bening, a false negative in this project, is a more serious error than a bening tumor being misdiagnosed as a malignant tumor i.e. a false positive.

The classification models that were compared:
 - Logistic Regression
 - Support Vector Classifier
 - Random Forest Classifier

A recall focused Logistic Regression model was selected as the final model after cross-validation and hyperparameture tuning.

The final model achieved fantastic results:

| Metric | Test Score |
|---|---:|
| Accuracy | 0.982 |
| Precision | 0.984 |
| Recall | 0.969 |
| F1-score | 0.976 |
| ROC-AUC | 0.998 |

The final model correctly classified 168 out of the 171 unseen test set samples.

## Objectives

The main objectives of the project were:
- Explore statistical characteristics of the dataset.
- Identify important relationships between input features and the output (tumor classification).
- Establish a baseline with a Logistic Regression Model.
- Compare multiple machine learning classification models.
- Tune the strongest model, prioritising the recall metric.
- Evaluated the tuned model on unseen test set.

## Dataset

The data (available through scikit-learn) contained:
- 569 observatiopns
- 30 input features (numerical)
- 1 output target (binary)
- 357 benign cases
- 212 malignant cases
- no missing values
- no duplicated observations

The numerical features included measurements related to:
- radius
- texture
- perimeter
- area
- smoothness
- symmetry
- compactnes
- concavity

Each measurement was reported with mean and worst- value variants

The original target column was remapped for ease in model evaluation:
- 1: Malignant (Orignally 0)
- 0: Bening (Originall 1)

The remapping allowed for the malignant (the more serious) class to be treated as the positive class.

## Train and Test Split

The data was split into two sets (Train and Test). This was done by using the stratification process to perserve the original proportion of the dataset and replicate it in the sub sets (Train and Test)

This was done before Exploratory Data Analysis (EDA) and as a result any EDA, model comparison and hyperparameter tuning was carried out on the training set. This ensured the test set remained unseen untill the final model had been chosen.

## Exploratory Data Analysis


## Findings
## Data Preprocessing
## Model Development
### Baseline - Logistic Regression
### Support Vector Classifier
### Random Forest Classifier
## Untuned Model Comparison
## Hyperparameter Tuning
### Effect of Tuning
## Final Test Set Evaluation
### Final Metrics
### Final Confusion Matrixz
### Model Interpretation
## Conclusion
## Limitations
## Future Work
## Tech Stack
## Machine Learning Methods

## Parting Notes:

This project had the purpose of me learning and implementing machine learning classification techniques in the context of cancer diagnosis. The notebook attached to this repo serves as both notes, writeup and ofcourse execution.
