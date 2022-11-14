---
permalink: /tutorials/plots
title: "Getting started with Plots.jl"
---

Plotting $\sin x$ is very easy. For our `x` coordinates, we can create a range from $0$ to $2\pi$ of, say,
100 elements. For the `y` coordinates, we can create a 1D array, a `Vector{Float64}`, by evaluating `sin(x)` 
in an element-wise fashion. To do this in Julia, we insert a dot right after the function call. This behavior 
is different from Python, where it is implicitly element-wise; mathematically, the sine of a vector is undefined, 
so Julia does not define it either.

```
x = range(0.0, 2*pi, length=100)
y = sin.(x)
```
