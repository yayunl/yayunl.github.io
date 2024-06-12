---
layout: post
title:  "Deep Learning 2.0.0: Neural Networks"
date:   2024-05-15 12:00:00
categories: machine-learning deep-learning
tags: nueral-networks
excerpt: This post covers the basics about the neural networks.
mathjax: true
---

* content
{:toc}


# What is a Neural Network?
A _neural network_ is a computing model whose layered structure resembles the networked structure of neurons in the brain. 
It features interconnected processing elements called neurons that work together to produce an output function. Neural networks are made of input and output layers/dimensions, and in most cases, they also have a hidden layer 
consisting of units that transform the input into something that the output layer can use.

# Types of Neural Networks
There are several types of neural networks, each with its unique architecture and application. Some of the most common types include:
1. **Feedforward Neural Networks**: These are the simplest type of neural networks, where the data flows in one direction, from the input layer to the output layer.
2. **Recurrent Neural Networks (RNNs)**: These networks have connections that form a directed cycle, allowing information to persist.
3. **Convolutional Neural Networks (CNNs)**: These networks are designed to process data that has a grid-like topology, such as images.
4. **Generative Adversarial Networks (GANs)**: These networks consist of two neural networks, a generator and a discriminator, that compete against each other to generate new data.

# Feedforward Neural Networks
This is the most basic and common type of architecture; here the information travels in only one direction from input to output. It consists of an input layer; an output layer and in between, we have some hidden layers. If the hidden layer is more than one then that network is called a deep neural network.
![Feedforward Neural Network](/assets/images/deep_learning/200/feed-forward.png)

# Recurrent Neural Networks (RNNs)
This is a more complex type of network; this artificial neural network is commonly used in speech recognition and natural language processing (NLP). RNNs perform the same task for every element of a sequence, with the output being depended on the previous computations.
![Recurrent Neural Network](/assets/images/deep_learning/200/RNN.png)

# Convolutional Neural Networks (CNNs)
A _CNN_ has several layers through which data is filtered into categories. CNNs have proven to be very effective in areas such as **image recognition**, **text language processing**, and **classification**. A convolutional neural network is made of an input layer, an output layer and a hidden layer that includes multiple convolutional layers, pooling layers, fully connected layers, and normalization layers.
![Convolutional Neural Network](/assets/images/deep_learning/200/CNN.png)