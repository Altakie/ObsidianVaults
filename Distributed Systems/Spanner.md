# How it works
- Sharding
	- Data is automatically split over several servers
- Paxos
	- Writes happening via Paxos

# Read-Only Transactions
- No locks
- Reads from closest replica (local reads)
- No two phase commits
- Maintain correctness
	- Serializable
		- Like linearizable but for multiple operations
		- All writes of preceding transactions or none
	- Externally Consistent
		- If $T_1$ completes before $T_2$ starts, $T_2$ must see the results of $T_1$
		- This must happen even if $T_1$ happens across the globe
		- Both of these together create real-time ordering
- Like reading history
	- Time stamps are only needed to support read-only transactions 


