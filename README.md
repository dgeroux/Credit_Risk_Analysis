# Credit_Risk_Analysis

## Overview
Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Therefore, it's necessary to employ different techniques to train and evaluate models with unbalanced classes. I'll be using imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, I'll oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. Then, I’ll use a combinatorial approach of over- and undersampling using the SMOTEENN algorithm. Next, I’ll compare two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. I will then evaluate the performance of these models and make a written recommendation on whether they should be used to predict credit risk.

## Results

The following definitions are paramount to the understanding of the following screenshots:

**Balanced accuracy score** - The balanced_accuracy_score function computes the balanced accuracy, which avoids inflated performance estimates on imbalanced datasets. The best value is 1 and the worst value is 0

**Precision** - The precision is intuitively the ability of the classifier not to label as positive a sample that is negative. The best value is 1 and the worst value is 0.

**Recall** - The recall is intuitively the ability of the classifier to find all the positive samples. The best value is 1 and the worst value is 0.

### Random Oversampling 
![image](https://github.com/dgeroux/Credit_Risk_Analysis/blob/main/Resources/random_oversampling.png)

**Balanced accuracy score** - 0.64

**Precision** - high_risk (0.01) and low_risk (1.00)

**Recall** - high_risk (0.61) and low_risk (0.66)
_______________________________________________________________________________________________
### SMOTE Oversampling 
![image](https://github.com/dgeroux/Credit_Risk_Analysis/blob/main/Resources/SMOTE_oversampling.png)

**Balanced accuracy score** - 0.65

**Precision** - high_risk (0.01) and low_risk (1.00)

**Recall** - high_risk (0.66) and low_risk (0.64)
_______________________________________________________________________________________________
### Cluster Undersampling 
![image](https://github.com/dgeroux/Credit_Risk_Analysis/blob/main/Resources/cluster_undersampler.png)

**Balanced accuracy score** - 0.51

**Precision** - high_risk (0.01) and low_risk (1.00)

**Recall** - high_risk (0.59) and low_risk (0.44)
_______________________________________________________________________________________________
### SMOTEENN Sampler 
![image](https://github.com/dgeroux/Credit_Risk_Analysis/blob/main/Resources/SMOTEENN_sampler.png)

**Balanced accuracy score** - 0.65

**Precision** - high_risk (0.01) and low_risk (1.00)

**Recall** - high_risk (0.72) and low_risk (0.58)
_______________________________________________________________________________________________
### BRFC Sampler 
![image](https://github.com/dgeroux/Credit_Risk_Analysis/blob/main/Resources/BRFC_sampler.png)

**Balanced accuracy score** - 0.76

**Precision** - high_risk (0.03) and low_risk (1.00)

**Recall** - high_risk (0.63) and low_risk (0.89)
_______________________________________________________________________________________________
### EEAC Sampler 
![image](https://github.com/dgeroux/Credit_Risk_Analysis/blob/main/Resources/EEAC_sampler.png)

**Balanced accuracy score** - 0.93

**Precision** - high_risk (0.08) and low_risk (1.00)

**Recall** - high_risk (0.91) and low_risk (0.94)
_______________________________________________________________________________________________
## Summary
The Easy Ensemble AdaBoost Classifier model produced the most dependable predicitions with the following scores:

**Balanced accuracy score** - 0.93

This score indicates that this models predicitons are accurate ~93% of the time.

**Precision** - high_risk (0.08) and low_risk (1.00)

High_risk precision score of 0.08 indicates that this model will NOT label a high risk borrower as a low risk borrower 8% of the time.
Low_risk precision score of 1.00 indicates that this model will NOT label a low risk borrower as a high risk borrower 100% of the time.

**Recall** - high_risk (0.91) and low_risk (0.94)

High_risk recall score of 0.91 indicates that this model will predict all the high risk borrowers 91% of the time.
Low_risk recall score of 0.94 indicates that this model will predict all the low risk borrowers 94% of the tiem.

These scores are quite impressive and satifactory enough to recommend when conducting credit risk analysis on borrowers. 
