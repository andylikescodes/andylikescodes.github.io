---
layout: post
title: Refresh on Trig Identities, Integrals and Substitutions
tag: [Math, Calculus]
category: Calculus
---

Link to the lecture: [Lec 27 MIT 18.01 Single Variable Calculus, Fall 2007](https://www.youtube.com/watch?v=Bv9kVDcj7yo&index=24&list=PL590CCC2BC5AF3BC1)

## Trig Identities

Suppose we have a circle with radius 1 centered at the origin $$(0,0)$$. If we connect a point on the circle and the origin and form an angle $$\theta$$ with the $$x$$ axis, we have $$\sin^2(\theta)+\cos^2(\theta)=1$$.

So then we have the double and half angle formulas:

$$\begin{array}{ccl}
\cos(2\theta) &= &\cos^2(\theta)-\sin^2(\theta)\\
&=&\cos^2(\theta)-(1-\cos^2(\theta))\\
&=&2\cos^2(\theta)-1\\
\cos^2(\theta) &=& \frac{1+\cos(2\theta)}{2}\\
\sin^2(\theta) &=& \frac{1-\cos(2\theta)}{2}\\
\sin(2\theta)&=&2\sin(\theta)cos(\theta)
\end{array}$$

## Trig Integrals
### $$\int \sin^n(x)cos^m(x)dx$$, $$m,n=0,1,2,...,$$

**case 1**: $$m=1$$

$$\int \sin^n(x)cos(x)dx$$

substitute $$u=sin(x)$$, $$du = cos(x)dx$$

$$\begin{array}{ccl}
\int \sin^n(x)cos(x)dx &= &\int u^ndu\\
&=&\frac{u^{n+1}}{n+1}+C\\
&=&\frac{\sin^{n+1}(x)}{n+1}+C
\end{array}$$

**case 2**: $$m=2, n=3$$

$$\int \sin^3(x)cos^2(x)dx$$

use $$\sin^2(x)=1-cos^2(x)$$, substitute $$u=\cos(x)$$, $$du=-\sin(x)dx$$

$$\begin{array}{ccl}
\int \sin^3(x)cos^2(x)dx &= &\int (1-\cos^2(x))\sin(x)\cos^2(x)dx\\
&=&\int (\cos^2(x)-\cos^4(x))\sin(x)dx\\
&=&\int (u^2-u^4)(-du)dx\\
&=&-\frac{u^3}{3}+\frac{u^5}{5}+C\\
&=&-\frac{\cos^3(x)}{3}+\frac{\cos^5(x)}{5}+C
\end{array}$$

**case 3**: $$m=0, n=3$$

$$\int \sin^3(x)dx$$

use $$\sin^2(x)=1-cos^2(x)$$, substitute $$u=\cos(x)$$, $$du=-\sin(x)dx$$

$$\begin{array}{ccl}
\int \sin^3(x)dx &= &\int (1-\cos^2(x))\sin(x)dx\\
&=&\int (1-\cos^2(x))\sin(x)dx\\
&=&\int (1-u^2)(-du)dx\\
&=&-u+\frac{u^3}{3}+C\\
&=&-\cos(x)+\frac{\cos^3(x)}{3}+C
\end{array}$$

**rule1**: If we have some odd power to play with, we can use the double angle formula and substitution method to play around and find the integration.

**case 4**: $$m=2,n=0$$

$$\int \cos^2(x)dx$$

use $$\cos^2(x)=\frac{1+cos(2x)}{2}$$,

$$\begin{array}{ccl}
\int \cos^2(x)dx &= &\int \frac{1+cos(2x)}{2}dx\\
&=&\frac{x}{2}+\frac{\sin(2x)}{4}+C
\end{array}$$

**case 5**: $$m=2,n=2$$

$$\int \cos^2(x)\sin^2(x)dx$$

use $$\cos^2(x)=\frac{1+cos(2x)}{2},\sin^2(x)=\frac{1-cos(2x)}{2}$$,

$$\begin{array}{ccl}
\int \cos^2(x)\sin^2(x)dx &= &\int \frac{1+cos(2x)}{2}\cdot\frac{1-cos(2x)}{2}dx\\
&= &\int \frac{1-cos^2(2x)}{4}dx\\
&= &\int \frac{1}{4}-\frac{1+cos(4x)}{8}dx\\
&=& = \frac{x}{8}-\frac{\sin(4x)}{32} + C
\end{array}$$

Or we can use $$\sin^2(x)\cos^2(x) = (\sin(x)\cos(x))^2 = \frac{sin^2(2x)}{4}$$

**rule 2**: If we have even exponents, use the half angle identities to reduce the power of the trig functions.

## Introduction to the polar coordinates

Any points $$(x,y)$$ on the circle $$x^2+y^2=a^2$$ can be represented in the polar coordinates $$(a\cos(\theta),a\sin(\theta))$$. Sometimes it is useful to calculate the integrals of some function in the form $$f(y)=\sqrt{a^2-y^2}$$. For example, we can substitute $$y=a\sin(\theta), dy=a\cos(\theta)d\theta$$:

$$\begin{array}{ccl}
\int \sqrt{a^2-y^2}dy &= &\int \sqrt{a^2-a\sin^2(\theta)}\cdot a\cos(\theta)d\theta\\
&= &\int a^2\cos^2(\theta)d\theta\\
&=& a^2(\frac{\theta}{2}+\frac{\sin(\theta)\cos(\theta)}{2}) + C\\
&=& \frac{a^2\arcsin(\frac{y}{a})}{2} + \frac{(a\sin(\theta))(a\cos(\theta))}{2} + C\\
&=& \frac{a^2\arcsin(\frac{y}{a})}{2} + \frac{y\sqrt{a^2-y^2}}{2} + C\\
\end{array}$$

It becomes something easier to solve.

## Other Trig Identities and Integration

$$\begin{array}{cl}\sec(x)=\frac{1}{\cos(x)}&\csc=\frac{1}{\sin(x)}\\
\tan(x)=\frac{\sin(x)}{\cos(x)}&\cot(x) = \frac{\cos(x)}{\sin(x)}
\end{array}$$

$$\sec^2(x) = 1+\tan^2(x)$$

$$\begin{array}{cl}\frac{d}{dx}\tan(x)=\sec^2(x)&\frac{d}{dx}\sec(x)=\sec(x)\tan(x)\\
\int\tan(x)dx=-\ln\vert\cos(x)\vert+c&\int\sec(x)dx = \ln(\sec(x)+\tan(x))+c
\end{array}$$

**Example**:

using $$u=tan(x),du=\sec^2(x)dx$$

$$\begin{array}{ccl}
\int\sec^4(x)dx&=&\int(1+\tan^2(x))\sec^2(x)dx\\
&=&\int(1+u^2)du\\
&=&u+\frac{u^3}{3}+c\\
&=&\tan(x)+\frac{\tan^3(x)}{3}+c
\end{array}$$
