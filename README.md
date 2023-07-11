# credit-risk-classification

## Overview of the Analysis

The overall goal was to train a machine learning model to accurately predict whether a loan was healthy or high-risk using supervised learning.

### The Dataset Included
* Size of Loan
* Interest Rate
* Borrower's Income
* Debt to Income Ratio
* Number of Accounts
* Derogatory Marks
* Total Debt
* Loan Status (Healthy or High-Risk)

I wanted to use all the data provided, excluding the Loan Status (as that is the information I want to predict) to train the model to predict the Loan Status. The original Dataset had a total of 75,036 loans that were classified as Healthy and 2500 classified as High-Risk. I first split the datsaset into training and testing datasets, then used Logistic Regression modeling to train and test. After that, the next step was to see if we can make the model more accurate. 

The models accuracy for predicting Healthy loans was very high, but the accurancy fell off when it came to predicting High-Risk loans. I believe this is due to the lack of examples of High-Risk loans with there being only 2500 compared to the 75,036 Healthy loan examples. Therefore, I used RandomOverSampler to create a new model that would randomly add duplicates of the High_Risk loans to replace some of the Healthy examples. This resulted in a total of 56,271 examples of both Healthy and High-Risk Loans.

## Results

### Machine Learning Model 1 (LogisticRegression):
  * 75,036 Healthy | 2500 High-Risk
  * Accuracy: 95%
  * Loan        |       Precision        |   Recall
:-------------------------:|:-------------------------:|:-------------------------:
Healthy | 99% | 100%
High-Risk | 91% | 85%



### Machine Learning Model 2 (RandomOverSampler):
  * 56,271Healthy | 56,271 High-Risk
  * Accuracy: 99%
  *  Loan        |       Precision        |   Recall
:-------------------------:|:-------------------------:|:-------------------------:
Healthy | 99% | 100%
High-Risk | 99% | 84%

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.
