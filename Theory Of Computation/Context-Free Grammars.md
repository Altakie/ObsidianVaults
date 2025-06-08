# Definition
- Collection of 4 objects
	1. Terminals
		- Symbols of alphabet of language being defined
		- Analagous to alphabet
	2. Variables
		- Finite set of other symbols, each of which is a language
		- Analogous to states
	3. Start Symbol
		-  The variable whose language is being defined
		- Analogous to start state
	4. Rule
		- Rules by which to transform variables
			- Analogous to transition functions
# Ambiguity
- If there is a string in the language that is a result of two or more parse trees
	- Solved using parenthesis

# Chomsky Normal Form
- Must rules must be of the form
	- $A \rightarrow BC$
	- $A \rightarrow a$
- Creates a binary parse tree
## Converting to Chomsky Normal Form
- Create new start symbol
- Eliminate $\varepsilon$ production
- Eliminate variable unit productions
- Move terminals to unit productions

# Closure Properties
- Union
- Intersection
	- **NOT** with another CFL
	- Yes with regular language
- Complement
	- **NOT** Closed
	- Because DeMorgan's Law

# Decision Properties
- String is in CFL
	- Chomsky normal form
- String is empty
	- If the start symbol only goes to $\varepsilon$ (in Chomsky normal form)
	- If the only terminal any rule ever goes to is $\varepsilon$
  - Equivalence of CFGs

# Pumping Lemma
- If L is a CFL, there is a pumping length $p = 2^k$, where if $w$ is any string L of length at least p then w can be divided into 5 pieces $w = uvxyz$ satisfying the conditions:
	1. $|vxy| \leq p$
	2. $|vy| \geq 0$
	3. For each $i \geq 0, uv^ixy^iz$ is still in the language
	   