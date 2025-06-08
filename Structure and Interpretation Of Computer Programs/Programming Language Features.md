- The code you write is just a string parsed by the interpreter
- Everything can be encoded as a number

# Static Binding
- Fast lookup of variables
# Dynamic Binding
- Procedures aren't bound to where the procedure was declared, but where it was called.
- Basically means you can use characters that are traditionally "out of scope"
- Apply defined differently
	- Usually (define (apply procedure arguments))
	- Now (define (apply procedure arguments environment))
# Normal Order Evaluation
- Don't evaluate arguments of procedures immediately
- Only evaluate them when they are used
	- Read eval print loop
	- Applying procedure
	- Applying primitive procedure
	- Conditions
- Actual value procedure to force evaluation
	- Have multiple procedures based on whether your arguments are real or delayed
- Thunks are unevaluated thingies

# Compilers
- Compilers do syntax analysis first to make the code easier to run, and only do it once.
- Optimization before the code is actually run
- Makes run-time faster
- Can't enter infinite loops
- Compilers when they first analyze code will always have some sort of redundancy because it is so algorithmic (not dynamic) in its analysis
	- Need a peephole optimizer to remove redundancies in code
- Continuations can be used for compiler

## One Implementation
- Analyzer detects what kind of syntax it is and then passes it to function that evaluates that kind of syntax
- Cleanup procedure to clean up redundant code and optimize things
- Back-quote doesn't spit out an explicit string, it semi-evaluates something and then spits out the string for that

# Explicit Continuation Evaluator
- Primitive procedures curried (one argument procedures with a value passed into them)
	- NOT (\*3 5) but instead  ((\*3) 5)
- Continuations are used to throw away a specific list of procedures to apply if they run into an error

# Lexical Addressing
- Can compute the variable's index in the environment
- Done during compile time
- Compiler returns a quoted list structure of variables
- Defining Procedures that are Mutually Recursive
	- First put the names of the procedures into the environment and generate their lexical addresses
- Compiler should only work off of variable names, not variable values
- ***A lexical address is not a pointer to a variable in a list, it tells you how many environments "up" you have to go in order to find the variable***