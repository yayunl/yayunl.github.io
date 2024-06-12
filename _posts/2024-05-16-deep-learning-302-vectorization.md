---
layout: post
title:  "Deep Learning 3.0.2: Vectorization"
date:   2024-05-16 18:00:00
categories: machine-learning deep-learning
tags: deep-learning
excerpt: This post discusses about the vectorization process in deep learning. Python code implementation is also provided.
mathjax: true
use_mermaid: true
---

* content
{:toc}

# What is vectorization?
_Vectorization_ is the process of converting a mathematical operation into a vector or matrix operation.
In the context of deep learning, vectorization is used to speed up the computation of neural networks by performing operations on multiple inputs simultaneously.

# Vectorization Demo
![vectorization](/assets/images/deep_learning/302/vectorization_demo.png)

![vectorization](/assets/images/deep_learning/302/vectorization_demo_2.png)

Note: Avoid using explicit for-loops in Python when possible, as they are slow compared to vectorized operations.
![vectorization](/assets/images/deep_learning/302/avoid_forloop.png)

# Vectorization Examples

![Example.png](/assets/images/deep_learning/302/example.png)

![Example2.png](/assets/images/deep_learning/302/example2.png)

![Example3.png](/assets/images/deep_learning/302/example3.png)


# References
- [Andrew Ng's Neural Networks and Deep Learning Course](https://www.coursera.org/learn/neural-networks-deep-learning)