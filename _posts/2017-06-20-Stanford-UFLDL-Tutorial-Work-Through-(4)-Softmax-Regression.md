---
layout: post
title: Stanford UFLDL Tutorial Work Through (4) - Softmax Regression
tag: [Deep Learning]
category: Deep Learning
---

Link to the Tutorial: [Softmax Regression](http://ufldl.stanford.edu/tutorial/supervised/SoftmaxRegression/)

## Problem

Logistic regression has two classes of output, $$y_i\in[1,0]$$. A questions raise when we want to do classification of more than 2 classes, $$y_i\in[1,\dots,k]$$. Softmax regression is an extension of logistic regression to handle multiple class classifications.

## Definition of the Cost Function

The softmax function is given by:

$$h_{\Theta}(x^{(i)})=
\left[\begin{array}{c}P(y_i=1|x^{(i)},\Theta^{(1)})\\
P(y_i=2|x^{(i)},\Theta^{(2)})\\
\vdots\\
P(y_i=k|x^{(i)},\Theta^{(k)})
\end{array}\right]=\frac{1}{\sum_{j=1}^k\exp{(-x^{(i)}\Theta^{(k)})}}\left[
\begin{array}{c}\exp{(-x^{(i)}\Theta^{(1)})}\\
\exp{(-x^{(i)}\Theta^{(2)})}\\
\vdots\\
\exp{(-x^{(i)}\Theta^{(k)})}
\end{array}
\right]$$

where

$$\Theta = \left(\begin{array}{cccc}
|&|&|&|\\
\Theta^{(1)} & \Theta^{(2)} & \dots &\Theta^{(k)}\\
|&|&|&|
\end{array}\right)$$

Similar to logistic regression, we want to get the log likelihood function for $$\Theta$$:

$$\ell(\Theta) = \sum_{i=1}^{m}\sum_{k=1}^{K}1\{y_i=k\}log\frac{\exp(x^{(i)}\Theta^{(k)})}{\sum_{k=1}^{K}\exp(x^{(i)}\Theta^{(k)})}$$

Note that $$1\{\}$$ is an indicator function so that $$1\{true\} = 1,1\{false\}=0$$.

Let $$P(y_i=k \vert x^{(i)},\Theta)=\frac{\exp(x^{(i)}\Theta^{(k)})}{\sum_{k=1}^{K}\exp(x^{(i)}\Theta^{(k)})}$$the cost function is defined as:

$$J(\Theta) = - \left[\sum_{i=1}^{m}\sum_{k=1}^{K}1\{y_i=k\}logP(y_i=k|x^{(i)},\Theta)\right]$$

Taking the derivatives, we get:

$$\nabla J_{\Theta^{(k)}}(\Theta) = -\sum_{i=1}^m[x^{(i)}(1\{y_i=k\}-P(y_i=k|x^{(i)},\Theta))]$$

In order to vectorize the gradient calculation, we define a output vector for each $$y_i$$:

$$Y_i=\left(\begin{array}{c}
0\\
\vdots\\
1\\
\vdots\\
0
\end{array}\right)$$

where the kth element is 1 and others are 0. Then we combine all the output vector for all records, we get a output matrix:

$$Y_{k\times m}=\left(\begin{array}{ccc}
0&0\\
\vdots&1\\
1&\vdots&\dots\\
\vdots&\vdots\\
0&0
\end{array}\right)$$

Using this matrix in calculation we get:

$$\nabla J_{\Theta}(\Theta) = -X^T[Y-H_{\Theta}(X)]^T=
-\left(\begin{array}{cccc}|&|&|&|\\
\nabla J_{\Theta^{(1)}}(\Theta)&\nabla J_{\Theta^{(2)}}(\Theta)&\vdots&\nabla J_{\Theta^{(k)}}(\Theta)\\
|&|&|&|
\end{array}\right)$$

$$H_{\Theta}(X)$$ is a matrix with each column corresponding to the softmax function output of each record, $$h_{\Theta}(x^{(i)})$$.

Then we update $$\Theta$$ with $$\Theta:=\alpha\nabla J_{\Theta}(\Theta)$$ in each iteration to achieve the local minimum of the cost function $$J(\Theta)$$.

## Properties of softmax regression parameterization

Please see the following calculation, for any vector $$\psi$$ with the same dimension as $$\Theta^{(k)}$$:

$$\begin{array}{ccl}P(y_i=k|x^{(i)},\Theta)&=&\frac{\exp(x^{(i)}(\Theta^{(k)}-\psi))}{\sum_{j=1}^{K}\exp(x^{(i)}(\Theta^{(j)}-\psi))}\\
&=&\frac{\exp(x^{(i)}\Theta^{(k)})\exp(-x^{(i)}\psi))}{\sum_{j=1}^{K}\exp(x^{(i)}\Theta^{(j)})\exp(-x^{(i)}\psi)}\\
&=&\frac{\exp(x^{(i)}\Theta^{(k)})}{\sum_{j=1}^{K}\exp(x^{(i)}\Theta^{(j)})}
\end{array}$$

From the above, we can see that no matter what $$\psi$$ is we get the same result as the original parameter $$\Theta$$. It is also telling us that there is more than one set of parameters that can take us to the minimum of the cost function.

If we set $$\psi=\Theta^{(k)}$$, then we have $$\Theta^{(k)}:=\Theta^{(k)}-\psi=\vec0$$. In this way we only need to train the other $$(k-1)$$ number of parameters. In my experience with statistics, it probability has to do with the degree of freedom concept, but more study need to be done on this to fully understand it entirely.

## Relationship between softmax regression and logistic regression

In a 2 class softmax regression case, we get the following:

$$\begin{array}{ccl}h_{\Theta}(x^{(i)})&=&\frac{1}{\exp{(-x^{(i)}\Theta^{(1)})}+\exp{(-x^{(i)}\Theta^{(2)})}}\cdot\left[
\begin{array}{c}\exp{(-x^{(i)}\Theta^{(1)})}\\
\exp{(-x^{(i)}\Theta^{(2)})}
\end{array}
\right]\\
&=&\frac{1}{\exp{(-x^{(i)}(\Theta^{(1)}-\Theta^{(2)}))}+\exp{(-x^{(i)}\vec0)}}\cdot\left[
\begin{array}{c}\exp{(-x^{(i)}(\Theta^{(1)}-\Theta^{(2)}))}\\
\exp{(-x^{(i)}\vec0)}
\end{array}
\right]\\
\end{array}$$

Let $$\Theta'=\Theta^{(1)}-\Theta^{(2)}$$, simplify the above equation, we get:

$$h_{\Theta}(x^{(i)}) = \left[\begin{array}{c}
1-\frac{1}{1+\exp(-x^{(i)}\Theta')}\\
\frac{1}{1+\exp(-x^{(i)}\Theta')}
\end{array}\right]$$

From the above, we can see that logistic regression is actually a special case of the softmax regression with class 2.
