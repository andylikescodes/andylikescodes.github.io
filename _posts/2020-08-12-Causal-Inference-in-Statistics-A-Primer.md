---
layout: post
title: MCMC - Gibbs Sampling
tag: [Study Notes]
category: Bayesian Statistics
---

This post is a review of the book: Causal Inference in Statistics: A Primer (Pearl, 2016)

Under Pearl's framework, causal inference for intervention can be carried out using the do calculas. For example, if we want to measure the average causal effect (ACE), we usually want to estimate 

$$P(Y=1||do(X=1))-P(Y=1||do(X=0))$$

Therefore, we would like to estimate the distribution $$P(Y||do(X=x))$$

However, $P(Y||do(X=x))$ is a manipulated model, which removes all arrows pointed $X$ from its paranets or stratified over the variables that meets the back-door criteria, i.e., $P(Y=y||do(X))$
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ4MzU3NzE5OSwtMTQxODMyNjk1MiwxMj
k3NjgwMl19
-->