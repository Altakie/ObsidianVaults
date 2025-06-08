- Linearizability
	- Real time
- Serializability
	- Every transaction has many reads/writes
	- Should run concurrently, but behave as though they run one at a time
	- ACID
- External Consistency 
	- A transaction that completes before another should appear as though it completed before the other transaction everywhere in the system


# Main Ideas
- Want to hide complexity from programmer (make it look like they are on a simple machine)
- Don't want to sacrifice performance
# Papers
## Map Reduce
- Workload should be representative as map reduce operations
	- Map and reduce operations have no side effects
- Computations should be idempotent

### Bottlenecks
- Network
- Large Files

### Performance
- Sharding
- Central coordinator
- Parallelism
- Tasks assigned with locality
	- Local reads
	- Map results are written locally 
	- Also local reduce of map results
## GFS
- For internal use
- Big files
- Mostly appends and sequential reads
- Split files into chunks (shards), each chunk assigned to a chunk server
- Each chunk server replicated several times
### Reads
- Can read from any replica
- Usually read from closest
### Writes
- Writes go to primary
- Primary orders writes
	- Order is sent to all replicas
- Write is not blocking, so not linearizable

### Leases
- Ensure only one primary
- Need to have a lease to act as primary
- Updated through heartbeat messages
	- Short heartbeat
		- Can overload network with data
		- Can think some machines are dead without them being actual dead
			- Wasted fault tolerance
	- Long heartbeat
		- Takes a long time to detect a machine is dead
		- Slows down the system

## Paxos
- RSM
	- Replicated state machine
- Every operation runs a paxos

### Reads
- Reads from learner, which learns value when majority learns order

### Fault tolerance
- Better tolerance because only majority needs to live
- No need to worry about recovery


### Protocol
- Proposing
	- Must have a higher number proposal than anything before
- Accepting
	- If haven't seen a larger proposal, promise they won't accept a smaller proposal
	- Send back highest accepted number and value
- If proposer hears back from majority
	- Sends accept request to all servers that got its prepare request
	- Acceptors will accept unless they responded to a prepare request with a higher value

### Persistence
- Accepted values are written to disk or logged
- Majorities share at least one member between them
	- Guarantees progress
### Getting stuck
- If majority cannot communicate 
- If proposal numbers are chosen badly

### Optimizations
- Primary

## Zookeeper
- Practical application of Paxos
- Only replicates state
- Optimized Reads
- Writer decides order
- Not linearizable
	- Writes are linearizable
- Batches writes
	- Asynchronous operations
- Read own writes
- Can subscribe to changes with node (watch)
	- Avoids polling
- Ephemeral nodes
	- Deleted when session ends
- Local reads

## Chain Replication

- Higher throughput than primary backup scheme
	- Reads and writes are split
	- Writes are very slow because they have to be propagated through the entire chain
- Failures


## Distributed Transactions
- Two phase commit 
	- Protocol
		- Grab locks
			- Two phase locking
				- Grab all locks that you need at the beginning and don't release until commit
				- Can release read locks early
		- Prepare
			- Replies to prepare
			- Does operation and sends back okay
		- Commit
			- Coordinator logs decision to commit
			- Release locks
			- Logs update in a way such that if it crashes, the change will persist past a crash
		- Confirm commit
			- Nevermind don't need this
	- Can be aborted
- Nodes should be replicated or if node fails, system is not durable
- Coordinator cannot crash
	- Needs to be replicated
## Spanner
- External Consistency no matter where geographically
- Snapshot isolation
	- Based on versions
		- All modifications based on all transactions
	 - Every read-only transaction has to pick a version
 - Use time intervals
	 - Highest version less than me
	 - Commit after the latest time interval


## Chardonnay
- Optimized two-phase commits

## FARM

## Memcached

## PNUTS