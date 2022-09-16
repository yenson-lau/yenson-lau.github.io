+++
date = 2022-09-12T21:01:58-04:00
title = "Notes on BERT"
description = ""
slug = ""
authors = []
tags = []
categories = []
externalLink = ""
series = []
draft = true
+++

## What does BERT do?

In short,

> BERT turns an input sequence of non-contextual token embeddings, and outputs a contextualized sequence of token representations.

but there are quite a few things to unpack in that statement:

1. BERT is a (sub-)word embedding, as each token in the input sequence is represented using a single vector in the output sequence.

2. At the same time, BERT is different from a non-contextual word embedding such as Word2Vec, since the output representation given to each token is dependent on its neighboring tokens, i.e. its context.

3. However, since the input sequence of token embeddings are trained jointly with the rest of the model, and doesn't yet depend on context, the input layer of BERT can be seen as a non-contextual word embedding similar to Word2Vec.


