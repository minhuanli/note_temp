---
layout: post
title: "ODE and PDE, Critial Points and Linearization"
date: 2021-06-01
progress: 50%
permalink: /am105/part8/
---
[Content](https://minhuanli.github.io/notes/)

This Note borrowed a lot from section notes by Lan.

* listnotshown
{:toc}

### <i class='contrast'>Classification of Critial Points</i>

Consider the two-dimensional system of first-order linear homogeneous equations with constant coefficients. Such a system has the form:

$$
\frac{d \mathbf{x}}{d t}=\mathbf{A x}
$$

where $$\mathbf{A}$$ is a $$2 \times 2$$ matrix and $$\mathbf{x}$$ is a $$2 \times 1$$ vector. By substituting $$\mathbf{x}(t)=\boldsymbol{\xi} e^{r t}$$ into the above system, we obtain:

$$
(\mathbf{A}-r \mathbf{I}) \boldsymbol{\xi}=\mathbf{0}
$$

We thus know that $$r$$ and $$\boldsymbol{\xi}$$ are an eigenvalue-eigenvector pair of the coefficient matrix $$\mathbf{A}$$. The eigenvalues $r$ are the roots of the polynomial equation:

$$
\operatorname{det}(\mathbf{A}-r \mathbf{I})=0
$$

and the eigenvectors $$\boldsymbol{\xi}$$ can then be determined from the equation $$(\mathbf{A}-r \mathbf{I}) \boldsymbol{\xi}=\mathbf{0}$$ up to some multiplicative constant.

The **<i class='contrast'>critical points</i>** (or equilibrium solutions) of the system are points $$\mathbf{x}$$ where:

$$
\frac{d \mathbf{x}}{d t}=\mathbf{A} \mathbf{x}=\mathbf{0}
$$

Assume $$\det \mathbf{A} \ne 0$$,it follows that $$\mathbf{x}=\mathbf{0}$$ is the only critical point of the system. The nature of the eigenvalues of $$\mathbf{A}$$ allows us to characterize the differential equation according to the geometric pattern formed by its trajectories in a phase portrait.

I. Suppose the eigenvalues of $$\mathbf{A}$$ are real and distinct, with $$r_{1} \neq r_{2} \in \mathbb{R} .$$ The origin $$\mathbf{x}=\mathbf{0}$$ can be classified as follows: 

- If $$r_{1}, r_{2}>0$$, the origin $$\mathbf{x}=\mathbf{0}$$ is an **unstable node**

- If $$r_{1}, r_{2}<0$$, the origin $$\mathbf{x}=\mathbf{0}$$ is an **asymptotically stable node**.

- If $$r_{1}$$ and $$r_{2}$$ have opposite signs, the origin $$\mathbf{x}=\mathbf{0}$$ is an **unstable saddle**.


II. Suppose the eigenvalues of $$\mathbf{A}$$ are complex, with $$r_{1,2}=\lambda \pm i \mu .$$ The origin $$\mathbf{x}=\mathbf{0}$$ can be classified as follows:

- If $$\lambda>0$$, the origin $$\mathbf{x}=\mathbf{0}$$ is an **unstable spiral**.

- If $$\lambda<0$$, the origin the origin $$\mathbf{x}=\mathbf{0}$$ is an **asymptotically stable spiral**.

- If $$\lambda=0$$, the origin $$\mathbf{x}=\mathbf{0}$$ is a **stable center**.

III. Suppose the eigenvalues of $$\mathbf{A}$$ are equal, with $$r_{1}=r_{2}=r$$. The origin $$\mathbf{x}=\mathbf{0}$$ can be classified as follows:

- If $$r>0$$, the origin $$\mathbf{x}=\mathbf{0}$$ is a **unstable improper node**.

- If $$r<0$$, the origin $$\mathbf{x}=\mathbf{0}$$ is a **stable improper node**.










