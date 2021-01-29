---
layout: post
title: "ODE and PDE, Basics II"
date: 2021-01-28
progress: 100%
permalink: /am105/part2/
---

* listnotshown
{:toc}

### 1. Separable Differential Equations

Set $$x$$ as the independent variable and $$y$$ is a function of $$x$$, we can generally write the first-order differential equation in the following form:

$$
M(x, y)+N(x, y) \frac{d y}{d x}=0\tag{1}
$$

where $$M$$ and $$N$$ are two functions of $$x$$ and $$y$$. Let's say, when $$M$$ is a function of $$x$$ and $$N$$ is the function of $$y$$ only, equation (1) becomes:

$$
M(x)d(x) + N(y)dy = 0 \tag{2}
$$

This can be easily integrated to solution:

$$
H_{1}(x)+H_{2}(y)=c \tag{3}
$$

where $$H_{1}(x) = \int M(x) dx$$ and $$H_{2}(y) = \int N(y) dy$$. The constant $$c$$ is determined by the initial value.

<p class='redbox'>
An example, we want to solve the following first-order differential equation:

$$
\frac{d y}{d x}=\frac{x^{2}}{1-y^{2}}
$$

which is apparently separable.<br>

<i class="contrast">Solution:</i><br>

Rewrite it in the form of equation (2):

$$
-x^{2}dx+\left(1-y^{2}\right)dy=0
$$

So:

$$
H_{1}(x) = \int (-x^2) dx = -\frac{1}{3}x^3 + c_1 \\ H_{2}(y) = \int (1-y^2) dy = y-\frac{1}{3}y^3 + c_2
$$

We have:

$$
-\frac{1}{3}x^3 + y - \frac{1}{3}y^3 = c
$$

Constant is determined by some boudnary condistions

</p>