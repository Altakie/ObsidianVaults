## Throughput
- Multiple replicas can handle processing
- Large chunk sizes make the metadata small
	- Metadata only stores locations of chunks
- Clients cache chunk location for a small time so they don't have to unnecessarily contact the master
## Fault Tolerance
- Multiple replicas of every chunkserver, if one goes down, others exist as backups
- Master handles chunkservers, if one goes down it will redirect clients to another
## Consistency Guarantees
### Primary Chunkserver and Leases
- When writes happen, there is a primary chunkserver that decides the order of the writes and reports it to the other chunkservers, so they can apply the write to other chunkservers
	- This primary chunkserver is given a **lease**, which tells it the time it can act as a primary. If it wants to keep acting as a primary, it needs to renew the lease.
	- Only one chunkserver can have a lease for a given chunk at a time, so we cannot possibly have 2 primaries at the same time
	- Master needs to wait for previous lease to expire before assigning a new primary
### Types of Regions
- Defined
	- Mutations are accurately reflected in the data and all clients will see the same thing no matter which replica they read from
- Undefined but consistent
	- No matter which replica is read from, clients will always see the same thing, but mutations may not be accurately reflected in the data
	- Happens when multiple concurrent writes happen
- Inconsistent
	- Not all clients may see the same thing
	- Happens when primary or chunkserver crashes during a write
	- One of the replicas is out of sync
### Version Numbers
- Chunk servers have version numbers to check if they are out of date

## Problems
- Only have one master, turns out to cause problems
- Sometimes have inconsistent regions - bad
- Chunkservers are bad at storing small files

## Reading Question
Describe a sequence of events that would result in a client reading stale data from the Google File System.

>A series of steps that could result in a client reading stale data form GFS is first a client reads from a chunkserver,  then that chunkserver goes down while a mutation occurs on another chunkserver. This means that chunkserver is not updated with the most up to date information from the other replicas. However, the client that interacted with that chunkserver before it went down cached its chunk handle, and that cached chunk handle didn't expire. This client now wants to read information from GFS again, so because the client has the stale chunkserver cached, it reads from it and gets stale data. This would only happen in the window where the client's cache entry did not expire.