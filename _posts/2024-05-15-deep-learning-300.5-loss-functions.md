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


# Logistic Regression cost function
The _logistic loss function_, also known as the _cross-entropy loss function_, is commonly used in binary classification problems. It measures the difference between the predicted probability distribution and the actual distribution of the target variable. The formula for the logistic loss function is given by:
$$ L(y, \hat{y}) = -\frac{1}{N} \sum_{i=1}^{N} y_i \log(\hat{y}_i) + (1 - y_i) \log(1 - \hat{y}_i) $$
where: 
- $y_i$ is the true label of the $i$-th example,
- $\hat{y}_i$ is the predicted probability of the $i$-th example belonging to the positive class,
- $N$ is the total number of examples.

## Cost function $J(w, b)$
![logistic loss function](/assets/images/deep_learning/300_5/log_loss_andrew.png)
Source: [Andrew Ng's Neural Networks and Deep Learning Course](https://www.coursera.org/learn/neural-networks-deep-learning)