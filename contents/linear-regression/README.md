# Linear Regression

## Table of Contents

- [Linear Regression](#linear-regression)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Data Preperation Needed for Linear Regression](#data-preperation-needed-for-linear-regression)
  - [Common Techniques](#common-techniques)
    - [Simple Linear Regression](#simple-linear-regression)
    - [Orinary Least Squares](#orinary-least-squares)
    - [Gradient Descent](#gradient-descent)
    - [Regularization](#regularization)
  - [Metrics for Regression](#metrics-for-regression)
  - [Plots](#plots)
  - [References](#references)

## Introduction

Predictive modeling's main objective is to minimize the error of the model and make accurate predictions. Linear regression is a statistical model to understand the relationship between numerical input and variables. Using linear regression, one can make predictions by finding the best model, therefore it is part of machine learning algorithms.

Linear regression assumes that there is a linear model between the input variable and the output variable. If the input variable is a single variable, then the model is known as `simple linear regression`, and if there are many input variables, it is `multiple linear regression`. 

## Data Preperation Needed for Linear Regression

Linear regression makes some assumptions about your dataset when you use ordinary least squares method for modeling for it to work properly.

- **Linearity**. The relationship between your input and output must be linear for any type of linear model. 
- **Remove any Noise**. Input and output variables need to be clearn without any outliers
- **Remove Collinearity**. Regression will overfit the data when are correlated variables.
- **Gaussian Distributions**. Predictions will be more accurate when input and output variables are normally distributed.
- **Rescale Inputs**: Using standardization or normalization.

More on the assumptions can be found in [Wikipedia](https://en.wikipedia.org/wiki/Ordinary_least_squares#Assumptions).

## Common Techniques

There are many techniques to apply a linear regression, but below are the most known and used ones:

- Simple regression (statistics)
- Ordinary Least Squares
- Gradient Descent
- Regularization


### Simple Linear Regression

Linear regression with a single input variable is called `simple linear regression`. Descriptive statistics (mean, standard deviation, corelations, covariance) can be used to find the coefficent of the input variable.

Check out detailed explanation and R implementation of simple linear regression in [Applied Statistics with R](https://daviddalpiaz.github.io/appliedstats/simple-linear-regression.html) book.

### Orinary Least Squares

When there are more input variables, ordinary least squares method can be used to find the optimal coeficents. This method aims to minimize the sum of squared residuals. For each data point in your data, the distance of any point to the regression line is summed and squared to find out the total squared errors of the equation. This squared error is minimized by ordinary least squares.

This awesome blog about [how ordinary least squares work](https://setosa.io/ev/ordinary-least-squares-regression/) is a good read to understand about this method more.

### Gradient Descent

Gradient descent can be used with one or more input variables by iteratively minimizing the error of the model.

This method randomly assigns coefficents to each input variable and sum of squared error are calculated for every iteration. A scaling factor is used to define the size of the improvement, known as learning rate, to change the coeffients each time and iterations continue until the sum of the squared error cannot be minimized more. This algorithm is known as gradient descent.

### Regularization

Regularization method using ordinary least squares method, seeks to minimize a function of the sum of errors in the model.

Two popular examples of regularization procedures for linear regression are:

**Lasso Regression:** OLS function changed to minimize the absolute sum of the coefficients (called L1 regularization).

**Ridge Regression:** OLS function changed to minimize the squared absolute sum of the coefficients (called L2 regularization).

## Metrics for Regression

| Metric                                        | Description                                                                                                                                                                                                                          |
| --------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Mean Absolute Error(MAE)                      | Sum of absolute difference between actual and observed values divided to total # of observations.                                                                                                                                    |
| Mean Squared Error(MSE)                       | MAE but squared distance of actual and observed values. If there are outliers this value will be bigger, not good.                                                                                                                   |
| Root Mean Squared Error(RMSE)                 | Root of the MSE.                                                                                                                                                                                                                     |
| R Squared (R2) (coefficient of determination) | The variance of the dependent variable explained by the independent variables of the model. Read more on [this medium article](https://towardsdatascience.com/evaluation-metrics-model-selection-in-linear-regression-73c7573208be). |

For more on regression metrics, check out scikit-learn's [regression API](https://scikit-learn.org/stable/modules/classes.html#regression-metrics).

## Plots
| Plot                      | Description                                                                                                                                                                          |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Actual vs Predicted graph | From scatter plots of Actual vs Predicted You can tell how well the model is performing. For Ideal model, the points should be closer to a diagonal line.                            |
| Histogram of residual     | One of the assumption in Linear regression is that the residual should be normally distributed                                                                                       |
| Normality Q-Q             | Used to determine the normal distribution of errors. For normally distributed data, observations should lie approximately on a straight line.                                        |
| Scale Location Plot       | Residuals should be spread equally along the ranges of predictors. Using this graph the assumption of equal variance or homoscedasticity can be checked. Should be a horizontal line |

Check out [Metrics and Plots for Analyzing Linear regression models](https://medium.com/ml-course-microsoft-udacity/metrics-and-plots-for-analyzing-linear-regression-models-43b533547574).
## References

- Applied Predictive Modeling, Chapter 6.
- https://machinelearningmastery.com/linear-regression-for-machine-learning/
- https://people.duke.edu/~rnau/regintro.htm