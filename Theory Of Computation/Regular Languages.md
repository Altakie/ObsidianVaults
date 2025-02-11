# Regular Operations
- Operations on languages
## Types of Regular Operations
### Union
- Anything that is in one set or the other set
### Concatenation
- Adding everything in one set to another set, not as another element, but creating new elements that are combinations of the elements of both sets
	- $A^1 \circ A = A^2$
	- $\circ$ represents concatenation operation
### Star
- 0 or more copies of something
### Plus
- 1 or more copies of something



# Closure
- A collection of objects is closed under an operation if applying that operation to any object in the collection results in another object within the collection
- Regular languages are closed under union, concatenation, and star
- Closed under reverse (compliment)
- Closed under intersection

# Ways to Express
- DFA or NFA
- Grammar
- Expression (only at some level)
	- [[Regular Expressions]]

# How to Check if a Language is Regular
- If you have to count, it is not regular
- If you cannot make a DFA for it, it is not regular
- Pidgeon-hole principle
	- IF D is a DFA, any string accepted by D that is longer than a certain length must have visited some state twice
- Pumping Lemma 
	- For any regular language L, there exists a pumping length such that for any string $w \in L$, where $|w| \geq p$, we can write $w = xyz$ (basically splitting the string into 3 pieces) with:
		1. $|xy| \leq p$ (Not always used in proof)
		2. $|y| > 1$
		3. $xy^iz \in L$, where $i$ is a natural number (i can be 0)
	- If the Lemma fails, the language is not regular
	- Regular Language $\implies$ Pumping Property
	- Just because the lemma succeeds, **does NOT** mean the language is regular
	- The "pumping" is just repeating the sequence y over and over again
	- If you can choose an i such that the string will no longer be in the language, and one that is, the language is **NOT** regular
	- If you can successfully split it and the string cannot be pumped, then it is not regular
		- This means that no matter what x,y,z you choose, it cannot be pumped
- Opposite of Pumping Lemma (more useful)
	-  $\neg$ Pumping Property$\implies$ $\neg$ Regular Language
		- $\forall$ p pumping length, $\exists$ string $w \in L$, where $|w| \geq p$
		- $\forall x,y,z$ such that $w = xyz$:
			1. $|xy| \leq p$ (Not always used in proof)
			2. $|y| > 1$
			3. $\exists i \geq 0$ such that $xy^iz \notin L$
		- Basically for every pumping length there is a string that cannot be pumped
		-  Prove a language is not regular by contradiction
			- Assume a language is regular, then strings should be able to be pumped. If we find a unpumpable string then the language is not regular