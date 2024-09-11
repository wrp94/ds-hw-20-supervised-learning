# Module 20 Report

## Overview of the Analysis

The purpose of this analysis is to detect if a supervised classifier can be used to detect credit risk and whether a loan will be risky. The features used in this analysis are:

* loan size
* loan interest rate
* borrower income
* debt to income ratio
* number of accounts
* derogatory marks
* total debt
* loan status

The target variable used in this analysis is `loan_status` and indicates if a loan is risky or not. A value of `0` indicates that the loan is healthy and a value of `1` indicates that the loan is risky. The counts of `0` and `1` are shown in the table below:

| loan_status | count |
| ----------- | ----- |
| 0           | 75036    |
| 1           | 2500     |

Because of the imbalance, so I stratified the data by the loan status when splitting the scaled data. I also used a standard scaler to make the features comparable.

I then used a logistic regression model to predict the loan status. The results were promising, but I followed it up with an ADA Boost Classifier which outperformed the logistic regression model slightly.

## Results

* Logistic Regression:
  * This model had an accuracy of 99%. The positive class had an f-score of 0.92, a recall of 0.98, and a precision of 0.87.

* ADA Boost Classifier:
  * This model had an accuracy of nearly 100%. The positive class had an f-score of 0.93, a recall of 0.99, and a precision of 0.87.

## Summary

Based on the results, it seems the ADA Boost Classifier model outperformed the Logistic Regression model in terms of both accuracy and f-score. If the goal of the model is to reduce false negatives, the ADA Boost Classifier model is a good choice. If the goal of the model is to reduce false positives, both models are acceptable.
