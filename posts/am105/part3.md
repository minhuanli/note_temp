---
layout: post
title: "ODE and PDE, Numerical Approximations I"
date: 2021-02-03
progress: 5%
permalink: /am105/part3/
---
[Content](https://minhuanli.github.io/notes/)

* listnotshown
{:toc}

### 1. Euler's Method

For a first-order IVP given $$f$$ and $$\partial f /\partial y$$ are continuous:

$$
\frac{d y}{d t}=f(t, y), \quad y\left(t_{0}\right)=y_{0}\tag{1}
$$

there are two facts driving the numerical approximations approaches:{% sidenote '1' 'from existence and uniqueness theorem' %}

1. There is a unique solution $$y=\phi(t)$$ in some interval around $$t=t_0$$

2. It is usually not possible to find the $$\phi$$ by symbolic manipulations.

