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
Exploratory data analysis was performed using the training set only.
The analysis included:
- Target class distribution
- Descriptive Statistics
- Feature Histograms
- Correlation Analysis
- Box plots
- Pairwise Relationships
- Skewness and Kurtosis Inspection


### Findings

Multiple size measurements showed strong correlations with the output diagnosis. Features that involved the raidii, perimenters and areas were the strongest features that were able to discriminate between malgnant and benign cases. Additionally, measurements like concavity also displayed strong relationships with malignancy.

The correlation heatmap revelead siginficant multicollinearity. E.g.
- Radius, perimeter and area measurements were related strongly.
- Compactness and concavity measurements also correlated heavily.
- Mean and Worst versions of measurements were also correlated.


The distributions showed the difference in scale between features. As a result, standardisation was implemented to accomodate for scale sensititve models like Logistic Regression.

It is important to note that no single feature was able to perfectly distinguish between malignant and bening tumors.

## Data Preprocessing

No imputation was required, as mentioned above the dataset contained no missing values or any duplicates hence the only preprocessing required was scaling for scale sensitive models.

StandardScaler was used and included within the Logistic Regression and SVC pipeline. This pipeline methodology was implemented to ensure that there was no data leakeage and any scaling parameters that were being learnt were from the relevant training folds during cross-validation.

No extra features were engineerd. The orignal dataset contained engineered measured extracted from images and additional feature engineering would have required substantial domain knowledge which is beyond the scope of this project.

## Model Development

Models were evaluated using the cross-validation technique with 5 folds. The metrics recorded were:
- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC

Recall was treated as the most important metric as it measured the proportion of malignant tumors identified correctly.

### Baseline - Logistic Regression

The baseline Logistic Regression model achieved the strongest overall performance across the untuned models. The out-of-fold confusion matrix achieved

| Outcome | Count |
|---|---:|
| True Negatives | 250 |
| False Positives | 0 |
| False Negatives | 7 |
| True Positives | 141|

The model was able to correctly identify 95.3% of malignant cases while producing no false positive predicitions.

### Support Vector Classifier

The untuned SVC also achieved a strong performance but did perform slightly worse than the Logistic Regression baseline.

It included a total of 11 errors with:
- 3 false positives
- 8 false negatives

The untuned SVC missed a malignant case that the Logistic Regression baseline didn't.


### Random Forest Classifier

The Random Forest model achieved perfect training scores but significnalty weaker validation performances. This indicated strong overfitting and this was evident through observing the confusion matrix which contained 12 false positives and 12 false negatives i.e. a total of 24 errors.

As a result, Random Forest was not selected for further tuning

## Untuned Model Comparison


| Model | Accuracy | Precision | Recall | F1-score | ROC-AUC|
|---|---|---|---|---|---|
| Logistic Regression | 0.982 | 1.000 | 0.953 | 0.976 | 0.993
| Support Vector Classifier | 0.972 | 0.979 | 0.946 | 0.961 | 0.993
| Random Forest  | 0.940 | 0.926 | 0.918 | 0.919 | 0.983

Logistic Regression achieved the highest validation accuracy, precision, recall and F1-score. Hence why it was selected for hyperparameter tuning.





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
