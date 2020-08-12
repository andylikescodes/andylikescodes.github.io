---
layout: post
title: Study Notes for Causal Inference in Statistics: A Primer (Pearl, 2016)
tag: [Paper Review]
category: Causal Inference
---


This post is a review of the book: Causal Inference in Statistics: A Primer (Pearl, 2016)

Under Pearl's framework, causal inference can be carried out using the do calculas. For example, if we want to measure the average causal effect (ACE), we usually want to estimate 

$$P(Y=1||do(X=1))-P(Y=1||do(X=0))$$

Therefore, we would like to estimate the distribution $$P(Y||do(X=x))$$

However, $P(Y||do(X=x))$ is a manipulated model, which removes all arrows pointed $X$ from its paranets or stratified over the variables that meets the back-door criteria, i.e., 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0MTQzODYyNCwxMjk3NjgwMl19
-->