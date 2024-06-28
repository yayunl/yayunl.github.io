---
layout: post
title:  "Deep Learning 4.0.3: Case studies in CNN"
date:   2024-06-28 11:25:00
categories: machine-learning deep-learning
tags: CNN
excerpt: This post shows some case studies in CNN such as LeNet-5, AlexNet, VGG, ResNet, and GoogleNet.
mathjax: true
use_mermaid: true
---

* content
{:toc}

# Case studies
## LeNet-5
- LeNet-5 is a simple CNN architecture developed by Yann LeCun in 1998.
- It was designed to recognize handwritten digits.
- LeNet-5 consists of 7 layers:
  1. Convolutional Layer
  2. Pooling Layer
  3. Convolutional Layer
  4. Pooling Layer
  5. Fully Connected Layer
  6. Fully Connected Layer
  7. Output Layer
- Link to the paper: [Gradient-Based Learning Applied to Document Recognition](http://yann.lecun.com/exdb/publis/pdf/lecun-01a.pdf)

![LeNet-5](/assets/images/deep_learning/403/lenet-5.png)

## AlexNet
- AlexNet is a deep CNN architecture developed by Alex Krizhevsky, Ilya Sutskever, and Geoffrey Hinton in 2012.
- It won the ImageNet Large Scale Visual Recognition Challenge (ILSVRC) in 2012.
- AlexNet consists of 8 layers:
  1. Convolutional Layer
  2. Pooling Layer
  3. Convolutional Layer
  4. Pooling Layer
  5. Convolutional Layer
  6. Convolutional Layer
  7. Convolutional Layer
  8. Fully Connected Layer
- Link to the paper: [ImageNet Classification with Deep Convolutional Neural Networks](https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf)

![AlexNet](/assets/images/deep_learning/403/alexnet.png)

## VGG-16
- VGG-16 is a deep CNN architecture developed by the Visual Geometry Group (VGG) at the University of Oxford in 2014.
- It was the runner-up in the ImageNet Large Scale Visual Recognition Challenge (ILSVRC) in 2014.
- VGG-16 consists of 16 layers:
  1. Convolutional Layer [64 filters]
  2. Convolutional Layer [64 filters]
  3. Pooling Layer [Max Pooling]
  4. Convolutional Layer [128 filters]
  5. Convolutional Layer [128 filters]
  6. Pooling Layer [Max Pooling]
  7. Convolutional Layer [256 filters]
  8. Convolutional Layer [256 filters]
  9. Convolutional Layer [256 filters]
  10. Pooling Layer [Max Pooling]
  11. Convolutional Layer [512 filters]
  12. Convolutional Layer [512 filters]
  13. Convolutional Layer [512 filters]
  14. Pooling Layer [Max Pooling]
  15. Fully Connected Layer [4096 units]
  16. Fully Connected Layer [4096 units]
- Link to the paper: [Very Deep Convolutional Networks for Large-Scale Image Recognition](https://arxiv.org/abs/1409.1556)   

![VGG-16](/assets/images/deep_learning/403/vgg-16.png)


# Residual Networks (ResNet)
- Residual Networks (ResNet) is a deep CNN architecture developed by Kaiming He, Xiangyu Zhang, Shaoqing Ren, and Jian Sun in 2015.
- It won the ImageNet Large Scale Visual Recognition Challenge (ILSVRC) in 2015.
- ResNet introduces the concept of residual blocks, which allow for the training of very deep networks (e.g., 152 layers) without the vanishing gradient problem.
- ResNet consists of residual blocks that contain skip connections (shortcuts) that bypass one or more layers.
- Link to the paper: [Deep Residual Learning for Image Recognition](https://arxiv.org/abs/1512.03385)   

![ResNet](/assets/images/deep_learning/403/resnet-1.png)
![ResNet](/assets/images/deep_learning/403/resnet-2.png)

## Why Residual Networks work?
- Residual Networks work because they allow for the training of very deep networks without the vanishing gradient problem.
- The skip connections in residual blocks help to propagate the gradient through the network, making it easier to train deep networks.
- The skip connections also allow for the learning of identity mappings, which can help improve the performance of the network.

![ResNet](/assets/images/deep_learning/403/why-resnet-works.png)

# GoogleNet (Inception Networks)
- Inception Networks are deep CNN architectures developed by Christian Szegedy et al. at Google in 2014.
- The Inception architecture is designed to improve the efficiency and performance of deep networks by using multiple filter sizes in parallel.
- Inception Networks consist of Inception modules that contain multiple filter sizes (1x1, 3x3, 5x5) and pooling layers.
- The Inception architecture has been used in various applications, including image recognition and object detection.
- Link to the paper: [Going Deeper with Convolutions](https://arxiv.org/abs/1409.4842)

![GoogleNet](/assets/images/deep_learning/403/googlenet1.png)
![GoogleNet](/assets/images/deep_learning/403/googlenet2.png)

# References
- [Andrew Ng's C4W2L02 Classic Network](https://youtu.be/dZVkygnKh1M?feature=shared)