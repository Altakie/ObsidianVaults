
# Correct Behavior
- ACID
	- **Atomic**
		- All writes or none
	- **Consistent**
		- Obey app-specific constraints
	- **Isolated**
		- No interactions between transactions/changes
		- Serializable
	- **Durable** 
		- Committed writes are permanent

# Mechanisms for Distributed Transactions
## Concurrency Control
- Pessimistic
	- Locks data before transactions use it
- Optimistic
	- Use data without acquiring locks
	- Check if data has been changed at the end before committing, if it has, roll back

## Atomic Commit
- All changes in commit happen at the same time

# Two Phase Locking
- As data is being used, a lock is acquired for it
	- Phase one
- At the end of the transaction, all locks are released
	- Phase two
	- Needs to happen so that no other transactions can read values that the transaction is modifying
- Can cause deadlocks
	- To avoid, access locks in fixed order
	- Detect deadlocks
	- Abort transaction in case of deadlock
- Pessimistic

# How it works
- Main transaction server (Transaction Coordinator)
	- Creates transactions, asks all others to prepare transaction
		- Once a server prepares to commit, it has to wait for communication from coordinator
	- Once it gets replies that all are prepared, commits and then asks all others to commit
		- Coordinator must remember transaction until it gets commits from all the participants
		- Participants can forget after they send the okay-commit message
	- Participants commit after they are told to commit and send okay-commit message
	- Other servers can send abort messages at any time and transaction will be rolled back
		- Transaction coordinator can also abort any time
	- All servers need to hold locks until commit
- Need replicated coordinator 
	- Coordinator is single point of failure