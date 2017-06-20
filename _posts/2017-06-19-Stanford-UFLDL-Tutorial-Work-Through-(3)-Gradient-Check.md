---
layout: post
title: Stanford UFLDL Tutorial Work Through (3) - Gradient Check
tag: [Deep Learning]
category: Deep Learning
---

Link to the Tutorial: [Gradient Check](http://ufldl.stanford.edu/tutorial/supervised/DebuggingGradientChecking/)

## Problem

[Linear regression](https://andylikescodes.github.io/deep%20learning/2017/06/17/Stanford-UFLDL-Tutorial-Work-Through-(1)/) and [logistic regression](https://andylikescodes.github.io/deep%20learning/2017/06/18/Stanford-UFLDL-Tutorial-Work-Through-(2)-logistic-regression/) both are required using gradient descent to optimize their cost functions. Linear regression and logistic regression are relatively simple regression models that their gradients are easy to compute. In later sections, when we start working with more complicated calculations, for example, back-propagation in neural network, which sometimes hard to see what's going on in the blackbox, we need a way to check whether the gradient is correct. In this section, a numerical method of checking the gradients is introduced so we can be more confident that our model is working as expected.

## Numerical Approximation for Derivatives

Recall the definition of a derivative:

$$\frac{dJ(\theta)}{d\theta} = \lim_{\epsilon\to0}\frac{J(\theta+\epsilon)-J(\theta-\epsilon)}{2\epsilon}$$

Using this definition we can approximate any derivative by:

$$\frac{dJ(\theta)}{d\theta}\approx\frac{J(\theta+\epsilon)-J(\theta-\epsilon)}{2\epsilon}$$

It follows that the smaller $$\epsilon$$ is, the better the approximation. A $$\epsilon$$ with value of $$10^{-4}$$ is an acceptable approximation a lot of the times. It gives at least 4 digits of accuracy.

The gradient in our case is a vector over all the $$\theta_i$$ that we want to train, for example, the gradient for linear regression is given by:

$$\nabla J_{\Theta}(\Theta)=\left( \begin{array}{c}
\frac{\partial {J(\Theta)}}{\partial\theta_0}\\
\frac{\partial {J(\Theta)}}{\partial\theta_1}\\
\vdots\\
\frac{\partial {J(\Theta)}}{\partial\theta_n}
\end{array}
\right)$$

If we want to check $$\frac{\partial J(\Theta)}{\theta_j}$$ in this vector, we need to define a helper vector $$\vec{e}_j=[0,0,...,1,...,0]^T$$, then calculate the $$\Theta^{(j\pm)} = \Theta \pm \epsilon \vec{e}_j$$. By using the numerical approximation formula introduced in the above, we get:

$$\frac{\partial J(\Theta)}{\theta_j}\approx \frac{J(\Theta^{(j+)})-J(\Theta^{(j-)})}{2\epsilon}$$

## Gradient Checker Code

Now let's review the code that the tutorial gives to check the gradients.

``` matlab
function average_error = grad_check(fun, theta0, num_checks, varargin)

  delta=1e-3;
  sum_error=0;

  fprintf(' Iter       i             err');
  fprintf('           g_est               g               f\n')

  for i=1:num_checks
    T = theta0;
    j = randsample(numel(T),1);
    T0=T; T0(j) = T0(j)-delta;
    T1=T; T1(j) = T1(j)+delta;

    [f,g] = fun(T, varargin{:});
    f0 = fun(T0, varargin{:});
    f1 = fun(T1, varargin{:});

    g_est = (f1-f0) / (2*delta);
    error = abs(g(j) - g_est);

    fprintf('% 5d  % 6d % 15g % 15f % 15f % 15f\n', ...
            i,j,error,g(j),g_est,f);

    sum_error = sum_error + error;
  end

  average_error=sum_error/num_checks;
```

This implementation randomly choose the gradients to check and average the error between the approximated ones and the ones calculated by using gradient descent.

The number of gradients to check is specified in the parameter `num_checks`, and we can see that a piece of code `j = randsample(numel(T),1)` is used to randomly generate the index of the gradients array. By doing this we can control the run time of the gradient check function because we don't want to check all the gradients in every iteration, which will make the program run significantly slower.
