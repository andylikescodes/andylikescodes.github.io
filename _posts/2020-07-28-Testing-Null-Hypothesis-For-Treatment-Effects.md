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

Watching the video again - under $H_0$ the potential outcomes are the same for each subject $y_i(0) = y_i(1)$ for all assignments in $\Omega$. In randomized experiments, all assignment vectors in $\Omega$ are equally likely. I am guessing that under the $H_0$, if we take $\bar{Y}_t - \bar{Y}_c$ as the statistics, then it should be some kind of a distribution around 0, because $H_0$ is making the assumption that there is no treatment effect. Then after we have a bunch of observations, then we can use these observations to get a statistics to do the hypothesis testing. Although, the question now is how do we know the distribution/statistics under $H_0$? If we think about hypothesis testing for the mean with known variance under normal distribution, we construct $H_0:\mu=\mu_0$. Then after we collect sample data and we have $\bar{x}$, we find the cumulated probability of  $\mu \geq \bar{x}$ from the normal distribution of $\mu$ with   mean $\mu_0$ and some fixed variance. In this $H_0$ we need to construct something like $H_0: \bar{Y}_t - \bar{Y}_c=0$. The first thing is that what is the statistics we are using in here? In the normal case, we know that the data is distributed normally, or we construct some statistics that distributed in a certain way. We do need to assume some kind of distribution a priori though, no? 

Just studying the Fisher and Bristol tea experiment example, for 8 cups of tea with 4 put in milk first and 4 put in tea first, the probability of each possible outcome is $\binom{8}{4} = \frac{8!}{4!(8-4)!}$. But still, what is the the $H_0$? Bristol knows that there are 4 put in milk first and 4 put in tea first, so she is going to provide answers with 4/4 format but just answer them in different places for all the 8 cups. So the statistcs that we are interested in would be the number of correct answers $t$. Now we want to know the probability of $t\geq t(obs)$, where $t(obs)$ is the observed value, the answer that Bristol provides. Now, the next question is still, how do we know the distribution of $t$? I guess it is because we have $\binom{8}{4}$ this many equally likely events, and we also know the correct answer. From this we can calculate the probability of Bristol answering correctly for 1, 2, 3, 4, ..., 8. This is the distribution for $t$. Now we know the distribution for $t$, we can calculate $Pr(t\geq t(obs))$ to see the probability of Bristol getting the correct answer by just guessing. If the probability is very small, then we say that it is very unlikely that Bristol is just guessing. With some significant p-values, we can reject $H_0$. 

However, that's when we know the correct answer, and then we can construct the probability distribution under $H_0$. In this case, when we have equally likely treatments, can we do the same thing? Let's say that the treatments are randomly assigned, then we calculated $Pr(t\geq t(obs))$, where $t(obs)$ is number of treated subjects. This is not what we want though. We want a statistics that relate to the effects, and in the example,  $\bar{Y}_t - \bar{Y}_c$ is selected. I guess that if we randomly shuffle the treatment assignment, we have all the possible events of treatment assignments.  I am not quite understanding this now. If we randomly shuffle the treatment, in reality, should I get different treatment effects? 

Consider that know all the possible treatment assignments and each of them are equally likely to happen, then each assignment have a test statistics $\bar{Y}_t - \bar{Y}_c$ calculated from one single observation $y=(1,3,4,6)$ and treatment $Z=(0,0,1,1)$. I think the rationale behine this is that, if we observed $y=(1,3,4,5)$, under $H_0$ that there is no treatment effect, it won't matter the way you assign treatments. $\bar{Y}_t - \bar{Y}_c$ is assumed to be 0 for all assignments. I think this example is just to demostrate a particular test statistic that we can use, but not demonstrating a valid hypothesis testing for no treatment effects (?).

In the later section of the video, a more valid $H_0$ is given that $H_0: \tau=1, H_1: \tau>1$ where $y_i(1) - y_i(0)=\tau$ and now everything start to make sense. Under the $H_0$, from the observed data we have $(y_1(0) = 1, y_2(0)=3, y_3(0)=3, y_4(0)=5)$ and $(y_1(1) = 2, y_2(1)=4, y_3(1)=4, y_4(1)=6)$ given treatment assignment $Z = (1,1,0,0)$. Gonna stop here for now and move on. This is still not very clear to me how to calculate the distriobution of $y_i(1) - y_i(0)$. I might come back to it later. 

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE3MDM4MDYwMiwxMjU1MDE4NjQwLDE1MD
g1MzYxMDAsLTE1NzgyMjQ5NDEsLTEwNzgyNDk0MzQsNjc4MzIz
NzkyLC01ODI2OTQ1NDMsMjEyODI3MTA2MiwyMDkxNjU1NzczLD
IwNTE0MTM3NTAsNjQ0MzczNjM1LC0xNDg1MTA4MDcxLC0xMDk4
MjI3Nzk1LDEzMTE0NTg4NzEsNTY2MjA2NjM4LC0xOTUzNDEzOD
Y0LDIwMDc0NTUzMjUsLTIwNjk3MDg1NDVdfQ==
-->