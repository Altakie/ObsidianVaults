- Writes happen at most once
# Idempotent Recovery of Log
- Main feature
- Idempotent Recovery on log
	- Write value and sequence number of log to database
	- When you update database, check that sequence number at database is lower than current, otherwise fail the update
		- This means the value was already written
		
# Log
- Tags in log
	- Can only read stream of updates related to particular tag
	- Allows for smaller histories
- Logbooks
- Shared log
	- Stores state transitions
# Ordering
- Logbooks are merged
	- Indexes are not consecutive, but are monotonically increasing
- Operations for traversal
	- Log read next
	- Log read previous 
	- Both take in a tag and a min/max sequence number
- Meta-log imposes order on other logs
	- Meta-log replicated
- Progress vector
	- Set of log records
- Sequencer
	- Picks max sequence number of records that have been replicated everywhere
- Can define total order over log
- Cache so you don't have to scan whole log every time

			- LOG IMPLEMENTATION IS MOST IMPORTANT PART

