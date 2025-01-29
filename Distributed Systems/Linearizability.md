

## Definition
- A linearized system behaves like a normal sequential program. To do this it needs:
	- Atomic changes
	- History is linearizable
		- Operations need to appear like they happened in the real-time order they finished in
		- Think like a time line, all operations must fit on a common time line and have a defined order on that time line
		- Ex: All clients must see writes in the same order
	- There must be consistency across replicas
## Pros
- Matches programmer intuition

## Cons
- Not all systems are linearizable
- Comes with performance costs