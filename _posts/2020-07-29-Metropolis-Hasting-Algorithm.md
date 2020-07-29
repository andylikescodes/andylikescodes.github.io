---
layout: post
title: Metropolis Hasting Algorithm
tag: [Study Notes]
category: Baysian Statistics
---

Study Notes for Cousera Course: [Bayesian Statistics: Techniques and Models](https://www.coursera.org/learn/mcmc-bayesian-statistics/)) by Matthew Heiner.

Bayesian statistics allows us to caluculate the posterior distribution using the likelihood function and the prior distribution. The posterior distribution is proportional to the likelihood function times the prior formulated by the following equation:
$$p(\theta) \propto g(\theta)$$ 
Where $p(\theta)$ is the posterior and $g(\theta)$ is the unormalized likelihood x prior. The reason why we need algorithm like the Metropolis Hasting is that in more sophisticated settings, the denorminator/normalizer is difficult to integrate, but we still want to be able to estimate the statistics of the posterior distribution, e.g., mean and variance.

The M


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NTE3NDc2NjBdfQ==
-->