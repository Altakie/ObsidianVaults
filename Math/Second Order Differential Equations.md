
# Homogeneous Equations with Constant Coefficients


# Linear Homogeneous Equations
> Section 3.2 in text

- Existence and Uniqueness theorem for second order linear and homogeneous equations
	- If $p(t),q(t),g(t)$ are continuous on an open interval I that contains $t_0$, then IVP has exactly one solutions that exists throughout I
		- Missing something here
- Main Theorem
	- Suppose $y^1, y^2$ are two solutions of $y'' + p(t)y't + q(t)y = 0$ where p and q are continuous functions on some open interval I. Then the two solutions are called a fundamental set of solutions of the previous equation and the general solution is $y(t) = c_1y_1(t) + c_2y_2(t)$ if and only if (Wronskian) $W[y_1, y_2] (t) \neq 0, \forall t \in I$ 
		- $$W[y_1,y_2](t) = \begin{matrix}
 y_1(t) & y_2(t) \\
 y'_1(t) & y'_2(t)
\end{matrix}$$
- Abel's Theorem
	- If $y_1$ and $y_2$ are solutions of $y'' + p(t)y' + q(t)y = 0$ where $q(t)$ and $p(t)$ are continuous on open interval $I$, then the wronskian $W[y_1, y_2] (t) = c*expr(- \int p(t)dt)$ where $c$ is a certain constant that depends on $y_1, y_2$ but not on $t$. 