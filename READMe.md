# Bank Deposit Acceptance Analysis
The core of this project was determining how to increase the acceptance of term deposits, when offered in campaigns targeted at existing customers of a Portuguese bank.

## Overview
We follow the CRISP-DM method to examine the features of customer information that was amalgamated from 17 marketing campaigns between 2008 and 2010. We comparing different machine learning classification methods: namely K Nearest Neighbor, Logistic Regression, Decision Trees, and Support Vector Machines.

## Contents
In this repository is the Jupyter Workbook that was used to do feature engineering on the data set (called Accept_Deposit.ipynb)

There is the data directory/folder containing:
   bank-additional-full.csv  (the .csv file for the data)
   bank-additional-names.txt  (has the data attribution)

## How to Run
Load the Jupyter into a suitable platform (Colab/Anaconda etc) and ensure the platform has access to the data.

## Results

# Model Selection:
We found that Logistic Regression performed better for the PR AUC than KNN, SVC and Decision Tree models. Tuning the hyper-parameters for all four models still resulted in Logistic Regression performing the best with C=3, Penalty=L2 and Solver=LBFGS gave the best performing model (by PR AUC). The best PR AUC of 0.429126 was notably higher than other models.

Logistic Regression was not the fasted to fit the trained model. But it was significantly faster than SVC (by two orders of magnitude).

# Business Information:
1. **Customer Characteristics:**
We sorted customers by their likeliness to accept (highest first) so a Lift Analysis could be done. This revealed that most of the value is captured early. After ~20% of the ranked population, each additional customer contacted yields far fewer acceptances.

We ranked the features of the data according to their contribution to the best model. This revealed:

2. **Macro-Economics**
Also several economic conditions at the time of a campaign is likely to increase yield so capitalising by increasing campaigns if the conditions are right is also useful.

3. **Timing:**
The customer characteristics can be built upon by timing campaigns for Mondays and in October.

4. **Contact Method**
For customers with landline telephone, this would be the first choice for contact method.