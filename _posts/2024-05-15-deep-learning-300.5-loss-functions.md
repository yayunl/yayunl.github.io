---
layout: post
title:  "Deep Learning 3.0.0.5: Loss Functions"
date:   2024-05-16 10:00:00
categories: machine-learning deep-learning
tags: deep-learning
excerpt: This post discusses the loss functions used in deep learning.
mathjax: true
use_mermaid: true
---

* content
{:toc}


# Logistic Regression loss function $L(y, \hat{y})$
The _logistic loss function_, also known as the _cross-entropy loss function_, is commonly used in binary classification problems. 
It measures the difference between the predicted probability distribution and the actual distribution of the target variable. The formula for the logistic loss function is given by:
$$ L(y, \hat{y}) =  y \log(\hat{y}) + (1 - y) \log(1 - \hat{y}) $$   
where: 
- $y$ is the true label of the example,
- $\hat{y}$ is the predicted probability of the example belonging to the positive class.

## Logistic loss function explained
![logistic loss function](/assets/images/deep_learning/300_5/log_loss_explained.png)


# Cost function $J(w, b)$
![logistic loss function](/assets/images/deep_learning/300_5/log_loss_to_cost_function1.png)
![logistic loss function](/assets/images/deep_learning/300_5/log_loss_to_cost_function2.png)

# References   
1. [Andrew Ng's Neural Networks and Deep Learning Course](https://www.coursera.org/learn/neural-networks-deep-learning)