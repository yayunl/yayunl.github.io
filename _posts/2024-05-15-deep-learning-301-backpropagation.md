---
layout: post
title:  "Deep Learning 3.0.1: Backpropagation"
date:   2024-05-16 14:00:00
categories: machine-learning deep-learning
tags: deep-learning
excerpt: This post discusses about the back propagation process of a neural network. Python code implementation is also provided.
mathjax: true
use_mermaid: true
---

* content
{:toc}


# Understanding Backpropagation
_Backpropagation_ is the process of updating the weights and biases of a neural network during training. 
As it's shown in the following diagram, backpropagation involves calculating the error between the predicted output and the actual output (shown in step 2), 
and then using this error to update the weights and biases of the network (step 3). 
This process is repeated for each layer in the network until the error is minimized.

<p align="center">![backpropagation](/assets/images/deep_learning/301/backpropagation.png)</p>

# Steps in Backpropagation
The backpropagation process in a neural network involves the following steps:
1. Calculate the error: The error between the predicted output and the actual output is calculated using a loss function.
2. Calculate the gradient: The gradient of the loss function with respect to the weights and biases is calculated using the chain rule of calculus.
3. Update the weights and biases: The weights and biases of the network are updated using the gradient descent algorithm to minimize the error.

## Flowchart of Backpropagation
<div class="mermaid"> 
stateDiagram-v2
    X: Update weights and biases (i.e. W-=learningRate*dW)
    S1 --> X: Gradient descent
    A --> S1: dX, dW, dB
    S1: Input layer
    A: Hidden layers
    B --> A: dY
    A --> A: Repeat for each layer
    note left of A
            downstream gradient=local gradient * upstream gradient
    end note
    state A {
      b --> a:dh
      a: Weighted sum
      b: Activation function
    }
    B: Output layer
    C --> B: dL
    C: Loss function

</div>

# Calculating gradients
The gradients of the loss function with respect to the weights and biases are calculated using the chain rule of calculus. 
A typical method is the **mathematical technique** using the chain rule. This approach needs lots of matrix calculus and is prone to errors. It is not easy to implement for complex neural networks.
A better approach is to use the **computational graph** method. This method is more intuitive and easier to implement.

## Computational graph method (CGM)
There are three main steps involved in calculating the gradients using the **computational graph method**:
1. Calculate the _local gradient_: The local gradient is the derivative of the output with respect to its inputs.
2. Inherit the _upstream gradient_: The upstream gradient is inherited and is already calculated in the previous layer. 
3. _Multiply_ the local gradient by the upstream gradient to get the downstream gradient. This is according to the chain rule of calculus.   

**Note**: The calculation of the gradients is done in the reverse order of the _forward propagation_ process. Hence, the process is called _backpropagation_.

## Explain CGM with a simple example
Consider a simple example as follows:
$$
f(x,y,z) = (x+y)z
$$
We want to calculate the gradient of f with respect to x, y, and z: dx, dy, dz.  

### Calculating $ \frac{df}{df} $
![dfdf](/assets/images/deep_learning/301/dfdf.png)

### Calculating $ \frac{df}{dz} $
![dfdz](/assets/images/deep_learning/301/dfdz.png)

### Calculating $ \frac{df}{dq} $   
![dfdq](/assets/images/deep_learning/301/dfdq.png)

### Calculating $ \frac{df}{dx} $   
![dfdx](/assets/images/deep_learning/301/dx.png)  

### Calculating $ \frac{df}{dy} $   
![dfdy](/assets/images/deep_learning/301/dfdy.png)


## General formula  
The general formula for calculating the gradients using the computational graph method is as follows:
<p align="center">$d_{downstream}=d_{local}\times d_{upstream}$</p>  

![general formula](/assets/images/deep_learning/301/general-rule.png)    

## Other examples  
![other examples](/assets/images/deep_learning/301/other-examples.png)    

![other examples2](/assets/images/deep_learning/301/other-examples-2.png)  

## Patterns in gradient flow  
![patterns in gradient flow](/assets/images/deep_learning/301/gradient-pattern.png)  


## Code Implementation
The following Python code snippet demonstrates the backpropagation process in a neural network for a simple example:
```python
x = 3 # example values
y = -4

# forward pass
sigy = 1.0 / (1 + math.exp(-y)) # sigmoid in numerator   #(1)
num = x + sigy # numerator                               #(2)
sigx = 1.0 / (1 + math.exp(-x)) # sigmoid in denominator #(3)
xpy = x + y                                              #(4)
xpysqr = xpy**2                                          #(5)
den = sigx + xpysqr # denominator                        #(6)
invden = 1.0 / den                                       #(7)
f = num * invden # done!                                 #(8)

# compute backpropagation
# backprop f = num * invden
dnum = invden # gradient on numerator                             #(8)
dinvden = num                                                     #(8)
# backprop invden = 1.0 / den 
dden = (-1.0 / (den**2)) * dinvden                                #(7)
# backprop den = sigx + xpysqr
dsigx = (1) * dden                                                #(6)
dxpysqr = (1) * dden                                              #(6)
# backprop xpysqr = xpy**2
dxpy = (2 * xpy) * dxpysqr                                        #(5)
# backprop xpy = x + y
dx = (1) * dxpy                                                   #(4)
dy = (1) * dxpy                                                   #(4)
# backprop sigx = 1.0 / (1 + math.exp(-x))
dx += ((1 - sigx) * sigx) * dsigx # Notice += !! See notes below  #(3)
# backprop num = x + sigy
dx += (1) * dnum                                                  #(2)
dsigy = (1) * dnum                                                #(2)
# backprop sigy = 1.0 / (1 + math.exp(-y))
dy += ((1 - sigy) * sigy) * dsigy                                 #(1)
```
Code reference: [CS231n-optimization-2](https://cs231n.github.io/optimization-2/)  

# Conclusion
> - We developed intuition for what the gradients mean, how they flow backwards in the circuit, and how they communicate which part of the circuit should increase or decrease and with what force to make the final output higher. 
> - We discussed the importance of **staged computation** for practical implementations of backpropagation. You always want to break up your function into modules for which you can easily derive local gradients, and then chain them with chain rule. Crucially, you almost never want to write out these expressions on paper and differentiate them symbolically in full, because you never need an explicit mathematical equation for the gradient of the input variables. _Hence, decompose your expressions into _stages_ such that you can differentiate every stage independently (the stages will be matrix vector multiplies, or max operations, or sum operations, etc.) and then backprop through the variables one step at a time._

# References
- [CS231n-optimization-2](https://cs231n.github.io/optimization-2/)