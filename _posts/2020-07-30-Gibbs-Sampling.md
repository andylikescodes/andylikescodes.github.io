---
layout: post
title: MCMC - Gibbs Sampling
tag: [Study Notes]
category: Bayesian Statistics
---

Study Notes for Coursera Course: [Bayesian Statistics: Techniques and Models](https://www.coursera.org/learn/mcmc-bayesian-statistics/) by Matthew Heiner.

Compare to Metropolis Hasting (MH) that samples for a single parameter, Gibbs Sampling (GS) can sample for multiple parameters, and it does this one by one for each parameter. The important derivation to keep in mind is the following:

$$p(\theta, \phi|y) \propto g(\theta, \phi) \\
    p(\theta, \phi|y) = p(\phi|y)p(\theta|\phi, y)\\
    p(\theta|\phi, y)\propto p(\theta, \phi|y) \propto g(\theta, \phi) \\
   p(\phi|\theta, y)\propto p(\theta, \phi|y) \propto g(\theta, \phi) $$

Sampling for one parameter at a time when treating the other parameters as constants.

 

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjIxMjA4ODA1LC04MTkzMTkyNDRdfQ==
-->