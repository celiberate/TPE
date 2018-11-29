---
layout: post
author: Shivam Sinha
title: Bias vs Variance
description: Understanding concept of Bias and Variance in ML Models
comments: true
quote: If you torture data long enough it will confess
---

 When your model predicts with a very high accuracy on training data, but performs differently with different test datasets (variance), you call your model to be over-fitting to a particular dataset.

 When your model predicts in a very generalized manner and pays little attention to data, you call your model to be over-simplified and not capturing true relationship(biased), this is known as under-fitting.


| underfit | good-fit | overfit|
|-------|--------|---------|
| ![underfit Function](/assets/LinearRegression/underfit.jpg) | ![goodfit Function](/assets/LinearRegression/goodfit.png) | red ![overfit Function](/assets/LinearRegression/overfit.jpg) |
|-------|--------|---------|
| high bias, low-variance | low bias, low variance | low bias, high variance |


 An ideal model should find the right balance between over-fitting (high variance) and under-fitting(high-bias) by consistent predictions with different datasets and capturing true relationship with the data. The goal of any supervised machine learning algorithm is to achieve low-bias and low-variance.

 Overfitting results in low training error and high test error, while underfitting results in high errors in both the training and test set.

 **Cross-Validations**











