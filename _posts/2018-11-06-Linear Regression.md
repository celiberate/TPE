---
layout: post
author: Shivam Sinha
title: Linear Regression
---

Linear Regression is often the first algorithm which you will find in ML books or courses. 

**Linear Regression** is a type of _Supervised_ Machine Learning algorithm where goal is to develop  a model to predict the value of a dependent variable, given a set of independent variables.

Lets understand this further

**Supervised Learning** - Means both input (which is set of independent variables) and output (which is dependent variable) is used to develop (train & test) the predictive model. Since the task is to predict value of a continous variable (and not discrete variable), this is termed as Regression problem.

**Independent Variables** - Features X1, X2, X3...Xn which are independent and are not correlated

**Dependent Variable** - Target Output Variable Y where Y = wo + w1X1 + w2X2 + ... + wnXn.
 wo,w1...wn are co-efficients or weights.


![Initial Dataset]({{site.baseurl}}/assets/LinearRegression/LinearRegression_P1.png)

In the above dataset, Happiness Rank is the independent variable (X feature) and Happiness Score is the dependent variable ( Y variable)

If you plot this data on a scatter plot, this is how it looks like
![Initial ScatterPlot]({{site.baseurl}}/assets/LinearRegression/LinearRegression_P2.jpg)

so summarizing our problem definition in language of Machine learning,

- **Task** - Predict Happiness Score, given any Happiness Rank
- **Performance** - Performance will be measured by accuracy of our model i.e. how close our prediction is to actual value
- **Experience** - our model will gain experience through iterations of existing dataset



## Line of Best Fit

Remember, equation for a line in 2-D plane is represented as y = mx + c, where m is the slope, c is the intercept and x,y are the independent and dependent variables respectively.

so equation for our linear regression model will be 

![Best Fit Line]({{site.baseurl}}/assets/LinearRegression/LR_Latex_P5.jpg)

and our goal is to predict w0,w1...wn that gives us the best line to fit our data


![Best Fit Line 2]({{site.baseurl}}/assets/LinearRegression/LinearRegression_P4.jpg)

### How we will come to know if the line is the best fit line

Basically, We need to identify a Cost function (or Loss function) through which we can measure error between our predicted values and actual values. And the line which gives us the least error will be the best line and the coefficients of that line will be our solution


 - Approach 1 - Residual Sum Loss i.e. sum of errors E where Ei = Predicted Value of Yi - Actual Value of Yi 

![Sum of Square]({{site.baseurl}}/assets/LinearRegression/LR_Latex_P7.jpg)

However, here the problem is that positive and negative errors will cancel out.

- Approach 2 - Take Absolute value of residual sum from Approach 1.

![Absolute Sum of Residuals]({{site.baseurl}}/assets/LinearRegression/LR_Latex_P8.jpg)

Again, this may not be ideal because large and small errors are penalized equally

- Approach 3 - We take Residual Sum of Squares so that we penalize large errors more.

![RSS]({{site.baseurl}}/assets/LinearRegression/LR_Latex_P9.jpg)

- Approach 4 - Even better approach will be if we take **Mean Square Error (MSE)** where we take mean of RSS (Residual Sum of Squares)

![MSE]({{site.baseurl}}/assets/LinearRegression/LR_Latex_P10.jpg)

Now that we have identified our Cost function f(x) to be MSE, We need to find an optimum point x for which our f(x) is minimized. Because it is a quadratic equation , we know its line will be a parabola and we need to identify the point where slope (derivative of f(x)) is equal to zero.

## Gradient Descent of MSE

Gradient Descent is an optimization algorithm to identify minima of our cost function incrementally. Basically, We begin with an initial value of w0,w1...wn and identify whether slope of our function is positive or negative for those values. If slope is negative, we know parabola is going downward and we update next iteration values of w0, w1...wn by

![GD of MSE]({{site.baseurl}}/assets/LinearRegression/LR_Latex_P11.jpg)

##  Performance - How do we measure accuracy of our Linear Regression Model

R^2 - R-squared is a statistical measure of how close the data are to the fitted regression line. It is also known as the coefficient of determination, or the coefficient of multiple determination for multiple regression.

R-squared = Explained variation / Total variation

![GD of MSE]({{site.baseurl}}/assets/LinearRegression/LR_Latex_P12.jpg)

It basically tells you how close the data points are to your regression line.

### However, there is a problem with R^2 values?

In my next blog, I will cover on why R^2 may not be the correct metric for measuring accuracy of linear regression model always and we can instead go for other metrics like R^2 Adjusted.










