# Why use Streams
- Sometimes want to delay evaluation to not waste computing power

# What Streams do
- Delay evaluation
	- Evaluation order is no longer substitution model
	- Demand driven evaluation
		- Only compute what you need
		- However, need to keep track of what is not being computed which is also overhead
- Like a list
	- However, instead of having pointer to next block, has procedure with no args that generates more of the list
		- This is how you generate only what you need
	- This allows streams to potentially be infinite
		-  Can be used to represent infinite data types, like real numbers
- Memoized Streams
	- Idea is to save the work you've already done so you don't have to do it again
	- Build a list with the pieces you have already computed

# Types of Numbers
## Rational Numbers
- Pair of integers
	- Numerator
	- Divisor
## Real Numbers
- Represented as an infinite stream of digits after the decimal point
- Can generate any degree of precision
	- However, can't tell if a number is equal to 0 because of infinite sequences
# Continuity
- Can only consume a finite amount of input to produce the output

# Data Structures
- Can generalize any data structure to be infinite
	-  Think procedural generation