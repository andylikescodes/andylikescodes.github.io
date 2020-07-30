---
layout: post
title: Metropolis Hasting Algorithm
tag: [Study Notes]
category: Bayesian Statistics
---

Study Notes for Coursera Course: [Bayesian Statistics: Techniques and Models](https://www.coursera.org/learn/mcmc-bayesian-statistics/) by Matthew Heiner.

Bayesian statistics allows us to calculate the posterior distribution using the likelihood function and the prior distribution. The posterior distribution is proportional to the likelihood function times the prior formulated by the following equation:

$$p(\theta) \propto g(\theta)$$ 

Where $p(\theta)$ is the posterior and $g(\theta)$ is the unnormalized likelihood x prior. The reason why we need algorithm like the Metropolis Hasting is that in more sophisticated settings, the denominator/normalizer is difficult to integrate, but we still want to be able to estimate the statistics of the posterior distribution, e.g., mean and variance.

The Metropolis Hasting algorithm uses a proposal distribution, and draw samples $\theta^\prime$ from this proposal distribution: 

$$\theta^\prime \sim q(\theta^\prime|\theta_{i-1})$$ 

This distribution shows that the drawing is a Markov chain, the probability of drawing a specific $\theta^\prime$ given the previous draw $\theta_{i-1}$. Based on some accept/reject criteria, all the accepted $\theta^\prime$s gives us simulated samples for the posterior distribution (? or just give us values around the mean with a normal distribution?). These samples converge to mean values that represent the mean for the posterior distribution.

The proposal distribution $q$ is not the actual posterior distribution of $p$. The accept/reject criteria are to correct for this error. The $q$ distribution usually used a normal distribution with the mean that is the $\theta^\prime$ previously drawn and a chosen standard deviation. The benefit of using a normal distribution is that in the accept/reject criteria the formula is simplified because normal distribution is symmetrical. Although one has to consider that the best $q$ should be similar to $p$. The lesson didn't mention anything about the best strategy of choosing $q$ (?), but from the simulation code, it seems like whatever distribution we choose for $q$, after a large number of iterations, the simulated $\theta^\prime$ centers around a mean value with some variance.

There are also two different types of Metropolis Hasting (MH) algorithm - independent MH and random walk MH. Independent MH draws from a fixed normal/uniform distribution that does not depend of the previous draw. 


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTYyMDAzMDIzOSwtMTMwMzgxNTI3MywtMz
g2NzUzMzkxLDEwNzI1NDI4OSwxMDgwMjI3MzEwLC0yMDY3NTk2
ODY4LC05OTU1MTA5NjgsLTE5Njk1ODA4NTgsOTk4MjE2NTU1LC
0xODY0OTc0Nzk2LC0xODY0OTc0Nzk2LC0yNTMwNjc4MDJdfQ==

-->