# East-West Airlines Neural Network and Logistic Regression Project

## Overview
This project involves the application of machine learning techniques to classify East-West Airlines customers based on their likelihood of purchasing a wireless phone service contract from Telcon. The dataset provided by East-West Airlines contains customer information, and the target variable is `Phone_Sale`, which indicates whether a customer purchased the phone service.

The project includes the following steps:
1. Model Estimation
2. Comparison of Model Performance between Logistic regression model and Neural Networks model
3. Case Study Analysis

## Logistic Regression Model Estimation

### Logistic Regression Results
- **Selected Variables:** `Bonus_trans`, `Online_12`, `Any_cc_miles_12mo`

- **Model Performance:**
  - Training AUC: 0.63093
  - Validation AUC: 0.62919
  - Initial Overall Accuracy: 88.16%
  - Initial Sensitivity: 0.42%
  - After Cutoff Adjustment:
    - New Probability Cutoff: 0.12205
    - New Overall Accuracy: 50.75%
    - New Sensitivity: 74.15%

## Neural Network Model Estimation

### Model Parameters
- **Hidden Layer:** 1 hidden layer with 5 nodes
- **Epochs:** 100 epochs
- **Standardization:** Data is standardized before training.

### Neural Network Results
- **Validation AUC:** 0.5041 (indicating poor performance)
- **Comparison with Logistic Regression:** Logistic regression outperforms the neural network model as indicated by steeper slopes in lift charts.

### Neural Network Diagram
The project also includes a diagram representing the structure of the neural network used in this analysis.

### Prediction Example
For a customer with 10 non-flight bonus transactions, 1 online purchase in the past 12 months, and no miles added on any credit card type within the past 12 months, the model predicts the likelihood of purchasing Telcom service as part of the direct mail campaign.

## Comparison

The lift chart for the logistic regression model (Model 1) shows a steeper slope than the lift chart for the neural network model (Model 2) throughout most of the decile range. This means that the logistic regression model is better at identifying the decile groups that are most likely to contain the desired outcome.

## Case Study Analysis

### Summary
The case study demonstrates the steps involved in building a logistic regression model and a neural network model, comparing their performance and refining the model to improve sensitivity and better align with the firm's objectives.

### Files Included
- `EastWestAirlinesNN_HK`: Dataset used for the analysis.
- `Project_Report.pdf`: Detailed report on the logistic regression and neural network model development and results.
