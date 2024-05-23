#  Boston Housing Values

## by (Eloebhose Kingsley Osazele)

## Introduction
> This project aims to create different regression models to predict the median house values in suburban Boston. The dataset used contains information collected by the U.S Census Service concerning housing in the area of Boston Mass.

## Summary of Findings

**I was Interested in investigating and finding out about:**

- creating different regression models and finding out the best by assessing their performance using the r2_score and the RMSE Metrics.
- Determine the predictor variables impacting the median housing value in Boston. 

**Data Exploration:**

- The variables in the dataset exhibit linearity, which is important for the different models to be successful in the prediction task

- They were presence of multicollinearity while using the OLS fitted summary, but after using correlation and level of significance, we realised that all variables were important.

- The reason for the detection of multicollinearity by the ols fitted summary while all the variables are important can be because linear regression is not flexible enough and can not fully capture the relationship between the features and the median housing values. This is further proven by the performance of the linear model as compared against the performance of the non linear models.

- We noticed from the correlation matrix that the LSTAT(Lower Status of the Population) and the RM(No of dwelling) are the highest correlated features with the median housing value (MEDV)

**Data Preprocessing:**

- The data was scaled using the MinMax Scaler from the Sklearn library and then split into training and testing sets

- The test set was converted back to the original scale since we would be using the RMSE metric for model assessment.

**Model Training and Evaluation:**

The linear model (Simple linear model and multiple linear model) was first trained with the dataset. The result shows that the multiple linear model performed a lot better than the simple linear model, having an R2 score of 54% and 67% respectively for the simple linear model and the multiple linear model.

- Ridge and Lasso regression models were created since it is more flexible and better at dealing with multicollinearity than the simple linear and multiple linear model. The results showing the performance of the models proved the earlier statement correct. The Ridge(l2) and Lasso(l1) regression performance showed and r2_score of 67.3% and 67.0% respectively, which proved that the l1 and l2 models performed better at predicting the median value of housing in Boston than the linear models.

- Nonlinear models like decision trees and random forest was used which performed better at predicting the median housing values than the ridge and lasso model, having an R2 score of 85.3% for the Decision tree and 85.7% for the random forest model.

- A heterogenous ensemble regression model (Stacking Ensemble) was used which used random forest and linear regression as its base learners and Linear regression as the final estimator. The ensemble regression model is the best-performing model with an R2 score of 86.4%

**Feature Importance**

- To get the features that most influence median housing value, we extracted the base learner that contributed the most to the final prediction of our best performing model (stacking ensemble model), and the important features were extracted. This showed us that **LSTAT (percentage lower status of the population)** and **RM (average number of rooms per dwelling)** are the most influential features for predicting the median housing values.
