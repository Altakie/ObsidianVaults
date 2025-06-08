> Facebook's storage system
# Features
- Freshness of data is not critical
	- Stale data allowed
- Read heavy
- No locality
- High load

# Structure
- Multiple databases
	- SQL databases
		  - Sharded
- Primary/ backup servers
	- Asynchronous syncing between them

## Reads
- Tries to read from cache first, if unable to, goes to server and stores information in local cache
## Writes
- Writes to main server, deletes associated entry from local cache
## Caches
- Not used for speed, but to remove load from database
## Sharding Vs Replication
- Uses a mix of both
- Shards keys
- Hot keys are replicated
## Bringing Up Clusters

## Herds of requests
- Leases
	- Only first miss will go to database, rest are told to wait
## Server Failures

# Consistency

## Read
- Ask db for value
- *Eventually* Consistent
- Can read your own writes
	- This is because key is deleted from local cache

## Writes
- When value is updated, database does 
	- Locks key
	- Tells all caches to invalidate key
	- Waits until all caches respond
	- Updates key
	- Removes the lock
- New value has to be hidden until new write completes

# McSquil
 - Invalidation protocol
	 - Propagates from primary to backup
	 - Sends invalidation messages
# Race Condition
- If one write happens and another one reads stale value and then tries to update
	- Leases on writes
	- Deletes invalidate leases: writes cannot go through
- 