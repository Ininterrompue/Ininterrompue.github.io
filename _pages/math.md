---
permalink: /sandbox
title: "Experimenting with LaTeX"
---

Given the quadratic equation $ax^{2} + bx + c = 0$, the quadratic formula is
$$
    x = \frac{-b \pm \sqrt{b^{2} - 4ac}}{2a}.
$$
When dealing with floating-point arithmetic, it is sometimes the case that the numerator suffers from 
catastrophic cancellation if $|b|$ is very nearly equal to $|\sqrt{b^{2}-4ac}|$. Therefore, it is sometimes 
necessary to use Citardauq's formula
$$
    x = \frac{2c}{-b \mp \sqrt{b^{2} - 4ac}}
$$
and choose the roots among these two formulas which avoid the cancellation.