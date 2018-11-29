---
layout: post
author: Shivam Sinha
title: Logistic Regression
description: Logistic Regression for Supervised Learning - Part 1
comments: true
quote: 
hasregex: true
---
Logistic Regression is _Supervised_ Machine learning algorithm for Classification. It is one of the most widely used algorithm for classification task, and, although it has word "Regression" in its name, it is actually not used for regression problems.

**Binomial Classification** -  When we have to choose between two values. Take for example
- Whether an email is SPAM or NOT SPAM
- Whether stock prices will INCREASE or DECREASE

**Multinomial Classification** - When we have to choose between 3 or more discrete values. For example
- Match Output - WIN LOSE or DRAW
- WEATHER FORECAST - SUNNY, RAINY, WINDY, HUMID


**Hypothesis Function**
Lets assume we decide to use hypothesis function of Linear regression model as the hypothesis function of our logistic regression model

$$
h_\theta(x) = \theta_0 + \theta_1X
$$


**Sigmoid Function or Logistic Function**

$$
h_\theta(x) = g(z) = \frac{1}{1 + e^-z}
$$

$$
x \in \{-\infty,\infty\}, y \in \{0,1\}
$$

**Cost Function** 

**Gradient Descent** 


{% if page.hasregex %}
<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>
{% endif %}








