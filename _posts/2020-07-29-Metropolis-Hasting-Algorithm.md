---
layout: post
title: Metropolis Hasting Algorithm
tag: [Study Notes]
category: Bayesian Statistics
---

Study Notes for Coursera Course: [Bayesian Statistics: Techniques and Models](https://www.coursera.org/learn/mcmc-bayesian-statistics/)) by Matthew Heiner.

Bayesian statistics allows us to calculate the posterior distribution using the likelihood function and the prior distribution. The posterior distribution is proportional to the likelihood function times the prior formulated by the following equation:
$$p(\theta) \propto g(\theta)$$ Where $p(\theta)$ is the posterior and $g(\theta)$ is the unnormalized likelihood x prior. The reason why we need algorithm like the Metropolis Hasting is that in more sophisticated settings, the denominator/normalizer is difficult to integrate, but we still want to be able to estimate the statistics of the posterior distribution, e.g., mean and variance.

The Metropolis Hasting algorithm uses a proposal distribution, and draw samples $\theta^\prime$ from this proposal distribution: 

$$\theta^\prime \sim q(\theta^\prime|\theta_{i-1})$$ 

This distribution shows that the drawing is a Markov chain, the probability of drawing a specific $\theta^\prime$ given the previous draw $\theta_{i-1}$. Based on some accept/reject criteria, all the accepted $\theta^\prime$s gives us simulated samples for the posterior distribution (? or just give us values around the mean with a normal distribution?). These samples converge to mean values that represent the mean for the posterior distribution.

The proposal distribution $q$ is not the actual posterior distribution of $p$. The accept/reject criteria are to correct for this error. The $q$ distribution usually used a normal distribution with the mean that is the $\theta^\prime$ previously drawn and a chosen standard deviation. The benefit of using a normal distribution is that in the accept/reject criteria the formula is simplified because normal distribution is symmetrical. Although one has to consider that the best $q$ should be similar to $p$. The lesson didn't mention anything about the best strategy of choosing $q$ (?), but from the simulation code, it seems like whatever distribution we choose for $q$, after a large number of iterations, the simulated $\theta^\prime$ centers around a mean value with some variance.


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyMzcyOTU0OTgsLTM4Njc1MzM5MSwxMD
cyNTQyODksMTA4MDIyNzMxMCwtMjA2NzU5Njg2OCwtOTk1NTEw
OTY4LC0xOTY5NTgwODU4LDk5ODIxNjU1NSwtMTg2NDk3NDc5Ni
wtMTg2NDk3NDc5NiwtMjUzMDY3ODAyXX0=
-->