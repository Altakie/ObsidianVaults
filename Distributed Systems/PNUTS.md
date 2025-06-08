# General Overview
- Geographically distributed data centers
- Data
	- Per user
	- Per item
	- Keeps states for apps
## Requirements
- Lots of concurrent reads/writes
- High fault tolerance

# Consistency Schemes
- No serializability
- Per item consistency/Serializability 
	- Each record has a record master
		- All updates go through record master
		- Record master assigns order to updates
		- Can move dynamically
			- Usually stays in region next to user (for speed)
		  - No serializability between records
- Can see stale data
## Replication
- Geographically replicated servers called region
## Reads
- Local and fast
- Different types of reads
	- Read any version
		- Can read stale data
		- Doesn't read own write
	- Read a certain version number or newer
		- Read local first
		- If local doesn't have version, read from master
		- Can have read own writes
	- Read latest
		- Always has read own writes
## Writes
- Local and fast
- Goes to local storage unit and reads record from there
	- Finds record there
	- Goes to YMB, which replicates the update
	- YMB sends messages to master
- Asynchronous
- Test and set write
	- Allows you to write atomically without any locks
	- Checks if the version number matches at master and writes only if it is
		- Fails otherwise
	- Allows for starvation
		- Only really happens for shared items
# Data Model
- Table
	- Record
		- Key -> Attribute
## Queries
- Primary key only

# Components of a Region
## YMB
- Message broker
## Router
- Have cached copies of where each tablet is
- Cached from tablet controller
## Tablet Controller
- Manages tablets
- Splits tablets that are too large
- Manages boundary between tablets
## Storage Units
- Where the data is stored

# Failures 
- Replication
- Failure of master disables read-latest temporarily (until new master is assigned)