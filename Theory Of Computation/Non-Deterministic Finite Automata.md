## Differences with DFA
- Like DFA, but can go into more than one state when they see a symbol
- Can move to next state without reading another symbol from input
- Does not need an arrow for each possible state
- Same definition as DFA, but transition function now takes a state and symbol as an input, and the output is the powerset of the current state (all possible next states)

## How does it work?
- When multiple possibilities for next transition state, the machine splits into multiple copies of itself, follow each possibility in parallel 
	- Similar to recursion 
- If at least one valid accept path exists, the machine accepts the input 