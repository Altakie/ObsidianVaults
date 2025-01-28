# What are Programming Languages made of?
- Primitive Expression
	- Simplest entities
	- Like +, -
- Means of Combination
	- Allow compound expressions to be made from simpler ones
- Means of Abstraction
	- Allow compound objects to be named and manipulated and used as if they were primitives

## Procedures
- To evaluate a procedure, substitute what it does into the code
# Recursion
- Can be used for for loops
	- I don't think scheme has normal for loops
- Commands
	- Do something, change something
	- Order in which you do commands matters
	- Think like an order
- Expressions
	- Evaluate to something
	- Order of expressions doesn't matter, unless it is for efficiency
## Space and Time
- The longer a line of code is after substitution, the more space it takes
- The more lines of code after substitution, the more time it takes
- Induction is useful for determining how long a function will take, and for figuring out functions that can evaluate something efficiently

## Tail Recursion
- No work builds up

## Lambda
- Basically just an anonymous function
- Why do we need anonymous functions?
	- If you want to call something repeatedly, you name it so you can reuse it
	- Otherwise you can leave it as an anonymous function

## Fixed Points
- A fixed point is an input into a function that returns itself from the function
	- Any element mapped to itself by a function
	- Ex: if f(x) = x, then x is a fixed point for the function
- Fixed point doesn't need to evaluate to itself, can be defined recursively????

## Composing Functions
- Can take functions(procedures) as arguments and return functions(procedures) as return values

## Currying
- Take a multi argument function and turn it into a single argument function
## First Class Values
- First class values have 3 properties
	- They can be named by variables
	- They can be parameters of procedures
	- They can be returned as results of procedures
- Examples of first class values
	- Procedures
	- Integers
	- Strings
	- Like a lot of things 