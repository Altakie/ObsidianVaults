# Turing Reduction
- If A reduces to B, you can use a solution to B to solve A
- If A is reducible to B and B is decidable, then A is also decidable
- If A is reducible to B and A is not decidable, then B is also not decidable
- How to do
	- Use decider for A to solve B
	- Map into to A for input to decider for B
	- Map results from B back into A
#  Mapping Reduction
- Function f(x) that takes a string x from domain and maps it to a string in B
	- Does not need to be surjective, injective, or bijective
- Reducable if every input #TODO
	- Everything in A maps to B
	- Everything not in A maps to something not in B
- Translate A question to B question
- Used to show stuff is not recognizable
## Computable Functions
- #TODO 