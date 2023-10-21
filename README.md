# Mushroom Classification Project

## Table of Contents

- [Problem Statement](#problem-statement)
- [Dataset Description](#dataset-description)
- [Logistic Regression Model](#logistic-regression-model)
- [Feature Selection and Model Diagnostics](#feature-selection-and-model-diagnostics)
- [Predictions and Confusion Tables](#predictions-and-confusion-tables)
- [Data Visualization](#data-visualization)
- [ROC Curve and AUC](#roc-curve-and-auc)
- [Cross-Validation](#cross-validation)
- [Probit and Identity Links](#probit-and-identity-links)
- [Model Comparison](#model-comparison)
- [Contingency Table Analysis](#contingency-table-analysis)
- [Report](#report)

## Problem Statement

In this project, we aim to build a classification model to predict whether mushrooms are edible or poisonous based on various features. This is a binary classification problem.

## Dataset Description

The dataset contains information about 8,124 mushrooms with 23 different attributes, including cap shape, cap surface, odor, gill color, and more. The target variable is "class," which indicates whether a mushroom is edible ("e") or poisonous ("p").

## Logistic Regression Model

A logistic regression model was fitted to the training data using all available features. The model yielded an accuracy of 96.35% on the test data and 96.96% on the train data. The area under the ROC curve (AUC) for the logistic regression model was 0.9408 on the test set.

## Feature Selection and Model Diagnostics

Predictor variables in the model exhibit high multicollinearity. Specifically, the variables "Gill spacing," "Gill size," "Stalk root," "Stalk surface above the ring," and "Ring type" have VIF values greater than 5, indicating a strong correlation among these variables. This high multicollinearity can affect the model's interpretability.   

## Predictions and Confusion Tables

- Using the selected model, we made predictions. The accuracy of 95.69% for the test data and 96.03% for the training data suggest that the model is able to accurately predict the class labels for the mushrooms based on the selected features in the new model. Similar to the previous model.
- These confusion matrices provide a detailed breakdown of the model's performance at different cutoff values, allowing you to analyze the trade-off between true positives and true negatives based on your specific requirements. At pi_0 = 0.5, the confusion matrix shows a balanced classification result, with a relatively equal number of edible and poisonous mushrooms correctly classified.
-  Among these cutoff values, the best cutoff value was found to be 0.5, which achieved an accuracy of 95.69%. This means that when using 0.5 as the cutoff point, the model correctly classified 95.69% of the mushrooms as edible or poisonous.

## Data Visualization

We will visualize the data and the model's performance through various plots and graphs.

## ROC Curve and AUC

- (ROC) curve:
  <img width="761" alt="roc curve" src="https://github.com/zeealhelfie/CategoricalDataAnalysis/assets/60905286/a16213d0-4c76-4d48-b0cb-45c279eeef9c">

- The AUC of the model is 0.99, indicating good performance in distinguishing between edible and poisonous mushrooms.
- The best cutoff point for classification is 0.5, which maximizes the trade-off between sensitivity and specificity. The sensitivity of the model is 0.94. This means that it correctly identifies 94% of the positive cases, while the specificity is 0.97, indicating that it correctly identifies 97% of the negative cases.


## Cross-Validation

- LOOCV Error: The LOOCV error, with a value of 0.5398, indicates that on average, approximately 53.98% of the observations were misclassified when each data point was left out once and the model was trained on the rest. This relatively high error rate suggests that the model may be overfitting the data, as it struggles to generalize to unseen examples.
- K-fold Cross-Validation Errors: The k-fold cross-validation, with an average error rate of 0.9746, demonstrates that, on average, approximately 97.46% of the observations were misclassified across the 10 iterations. This high error rate across different folds is consistent with the LOOCV result and further suggests potential overfitting.

## Probit and Identity Links

- Probit Model Training Accuracy: 0.9135252 
- Probit Model Test Accuracy: 0.8990769 
- Identity Model Training Accuracy: 0.9458378 
- Identity Model Test Accuracy: 0.944 

Based on these results, it appears that the identity model performs better than the probit model both in terms of training accuracy and test accuracy. However, the performance difference between the two models is relatively small.

## Model Comparison

- Probit Model ROC-AUC (Train): 0.9158774 
- Probit Model ROC-AUC (Test): 0.9018522 
- Identity Model ROC-AUC (Train): 0.945271 
- Identity Model ROC-AUC (Test): 0.9436352 

Based on the accuracy ROC-AUC and the consistent performance across training and test sets, the identity model appears to perform better than the probit model for this particular data.

Comparing the three models, logistic regression achieved the highest accuracy and AUC on the test set. However, all models performed relatively well in predicting the mushroom class, with accuracies above 94%. The differences in performance among the models were minimal.

## Contingency Table Analysis

Contingency Tables:

- Logistic Classes: For the logistic regression model, a contingency table was constructed, showing a sum of 1625 observations. Among these, 842 observations were classified as '0' (e.g., Edible) and 783 as '1' (e.g., Poisonous).
- Probit Classes: In the case of the probit regression model, the contingency table displayed a sum of 1625 observations, with 842 categorized as '0' and 783 as '1'.
- Identity Classes: For the identity regression model, the contingency table presented 1625 observations, with 842 classified as '0' and 783 as '1'.

Statistical Tests:

- Chi-Squared Test (Yates' Continuity Correction): Chi-squared tests were conducted for all three models to examine the association between the model-predicted classes and actual class labels. The p-values for the chi-squared tests are as follows:
Logistic Model: p-value = 0.06091
Probit Model: p-value < 2.2e-16
Identity Model: p-value < 2.2e-16
These p-values suggest that the association between model-predicted classes and actual classes is statistically significant for both the probit and identity models but not significant for the logistic model.
- Fisher's Exact Test: Fisher's exact tests were conducted to evaluate the odds ratio for independence between model-predicted classes and actual classes. The p-values and odds ratio estimates are as follows:
- Logistic Model: p-value = 0.0258, odds ratio = Inf
Probit Model: p-value < 2.2e-16, odds ratio = 211.9047
Identity Model: p-value < 2.2e-16, odds ratio = 285.8168
The Fisher's exact test further supports the significance of the association for the probit and identity models, with odds ratios significantly different from 1, indicating a strong relationship between the predicted and actual classes. However, the logistic model yielded an odds ratio of Inf, suggesting an infinite association, which may require further investigation.

In conclusion, the Contingency Table Analysis reveals that the probit and identity models are significantly associated with the actual class labels, while the logistic model's association is not statistically significant. These results indicate that the probit and identity models may be better at predicting class labels based on the provided data, with the identity model showing the strongest association. It is essential to choose a model that not only fits well but also has a significant association with the actual outcomes, as demonstrated by these statistical tests.

## Report

In conclusion, the logistic regression model demonstrated the highest accuracy and AUC in predicting the class of mushrooms as edible or poisonous. However, all three models showed good predictive performance. The chi-squared and Fisher's exact tests indicated a significant association between the predicted and actual classes, additionally validating the models' performance.


