---
layout: post
title:  "Probability and Statistics 1.1.0: Descriptive Statistics"
date:   2024-04-18 12:00:00
categories: machine-learning
tags: probability-and-statistics
excerpt: This post covers the basics of descriptive statistics, including central tendency, dispersion, and quartiles.
mathjax: true
---

* content
{:toc}

# Central tendency  
To measure the central tendency of a data set, we often use the arithmetic mean, the median, and the mode.

## Mean
If we are given a set of n numbers, x1, x2,..., xn, then the *mean*, often denoted by µ, is given by 
$$
\mu = \frac{1}{n} \sum_{i=1}^{n} x_i
$$

## Median

The *median* is the value where half of the values of x1 , x2 , … , xn are larger than the median, and half of the values of x1 , x2 , … , xn are smaller than the median.


Finding the *median* of a data set with n ordered data points:  
- If n is an odd number, then the median is the data point located exactly in the middle of the set. This can be found in location $$ \frac{n+1}2 $$ of your set. 
- If n is an even number, then the median is the average of the two middle terms of the ordered set. These can be found in locations $$ \frac{n}2 $$ and $$ \frac{n}2+1 $$.


## Mode

The *mode* of a data set is the value that occurs most often, or in other words, has the most probability of occurring. Sometimes we can have two, three, or more values that have relatively large probabilities of occurrence. 
In such cases, we say that the distribution is bimodal, trimodal, or multimodal, respectively.


# Dispersion/Scatter
We measure the dispersion or scatter of the values of a data set about the *mean* of the data set. Two measures of dispersions that are usually used are called the **variance**($$ \sigma^2 $$) and **standard deviation**($$ \sigma $$).


## Variance $$ \sigma^2 $$

The *variance* is denoted by $$ \sigma^2 $$($$ \sigma $$ is the Greek letter sigma)

Note: It is widely accepted to divide the variance by (n-1) as opposed to n. As n gets large, the difference between divided by (n-1) and n becomes minimal. 


## Standard deviation $$ \sigma $$

The *standard deviation* can be taken by taking the square root of the variance, and is denoted by $$ \sigma $$.


# Quartiles

## 1st and 3rd quartiles

The 25th percentile is often thought of as the median of the scores below the median, and the 75th percentile is often thought of as the median of the scores above the median. 
The 25th percentile is called the *first quartile*, while the 75th percentile is called the *third quartile*. As you can imagine, the median is also known as the *second quartile*.