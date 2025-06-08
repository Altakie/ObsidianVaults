# Environments
## Global Environment
- Created with every program

## Environment
- List of frames 
## Frame
- List if bindings of names to values
- Pointer to another frame
## Environment Frame
- Kind of like stack frames, except it's a list
- Local context with variables defined
- When expressions are evaluated, they are evaluated in their own environment frame

## Eval and Apply
- Evaluate stuff (figure out what it means by looking it up in the environment, and make it into actual code)
- Apply it by actually running the code
## Set!
- Assignment operator
- Command
## Begin
- Evaluates a set of expressions and evaluates to whatever the last expression evaluated to, which allows side effects to occur

## Applicative Order
- Evaluate definitions (up to lambda)
- In a procedure call, evaluate the arguments first

## Normal Order
- Don't compute anything until you absolutely have to except:
	- Testing
	- Printing
	- Evaluating functions
- 