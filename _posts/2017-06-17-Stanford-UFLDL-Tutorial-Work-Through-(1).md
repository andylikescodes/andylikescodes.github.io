---
layout: post
title: Stanford UFLDL Tutorial Work Through (1) - Linear Regression
tag: [Deep Learning]
category: Deep Learning
---

Link to the tutorial: [Unsupervised Feature Learning and Deep Learning: Linear Regression](http://ufldl.stanford.edu/tutorial/supervised/LinearRegression/)

## Problem

Suppose we have a dataset with $$m$$ records , $$n$$ input variables and $$1$$ output variable.

We can contained all the inputs in a matrix with dimension $$m\times n$$. Then we add a dummy column with all ones to the input matrix and get the following matrix with dimension $$m\times (n+1)$$:

$$X_{m\times (n+1)}=\left( \begin{array}{ccccc}
1&x_{1}^{(1)}&x_{2}^{(1)}&...&x_{n}^{(1)}\\
1&x_{1}^{(2)}&x_{2}^{(2)}&...&x_{n}^{(2)}\\
\vdots&\vdots&\vdots&\vdots&\vdots\\
1&x_{1}^{(m)}&x_{2}^{(m)}&...&x_{n}^{(m)}
\end{array}
\right)=\left( \begin{array}{c}
x^{(1)}\\
x^{(2)}\\
\vdots\\
x^{(m)}
\end{array}
\right) = \left( \begin{array}{cccc}
\vdots&\vdots&...&\vdots\\
X_0&X_1&...&X_n\\
\vdots&\vdots&...&\vdots
\end{array}
\right)$$


Here is the $$m \times 1$$ output variable vector $$Y$$:

$$Y_{m\times 1}=\left( \begin{array}{c}
y_{1}\\
y_{2}\\
\vdots\\
y_{m}
\end{array}
\right)$$

The task of linear regression is to try to find a linear function $$y = h_{\Theta}(x)$$ such that $$y_i \approx h_{\Theta}(x^{(i)})$$, where:

$$\Theta_{(n+1)\times 1}=\left( \begin{array}{c}
\theta_{0}\\
\theta_{1}\\
\vdots\\
\theta_{n}
\end{array}
\right)$$

If we vectorized $$y_i\approx h_\Theta(x^{(i)})$$, the problem is equivalent to finding a vector $$\Theta_{(n+1)\times 1}$$ such that $$Y_{m\times 1} \approx H_{\Theta}(X) = X_{m\times(n+1)}\Theta_{(n+1)\times 1}$$.

## Cost Function $$J(\Theta)$$

Now let's define a function usually referred to as the "cost function" or "loss function" to measure how close $$H_{\Theta}(X)=X\Theta$$ is to $$Y$$. The function is given by:

$$J({\Theta}) = \frac{1}{2}(X\Theta-Y)^T(X\Theta-Y)$$

The intuition of the cost function is that it is the sum of the squared errors between the expected output of the function $$H_{\Theta}(X)$$ and the output variable $$Y$$.

## Gradient Descent $$\nabla J_{\Theta}(\Theta)$$

Now we have the cost function $$J(\Theta)$$ and we want to minimize it, so that $$H_{\Theta}(X)$$ is as "close" as possible to $$Y$$. The technique that we use to do this is gradient descent ([wiki](https://en.wikipedia.org/wiki/Gradient_descent)), which is a commonly used simple but powerful iterative numerical method to find the minimum of a multi-dimensional function. The gradient of $$J(\Theta)$$ is given by:

$$\nabla J_{\Theta}(\Theta)=\left( \begin{array}{c}
\frac{\partial {J(\Theta)}}{\partial\theta_0}\\
\frac{\partial {J(\Theta)}}{\partial\theta_1}\\
\vdots\\
\frac{\partial {J(\Theta)}}{\partial\theta_n}
\end{array}
\right)$$

Where $$\frac{\partial J(\Theta)}{\partial \theta_j} = X_j^T(X\Theta-Y)$$. Therefore $$\nabla J_{\Theta}(\Theta)= X^T(X\Theta-Y)$$.

We then randomly initialize the $$\Theta$$ and iteratively look for the local minimum of $$J(\Theta)$$ by updating $$\Theta$$ in each iteration with $$\Theta:=\Theta+\alpha\nabla J_{\Theta}(\Theta)$$, where $$\alpha$$ is called the learning rate that control the rate of change of $$\Theta$$ in each iteration. A too small learning rate might make the model slow to run, while a too big learning rate might diverge the cost function.

## Exercise 1 Solution

Please see this [github repo](https://github.com/andylikescodes/Stanford_UFLDL_Tutorial_Solutions) for the solution to exercise 1.
