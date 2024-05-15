---
layout: post
title:  "Deep Learning 1.0.0: The basics about the perceptron"
date:   2024-05-14 12:00:00
categories: machine-learning deep-learning
tags: deep-learning
excerpt: This post covers the basics about the concept of perceptron in deep learning.
mathjax: true
---

* content
{:toc}


# Evolution of Artificial Neurons

## Human Neurons
A human brain has billions of neurons. Neurons are interconnected nerve cells in the human brain that are involved in processing and transmitting chemical and electrical signals. Dendrites are branches that receive information from other neurons.

![Biological-Neuron](/assets/images/deep_learning/100/human-neurons.png)

Cell nucleus or Soma processes the information received from dendrites. Axon is a cable that is used by neurons to send information. Synapse is the connection between an axon and other neuron dendrites.

Let us discuss the rise of artificial neurons in the next section.

## Rise of Artificial Neurons
Researchers Warren McCullock and Walter Pitts published their first concept of simplified brain cell in 1943. This was called *McCullock-Pitts (MCP)* neuron. They described such a nerve cell as a simple logic gate with binary outputs.

Multiple signals arrive at the dendrites and are then integrated into the cell body, and, if the accumulated signal exceeds a certain threshold, an output signal is generated that will be passed on by the axon. In the next section, let us talk about the artificial neuron.


## Artificial Neuron

An artificial neuron is a mathematical function based on a model of biological neurons, where each neuron takes inputs, weighs them separately, sums them up and passes this sum through a nonlinear function to produce output.
![Artificial-Neuron](/assets/images/deep_learning/100/evolution.png)

# Perceptron
*Perceptron* was introduced by [Frank Rosenblatt](https://en.wikipedia.org/wiki/Frank_Rosenblatt) in 1957. He proposed a Perceptron learning rule based on the original MCP neuron. 
A Perceptron is an algorithm for supervised learning of binary classifiers. This algorithm enables neurons to learn and processes elements in the training set one at a time.

![Perceptron](/assets/images/deep_learning/100/perceptron.png)

## Components of Perceptron
A Perceptron consists of four main components:
1. **Input values or One input layer**: The input layer receives the input values.
2. **Weights and Bias**: Each input value is multiplied by a weight and then summed up. A bias is added to the sum.
3. **Net sum**: The sum of the weighted input values and bias is calculated.
4. **Activation function**: The net sum is passed through an activation function to produce the output.  Common activation functions used in perceptron include the *step function*, *sigmoid function*, *softmax function*, and *ReLU function*.
5. **Output**: The output of the perceptron is a single binary value, either 0 or 1, which indicates the class or category to which the input data belongs.

## Types of Perceptron

### Single-layer Perceptron 
A single-layer perceptron is a feedforward neural network with a single layer of output units. It can only learn linearly separable patterns. The activation function used in a single-layer perceptron is the step function.
![single-layer-perceptron](/assets/images/deep_learning/100/single-layer-perceptron.png)

### Multi-layer Perceptron
A multi-layer perceptron is a feedforward neural network with one or more hidden layers between the input and output layers. It can learn non-linear patterns. "Multi-layer" often refers to the *neural network* having more than one hidden layer. The activation function used in a multi-layer perceptron is usually the sigmoid function or the ReLU function.

![multi-layer-perceptron](/assets/images/deep_learning/100/multilayer-perceptron.png)