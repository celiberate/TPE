---
layout: article
title: Linear Regression
description: Linear Regression for Supervised Learning
comments: true
quote: In ML, Its not who has the best algorithm that wins, its who has the most data.
hasregex: true
image:
    teaser: teaser.jpg
    feature: feature.jpg
---
<i>{{ page.quote }}</i>

Linear models are often the introductory model that one begin with and one of the reason being it is easier to visualize than complex curves and can be easily projected.

**Linear Regression** is a type of _Supervised_ Machine Learning algorithm where goal is to develop  a model to predict the value of a dependent variable, given a set of independent variables.

Lets understand this further

**Supervised Learning** - Means both input (which is set of independent variables) and output (which is dependent variable) is used to develop (train & test) the predictive model. Since the task is to predict value of a continous variable (and not discrete variable), this is termed as **Regression** problem.

**Independent Variables** - Features (or Predators) X1, X2, X3...Xn which are independent and are not correlated

**Dependent Variable** - Target Output Variable Y

Look at this dataset of Happiness Rank vs Happiness Score of countries

![Initial Dataset]({{site.url}}/images/assets/LinearRegression/LinearRegression_P1.png)

In the above dataset, Happiness Rank is the independent variable (X feature) and Happiness Score is the dependent variable ( Y variable)

If you plot this data on a scatter plot, this is how it looks like
![Initial ScatterPlot]({{site.url}}/images/assets/LinearRegression/LinearRegression_P2.jpg)

so summarizing our problem definition in language of Machine learning,

- **Task** - Given any Happiness Rank, Predict Happiness Score for a country.
- **Performance** - Performance will be measured by accuracy of our model i.e. how close our prediction is to actual value
- **Experience** - our model will gain experience through iterations of existing dataset



## Line of Best Fit

Remember, equation for a line in X-Y plane is represented as y = mx + c, where m is the slope, c is the intercept and x,y are the independent and dependent variables respectively.

so equation for our linear regression model will be <br> 
$$ 
\hat{Y} = w0 + w1X1 + w2X2 + ... + wnXn 
$$
<br><br>    where, $$ \hat{Y} $$ is the predicted value of Y.
<br>    X1, X2,...Xn are the feature sets 
<br>    w0,w1,..wn are the coefficients (or weights) of each feature

This can also be represented in a Matrix form as
$$
\hat{Y} = X . {W}^T 
$$

where, W is a row vector of coefficients <br>
X is a mXn matrix - m data samples with n features (X0 = 1)

$$
W = \begin{bmatrix}w0 & w1 & w2 & wn\end{bmatrix}
$$

$$
X = \begin{bmatrix}X0^0 & X1^0 & X2^0 & Xn^0\\X0^1 & X1^1 & X2^1 & Xn^1\\
X0^m & X1^m & X2^m & Xn^m
\end{bmatrix}

$$


<!-- ![Best Fit Line](/assets/LinearRegression/LR_Latex_P5.jpg) -->

and our goal is to predict w0,w1...wn that gives us the best line to fit our data

![Best Fit Line 2]({{site.url}}/images/assets/LinearRegression/LinearRegression_P4.jpg)

## How we will come to know if the line is the best fit line

Basically, We need to identify a Cost function (or Loss function) through which we can measure error between our predicted values and actual values. And the line which gives us the least error will be the best line and the coefficients of that line will be our solution


 - Approach 1 - Residual Sum Loss i.e. sum of errors E where Ei is the error in the ith Sample (Predicted Value of Yi - Actual Value of Yi)
 
$$
E = \sum_{i=1}^{m}(\hat{Y}_i - Y_i)
$$

<!-- ![Sum of Square](/assets/LinearRegression/LR_Latex_P7.jpg) -->

However, here the problem is that positive and negative errors in our prediction will cancel out.

- Approach 2 - Take Absolute value of residual sum from earlier approach

$$
E = \sum_{i=1}^{m}|(\hat{Y}_i - Y_i)|
$$

<!-- ![Absolute Sum of Residuals](/assets/LinearRegression/LR_Latex_P8.jpg) -->

Again, this may not be ideal because large and small errors are penalized equally

- Approach 3 - We take Residual Sum of Squares so that we penalize large errors more.

$$
E = \sum_{i=1}^{m}(\hat{Y}_i - Y_i)^2
$$

<!-- ![RSS](/assets/LinearRegression/LR_Latex_P9.jpg) -->

- Approach 4 - Even better approach will be if we take **Mean Square Error (MSE)** where we take mean of RSS (Residual Sum of Squares)

$$
MSE = \frac{1}{m}\sum\limits_{i=1}^{m}(\hat{Y}_i - Y_i)^2
$$


<!-- ![MSE](/assets/LinearRegression/LR_Latex_P10.jpg) -->

Now that we have identified our Cost function f(x) to be MSE, We need to find an optimum point x for which our f(x) is minimized. 

## Ordinary Least Square Method

Because our cost function f(x) is a quadratic equation, we know this will be a parabola once plotted. we need to identify the point where error is minimum, that is  global minima of parablola. This is the point where slope (derivative of f(x)) is equal to zero.

We will take partial derivative of our cost function f(x) w.r.t weights w0, w1,..wn and equate it to 0 to get a system of n-linear equations with n-unknowns. 


## Gradient Descent of MSE
Performing OLS method is extremely expensive to compute when you have a large set of features and sample (imagine 10000 features and 1000000 records)

Computationally, a better approach is to perform iterative computation using Gradient descent.

Gradient Descent is an optimization algorithm to identify minima of our cost function incrementally. Basically, We begin with an initial value of w0,w1...wn and identify whether slope of our function is positive or negative for those values. If slope is negative, we know parabola is going downward and we update next iteration values of w0, w1...wn by

$$
\begin{align*} \text{repeat until convergence: } \lbrace & \newline w_0 := & w_0 - \alpha \frac{1}{m} \sum\limits_{i=1}^{m}(h_w(x_{i}) - y_{i}) \newline w_1 := & w_1 - \alpha \frac{1}{m} \sum\limits_{i=1}^{m}\left((h_w(x_{i}) - y_{i}) x_{i}\right) \newline \rbrace& \end{align*}
$$

<!-- ![GD of MSE](/assets/LinearRegression/LR_Latex_P11.jpg) -->

##  Performance - How do we measure accuracy of our Linear Regression Model

R^2 - R-squared is a statistical measure of how close the data are to the fitted regression line. It is also known as the coefficient of determination, or the coefficient of multiple determination for multiple regression.

R-squared = Explained variation / Total variation

![GD of MSE]({{site.url}}/images/assets/LinearRegression/LR_Latex_P12.jpg)

It basically tells you how close the data points are to your regression line.

However there are some obvious problems with R-squared metrices

1. R-Square keeps on increasing as you add more features, which may not be the case always. so a model with more features always appear to better fit.
2. If a model has high-order polynomials, It begins to model the random noise in the data and starts overfitting the model

### Underfitting & Overfitting
What happens if my model has very high accuracy on training data but not so much on test data. We need to understand the concept of Overfitting and Underfitting models, which I have covered in a seperate post here



{% if page.hasregex %}
<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>
{% endif %}








