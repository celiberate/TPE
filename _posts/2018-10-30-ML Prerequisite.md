---
layout: post
author: Shivam Sinha
title: Learning ML - Prerequisites
description: Getting started with Machine Learning - Basics
comments: true
quote: Beat the data until it spits what you want to learn
---
Standard deviation, eigenValues, patial derivatives...When was the last time you encountered these terms. For someone like me whose previous encounter with these Mathematics and Statistics topics, were more than a decade back, even getting started with learning ML, required a lot of groundwork and cleaning up all the dust settled on fundamental maths and statistics concepts.

Unlike learning a new language or a framework, where you straightaway jump to writing a "Hello World" program or executing commands to build and run, in the case of ML, the first major challenge is to identify where & how to begin with. Because ML will require you to have a fair understanding of

1. Linear Algebra
2. Calculus
3. Probability
4. Statistics
5. Algorithms & Data Structures
6. Programming Languages - Python (or R)
7. Numerous Python packages - Numpy, Pandas, Matplotlib...etc
8. SQL
9. ....
10. & many more

![introduction](/assets/intro.png)


A good part is we don't need to write the Machine learning algorithms from scratch as there are libraries like Scikit learn, keras or tensorflow which already does it for us. However to identify which ML algorithm is a right fit for our problem and how to apply it, We need to understand the algorithm first. 
Lets take an example - Below is the python implementation of Linear Regression Model from Scikit learn library (Did you notice it just 3-4 lines of code?) 

```
import matplotlib.pyplot as plt
import numpy as np
from sklearn import datasets, linear_model
from sklearn.metrics import mean_squared_error, r2_score

# Create linear regression object
regr = linear_model.LinearRegression()

# Train the model using the training sets
regr.fit(X_DATA, Y_DATA)

# Make predictions using the testing set
Y_PREDICTION = regr.predict(X_TEST_DATA)

}
```

However, Till we have the understanding of how linear regression model works, we will not be able to understand the model behaviour and adjust it for our needs. 

so my pre-requisite for beginners for learning ML is fairly simple
- **Come out of Comfort Zone**
- **Put your learning hats on**
- **And above all, Remain physically fit** (as it will require a lot of mental strength to take all this in)

Rest all skills you can acquire over the journey as you deep dive in this mammoth world of Machine Learning. One thing is for sure, no matter whether machine learns or not, you will enjoy getting back to school days and revisiting fundamental topics of vectors, matrices, permutations, mean, medians...& many more.
