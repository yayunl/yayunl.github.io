---
layout: post
title:  "Natural Language Processing 0.0.1: Tokenization"
date:   2024-07-26 8:00:00
categories: NLP deep-learning
tags: NLP tokenization
excerpt: This post covers tokenization and building a vector representation of a statement.
mathjax: true
use_mermaid: true
---

* content
{:toc}

# Tokenization

A _tokenizer_ breaks unstructured data into chunks of information that can be counted as discrete elements. The simplest way to tokenize a sentence is to use whitespace within
a string as the "delimiter" of words. In Python, you can use the function _split()_ to do this:
```python
sentence = "The quick brown fox jumps over the lazy dog"
words = sentence.split()
```

## _one-hot vectors_
```python 
import numpy as np
token_seq = str.split("Thomas Jefferson began building Monticello at the age of 26.")
vocab = sorted(set(token_seq))
num_tokens = len(token_seq)
vocab_size = len(vocab)
print("Number of tokens: %s, vocab size: %s" %(num_tokens, vocab_size))
# print
# Number of tokens: 10, vocab size: 10
onehot_vectors = np.zeros((num_tokens, vocab_size), int)
# For each word in the sentence, makr the column for that word in the vocabulary with a `1`.
for i, word in enumerate(token_seq):
    onehot_vectors[i, vocab.index(word)] = 1
onehot_vectors
#array([[0, 0, 0, 1, 0, 0, 0, 0, 0, 0], <- Thomas
       # [0, 1, 0, 0, 0, 0, 0, 0, 0, 0], <- Jefferson
       # [0, 0, 0, 0, 0, 0, 1, 0, 0, 0],
       # [0, 0, 0, 0, 0, 0, 0, 1, 0, 0],
       # [0, 0, 0, 0, 0, 0, 0, 0, 0, 1],
       # [0, 0, 1, 0, 0, 0, 0, 0, 0, 0],
       # [0, 0, 0, 0, 0, 1, 0, 0, 0, 0],
       # [0, 0, 0, 0, 0, 0, 0, 0, 0, 1],
       # [0, 0, 0, 0, 1, 0, 0, 0, 0, 0],
       # [0, 0, 0, 0, 0, 0, 0, 0, 1, 0],
       # [1, 0, 0, 0, 0, 0, 0, 0, 0, 0]]) <-- 26.
```


## Binary bag-of-words vectors
A bag-of-words vector is a binary vector where each element is 1 if the word is present in the sentence.
```python
sentence_bow = {}

token_seq = str.split("Thomas Jefferson began building Monticello at the age of 26.")
for token in token_seq:
    sentence_bow[token] = 1
    
sentence_bow
#{'Thomas': 1,
 # 'Jefferson': 1,
 # 'began': 1,
 # 'building': 1,
 # 'Monticello': 1,
 # 'at': 1,
 # 'the': 1,
 # 'age': 1,
 # 'of': 1,
 # '26.': 1}
``` 

##  _n_-grams
A string of words can be split into pairs, triplets, quadruplets, and even quintuplets of tokens. Pairs of words are 2-grams, triplets are 3-grams, and so on. 
Using n-grams allows us to create a vector representation of a statement. All possible n-grams of words will be included in the vocabulary. However, depending on the frequency of the n-grams, some 
n-grams that rarely occur will be omitted from the vocabulary.

# References
- Natural Language Processing in Action - Understanding, analyzing, and generating text with Python by Hobson Lane, Cole Howard, and
Hannes Max Hapke