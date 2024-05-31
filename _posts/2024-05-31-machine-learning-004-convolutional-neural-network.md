---
layout: post
title:  "Machine Learning 0.0.4: Introduction to Convolutional Neural Network (CNN)"
date:   2024-05-31 14:00:00
categories: machine-learning 
tags: machine-learning
excerpt: This post explains the Convolutional Neural Network (CNN) and its applications in computer vision.
mathjax: true
use_mermaid: true
---

* content
{:toc}

# Introduction
A Convolutional Neural Network (CNN) is a type of neural network that is designed to process data that has a grid-like topology, such as images. 
CNNs are widely used in computer vision tasks such as image classification, object detection, and image segmentation. 
In this post, we will explain the architecture of a CNN and how it works.


# Convolutions
Before we dive into CNNs, let's first understand the concept of _convolutions_. 
A convolution is an operation that takes two functions $f$ and $g$ and produces a third function that represents how the shape of $g$ is modified by $f$. 

The convolution can be explained by sliding the _kernel_ or _filter_ by a given strikes of $k$ over the input data $x$ and computing the dot product of the slided area of the input data and the filter $w$.
The computation of the dot product is simply the element-wise multiplication of the two matrices and then summing the results. The result is then stored in the output matrix $y$.
When the _filter_ is slided over the entire input data, the output matrix $y$ is produced and is considered as the output of the convolution operation.  

![Convolution](/assets/images/ML/004/convolution2.png)

## Impact of applying a filter
The filter $w$ is used to detect certain patterns in the input data $x$. For example, a filter can be used to detect vertical lines, horizontal lines, or edges in an image.

For example, a filter with negative values on the left, positive values on the right, and zeros in the middle will end up removing most of the information from the image
except for vertical lines, as shown in the figure below.
![Vertical Line Detection](/assets/images/ML/004/detect-vertical.png)

Similarly, a filter with negative values on the top, positive values on the bottom, and zeros in the middle will end up removing most of the information from the image
except for horizontal lines, as shown in the figure below.
![Horizontal Line Detection](/assets/images/ML/004/detect-horizontal.png)

By applying different filters to the input data, we can extract different _features_ from the data. That's why the output of the convolution operation is called a _feature map_.
These features can then be used to build more complex models that can recognize objects in images. 


## Weights and biases
In the context of CNNs, a _filter_ is a _weight_ as we discussed in the previous post on neural networks. The goal of training a CNN is to find the optimal _filters_ that can extract the most useful features from the input data
to make accurate predictions. The _biases_ are also used in CNNs to shift the output of the convolution operation by a certain amount.

![Weights and Biases](/assets/images/ML/004/bias.png)

# Padding
When applying a convolution operation to an image, the output size of the feature map is smaller than the input size. 
This is because the filter cannot be applied to the edges of the image.


# References
- Chapter 3: Going Beyond the Basics: Detecting Features in Images, AI and Machine Learning for Coders, by Laurence Moroney, 2021, O'Reilly Media, Inc.