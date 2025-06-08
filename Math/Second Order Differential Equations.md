
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

# Complex roots of Characteristic Eq
> Section 3.3 in text

- Can't have imaginary number in exponent of $e$
- The general solution of $ay'' + by' + cy = 0$ when root of $ar^2 + br + c = 0$ is $\lambda \neq ui$ is $y-c_1e^{\lambda t}$ 
- Theorem
	- Consider $y'' + p(t)y'+q(t)y = 0$ where $p(t)$ and $q(t) are continuous real-valued functions. If $y = u(t) + i v(t)$ is a complex-valued soln, then $u(t)$ and $v(t)$ are also the solutions 

# Repeat Roots
> Section 3.4 in text
- Method:
	- Order of reduction

# Non-homogeneous Equations
> Section 3.5 in text
- Theorem 3.5.1
	- If $Y_1$ and $Y_2$ are two solutions of $(NH)$ then their difference is $Y_1 - Y_2$ is a solution of $(H)$
- Theorem 3.5.2
	- The general solution of verify $(NH)$ is $y(t) = c_1y_1(t) + c_2y_2(t) + Y_{p(t)}$ where $y_1, y_2$ form a fundamental set of solutions of $(H)$
	- $c_1,c_2$ are arbitrary constants
	- $Y_{p(t)}$ is any solution of $(NH)$