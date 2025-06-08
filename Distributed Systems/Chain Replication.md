

# Main Idea
- Chain of servers forwarding an update from the head to the tail
	- Head is first to receive an update, acts as primary
	- Update is forwarded and applied down the chain of servers
	- Tail acknowledges that the update has fully propagated to all servers to client after it applies it
	- 

# Updates
- Costly because every server has to process update in a line
	- Can preprocess request at each server and can forward processed request so that each server doesn't have to compute it
# Queries
- All queries go directly to the tail


# Chain vs Paxos
- Paxos is better