# Credit_Risk_Analysis

## Overview
The objective of this analysis is to find the best model to predict what customers are at high risk of not paying back loans. The credit card credit dataset is from Lending Club, a peer-to-peer lending services company. 

A model that accurately predicts high risk clients even though it may identify certain low risk clients as high risk is best for financial institutions. Therefore, recall (sensitivity) is a more important metric due to the high risk of losing money. Low precision might result is losing customers (false positives), this might need to be evaluated further by understanding the cost of loosing a customer vs giving credit to a customer who may not pay back the loan.

High risk are those clients who are late in their payments from 16 to 120 days, have defaulted or are in the grace period.

For this analysis we will define the best model leaning more towards a high recall rather than hig precision. Since the data is imbalanced (a low number of data points for high risk), imblanaced-learn and scikit-learn libraries to build and evaluate the models using resampling and logistic regression. For oversampling the data, RandomOverSampler (Naive Random) and SMOTE algortihms; for undersampling Cluster Centroids; and a combinational approach over-and undersampling with SMOTEEN. Then, RandomForestClasifier and EasyEnsembleClasifier, two machine learning models that reduce bias, will be compared including Logistic Regression to predict credit risk.

## Results
### Naive Random Oversampling
- Balanced accuracy score: 64.4%
- High risk Precision: 1%
- High risk Recall: 69%

![Naive](https://github.com/Jimena-QM/Credit_Risk_Analysis/blob/main/images/1_naive_random.JPG)


### SMOTE
- Balanced accuracy score: 66.3%
- High risk Precision: 1%
- High risk Recall: 63%

![Smote](https://github.com/Jimena-QM/Credit_Risk_Analysis/blob/main/images/2_smote.JPG)


### Cluster Centroids
- Balanced accuracy score: 54.4%
- High risk Precision: 1%
- High risk Recall: 69%

![Centroids](https://github.com/Jimena-QM/Credit_Risk_Analysis/blob/main/images/3_centroids.JPG)


### SMOTEENN
- Balanced accuracy score: 63.9%
- High risk Precision: 1%
- High risk Recall: 70%

![Smoteenn](https://github.com/Jimena-QM/Credit_Risk_Analysis/blob/main/images/4_smoteenn.JPG)

### Balanced Random Forest
- Balanced accuracy score: 78.9%
- High risk Precision: 3%
- High risk Recall: 70%

![Random_Forest](https://github.com/Jimena-QM/Credit_Risk_Analysis/blob/main/images/5_random_forest.JPG)

### Easy Ensemble AdaBoost
Balanced accuracy score: 93.2%
High risk Precision: 9%
High risk Recall: 92%
    AdaBoost has the best scores of all models tested. Highest accuracy, precision and recall. 

![Adaboost](https://github.com/Jimena-QM/Credit_Risk_Analysis/blob/main/images/6_adaboost.JPG)

## Summary

For the conclusion of this analysis it is assumed that there is a higher cost of giving credit to a high risk client than to loose a client who is low risk but was identified as high risk. Given this, recall is our best measure of success for the model. 

Adaboost is the best model with a 92% recall which means the model will identify the greater number of high risk clients and may identify certain low risk clients as high risk. For the company to reduce the nombre of wrongly predicted low risk clients they can add an additional layer of validation.
Given the low precision level of 9%, it may be best to research other machine learning models that can have a better f1 score (harmonic mean between precision and recall).
