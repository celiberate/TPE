---
layout: article
author: Shivam Sinha
title: Bias vs Variance
description: Understanding concept of Bias and Variance in ML Models
comments: true
quote: “Numbers have an important story to tell. They rely on you to give them a voice.” — Stephen Few
---
Hyperparameters - Hyperparameters are the parameters that are used to tune the performance of our model.

Train/Validation/Test Set data

 Many times when your machine learning model is not performing well, it is mostly due to a high-bias(underfitting) or high-variance (overfitting) problem.

 When your model predicts with a very high accuracy on training data, but performs differently with test datasets, you call your model to be over-fitting to a particular dataset.

 When your model predicts in a very generalized manner and pays little attention to data, you call your model to be over-simplified and not capturing true relationship, this is known as under-fitting.

Overfitting generally results in low training error and high test error, while underfitting results in high errors in both the training and test set.

| underfit | good-fit | overfit|
|-------|--------|---------|
| ![underfit Function](/assets/LinearRegression/underfit.jpg) | ![goodfit Function](/assets/LinearRegression/goodfit.png) | red ![overfit Function](/assets/LinearRegression/overfit.jpg) |
|-------|--------|---------|
| high bias, low-variance | low bias, low variance | low bias, high variance |


 An ideal model should find the right balance between over-fitting (high variance) and under-fitting(high-bias) by consistent predictions with different datasets and capturing true relationship with the data. The goal of any supervised machine learning algorithm is to achieve low-bias and low-variance.

***Metrics***
Impact of degree of polynomials
Impact of lambda
Impact of training examples
 

 **Higher degree Polynomials** - fixes high bias
 **Decrease regularization paramter lambda** fixes high bias
 **Add more features** fixes high bias

 **Increase Regularization parameter lambda** fixes high variance
 **Take more training samples** fixes high variance
 **Try with small set of features** fixes high variance













