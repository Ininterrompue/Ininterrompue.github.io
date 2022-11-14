---
permalink: /tutorials/plots
title: "Getting started with Plots.jl"
---

The first thing to do is to ensure that `Plots.jl` is installed.
This package is actually a meta-package, a sort of compendium that hosts a bunch of backends.
The default backend is GR. If you want the plots to look like the plots from matplotlib, you must
first install `PyPlot.jl` and then add `pyplot()` after importing the `Plots.jl` package. We'll
stick with GR for now.

```
using Plots
```

Our first plot will be of the functions $\sin x$ and $\cos x$.
For our `x` coordinates, we can create a range from 0 to 10 of, say, 100 elements. The `range` function
is the closest analogue to `np.linspace` in Python. The advantage of `range` is the reduced memory
footprint. If we really need it as a vector (1D array), we can simply do `collect(x)`.

For the `y1` coordinates, we can create a vector by evaluating `sin(x)` in an element-wise fashion. 
To do this in Julia, we insert a dot right after the function call. 
This behavior is different from Python, where it is implicitly element-wise; mathematically, the sine 
of a vector is undefined, so Julia does not define it either.

```
x = range(0.0, 10.0, length=100)
y1 = sin.(x)
y2 = cos.(x)
```

Now we can start plotting. For a line plot, we use `plot()`. We can assign this to some variable which 
we call `plt`, but this is not strictly required. You may be working in an IDE or a notebook where the 
plots don't show up by default. If the plot doesn't show up, you'll need to call `gui()` (or `display(plt)`) 
explicitly for the plot to display.

```
plt = plot(x, y1)
```

This plots the sine function only. To plot both functions, we insert brackets:

```
plt = plot(x, [y1, y2])
```

This is a bare-bones plot with a default legend and no title/axes. Let's give it some. The `!` after the
function names in Julia means that the function is modifying one or more of its arguments. Here, it is
modifying the current plot. Notice that the `plot!()` function doesn't need to plot a second set of data;
if we want to remove the legend, we can simply write `plot!(legend=false)`.

```
plot!(legend=false)
title!("Trig functions")
xlabel!("x")
ylabel!("y")
```

Alternatively, we can define all of these things in one line. It's up to you whether to have these attributes 
on one line or multiple lines. 
Here, instead of removing the legend, we'll have a `label` for the data. The label also takes in a vector of 
the same number of elements as the number of columns of the `y` argument, in our case 2.

```
plt = plot(x, [y1, y2], title="Trig functions", xlabel="x", ylabel="y", label=["sin(x)", "cos(x)"])
```

Now, there's a bunch of other things that a scientific programmer is interested in besides this. I'll
go over these by section.

## Legend placement 
Perhaps the legend is in a bad spot, obscuring the data. We can change the location by setting the 
`legend` keyword argument.

```
plot!(legend=:bottomleft)
```

For legends within the plot axes, this keyword can take on the following possible values:
`:right, :left, :top, :bottom, :inside, :best, :legend, :topright, :topleft, :bottomleft, :bottomright`.
To have legends outside the plot axes, simply prepend `outer` to these names, such as `:outertopleft`.


