Regression
===


####**Guass-Newton Method**

for solving non-linear mean-square


####**Gradient Descent Method** (steepest descent)

assume the gradient can be computed
used to find local minimum

while gradient is not 0
1. guess an initial point
2. calculate the gradient at the point
3. take a step in the negative direction of the gradient
4. the next point is obtained

parameter : step

####**Levenberg-Marquardt algorithm**

the combination of steepest descent and Guass-Newton method
when the solution is far from correct, it behaves like steepest descent method, slow but guarantee to converge
when its close, it behaves like guass-newton method


---

reference

[Walfram:Method of Steepest Descent](http://mathworld.wolfram.com/MethodofSteepestDescent.html)

[]()