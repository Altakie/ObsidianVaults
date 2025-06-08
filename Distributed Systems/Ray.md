- Uses Distributed Futures
# Futures
- Lazily evaluated
- Just a pointer to a value
- Can force it to be evaluated


- Transparent recovery of idempotent futures
	- 

# Ownership
- Caller of function owns its future
- Value stored in worker that executes function
# Recovery
- Lineage
	- Every future has a list of invocations that created it
	- This list can be used to recreate that future
- Lineage Reconstruction
	- Re-execute futures and their descendants
		- This means re-execute the root function and all descendant functions
		- Works because data is never actually modified
	- Works because futures are idempotent

# Sharded Table

# Fate Sharing
- If owner crashes, I also crash
- Loss of owned object leads to re-execution