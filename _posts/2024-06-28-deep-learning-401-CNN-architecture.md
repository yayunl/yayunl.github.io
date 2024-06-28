---
layout: post
title:  "Deep Learning 4.0.2: The Convolution Layer"
date:   2024-06-28 12:20:00
categories: machine-learning deep-learning
tags: CNN
excerpt: This post explains the convolution layer in CNN.
mathjax: true
use_mermaid: true
---

* content
{:toc}

# Convolution Layer
The convolution layer is the first layer in a Convolutional Neural Network (CNN). It is responsible for extracting features from the input image. The convolution layer consists of a set of filters that are convolved with the input image to produce feature maps. Each filter is a small matrix that is applied to the input image using a sliding window. The filter is moved across the input image, and at each position, the dot product of the filter and the input image is computed to produce a single value in the feature map. This process is repeated for each filter in the convolution layer to produce multiple feature maps.

# Illustration of CNN Architecture
![Convolution-layer](/assets/images/deep_learning/402/convolution-layer.png)


# References
- [StatQuest: Neural Networks Part 8: Image Classification with Convolutional Neural Networks (CNNs)](https://youtu.be/HGwBXDKFk9I)