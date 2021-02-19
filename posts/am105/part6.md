---
layout: post
title: "ODE and PDE, Nonhomogeneous ODEs"
date: 2021-02-18
progress: 100%
permalink: /am105/part6/
---
[Content](https://minhuanli.github.io/notes/)

* listnotshown
{:toc}


### 1. Methods of undetermined coefficients

For a nonhomogeneous second-order ODE: 

$$
y^{\prime \prime}+p(t) y^{\prime}+q(t) y=g(t) \tag{1}
$$

where $$g(t)$$ is nonzero. We can write out the general solution as:

$$
y=\phi(t)=c_{1} y_{1}(t)+c_{2} y_{2}(t)+Y(t)\tag{2}
$$

$$y_1$$ and $$y_2$$ are the two solutions for the homogeneous form{% sidenote '1' 'set $$g(t)=0$$' %}  of equation (1). Our task now is finding the specific solution $$Y(t)$$.

Say, if $$g(t)$$ involves only polynomials, sines, cosines, or exponential functions, or sums or products of any of these functions.{% sidenote '2' 'Think about why. Take equation (2) back to (1)' %}

We can get the general solution with the following four steps:

1. Get the solution to the homogeneous equation $$y_1(t)$$ and $$y_2(t)$$

2. Assume an appropriate form for the particular solution $$Y(t) .$$ If $$g(t)=\exp (\alpha t),$$ assume $$Y(t)=$$ $$A \exp (\alpha t) .$$ If $$g(t)=\sin (\beta t)$$ or $$\cos (\beta t),$$ assume $$Y(t)=A \cos (\beta t)+B \sin (\beta t) .$$ If $$g(t)$$ is a polynomial of order $$n,$$ then assume $$Y(t)$$ is a polynomial of order $$n$$. If $$g(t)$$ is a sum or product of the aforementioned functions, assume $$Y(t)$$ is also a sum or product of those same functions. It may be necessary to multiply by $$t$$ or $$t^{2}$$ to avoid duplicating the homogeneous solution.

3. Plug the assumed $$Y (t)$$ into the differential equation to determine the necessary coefficients.

4. Take the sum of the homogeneous and particular solutions to get the general solution of the non-homogeneous differential equation.


### 2. Variation of parameters

If $$g(t)$$ is not the case mentioned above, we need a more general method to solve, here are the general solution for equation (1):

$$
y=c_{1} y_{1}(t)+c_{2} y_{2}(t)+u_{1}(t) y_{1}(t)+u_{2}(t) y_{2}(t)\tag{3}
$$

$$y_1$$ and $$y_2$$ are the two solutions for the homogeneous form{% sidenote '3' 'set $$g(t)=0$$' %}  of equation (1). 

where:

$$
u_{1}(t)=-\int \frac{y_{2}(t) g(t)}{W\left[y_{1}, y_{2}\right](t)} d t , \   u_{2}(t)=\int \frac{y_{1}(t) g(t)}{W\left[y_{1}, y_{2}\right](t)} d t \tag{4}
$$

and the Wronskian is:

$$
W\left[y_{1}, y_{2}\right](t)=\left|\begin{array}{ll}
y_{1}(t) & y_{2}(t) \\
y_{1}^{\prime}(t) & y_{2}^{\prime}(t)
\end{array}\right|=y_{1}(t) y_{2}^{\prime}(t)-y_{1}^{\prime}(t) y_{2}(t)\tag{5}
$$