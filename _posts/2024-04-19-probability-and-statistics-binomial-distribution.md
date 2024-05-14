---
layout: post
title:  "Probability and Statistics 1.3.0: Binomial distribution"
date:   2024-04-19 13:00:00
categories: machine-learning
tags: probability-and-statistics
excerpt: This post covers the basics of descriptive statistics, including central tendency, dispersion, and quartiles.
mathjax: true
---

* content
{:toc}

# Binomial distribution model
*Binomial* in definition is an expression (= a mathematical statement) that has two terms (= numbers or symbols) that are not the same. For example, $$ 4x + y $$ is a binomial.

*Binomial distribution* is a probability model that is associated with situations involving two outcomes, labeled as success or failure. 

# Properties
The following conditions must hold for a *binomial distribution*:   
- **A fixed number of trials involving a random process.** It is often denoted as n. 
- **The outcome of each trial can be classified into one of the two groups:** success and failure.
- **The trials are independent,** meaning the outcome of one trial does not influence the outcome of any other trail. For example, flipping a coin at N time does not change the result of the flipping at N+1 time.
- **The probability of success is the same for each trial.** Let p be the probability of success, which means 1-p is the probability of failure.

# Definition 
![Binomial-distribution](/assets/images/probability_and_statistics/binomial-definition.png)

# Describe a binomial distribution  

## Describe with the PMF
The probability mass function (PMF) for a binomial random variable X is 
<p align="center">$$P(X=k)=\binom{n}{k}p^k(1-p)^{n-k},   k=0,1,...,n$$</p>

where   
- n is the number of trials   
- k is the specified number of successes    
- n-k is the number of failures    
- p is the probability of success on any given trial   
- 1-p is the probability of failure on any given trial  

## Describe with the CDF
The cumulative density function (CDF) of X is the probability that X is less than or equal to any number x, and is denoted by F(x). For the binomial model, the cdf is

<p align="center"> $\displaystyle\sum\limits_{k=0}^{n}P(X=k)=\displaystyle\sum\limits_{k=0}^{n}\binom{n}{k}p^k(1-p)^{n-k}$</p>
