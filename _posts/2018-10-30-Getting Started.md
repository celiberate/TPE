---
layout: article
title: Getting started - Initial Roadblock
description: Where and How to begin?
comments: true
quote: Beat the data until it spits what you want to learn
image:
    teaser: assets/gettingstarted.jpg
    feature: feature.jpg
---
<i>{{ page.quote }}</i>

Being a mobile app developer, I had been involved in creating rich engaging User experience applications. As a frontend developer, I was not too worried about data storage and processing. All the data exchange used to happen through APIs, which were designed to serve limited and concise data for end-users. The primary reason being, mobile devices having a limited real estate and processing capabilities, is not advisable to do computationally expensive operations on mobile for best user experience.

So, when I decided to pursue Machine learning, more than a technical leap, it was a complete mindset change, where I had to start thinking about volume and velocity of data (big data), and processing of data to find patterns or predictive models.

The next challenge was getting on top of Maths and statistics concepts, which I had not even touched for over a decade. The moment you realize that one needs to be versed with Linear Algebra concepts like eigenvalues and eigenvectors or statistical concepts like standard deviation and random sampling or conditional probability, for understanding machine learning, you realize how much of groundwork needs to be done and dust needs to be cleaned up. A good part is we can learn these concepts as we make progress and encounter them in our journey to learn AI/ML.

The biggest hurdle was identifying how and where to start with. With tons n tons of reading materials and MOOCs being offered all over the internet on Machine learning, it becomes even more confusing as we browse to chalk out a learning path. Thanks to @Siraj Raval and his informative youtube videos on how to get started, I could chalk out a 3-months plan and decided to stick to it.

This is how I decided to structure it up, assuming I will spend 2-hrs daily

- 1st Month
   - Linear Algebra - MIT 18.06 course videos by Gilbert Strang
   - Python - Basic Python programming skills
   - Calculus - 3 Blue 1 Brown videos on Calculus

- 2nd Month
   - Andrew Ng Course on Machine Learning offered on Coursera - Supervised Learning
   - Getting started on Kaggle kernels
   - Jupyter notebooks 
   - Pandas & Numpy ( a little bit of Matplotlib)

- 3rd Month
  - Andrew Ngs course continued - (Unsupervised  Learning)
  - Probability and Statistics - Descriptive and Inferential
  - Exploratory data analysis ( Mostly reading through different blogs on Analytics Vidhya)

After 3-months, I was enough prepared to understand the basics of Machine learning and apply them to practice problems and look at my model.

For, The next 3-months, I have decided to focus on
   - Pick any 1 area - NLP or Computer Vision or Recommendation System and go deep into that.
   - Understand Machine Learning in production - This will require knowledge of Kubernetes / Docker container and understanding of DevOps for ML python notebooks
   - Participate in Kaggle competitions and/or contribute to ML blogs
  
There is still a long way to go, as developing enterprise level Machine Learning solutions, will require us to touch on more areas
  - Apache Spark/Kafka - Streaming big-data and in-memory processing
  - Visualization tools like Tableau or SAS ( any 1)
  - R ( I have stuck to python assuming I will not require to learn R)



![introduction]({{site.url}}/images/assets/intro.png)

### Exploratory Data Analysis

Because Machine Learning models use the experience from available data (training data) for predictive modeling, it is very important to make sure that data which goes as input to ml model is clean and pre-processed for missing values, outliers, anomalies etc. It is exploratory data analysis at the pre-processing stage that is where you will end up giving almost 70% of your time. And this is where knowledge of statistics and data visualization is very important.

### Do we need to write the models from scratch?

A good part is we don't need to write(code) the Machine learning algorithms from scratch as there are libraries like Scikit learn, keras or tensorflow which already does it for us. However, to identify which ML algorithm is the right fit for our problem and how to apply it, We need to understand the algorithm first. 

Let us take an example - Below is the python implementation of a Linear Regression model from Scikitlearn library (Did you notice it just 3-4 lines of code?) 

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

However, Until we have the understanding of how linear regression model works, how tuning hyperparameters affect the model accuracy, we will not be able to understand the model behavior and adjust it for our needs. 

## Link to Materials I referred

These are some of the online resources which I referred to..will keep updating it as I move ahead in my journey.

  - Linear Algebra MIT 18.06 - by gilbert strang
  - Andrew Ng course on machine learning
  - Python - Youtube videos by Corey Schafer
  - EDA - Exploratory Data analysis
    - https://www.analyticsvidhya.com/blog/2016/01/guide-data-exploration/
    - 
  - Probability & Statistics - https://medium.com/diogo-menezes-borges/introduction-to-statistics-for-data-science-7bf596237ac6

### Any Prerequisite for learning AI/ML


The prerequisites for learning AI/ML is fairly straightforward

- Come out of Comfort Zone
- Attend meetups, technical conferences, seminars. start reading /writing blogs, tech articles, watching youtube videos on AI/ML. This will help you to network with data science professionals as well as understand what all is going around in the community.
- Collaborate and build your profile by sharing your project work through GitHub
- And above all, Remain physically fit (as it will require a lot of mental strength to take all this in)

Rest all skills you can acquire over the journey as you deep dive in this mammoth world of Machine Learning. One thing is for sure, no matter whether machine learns or not, you will enjoy getting back to academics and learning and revisiting fundamental topics of vectors, matrices, permutations, mean, medians...& many more.


