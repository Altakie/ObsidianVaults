
> Form is $dy/dt = f(t,y)$
# Ways to Solve
 - Linear - Integrating Factor
 - Separable
## Integrating Factor
 - One integrating factor is $\mu (t) = e^{\int p(t)dt}$ 
 - $p(t)$ is the coefficient of the 0th order derivative divided by the coefficient of the 1st order derivative
 - General solution is $y(t) = \frac{1}{\mu (t)}(\int \mu (s) g(s) ds)$
 ### Steps to solve
1. Find an integrating factor $u(t)$ (or compute using an existing one)
2. Multiply both sides of the equation by $u(t)$ 
3. Identify what the left hand side of the equation is a derivative of, and rewrite it like that 
4. Integrate out the derivative to find general solution