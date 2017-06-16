---
layout: post
title: Order Statistics
tag: [Statistics, Probability]
category: Probability Theory and Statistics
---

Order statistic is interesting because it is a little bit different from the often seen probability distributions. The nature of the order statistics allows us to design sampling methods that save us money and time. In certain experiments when there are strict constrains on measurements of samples or the number of samples we can take, order statistic can sometimes help us identify the best model using limited information.

## Definition
Supposed we have a random sample with size n associated with random variables $$X_i = \{X_1, X_2, ..., X_n\}$$ and each from the a continuous distribution $$f(x)$$, then the joint pdf can be derived as the followings:

$$f(x_1,x_2,...,x_n) = f(x_1)f(x_2)...f(x_n)$$

If we order these random samples from the smallest to the largest and name them $$x_{1:n}, x_{2:n}, ..., x_{n:n}$$, we get a list of numbers in order, where the smallest number is $$x_{1:n}$$ and the largest number is $$x_{n:n}$$.

Now we define a set of new random variables, $$Y_{i} = \{Y_1, Y_2, ...,Y_n\}$$, where $$y_{1} = x_{1:n}, y_{2} = x_{2:n}, ..., y_{n} = x_{n:n}$$. From this definition we can see that each random variable in $$Y_{i}$$ is actually a function of the n random variables from $$X_{i}$$, where:

$$\left\{
\begin{array}{lcl}
y_1=u_1(x_1,x_2,...,x_n) & = & \min(x_1,x_2,...,x_n) \\
y_i=u_k(x_1,x_2,...,x_n) & = & i_{th}\min(x_1,x_2,...,x_n)\\
y_n=u_n(x_1,x_2,...,x_n) & = & \max(x_1,x_2,...,x_n)
\end{array}
 \right$$

We called this set of ordered random variables $$Y_i$$ order statistics.

## The joint pdf of $$Y_1, Y_2,...,Y_n$$

Then we can derive the joint distribution of $$Y_{i}=\{Y_1, Y_2,...,Y_n\}$$ by the following equation:

$$g(y_1,y_2,...,y_n)=n!f(y_1)f(y_2)...f(y_n), y_1<y_2<...<y_n$$

The intuition of the equation is that if we have a list of unordered samples $$y_1=x_{1:n}, y_2=x_{2:n},...,y_n=x_{n:n}$$, the probability of them appearing at the same time in a particular order is $$f(y_1)f(y_2)...f(y_n)$$, and we have $$n!$$ ways of ordering these random samples. For all different orderings they all have the same order statistics, because they are the same when we order them from the smallest to the largest.

## The pdf of the $$k_{th}$$ order statistic $$Y_{k}$$
Using integration techniques over all other random variables except $$y_k$$ from $$g(y_1,y_2,...,y_n)$$, we get:

$$g_k(y_k) = \frac{n!}{(k-1)!(n-k)!}[F(y_k)]^{k-1}[1-F(y_{k})]^{n-k}f(y_k)$$

Where $$F(x_{i})$$ is the CDF of $$X_i$$. The intuition is that $$P(X_{i}<=y_k)$$ is $$F(y_k)$$ and there are $$(k-1)$$ of samples smaller than $$y_k$$, while $$P(X_{i}>=y_k)$$ is $$(1-F(y_k))$$ and there are (n-k) samples greater than $$y_k$$. Similar to the way we think about the joint pdf of $$Y_{i}$$, we get the pdf of the kth order statistic.

From the kth order statistic distribution we can derive the distribution of $$Y_{1}$$ and $$Y_{n}$$:

$$\left\{
\begin{array}{l}
g_1(y_1)=n[1-F(y_1)]^{n-1} \\
g_n(y_n)=n[F(y_n)]^{n-1}f(y_n)]
\end{array}
 \right$$

## The CDF of $$Y_k$$

From the pdf of $$g_1(y_1)$$ and $$g_n(y_n)$$ we can derive the CDF of them $$G_1(y_1)$$ and $$G_n(y_n)$$.

$$\left
\begin{array}{lcl}
G_1(y_1)&=&P[Y_1\leq y_1] \\
&=&1-P[Y_1>y_1]\\
&=&1-P[(X_1>y_1)\cap(X_2>y_1)\cap...\cap(X_n>y_1)]\\
&=&1-[1-F(y_1)]^n
\end{array}
 \right$$

The intuition of $$G_1(y_1)$$ is that the probability of the smallest number of all random samples from $$X_i$$ is smaller than or equal to $$y_1$$, which is equal to the probability of all the samples in $$X_i$$ are greater than $$y_i$$.

$$\left
\begin{array}{lcl}
G_n(y_n)&=&P[Y_n\leq y_n] \\
&=&P[(X_1<y_1)\cap(X_2<y_1)\cap...\cap(X_n<y_1)]\\
&=&[F(y_n)]^n
\end{array}
 \right$$

The intuition of $$G_1(y_1)$$ is that the probability of the largest number of all random samples from $$X_i$$ is smaller than or equal to $$y_1$$, which is equal to the probability of all samples from $$X_i$$ are smaller than or equal to $$y_1$$.

Similarly, we can derive the CDF of $$Y_k$$:

$$\left
\begin{array}{lcl}
G_k(y_k)&=&P[Y_k\leq y_k]
\end{array}
 \right$$

Since $$P[Y_k\leq y_k]$$ is the probability of the kth order $$Y_k$$ is smaller than $$y_k$$ and $$Y_k = X_{k:n}$$, we get $$P[Y_k\leq y_k] = P[X_{k:n}\leq y_k]$$. It means that we need to have at least k number of samples from $$X_{i}$$ that are smaller $$y_k$$.

From the CDF of $$X_{i}$$ we know that $$P[X_{i}<=y_{k}] = F(y_k)$$. Now we define a random variable $$K$$, which is the number of the $$n$$ samples smaller than $$y_k$$. The distribution of $$K$$ is a binomial distribution with pdf:

$$bin(k;n, p) = {n \choose k}p^k(1-p)^{n-k}$$

where $$p=P[X_{i}<=y_k]=F(y_k)$$.

Then we can calculate the probability of at least $$k$$ number of $$X_i$$ are smaller than $$y_k$$, $$P[K>=k]$$, by following the CDF of bin(k;n,p):

$$\left
\begin{array}{lcl}
P[K>=k]&=&1-P[K<k]\\
&=&1 - \sum_{j=0}^{k-1}bin(j;n,p)\\
&=&\sum_{j=k}^{n}bin(j;n,p)\\
&=&\sum_{j=k}^{n}{n \choose j}[F(y_k)]^j[1-F(y_k)]^{n-j}
\end{array}
 \right$$

Then we can conclude that:

$$\left
\begin{array}{lcl}
G_k(y_k)&=&P[Y_k\leq y_k]\\
&=&P[K>=k]\\
&=&\sum_{j=k}^{n}{n \choose j}[F(y_k)]^j[1-F(y_k)]^{n-j}
\end{array}
 \right$$

## Application

One example of using order statistic is Type I and Type II censored sampling. These sampling methods are developed to handle  some situations where it is impossible to have complete information about the entire sample. In these cases, if we want to derive a statistical model from the observed data, these sampling techniques can help us develop the joint pdfs that allow us to evaluate our model under some physical constrains.

**Type II censored sampling**: with a random sample size of n, we stop the experiment after achieving the first r desired outcomes. The marginal density function of the first r order statistics is given by:

$$g(y_1, y_2, ..., y_r) = \frac{n!}{(n-r)!}[1-F(y_r)]^{n-1}\prod_{i=1}^{r}f(y_i)$$

if $$-\infty < y_1 < ... < y_r < \infty$$ and zero otherwise.

Some experiments such as measuring the lifetime a certain product, waiting the entire sample to die out and measure all of their life time is too time consuming. A lot of the times, only a portion of the samples (eg. the life time of the first r ordered samples) are measured and a joint pdf of the ordered statistic can be derived by the above formula.

**Type I censored sampling**: instead of terminating the experiment after achieving a certain number desired outcomes, Type I censored sample terminate the experiment whenever $$Y$$ hits a preset value.

For example, in the lifetime experiment of a product mentioned in Type II censored sampling, we might decide to terminate the experiment when $$Y$$ is at time $$t_{0}$$ and record the lifetime the die out products as $$Y_i=\{Y_1,...,Y_{r}\}$$.

The joint pdf of $$Y_{1},...,Y_{r}$$ is given by:

$$f_{Y_1,...,Y_R}(y_1,...,y_r)=\frac{n!}{(n-r)!}[1-F(t_{0})]^{n-r}\prod_{i=1}^{r}f(y_i)$$

if $$y_1 <...< y_r < t_0$$ and $$r=1,2,...,n$$.

**Reference**:

All the above formulas and writings are summarized from a classic book [Introduction to Probability and Mathematical Statistics](https://www.amazon.com/Introduction-Probability-Mathematical-Statistics-Duxbury/dp/0534380204/ref=sr_1_1?ie=UTF8&qid=1497655067&sr=8-1&keywords=introduction+to+probability+and+mathematical+statistics) by Bain/Engelhardt.
