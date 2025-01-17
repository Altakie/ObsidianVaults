# 1.1 Direction Fields

> Direction fields are like vector fields but they denote direction instead and you can see direction from them because they are denoted as lines 
> ![Direction Field](https://images.squarespace-cdn.com/content/v1/533db07de4b0d9f7ba7f1e77/1531405502901-FC694UQ1OKIXKG3C1G4Q/solution+curve+in+the+direction+field.png)
### Example: 
> Suppose an object is falling near the sea level. Formulate a diff eq that describes the motion:

$$
F=ma=m\frac{dv}{dt} = mg -\gamma v
$$
$$
m = 10kg
$$
$$
\gamma = 2kg/s
$$
$$
g = 9.8 m/s
$$
$$
dv/dt = 9.8 - v/5
$$

### Ex 2:
> Without solving \*, investigate qualitative behaviors

Direction Field / slope field / vector field line segments with slope dv/dt in the t,v plane

| t    | v   | dv/dt(RHS)      |
| ---- | --- | --------------- |
| -    | 60  | 9.8 - 12 = -2.2 |
| <br> | 55  | -1.2            |
|      | 49  | 0<br>           |
|      | 45  | 0.8             |
### Ex 3:
$$
p/2 - 3 = 0 => Peq = 6
$$
# 1.2 Solutions of Some Diff Eqs
### Ex 1:
> Solve 
> $$
dv/dt = 9.8 - v/5
$$ 

$$
dv = (9.8 - v/5)dt
$$
$$
\int \frac{dv}{9.8-v/5} = \int dt
$$
$$
\int \frac{dv}{v/5 - 9.8} = \int -dt
$$
$$
ln|v-49| = \int \frac{dv}{v - 49} = \int -1/5dt = -1/5t + C
$$
$$
|v-49| = e^{1-5t} * e^c
$$
$$
v-49 = \pm e^{1-5t} * e^c
$$
$$
v = 49 \pm e^{1-5t} * e^c
$$
The above is the general solution
The equation solution is v = 49

### Ex 2:
> Initial Value Problem
> Suppose this object is dropped from a height of 300m. Find its velocity at any time t.
> where v satisfies
> $$
 dv/dt = 9.8 - v/5
 $$
 > How long does it take to fall to the ground. How fast will it be falling at the time of impact?
 
 $$
\displaylines{
 v = 49 + ce^{-t/5} \\
 v(0) = 0 \\
 c = 49 \\
 v(t) = 49 - 49e^{-t/5} 
 }
 $$
 Choose coordinate system for $$\gamma (t)$$ such that 
 $$
 \gamma (0) = 0
 $$
 $$
 \displaylines{
 dx/dt = v(t) = 49 - 49e^{-t/5} \\
 \int dx/dt = \int v(t) = \int 49 - 49e^{-t/5}dt \\
 x(0) = 245 + k = 0 \\ 
 k = -245 \\ \\ 
 x(t) = 49t + 245e^{-t/5} - 245 = 300
 t ~  10.51s
 v(10.51) - 43.01 m/s
 }
 $$
### Ex:
> Solve 
> $$
dP/dt = P/2 - 3
 $$
 > When P(0) = 6 or when P(0) = 5

$$
\displaylines{
dP/dt = P/2 - 3 \\
\int dP/dt = \int P/2 - 3dt \\
P = 6 + ce^{t/2}
\\ \\
P(0) = 6 \\
p(t) = 6
\\ \\ 
p(0) = 5 \\
P(t) = e^{t/2}
}
$$

# 1.3 Classification of Diff Eqs
## ODE
>  A single independent variable (Ordinary DE)

## PDE
> Multiple independent variables (Partial Diff eq)