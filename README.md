# Credit Risk Classification

## Overview of the Analysis
The purpose of this analysis is to predict which loans pose a high financial risk to the lending to better determine which borrowers should be extended loans. The data provided includes:
- the size of the loan
- the interest rate
- the borrower's income
- the borrower's debt to income ratio
- the number of accounts the borrower has
- the number of marks against the borrower
- the borrower's total debt, and
- the loan status.  

To determine the risk, I need to use the borrower's financial information to predict the loan status. 

To prepare the data for the machine learning model, I assign the information I'm trying to predict, the loan status, to the "y" variable. I drop the loan status from the rest of the data to create the "X" variable. 

After assigning the variables, I split the data into two sets: a larger one to train the data, and a smaller set to test the data. I assign a random state of 1 to the split to enable reproducibility, and stratify the data to ensure both kinds of loans exist in the training and testing sets. 

The model I apply for this iteration is a logistic regression model, because the information I'm trying to predict lends itself to a simple, binary classification, which is what this algorithm delivers. 

I build the model using lbfgs as the solver, and again assign a random state for reproducibility, then fit the training set. After fitting the training data, I make predictions using the testing set, then generate a confusion matrix and print the classification report for evaluation. 

## Results
The model performs as follows:

- Precision: 
	- Healthy loans: 1.00
	- High-risk loans: .87
- Recall:
	- Healthy loans: 1.00
	- High-risk loans: .89
- F1-score:
	- Healthy loans: 1.00
	- High-risk loans: .88
- Accuracy: .99

## Results
Looking at the overall picture, the logistic regression model predicts the labels well with an accuracy of 99%. However, looking at the individual labels, we see that while the model scored very well on the healthy loans, it struggled with the high-risk loans, scoring only .87 in precision, .89 in recall, and .88 in f1-score. 

I believe this marked difference in performance arises from the inbalance between the number of healthy loans and the number of high-risk loans, with healthy loans far out-numbering the at-risk loans. This suggests underfitting. Therefore, this model is likely not the best fit, despite the high accuracy, to appropriately predict both loan types.
