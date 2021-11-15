# linear regression
There are two types of supervised machine learning algorithms: Regression and classification. The former predicts continuous value outputs while the latter predicts discrete outputs. For instance, predicting the price of a house in dollars is a regression problem whereas predicting whether a tumor is malignant or benign is a classification problem.

- **Scikit-learn** is a powerful Python module for machine learning.
  - It contains function for regression, classification, clustering, model selection and dimensionality reduction.
- the UCI Machine Learning Repository. UCI machine learning repository contains many interesting data sets
- l**east squares** method as the way to estimate the *coefficients*.

- `lm.fit()` -> fits a linear model
- `lm.predict()` -> Predict Y using the linear model with estimated coefficients
- `lm.score()` -> Returns the coefficient of determination (R^2). A measure of how well observed outcomes are replicated by the model, as the proportion of total variation of outcomes explained by the model.
- `.coef_` gives the coefficients and `.intercept_` gives the estimated intercepts.

## Training and validation data sets
In practice you wont implement linear regression on the entire data set, you will have to split the data sets into training and test data sets. So that you train your model on training data and see how well it performed on test data.
- You have to divide your data sets randomly. Scikit learn provides a function called `train_test_split` to do this.

## Residual plots
- are a good way to visualize the errors in your data.
  - If you have done a good job then your data should be randomly scattered around line zero.
  -  If you see structure in your data, that means your model is not capturing some thing.






















