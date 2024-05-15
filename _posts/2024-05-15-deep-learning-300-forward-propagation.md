---
layout: post
title:  "Deep Learning 3.0.0: Forward Propagation"
date:   2024-05-15 13:00:00
categories: machine-learning deep-learning
tags: deep-learning
excerpt: This post discusses about the forward propagation process of a neural network.
mathjax: true
---

* content
{:toc}


# Understanding Forward Propagation
Forward propagation is the process of moving the input data through the neural network to produce an output. 
The input data is multiplied by the weights and biases, and passed through the activation function to produce the output.  
This process is repeated for each layer in the neural network until the final output is produced.
The following diagram shows the computation of a feedforward neural network:   

![feedforward neural network](/assets/images/deep_learning/300/forward-pass.png)

# Flow of Forward Propagation
{% mermaid %}
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
{% endmermaid %}
