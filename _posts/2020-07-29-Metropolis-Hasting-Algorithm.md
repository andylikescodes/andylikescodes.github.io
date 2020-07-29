---
layout: post
title: Metropolis-Hasting-Algorithm
tag: [Study Notes]
category: Baysian Statistics
---

Study Notes for Cousera Course: [Bayesian Statistics: Technique](https://www.coursera.org/learn/causal-inference)) by Michael Sobel.

If we have an observed treatment $Z$ and a test statistic $t(Z, y)$. If we calculate $t(Z, y)$ for all other treatment assignments, we get a distribution of $t(Z, y)$. When we calculate $t = t(Z, y)$ using the observed $Z$ and $y$, we are assuming the Null Hypothesis, $H_0$, that there is no treatment effect. We have the distribution for $t(Z, y)$, and we know under $H_0$ the statistic we have is t. And we calculate the probability that $t(Z, y)$ is greater than t. In the example, the statistics $t(Z, y)$ used $\bar{Y}_t - \bar{Y}_c$. 

$\bar{Y}_t - \bar{Y}_c$ is the average effect under the treated subjects and the untreated subjects. When we calculate this value for all possible assignments $Z$, then we get a distribution for $\bar{Y}_t - \bar{Y}_c$. An important question is that what does this probability distribution represent?

Should I consider this distribution as the $H_0$ distribution? Assuming there is no treatment effect? However, the observed $Y$ is associated with a particular $Z$, so what does it mean by randomizing $Z_1$ and then calcuate $\bar{Y}_t - \bar{Y}_c$?



> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0MzU1ODQ2NDhdfQ==
-->