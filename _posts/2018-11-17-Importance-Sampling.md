---
layout: post
title: Importance sampling
---
This post is about importance sampling. Although it seems to be a sampling method as its name suggests, it is actually a method for estimating the expectation of some certain function w.r.t a probability distribution.

$$\mathbb{E}(f) = \int p(z) f(z) dz$$

One simple strategy is to take discretised $z$ values in $z$-space uniformly and the expectation above is approximated by

$$ \mathbb{E}(f) \approx \sum_{l=1}^{L} p(z^{(l)}) f(z^{(l)}) $$

However, it is inefficient because small value of $p(z^{(l)}) f(z^{(l)}) $ attributes few for the expectation $\mathbb{E}(f)$. Only a small region of $z$ makes contribution to the sum. As the dimensionality of $z$ grows, the situation will get worse.

As we do in rejection-sampling, in importance sampling we also have propose distribution $q(z)$, which is easy to take samples from it. The expectation $\mathbb{E}(f)$ is reformulated.

$$\begin{align}
\mathbb{E}(f) &= \int f(z) p(z) dz \nonumber \\
&= \int f(z) \frac{p(z)}{q(z)} dz \\
& \approx  \frac{1}{L}\sum_{l = 1}{L} \frac{p(z^{l})}{q(z^{(l)})} f(z^{(l)}) \label{equ:approx_e}
\end{align}$$
