## Definition
- 5 tuple of 
	- States
	- Alphabet containing symbols
	- Transition function - input is set of tuples of (state, input) and output is what state to move to next
	- Start State
	- Set of acceptance states

## Description
- Moves from state to state based on input string and current state
- Also known as a Finite State Machine
- Good for machines with little memory

## Terminology
- States
- Start State
- Acceptance State
- State Transition
- Alphabet

## Reversing a DFA
- Start state is either of final states
- Turn arrows of machine (reverse arrows)
## Intersection and Union of Two DFAs
- Cartesian product of two machines
- For intersection, final state would have to be the product of two final states
- For union, final state is product of at least 1 final state
- Start state is product of two start states for both