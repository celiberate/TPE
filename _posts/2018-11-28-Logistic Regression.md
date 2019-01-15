---
layout: article
author: Shivam Sinha
title: Logistic Regression
description: A Supervised Machine Learning Algorithm for Classification
comments: true
quote: If data is 'the new oil'; then data scientists function like oil refinery, converting data into insights.
hasregex: true
image:
    teaser: assets/logisticregression.jpg
    feature: feature.jpg
---
<i>{{ page.quote }}</i>

Logistic Regression is a Supervised Machine learning algorithm used for the Classification task. Although it has word “Regression” in its name, it is not to be confused with the regression algorithm like linear regression.

**Binomial Classification** -  When we have to choose between two distinct values. Take for example
- Whether an email is SPAM or NOT SPAM
- Whether stock prices will INCREASE or DECREASE

**Multinomial Classification** - When we have to choose between 3 or more discrete values. For example
- Match Output - Win, Lose or Draw
- Weather forecast - Sunny, Rainy, Cloudy, Snow

In a binomial classification, Output variable Y $$\in$$ {0,1}. Our Goal is, given a set of input features, predict the probability of outcome belonging to positive class (Y=1) or negative class (Y=0).

P{Y=1 \| X;$$\theta$$} refers to Probability of Y = 1 (positive Class); given X as a function of theta
<br>
P(Y=0 | X;$$\theta$$) refers to Probability of Y = 0 (negative class)

Take note, we are not predicting the actual Y labels, instead we are predicting the probability of Y belonging to a particular class.

### Hypothesis Function

What if we decide to use hypothesis function of our Linear regression model, for our logistic regression problem as well i.e. $$ h_\theta(x) = \theta_0 + \theta_1X $$

Well, Hypothesis function may give values > 1 or < 0, however because we are predicting probability, we need to have values $$0 \leq h_\theta(x) \leq 1; $$

so, we will modify the hypothesis function to  make sure 
$$
0 \leq h_\theta(x) \leq 1; 
$$

```
Let p be the probability

# For p to be > 0, We will take exponential function
    p = exp(z)              (1)
# For p to be < 1, we let
     p = p / (1 + p)        (2)
    using (1) and (2),
     p = exp(z)/1+exp(z)

     p = 1/(1+exp(-z))        (3)

```

This function is also known as Sigmoid function and this will be used as our hypothesis function.

### Sigmoid Function or Logistic Function

$$
h_\theta(x) = g(z) = \frac{1}{1 + e^-z}

  where,

z = X.\theta^T \in \{-\infty,\infty\}, y \in \{0,1\}
$$

![Sigmoid Function](/images/assets/LogisticRegression/sigmoid.png)

```
If p = Probability of success,
q = 1 - p will be the probability of failure

p/(1-p) = exp(z)            (4)

(P/1-P) is called odd ratio

Taking log on both sides,
log(p/1-p) = z              (5)
```

### Decision boundary

If you look closely at sigmoid function, for x > 0, y = 1. and x < 0, y = 1. 

solution for $$X.\theta^T = 0$$ will provide us with the decision boundary

### Cost Function

Now, that we have identified our hypothesis function, We need to find out the cost function or loss function to measure the error in our prediction.

Consider these two scenarios

| Cost fn for Y = 1 | Cost fn for Y = 0|
|-------|--------|---------|
| ![cf0 Function](/images/assets/LogisticRegression/cf0.png) | ![cf1 Function](/images/assets/LogisticRegression/cf1.png) | 
|-------|--------|---------|
| $$ -log(\frac{1}{1+e^-z}) $$ | $$ -log(\frac{e^-z}{1+e^-z}) $$ | 

If you observe closely, Our cost function for Y = 1, penalizes heavly as our predictions gets closer to 0 (implying our prediction is totaly way off from actual value of Y = 1). At the same time, it doesn't penalize as our prediction gets closer to actual value of (Y = 1).

- Do we need to have two seperate functions as our Cost functions?

Not really, As both these equations can be merged to form a single cost function

$$
J(\theta) = \frac{1}{m}\sum\limits_{i=1}^{m}(-y^i*log(h_\theta(x^i) - (1-y^i)*log(1 - h_\theta(x^i))
$$

where

$$y^i$$ - value of target variable in ith sample<br>
$$h_\theta(x^i)$$ hypothesis of ith sample  i.e. sigmoid function value =  $$\frac{1}{1 + e^-z}$$<br>
$$z = X*\theta^T$$

This is also called as Cross Entropy or log loss function.

### Gradient Descent

Taking partial derivative of our cost function with respect to theta,
<br>

__Repeat this until we get $$min_{\theta}J(\theta)$$:__

{

$$ \large \theta_{j} := \theta_{j} -\alpha \sum_{i=0}^{m}[x^{(i)}_{j}h_{\theta}(x^{(i)}) - y^{(i)}x^{(i)}_{j}] $$

}
        
__Here $$\alpha$$ is Learning Rate __


### Measuring Performance of Logistic Regression Model
Unlike evaluating the accuracy of Regression model where we predicting continous or discrete dependent variable,evaluating accuracy of a classification model is bit tricky. Before we understand how is accuracy measured, we need to understand below confusion matrix

| | | Actual Value|
| | |Y = 1 | Y = 0|
|-------|--------|
|Predicted | Y = 1 |True Positive | False Positive |
| | |-------|--------|
| Predicted | Y = 0|False Negative | True Negative |
|-------|--------|

**True Positive**: When both Actual and Predicted values are True
**False Positive**: When Actual value is false but we predicted it to be True
**True Negative**: When both Actual and Predicted values are False
**False Negative**: When Actual value is True, however we predicted it to be False


Accuracy = (TP + TN) / (TP + TN + FP + FN)

Precision - Ratio of correct predictions out of all predictions

Recall - Ratio of correct predictions out of all predictions


{% if page.hasregex %}
<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>
{% endif %}








