---
layout: post
title: Study Note - Causal Inference in Statistics A Primer
tag: [Study Notes]
category: Causal Inference
---

This post is a review of the book: Causal Inference in Statistics: A Primer (Pearl, 2016)

Under Pearl's framework, causal inference for intervention can be carried out using the do calculas. For example, if we want to measure the average causal effect (ACE), we usually want to estimate 

$$P(Y=1|do(X=1))-P(Y=1|do(X=0))$$

Therefore, we would like to estimate the distribution 

$$P(Y|do(X=x))$$

$P(Y|do(X=x))$ is a manipulated model, which removes all arrows pointed $X$ from its paranets or stratified over the variables that meets the back-door criteria, i.e., $P(Y=y|do(X)) = \sum_{z}P(Y=y|X=x, Z=z)P(Z=z)$. This formula is derived using the unchanged conditional probability after the model is manipulated from the original one, therefore the conditional distribution can be directly estimated from the data. Therefore, the causal effect can be calculated using the observational data.

 


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1NTU1NzgzNjksLTE0MTgzMjY5NTIsMT
I5NzY4MDJdfQ==
-->