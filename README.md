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

I wanted to use all the data provided, excluding the Loan Status (as that is the information I want to predict) to train the model to predict the Loan Status. The original Dataset had a total of 75,036 loans that were classified as Healthy and 2500 classified as High-Risk. I first split the datsaset into training and testing datasets, then usedthe original data and Logistic Regression modeling to train and test. After that, the next step was to see if we can make the model more accurate. 

The models accuracy for predicting Healthy loans was very high, but the accurancy fell off when it came to predicting High-Risk loans. I believe this is due to the lack of examples of High-Risk loans with there being only 2500 compared to the 75,036 Healthy loan examples. Therefore, I used RandomOverSampler to create a new model that would randomly add duplicates of the High_Risk loans to replace some of the Healthy examples. This resulted in a total of 56,271 examples of both Healthy and High-Risk Loans.




## Results

### Machine Learning Model 1 (Original Data):
  * 75,036 Healthy | 2500 High-Risk
  * Accuracy: 95%
  * Precision:
       * Healthy: 99%
       * High-Risk: 91%
  * Recall:
       * Healthy: 100%
       * 85%



### Machine Learning Model 2 (RandomOversampler):
  * 56,271Healthy | 56,271 High-Risk
  * Accuracy: 99%
  * Precision:
       * Healthy: 99%
       * High-Risk: 99%
  * Recall:
       * Healthy: 100%
       * 84%



## Summary

The Original Data model does an excellent job of prediciting the Healthy Loan labels with a 99% precision (only 1% false positive) and 100% recall (0% false negative). However, the model does not do as well with predicting High-Risk Loans with 91% precision (9% false positive) and 85% recall (15% false positive). This means that there are 9% of high-risk loans are being predicted as healthy and 15% of healthy loans are being predicted as high-risk.

By using RandomOversampler to randomly duplicate some of the values of high-risk loans to increase the amount in the test set, we have greatly increaded the precision of predicting high-risk loans. Now both healthy and high-risk loans have a 99% precision score. Despite the recall of high-risk loans going down to 84%, this model is still much better because it is safer to predict a healthy loan as high-risk than it is to predict a high-risk loan as healthy.

Therfore, I would recommend using the RandomOversampler model due to its precision in predicting High-Risk loans. In the world of loans, high-risk loans are the main thing to watch out for. Accurately prediciting a Healthy loan is beneficial, however falsing prediciting a High-Risk loan as healthy can be detrimental. 
