---
layout: post
author: shivam
title: Learning ML - Prerequisites
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

However, until you have background knowledge of concepts and logic behind linear regression algorithm and which in turn will require you to be aware of statistic concepts like variance or covariance , you will struggle to relate why linear regression algorithm was applied to a particular problem and how it derived the solution.

so my pre-requisite for beginners for learning ML is fairly simple
- **Come out of Comfort Zone**
- **Be physical fit** (it will require a lot of mental strength)

Rest all skills you can acquire over the journey as you deep dive in this mammoth world of Machine Learning. One thing is for sure, no matter whether machine learns or not, you will enjoy getting back to school days and revisiting fundamental topics of vectors, matrices, permutations, mean, medians...& many more.
