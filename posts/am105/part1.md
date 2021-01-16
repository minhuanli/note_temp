---
layout: post
title: ODE and PDE, Basics
date: 2021-01-15
progress: 30%
permalink: /am105/part1/
---

[Back]({{ 'am105' | relative_url }})
### 1. Classification of Differential Equations

Only ordinary derivatives appear in the differential equation, and it is said to be an **ordinary differential equation (ODE)**, like:

$$
L \frac{d^{2} Q(t)}{d t^{2}}+R \frac{d Q(t)}{d t}+\frac{1}{C} Q(t)=E(t) \tag{1.1}
$$

the derivatives are partial derivatives, and the equation is called a **partial differential equation(PDE)**, like:

$$
\alpha^{2} \frac{\partial^{2} u(x, t)}{\partial x^{2}}=\frac{\partial u(x, t)}{\partial t} \tag{1.2}
$$

Let's focus on ODE at this moment. For an ODE:

$$
F\left(t, y, y^{\prime}, \ldots, y^{(n)}\right)=0 \tag{1.3}
$$

where $$F$$ is a linear function of the variables $$y, y', \dots, y^{(n)}$$, like:

$$
F(\cdot)= a_{0}(t) y^{(n)}+a_{1}(t) y^{(n-1)}+\cdots+a_{n}(t) y+g(t) = 0\tag{1.4}
$$

This ODE is said to be **linear**. An equation which is not in the form of equation (1.4) is **nonlinear**.

### 2. Order and Solutions
The order of a differential equation is the order of the highest derivative that appears in the equation. Generally speaking, 

$$
F\left(t, u(t), u^{\prime}(t), \ldots, u^{(n)}(t)\right)=0 \tag{2.1}
$$

is a $$n^{th}$$ order ODE. 

A **solution** of the $$n^{th}$$ order ODE on the interval $$\alpha< t < \beta$$ is a function $$\phi$$ such that $$\phi', \phi'',\dots, \phi^{(n)}$$ **exist** and satisfy:

$$
\phi^{(n)}(t)=f\left(t, \phi(t), \phi^{\prime}(t), \ldots, \phi^{(n-1)}(t)\right)\tag{2.2}
$$

for every $$t$$ in $$\alpha< t < \beta$$. Need to investigate the **existence** and **uniqueness** of solutions of differential equations. 

