---
layout: post
author: Shivam Sinha
title: Logistic Regression
description: Logistic Regression for Supervised Learning - Part 1
comments: true
quote: 
hasregex: true
---
Logistic Regression is a _Supervised_ Machine learning algorithm used for Classification tasks. It is one of the most widely used algorithm for classification task, and, although it has word "Regression" in its name, it is not to be confused with regression algorithm like linear regression.

**Binomial Classification** -  When we have to choose between two distinct values. Take for example
- Whether an email is SPAM or NOT SPAM
- Whether stock prices will INCREASE or DECREASE

**Multinomial Classification** - When we have to choose between 3 or more discrete values. For example
- Match Output - WIN LOSE or DRAW
- Weather forecast - Sunny, Rainy, Cloudy, Snow

In a binomial classification, Output variable Y $$\in$$ {0,1}. Our Goal is to given a set of input features, predict the probability of outcome belonging to positive class (Y=1) or negative class (Y=0).

P{Y=1 \| X;$$\theta$$} refers to Probability of Y = 1 (positive Class) for given X
<br>
P(Y=0 | X;$$\theta$$) refers to Probability of Y = 0 (negative class)

**Hypothesis Function**
What if we use the same hypothesis function of our Linear regression, for our logistic regression problem i.e. $$ h_\theta(x) = \theta_0 + \theta_1X $$

Hypothesis function may give values > 1 or < 0, however for our classification problem, we need to have $$0 \leq h_\theta(x) \leq 1; $$(* Our task is to predict probability hence it should be between 0 & 1)

so, we will modify the hypothesis function to  make sure 

$$
0 \leq h_\theta(x) \leq 1; 
$$

We will do this by using Sigmoid function as our hypothesis function.

**Sigmoid Function or Logistic Function**

$$
h_\theta(x) = g(z) = \frac{1}{1 + e^-z}
$$

$$
x \in \{-\infty,\infty\}, y \in \{0,1\}
$$

![Sigmoid Function](/assets/LogisticRegression/sigmoid.png)

**Cost Function**

Now, that we have identified our hypothesis function, We need to find out the cost function or loss function to measure the error in our prediction.

Consider these two scenarios

| Cost fn for Y = 1 | Cost fn for Y = 0|
|-------|--------|---------|
| ![cf0 Function](/assets/LogisticRegression/cf0.png) | ![cf1 Function](/assets/LogisticRegression/cf1.png) | 
|-------|--------|---------|
| $$- log(\frac{1}{1+e^-z})$$ | $$-log(\frac{e^-z}{1+e^-z})$$ | 

If you observe closely, Our cost function for Y = 1, penalizes heavly as our predictions gets closer to 0 (implying our prediction is totaly way off from actual value of Y = 1). At the same time, it doesn't penalize as our prediction gets closer to actual value of (Y = 1).

Do we need to have two seperate functions as our Cost functions?

Not really, As both these equations can be merged to form a single cost function

$$
J(\theta) = \frac{1}{m}\sum\limits_{i=1}^{m}(-y^i*log(h_\theta(x^i) - (1-y^i)*log(1 - h_\theta(x^i))
$$

where

$$y^i$$ - value of target variable in ith sample<br>
$$h_\theta(x^i)$$ hypothesis of ith sample  i.e. sigmoid function value =  $$\frac{1}{1 + e^-z}$$<br>
$$z = X*\theta^T$$

**Gradient Descent** 

Taking partial derivative of our cost function with respect to theta,
<br>

__Repeat this until we get $$min_{\theta}J(\theta)$$:__

{

$$ \large \theta_{j} := \theta_{j} -\alpha \sum_{i=0}^{m}[x^{(i)}_{j}h_{\theta}(x^{(i)}) - y^{(i)}x^{(i)}_{j}] $$

}
        

__Here $$\alpha$$ is Learning Rate __


{% if page.hasregex %}
<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>
{% endif %}








