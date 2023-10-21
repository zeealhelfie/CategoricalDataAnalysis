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

- We will plot the Receiver Operating Characteristic (ROC) curve.
- Calculate the Area Under the Curve (AUC) to evaluate the model's discriminative ability.
- Find the best cut-off point for classification based on the ROC curve.

## Cross-Validation

- We will perform Leave-One-Out Cross-Validation (LOOCV) and k-fold cross-validation to assess the model's robustness.

## Probit and Identity Links

- We will try using the probit and identity links to model the data.
- Compare the performance of these models to determine which works better for this dataset.

## Model Comparison

We will compare the logistic regression, probit regression, and identity regression models to identify the most effective model for this data.

## Contingency Table Analysis

If applicable, we will apply methods for contingency tables to analyze grouped data, such as Chi-squared tests, G^2 tests, and more.

## Report



