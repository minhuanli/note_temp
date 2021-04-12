---
layout: post
title: "ODE and PDE, Systems of ODEs"
date: 2021-04-11
progress: 25%
permalink: /am105/part7/
---
[Content](https://minhuanli.github.io/notes/)

* listnotshown
{:toc}


### 1. Systems of first-order linear equations

Equations of higher order can always be transformed into systems of first order equations. To transform an arbitray $$n^{th}$$ order equation:

$$
y^{(n)}=F\left(t, y, y^{\prime}, \ldots, y^{(n-1)}\right)\tag{1}
$$

into a system of $$n$$ first-order differential equations by introducing the variables $$x_{1}, x_{2}, \ldots, x_{n}$$ defined by:

$$
x_{1}=y, x_{2}=y^{\prime}, x_{3}=y^{\prime \prime}, \ldots, x_{n}=y^{(n-1)} \tag{2}
$$

It follows immediately that:

$$
\begin{array}{c}
x_{1}^{\prime}=x_{2} \\
x_{2}^{\prime}=x_{3} \\
\vdots\\
x_{n-1}^{\prime}=x_{n} \\
x_{n}^{\prime}=F\left(t, x_{1}, x_{2}, \ldots, x_{n}\right) 
\end{array} \tag{3}$$

A more general case of such n first-order **linear** differential equation has the form:

$$
\begin{aligned}
x_{1}^{\prime} &=p_{11}(t) x_{1}+\cdots+p_{1 n}(t) x_{n}+g_{1}(t), \\
x_{2}^{\prime} &=p_{21}(t) x_{1}+\cdots+p_{2 n}(t) x_{n}+g_{2}(t), \\
&\vdots \\
x_{n}^{\prime} &=p_{n 1}(t) x_{1}+\cdots+p_{n n}(t) x_{n}+g_{n}(t) .
\end{aligned} \tag{4}
$$

If each of the functions $$g_{1}(t), \ldots, g_{n}(t)$$ is zero for all $$t$$ in the interval $$I$$, then the system
(4) is said to be <i class='contrast'>homogeneous</i>; otherwise, it is <i class='contrast'>nonhomogeneous</i>.