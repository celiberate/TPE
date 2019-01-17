---
layout: article
title: Label encoding
description: One-hot encoding vs Label encoding
comments: true
quote: Predictive Modeling works on constructive feedback principle.
asregex: true
image:
    teaser: teaser.jpg
    feature: feature.jpg
---
<i>{{ page.quote }}</i>

Problem Statement: Machine learning models work on the numerical data, and so, we need to convert our categorical data (labels) to numerical data before using it for training.

Let say we have a predictor variable "Status" with values ['Y' , 'N' , 'NA']. Now to use this variable for our training purpose, we need to first convert these labels to numeric values like 0,1,2.

![Initial dataframe]({{site.url}}/images/assets/labelencoding/initial.png)


There are two ways we can handle this using Scikit Learn library. As an alternative, we can choose to provide our own implementation, if required.

**Label encoding**  - This is like in-place encoding where unique values in the columns are replaced with respective unique ordered numerical values. so all 'N' gets replaced with 0, all 'Y' gets replaced with 1 and all 'NA' gets replaced with '2' etc.
   
This doesn't create new columns in the dataframe and does encoding in-place. However, it may lead to believe that there is some kind of order within the values. so, the other way is to do one-hot encoding

```
from sklearn import preprocessing

label_encoder = preprocessing.LabelEncoder()
label_encoder.fit(df)

y = label_encoder.transform(df)
```
![labelendoded dataframe]({{site.url}}/images/assets/labelencoding/labelencoding.png)
   
**One-hot encoding** - To avoid the column being interpreted as ordinal variable, we instead do one-hot encoding. Here, categorical columns is split into multiple columns, one for each label, and labels are replaced with 1s or 0s, assigning 1 to label assigned for that column and 0 for all other labels
   
Status column will get 3 new columns as Status_Y, Status_N and Status_NA columns. Status_Y will have 1 for all 'Y' values and 0 for all rest values. similarly, Status_N will have 1 for all 'N' values and 0 for rest.

![1hot dataframe]({{site.url}}/images/assets/labelencoding/onehotencoding.png)

<!-- Random Distribution vs Gaussian Distribution
Normal Curve - Probabilistic Distribution

Z-Score : Z-Score is just another measure of average score. A z-score of 1 means we are 1 standard deviation away from average. Z-Score of Mean is always equal to 0.

ANOVA
Null Hypothesis / Alternate Hypothesis
T-Test





We have to find solution for AX = b where X is the vector of unknowns.
$$
AX = b
X = (A^TA)^-1A^Tb
$$

ATA has an inverse only if columns of A re independent i.e. AX = 0 has only 1 solution and that is zero vector.

If AX = 0 has more than one solution, that means columns are dependent and hence that mean ATA is not invertible.

so for linear regression to work, A should have independent columns (features)


 -->

