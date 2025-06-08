# Top Level
## Eval
- Just a giant conditional (switch statement)
- Takes in expression and environment
	- Expression is list with arguments
	- Environment is list of frames
- Checks if a keyword is a specific type (using a function that returns a boolean)
## Apply
- Co-routine with eval
	- They call each other


# Environments
- Frames are just cons cells
	- First points to list of parameters
	- Second points to a list with the values of those parameters 
- Environments are lists of frames
	- Each environment has a pointer to its parent environment
		- When looking up a variable in environment, first go through current environment, look through all the bindings in the frame
		- If not found, go to parent environment
		- If current environment empty, variable is unbound (error)