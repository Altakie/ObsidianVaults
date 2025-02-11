	
> Form is $dy/dt = f(t,y)$
# Ways to Solve
 - Linear - Integrating Factor
 - Separable
 - Usually need initial condition to solve for C (constant of integration)
## Integrating Factor
 > Section 2.1 In the text
- One integrating factor is $\mu (t) = e^{\int p(t)dt}$ 
- General form of the equation is $dy/dt + p(t)y = g(t)$
 - $p(t)$ is the coefficient of the 0th order derivative divided by the coefficient of the 1st order derivative
 - General solution is $y(t) = \frac{1}{\mu (t)}(\int \mu (s) g(s) ds)$
 ### Steps to solve
1. Find an integrating factor $u(t)$ (or compute using an existing one)
2. Multiply both sides of the equation by $u(t)$ 
3. Identify what the left hand side of the equation is a derivative of, and rewrite the left hand side as that unsimplified derivative 
4. Integrate out the derivative to find general solution
5. Solve for C using initial condition and plug that into your general solution to get the answer

## Separable Differential Equations
>  Section 2.2 in text
- General form is $dy/dx = (f(x,y))$
- To solve, set $dy/dx = (f(x,y)) = F(x)/M(y) \implies \int M(y)dy = \int F(x)dx$
## Modeling with First Order Equations
> Section 2.3 in text
- Can turn second order ODEs into first order sometimes to make it simpler to solve	
## Differences between Linear and Non-Linear DEs
> Section 2.4 in text
- Existence and Uniqueness Theorem (1st order **linear** DE)
	- If the functions $p(t)$ and $g(t)$ are continuous on an open interval $I: a < t < b$ containing $t=t_0$, then there exists a unique function $y = \phi (t)$ that satisfies the DE $y' + p(t)y = g(t)$ with initial value $y(t_0) = y$ for each $t$ in $I$. $y_0$ is an arbitrarily prescribed initial value
	- This theorem guarantees:
		- A nice enough linear ODE has a unique solution
		- Can find an Interval of Existence without solving ODE
		- Interval containing $t_0$ in which $p(t), g(t)$ are continuous 
	- In English, this basically means that if $p(t)$ and $g(t)$ are continuous on some interval, there is a solution for every t on that interval
- Existence and Uniqueness Theorem (1st order **non-linear** DE)
	- If the functions $f(t)$ and $df/dy$ are continuous on an open interval $I: a < t < b,\ c < y < d$ containing $(t_0,y_0)$, then in some interval $t_0 -h < t < t_0 +h$ there is a unique solution $y= \phi (t)$ that satisfies the Initial value problem 
	- $f(t)$ is in form $dy/dt = smth$
	- Key Differences with other theorem
		- **Cannot** find an Interval of Existence without solving ODE
		- Interval of Existence for linear case doesn't depend on $y_0$, this does
		- Not always applicable
	- In English, this basically means that you need to solve the equation to figure out the interval of existence
## Autonomous ODE and Population Dynamics
> Section 2.5 in text

### Autonomous Equations
- An equation in which the independent variable does not appear explicitly 
	- Independent variable is usually time
### Types of Population Dynamics
- Simple model
	- $p' = \gamma p$
	- Autonomous (no t)
- 
	- $p' = \gamma (1 - \frac{p}{10}) p$
	- Autonomous (no t)
### Phase Line
- Like a simplified direction field
	- Think a number line but with arrows on the number line that point in the direction the value is changing along an interval

### Stable and Unstable Equilibriums
- Stable
	- Solutions approach equilibrium from both sides
- Unstable
	- Solutions diverge from equilibrium from both sides
	- Also known as a source
- Asymptotically Stable
	- Solutions approach equilibrium from both sides and end up in equiibrium
	- AKA sink
	- Not the same as stable
- Semi-stable
	- Solution approaches from one side but diverges from other
	- Follow same direction/ do not change behavior after equillibrium point