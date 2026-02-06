# Bank Deposit Acceptance Analysis

The core objective of this project is to determine how to increase the acceptance of term deposits when offered through marketing campaigns targeted at existing customers of a Portuguese bank.

## Overview
This project follows the CRISP-DM methodology to examine customer information aggregated from 17 marketing campaigns conducted between 2008 and 2010. We compare several machine learning classification models, namely K-Nearest Neighbour (KNN), Logistic Regression, Decision Trees, and Support Vector Machines (SVM).

## Contents
This repository contains:
- A Jupyter Notebook (`Accept_Deposit.ipynb`) used for feature engineering, model training, and evaluation
- A `data` directory containing:
  - `bank-additional-full.csv` (the dataset)
  - `bank-additional-names.txt` (data description and attribution)
- The CRISP-DM reference document (`CRISP-DM-BANK.pdf`)

## How to Run
Open the Jupyter notebook in a suitable environment (e.g. JupyterLab, Anaconda, or Google Colab) and ensure the runtime has access to the `data` directory.

## Results

### Model Selection
Logistic Regression achieved the strongest performance in terms of Precision–Recall AUC (PR AUC) compared with KNN, SVC, and Decision Tree models. After hyperparameter tuning, Logistic Regression remained the best-performing model, with the optimal configuration:

- C = 3  
- Penalty = L2  
- Solver = LBFGS  

The best PR AUC achieved was **0.429**, which was notably higher than that of the other models.

Although Logistic Regression was not the fastest model to train, it was **significantly faster than SVC by approximately two orders of magnitude**, making it a strong choice in both performance and efficiency.

### Business Insights

#### 1. Customer Characteristics
Customers were ranked by their predicted likelihood of acceptance, enabling a lift analysis. This showed that most of the value is captured early: beyond approximately the top 20% of ranked customers, each additional customer contacted yields substantially fewer acceptances.

Feature importance analysis of the best-performing model showed that customer characteristics contribute meaningfully to prediction accuracy.

#### 2. Macro-Economic Conditions
Several macro-economic indicators were found to be highly influential. This suggests that campaign effectiveness is sensitive to broader economic conditions, and that increasing campaign intensity during favourable conditions may improve acceptance rates.

#### 3. Timing
Campaign timing also matters. The analysis indicates that running campaigns on Mondays and during October is associated with higher acceptance rates.

#### 4. Contact Method
Customers with a landline telephone were more likely to accept when contacted via telephone, making this the preferred contact method for that customer segment.