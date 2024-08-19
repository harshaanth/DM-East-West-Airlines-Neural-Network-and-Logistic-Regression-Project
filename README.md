# East-West Airlines Neural Network and Logistic Regression Project

## Overview
This project involves the application of machine learning techniques to classify East-West Airlines customers based on their likelihood of purchasing a wireless phone service contract from Telcon. The dataset provided by East-West Airlines contains customer information, and the target variable is `Phone_Sale`, which indicates whether a customer purchased the phone service.

The project includes the following steps:
1. Logistic Regression Model Estimation
2. Neural Network Model Estimation
3. Comparison of Model Performance
4. Case Study Analysis

## 1. Logistic Regression Model Estimation

### Model Estimation Process
- **Weights Initialization:** Weights (θ) and biases (w) are initialized to random values between -0.05 and +0.05.
- **Forward Pass:** Calculate the output of each layer using the sigmoid activation function.
  - Output Layer 1: 
    \[
    \text{output}_4 = \frac{1}{1 + e^{-(\theta_4 + w_{14}x_1 + w_{24}x_2 + w_{34}x_3)}}
    \]
  - Output Layer 2:
    \[
    \text{output}_5 = \frac{1}{1 + e^{-(\theta_5 + w_{15}x_1 + w_{25}x_2 + w_{35}x_3)}}
    \]
  - Second Hidden Layer:
    \[
    \text{output}_6 = \frac{1}{1 + e^{-(\theta_6 + w_{46}\text{output}_4 + w_{56}\text{output}_5)}}
    \]
  - Output Layer:
    \[
    \text{output}_7 = \frac{1}{1 + e^{-(\theta_7 + w_{67}\text{output}_6)}}
    \]
- **Error Calculation:**
  \[
  \text{error} = \text{output}_7(1 - \text{output}_7)(y - \text{output}_7)
  \]
- **Weights Update:** Use error to update all weights and biases.
  \[
  \theta_{\text{new}_j} = \theta_{\text{old}_j} + \lambda \times \text{error}
  \]
  \[
  w_{\text{new}_{ij}} = w_{\text{old}_{ij}} + \lambda \times \text{error}
  \]
- **Training Iteration:** Repeat the above steps for all records in the dataset, completing one epoch for the model.

### Logistic Regression Results
- **Selected Variables:** `Bonus_trans`, `Online_12`, `Any_cc_miles_12mo`
- **Regression Model Equation:**
  \[
  \text{Logit(Phone_sale=1)} = -2.5062 + 0.0296 \times \text{Bonus_trans} + 0.16 \times \text{Online_12} + 0.4974 \times \text{Any_cc_miles_12mo}
  \]
  \[
  \text{Probability (Phone_sale=1)} = \frac{1}{1 + e^{-(-2.5062 + 0.0296 \times \text{Bonus_trans} + 0.16 \times \text{Online_12} + 0.4974 \times \text{Any_cc_miles_12mo})}}
  \]

- **Model Performance:**
  - Training AUC: 0.63093
  - Validation AUC: 0.62919
  - Initial Overall Accuracy: 88.16%
  - Initial Sensitivity: 0.42%
  - After Cutoff Adjustment:
    - New Probability Cutoff: 0.12205
    - New Overall Accuracy: 50.75%
    - New Sensitivity: 74.15%

## 2. Neural Network Model Estimation

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

## 3. Case Study Analysis

### Summary
The case study demonstrates the steps involved in building a logistic regression model and a neural network model, comparing their performance and refining the model to improve sensitivity and better align with the firm's objectives.

### Files Included
- `EastWestAirlinesNN.xls`: Dataset used for the analysis.
- `Final_Report.pdf`: Detailed report on the logistic regression and neural network model development and results.
