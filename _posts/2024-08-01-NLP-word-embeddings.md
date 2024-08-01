---
layout: post
title:  "Natural Language Processing 0.0.2: Word Embeddings"
date:   2024-08-01 8:00:00
categories: NLP deep-learning
tags: word-embeddings
excerpt: This post discusses word embeddings and the methods of using word embeddings.
mathjax: true
use_mermaid: true
---

* content
{:toc}

# Word Embeddings
A common way to associate a vector with a word is the use of dense _word vectors_, also called _word embeddings_. The following is the comparison between
_one-hot_ word vectors and _word embeddings_:  

**Word vectors obtained via one-hot encoding**
* Binary, sparse, and high-dimensional (same dimensionality as the number of words in the vocabulary).
* Obtained via one-hot encoding.

**Word Embeddings**
* Low-dimensional floating-point vectors.
* Learned from data.

![embeddings](/assets/images/NLP/002/embeddings_vs_onehot.png)  


# Methods of Obtaining Word Embeddings

## Learning Word Embeddings with Embedding Layer

We can use the _Embedding_ layer offered by Keras to create an embedding layer which can map word index (one-hot encoding) to vector representation. 
```python
from keras.layers import Embedding
embedding_layer = Embedding(input_dim=1000, output_dim=64)
```

The following picture shows how a 1000-dim word index can be mapped to a N-dim vector representation.  
![vector-repre](/assets/images/NLP/002/vector-repre.png)

### Code example 
Github word embeddings: [link](https://github.com/yayunl/colab-code/blob/main/word_embeddings.ipynb)


## Using _pretrained word embeddings_
Instead of learning word embeddings from scratch, we can use pretrained word embeddings. 
The most famous pretrained word embeddings are word2vec, GloVe, and FastText.   
* _word2vec_ was developed by Tomas Mikolov in an internship project at Google in 2013. 
* _GloVe_, which stands for Global Vectors for Word representation, was developed by Stanford University in 2014. The data used for the training is from Wikipedia and Common Crawl data.
* _FastText_ was developed by Facebook in 2016.

### Code example
Using GloVe as the pretrained word embeddings: [link](https://github.com/yayunl/colab-code/blob/main/word_embeddings_from_raw.ipynb)



# References
- Deep Learning with Python by Francois Chollet, Chapter 6