---
layout: post
author: Shivam Sinha
title: Learning ML - Prerequisites
description: Getting started with Machine Learning - Basics
comments: true
quote: Beat the data until it spits what you want to learn
---
Standard deviation, eigenValues, patial derivatives...When was the last time you encountered these words. For someone like me whose previous encounter with these Mathematics and Statistics topics, were more than a decade back, even getting started with learning ML, required a lot of groundwork and cleaning up the dust settled on those high school maths and statistics concepts.

Unlike learning a new language or a framework, where you straightaway jump to writing a "Hello World" program or executing commands to build and run, in the case of ML, the first major challenge is to identify where & how to begin with. Because ML will require you to have a fair understanding of

1. Linear Algebra
2. Calculus
3. Probability
4. Statistics
5. Algorithms & Data Structures
6. Programming Languages - Python (or R)
7. Numerous Python packages - Numpy, Pandas, Matplotlib...etc
8. Big Data
9. ....
10. & many more

If you come with programming and development background, Often the desire is to jump to coding and see real action and you make a google search on machine learning poblems & implementation say Linear Regression, and you get a few lines of python code which does it for you

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

However, To have an understanding and build a Machine Learning model for your dataset, will require you to be first clear with the mathematical concepts behind those algorithms, without which you will just be hitting in the dark. so, till you understand that geometric view of a linear euation is a line and a quadratic equation is a parabola, you will keep wondering why derivative of cost function of linear regression model gives the minima.

so my pre-requisite for beginners for learning ML is fairly simple
- **Come out of Comfort Zone**
- **Remain motivated, as there will be many failures**
- **And above all, Be physically fit** (as it will require a lot of mental strength to take all this in)

Rest all skills you can acquire over the journey as you deep dive in this mammoth world of Machine Learning. One thing is for sure, no matter whether machine learns or not, you will enjoy getting back to school days and revisiting fundamental topics of vectors, matrices, permutations, mean, medians...& many more.
