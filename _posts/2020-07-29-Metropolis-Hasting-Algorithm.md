---
layout: post
title: MCMC-Metropolis Hasting
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

There are also two different types of Metropolis Hasting (MH) algorithm - independent MH and random walk MH. Independent MH draws from a fixed normal/uniform distribution that does not depend of the previous draw. Random walk MH use the previous draw $\theta^\prime$ as the proposal distribution. I am assuming that the random walk MH converges faster? Not sure what the benefits of each of them.

Just found that for independent MH, it is better to choose a proposal distribution that is very close to the actual posterior distribution. Though, I am not sure how because isn't that the original purpose of using the MH method because we want to approximate the posterior distribution through simulations? It seems like using random walk MH, we can choose some normal distribution to begin with and over time it will get to the target distribution. I think random walk MH  is more useful, although I guess it takes more time to run. 

The MH is able to converge to $p$ beacause it is utilizing the information from $g$. $g$ is known and derivable from the data and prior distribution we have, although it is hard to get the probability distribution for $p$ because the denorminator might be hard to integrate and therefore the posterior $p$ has no close form solution. Markov Chain Monte Carlo (MCMC) sampling methods like MH and Gibbs Sampling solved this problem by approximating the posterior distribution $p$ by using the information from $g$ through some accept/reject criteria.


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIxNDQyNTUwNjcsLTkyNTYyNzE0LC0xMz
AzODE1MjczLC0zODY3NTMzOTEsMTA3MjU0Mjg5LDEwODAyMjcz
MTAsLTIwNjc1OTY4NjgsLTk5NTUxMDk2OCwtMTk2OTU4MDg1OC
w5OTgyMTY1NTUsLTE4NjQ5NzQ3OTYsLTE4NjQ5NzQ3OTYsLTI1
MzA2NzgwMl19
-->