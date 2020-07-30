---
layout: post
title: Testing Null Hypothesis for No Treatment Effects
tag: [Study Notes]
category: Causal Inference
---

Study Notes for Cousera Course: [Causal Inference I](https://www.coursera.org/learn/causal-inference)) by Michael Sobel.

If we have an observed treatment $Z$ and a test statistic $t(Z, y)$. If we calculate $t(Z, y)$ for all other treatment assignments, we get a distribution of $t(Z, y)$. When we calculate $t = t(Z, y)$ using the observed $Z$ and $y$, we are assuming the Null Hypothesis, $H_0$, that there is no treatment effect. We have the distribution for $t(Z, y)$, and we know under $H_0$ the statistic we have is t. And we calculate the probability that $t(Z, y)$ is greater than t. In the example, the statistics $t(Z, y)$ used $\bar{Y}_t - \bar{Y}_c$. 

$\bar{Y}_t - \bar{Y}_c$ is the average effect under the treated subjects and the untreated subjects. When we calculate this value for all possible assignments $Z$, then we get a distribution for $\bar{Y}_t - \bar{Y}_c$. An important question is that what does this probability distribution represent?

Should I consider this distribution as the $H_0$ distribution? Assuming there is no treatment effect? However, the observed $Y$ is associated with a particular $Z$, so what does it mean by randomizing $Z_1$ and then calcuate $\bar{Y}_t - \bar{Y}_c$?

Watching the video again - under $H_0$ the potential outcomes are the same for each subject $y_i(0) = y_i(1)$ for all assignments in $\Omega$. In randomized experiments, all assignment vectors in $\Omega$ are equally likely. I am guessing that under the $H_0$, if we take $\bar{Y}_t - \bar{Y}_c$ as the statistics, then it should be some kind of a distribution around 0, because $H_0$ is making the assumption that there is no treatment effect. Then after we have a bunch of observations, then we can use these observations to get a statistics to do the hypothesis testing. Although, the question now is how do we know the distribution/statistics under $H_0$? If we think about hypothesis testing for the mean with known variance under normal distribution, we construct $H_0:\mu=\mu_0$. Then after we collect sample data and we have $\bar{x}$, we find the cumulated probability of  $\mu \geqq \bar{x}$ from the normal distribution of $\mu$ with   mean $\mu_0$ and some fixed variance. In







> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbODk3NzcyOTM4LDEzMTE0NTg4NzEsNTY2Mj
A2NjM4LC0xOTUzNDEzODY0LDIwMDc0NTUzMjUsLTIwNjk3MDg1
NDVdfQ==
-->