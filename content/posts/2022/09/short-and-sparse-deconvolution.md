+++
date = 2022-09-13T02:00:28-04:00
title = "Short and Sparse Deconvolution"
description = ""
slug = ""
authors = []
tags = []
categories = ["research", "projects"]
externalLink = ""
series = []
draft = true
+++


<!-- Setting -->
Many signals arising in science and engineering, such as [calcium signals from neuronal spike trains](https://openreview.net/pdf?id=Byg5ZANtvH) or [electron microscopy images](https://www.nature.com/articles/s41467-020-14633-1), can be modeled as sparse superpositions of localized, recurring motifs.

{{< rawhtml >}}
<p style="text-align:center;">
<img src="/images/projects/sasd-stm.png" width="80%"/>
</p>
{{< /rawhtml >}}


We can idealize the resulting signal $\bm y$ as a convolution between a *short kernel* $\bm a \in \R^n$ (where only the first $p$ entries are nonzero, $p<n$) and an *activation map* $\bm x \in \R^n$ or, in other words, $\bm y \approx \bm a * \bm x$.

In many applications, we would like to recover the consituent components up to some shift in $\bm a$ and $\bm x$.

![Short and sparse convolution](/images/projects/sasd-conv.png)

## Optimization and Geometry

One possible formulation for this task is the following optimization problem:

$$\begin{aligned}
\min_{\hat{\bm a},\\, \hat{\bm x} \ \in\ \R^n} \quad
&\frac12\Vert\bm y - \hat{\bm a} * \hat{\bm x}\Vert_2^2 + \lambda\Vert\hat{\bm x}\Vert_1,
\\\\
\text{s.t.} \quad
&\Vert \hat{\bm a}\Vert_2 = 1, \quad
\hat a_{p+1} = \hat a_{p+2} = \dots = \hat a_n = 0.
\end{aligned}$$

Notice that in addition to using the $\ell_1$-norm to promote sparsity in $\bm x$ and the shortness requirements for $\hat{\bm a}$, we also require that $\hat{\bm a}$ live on the sphere $\mathcal S^{n-1} = \\{\bm z\in \R^n: \Vert z \Vert_2 = 1\\}$. The restriction of the norm of $\bm a$ is important because convolutions have *scale-symmetry*, which makes $\bm a$ unidentifiable otherwise.
Furthermore, the optimization problem is nonconvex, so it is not immediately clear that this formulation lends itself to standard optimization techniques.

We discovered, surprisingly, that the specific choice of putting $\bm a$ on the *sphere* leads to benign optimization properties. In fact, once the objective is marginalized by minimizing $\bm x$, the remaining objective landscape (over the sphere in $[\hat a_1, \dots, \hat a_p]$),

1. Is strongly convex near shifts of $\bm a_0$;
2. Has saddle points between shifts of $\bm a_0$, with negative curvature pointing towards individual shifts; and
3. $\hat{\bm a}$ can be initialized to be in the vicinity of (1) or (2).


{{< rawhtml >}}
<p style="text-align:center;">
<img src="/images/projects/sasd-geometry.png" width="60%"/>
</p>
{{< /rawhtml >}}



<!-- Applications -->
