---
permalink: /sandbox
title: LaTeX sandbox
---

# Quadratic equation

Given the quadratic equation $ax^{2} + bx + c = 0$, the quadratic formula is

$$\begin{equation}
x = \frac{-b \pm \sqrt{b^{2} - 4ac}}{2a}.
\end{equation}$$

When dealing with floating-point arithmetic, the numerator can suffer from 
catastrophic cancellation if $|b|$ is very nearly equal to $\sqrt{b^{2}-4ac}$. Therefore, it is sometimes 
necessary to use Citardauq's formula

$$\begin{equation}
x = \frac{2c}{-b \mp \sqrt{b^{2} - 4ac}}
\end{equation}$$

and choose the roots among these two formulas which avoid the cancellation.

# Einstein field equations

The Einstein field equations relate the geometry of spacetime to the distribution of matter with it:

$$\begin{equation}
R_{\mu\nu} - \frac{1}{2}g_{\mu\nu} = \frac{8\pi G}{c^{4}}T_{\mu\nu}
\end{equation}$$