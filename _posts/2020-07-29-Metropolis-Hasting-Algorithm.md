---
layout: post
title: Metropolis Hasting Algorithm
tag: [Study Notes]
category: Baysian Statistics
---

Study Notes for Cousera Course: [Bayesian Statistics: Techniques and Models](https://www.coursera.org/learn/mcmc-bayesian-statistics/)) by Matthew Heiner.

Bayesian statistics allows us to caluculate the posterior distribution using the likelihood function and the prior distribution. The posterior distribution is proportional to the likelihood function times the prior formulated by the following equation:$$p(\theta) \propto g(\theta)$$ Where $p(\theta)$ is the posterior and $g(\theta)$ is the unormalized likelihood x prior. The reason why we need algorithm like the Metropolis Hasting is that in more sophisticated settings, the denorminator/normalizer is difficult to integrate, but we still want to be able to estimate the statistics of the posterior distribution, e.g., mean and variance.

The Metropolis Hasting algorithm uses a proposal distribution, and draw samples $\\theta$ from this proposal distribution: 
$$\theta^* \sim q(\theta^*|\theta_{i-1})$$ 
This distribution shows that the drawing is a markov chain, the probability of drawing a specific $\theta^*$ given the previous draw $\theta_{i-1}$. Based on some accept/reject criteria, all the accepted $\theta^*$s gives us simulated samples for the posterior distribution (? or just give us values around the mean with a normal distribution?). These samples converges to a mean values that represents the mean for the posterior distribution.

The proposal distribution $q$ is not the actual posterior distribution $p$. The accept/reject criteria is to correct for this error. The $q$ distribution ususally used a normal distribution with a mean and standard deviation around the $\theta^*$ drawn. The benefits of using a normal distribution is that in the accept/reject criteria the formular is simplified. Although one has to consider that the best $q$ should be simular to $p$. The lesson didn't mention anything about the best strategy of choosing $q$ (?), but from the simulation code, it seems like whatever distribution we choose for $q$, after a large number of iterations, the simulated $\theta^*$ centers around a value with some variance.


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwNjc1OTY4NjgsLTk5NTUxMDk2OCwtMT
k2OTU4MDg1OCw5OTgyMTY1NTUsLTE4NjQ5NzQ3OTYsLTE4NjQ5
NzQ3OTYsLTI1MzA2NzgwMl19
-->