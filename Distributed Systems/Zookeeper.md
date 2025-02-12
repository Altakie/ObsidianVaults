# Main Concepts
- Does not replicate the calculations, only replicates state
- When leader dies, new leader is elected through Paxos

# Z-nodes

- Have version numbers
- Hierarchal structure like a file system
## Types
- Regular
	- Created and destroyed by clients
- Ephemeral
	- Created by clients. Can be deleted by client or deleted by Zookeeper if the client's session ends
- Sequential
	- At the end of their names, always have number that is always increasing
	- New node will have highest number
	- Nodes have unique number
## Operations
- Open session with client
- Create Node
	- Fails if the node already exists
		- Cannot create 2 of the same node
- Exists
	- Checks if a node exists
	- Can put a watch on this node to see if it is updated
		- Gives notification if someone deletes or creates it
- Get Data
	- Returns data and version
	- Can also place watch
- Set data
	- Updates the data if the version matches the value you supplied
		- If different version than current Z-node, change is invalid
		- Similar to compare and swap
- Get children
	- Returns Z-node children
- Sync
	- Waits for all updates (when sync is called) to complete and propagate

# Fencing 
- 
# Performance
## Writes
- All forwarded to the leader
- Leader serializes writes
	- Leader chooses order of writes
- Once changes have been applied, leader atomically broadcasts new state to all followers
	- Like a mini-paxos

## Reads
- Reads call *sync* and then read
	- Makes sure reads are up to date
- Reads are asynchronous 
	- Good for performance because you do not need to wait for RTT