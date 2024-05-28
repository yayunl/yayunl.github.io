---
layout: post
title:  "Machine Learning 0.0.3: Introduction to Computer Vision"
date:   2024-05-28 14:00:00
categories: machine-learning 
tags: machine-learning
excerpt: This post describes how to create a simple computer vision neural network using the Fashion MNIST dataset.
mathjax: true
use_mermaid: true
---

* content
{:toc}

# The Data: Fashion MNIST
The Fashion MNIST dataset is a collection of 70,000 grayscale images of 10 different categories of clothing items. Each image is 28x28 pixels in size. The dataset is commonly used as a benchmark for machine learning algorithms in computer vision. The categories in the dataset are as follows:  
- 0 T-shirt/top
- 1 Trouser
- 2 Pullover
- 3 Dress
- 4 Coat
- 5 Sandal
- 6 Shirt
- 7 Sneaker
- 8 Bag
- 9 Ankle boot

Note: MNIST stands for _Modified National Institute of Standards and Technology_.

<strong>A closeup of an image from the Fashion MNIST dataset:</strong>  
![A Closeup](/assets/images/ML/003/closeup.png)  

Any image in teh dataset, like the one above, can be represented as a 28x28 matrix of pixel values. Each pixel value is an integer between 0 and 255, where 0 represents black and 255 represents white.
# TensorFlow high-level architecture
![TensorFlow high-level architecture](/assets/images/ML/002/tensorflow-architecture.png)

_Training_ is the process of creating machine learning models. It involves feeding the model with input data and the corresponding labels, and 
adjusting the model's parameters to minimize the difference between the predicted output and the actual output. 
For example, if you want a computer to recognize images of cats, you would train a model on a dataset of images of cats and non-cats.

Beyond creating models, TensorFlow also provides tools for _serving_ and _deploying_ models. _Serving_ is the process of making trained models available for
inference, which is the process of using a trained model to make predictions on new data. _Deploying_ is the process of making trained models available to end users.
TensorFlow provides APIs for serving, where you can provide model inference over an HTTP connection for cloud or web users.   

For models to run on mobile devices, TensorFlow provides _TensorFlow Lite_, a lightweight version of TensorFlow that is optimized for mobile and embedded devices such as Raspberry Pi.  

If you want to provide models to your browser, TensorFlow provides _TensorFlow.js_, a JavaScript library that allows you to run machine learning models in the browser or on Node.js.  

# Using TensorFlow  

## Installing TensorFlow in Python

```bash
pip install tensorflow-cpu
```

## Using TensorFlow in Google Colab
Google Colab is a free cloud service that provides a Jupyter notebook environment. It comes with TensorFlow pre-installed. Colab provides GPU and TPU backends so you 
can train models using state-of-the-art hardware for free.

![Google Colab](/assets/images/ML/002/colab.png)

## Getting started with TensorFlow

Here's the code to create a simple neural network using TensorFlow:

```python
import tensorflow as tf
import numpy as np
from tensorflow.keras import Sequential
from tensorflow.keras.layers import Dense

# Sequential is used to define layers. Inside the Sequential, you can define the layers of the neural network. 
#   In this example, we have only one layer `[Dense(units=1, input_shape=[1])]`.
# Dense is a layer type that connects every neuron in the previous layer to every neuron in the current layer.
#   The `units=1` argument specifies the number of neurons in the layer. In this case, we have only one neuron.
#   The `input_shape=[1]` argument specifies the shape of the input data. In this case, the input data is a single number.
model = Sequential([Dense(units=1, input_shape=[1])])

# The optimizer is the algorithm used to adjust the weights of the neural network during training to minimize the loss.
#   `sgd` stands for Stochastic Gradient Descent. It is a simple and widely used optimizer.
#   `loss='mean_squared_error'` specifies the loss function is the mean squared error. It is used to measure the difference between the predicted output and the actual output.
model.compile(optimizer='sgd', loss='mean_squared_error')

# Specify the input data and the corresponding output data. In this example, we are trying to learn the function y = 2x - 1.
xs = np.array([-1.0, 0.0, 1.0, 2.0, 3.0, 4.0], dtype=float)
ys = np.array([-3.0, -1.0, 1.0, 3.0, 5.0, 7.0], dtype=float)

# The `fit` method is used to train the model on the input data and the corresponding output data.
model.fit(xs, ys, epochs=500)

# The `predict` method is used to make predictions on new data. In this example, we are predicting the output for x = 10.
print(model.predict([10.0]))
```
The illustration of the above neural network is shown below:
![Neural Network](/assets/images/ML/002/nn.png)


# Conclusion
This post explains TensorFlow, an open source platform for machine learning and deep learning developed by Google. TensorFlow provides a comprehensive ecosystem of tools, libraries, and community resources that lets researchers and developers build and deploy machine learning models at scale. TensorFlow provides tools for training, serving, and deploying models, as well as APIs for serving models over HTTP connections, TensorFlow Lite for mobile and embedded devices, and TensorFlow.js for running models in the browser or on Node.js. TensorFlow is widely used in the machine learning community and is a powerful tool for building and deploying machine learning models.

# References
- Chapter 1 "Introduction to TensorFlow", "AI and Machine Learning for Coders: A Programmer's Guide to Artificial Intelligence", Laurence Moroney, 2021