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

$$P(Y\|do(X=x))$$ is a manipulated model, which removes all arrows pointed $X$ from its paranets or stratified over the variables that meets the back-door criteria, i.e., $$P(Y=y \| do(X)) = \sum_{z}P(Y=y \| X=x, Z=z)P(Z=z)$$. This formula is derived using the unchanged conditional probability after the model is manipulated from the original one, therefore the conditional distribution can be directly estimated from the data. Therefore, the causal effect can be calculated using the observational data.

The front-door criteria is also another way of calculating the causal effect of $X$ on $Y$ given a mediating variable $Z$, which does not depend on any confounding variables. Using the back-door criteria, we can estimate the causal effect of $Z$ on $Y$. We can also estimate the causal effect of $X$ on $Z$ directly because we know that it is a mediating variable and does not depend of other variables. When we aggregate the causal effect of $X$ on $Z$ and $Z$ on  $Y$, then we get the causal effect of $X$ on $Y$.

The graphical models also allow us to use the trancated product rule to calculate the manipulated model after intervention. For example:

$$P(z, y| do(x))=P_m(z)P_m(y|x,z)=P(z)P(y|x,z)$$

and $$P(y|do(x)) = \sum_zP(z)P(y|x,z)$$

The adjustment formula is straight forward to use while estimating causal effects, however, the adjustment procedure might have practical issues, as we adjust for many variables in $Z$, the data within each $Z=z$ cell might be too small to estimate  The book also talks about another, more subtle procedure that overcomes the practical difficulties of 
 


<!--stackedit_data:
eyJoaXN0b3J5IjpbNjc2ODY1OTM3LC0xODU1NTI2NzUwLC0xNz
I5MDU2ODY4LC0xNTU1NTc4MzY5LC0xNDE4MzI2OTUyLDEyOTc2
ODAyXX0=
-->