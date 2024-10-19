motivation: previously, we *optimized* a function, meaning we found its absolute extreme, on a region that contained its bounday. finding the potential optimal points within the region isn't so difficult.
- find critical points
- plug them into function
- analyze behavior.

however, when finding optimal points along the boundary of a function, the process is lengthy and rather difficult.

# langrange multipliers

we want to optimize f(x,y,z) subject to the constraint g(x,y,z) = k. 
k may be the equatoin that describes the boundary of f, or it might not be. 
k is just a general constraint. 

## method

1. solve the following system of equations

delta f(x,y,z) = lambda * delta g (x,y,z), where g(x,y,z) = k
2. plug in all solutions (x,y,z) from first step into fx,y,z). 
3. identify min and max values, provided they exist and delta g ~= 0 at the point (x,y,z)

the constraint lamba is called the Lagrange multiplier.

**note**: the delta symbol signifies the gradient of the function.
it tells us at what rate your extreme value changes as we change k.
for instance, in economics, we  might want to maximize utility f subject to a budget under constraint g = k. lambda will tell us about how much additional utility we get if we  slightly increase our budget.
"utility" here could just be like a profit function or something, abstractly meaning just "goodness" as a function of variables.
