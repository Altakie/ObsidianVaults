
# Differences from Spanner
- Want to use standard hardware
	- Don't want to use special hardware
	- Don't want time synchronization

# Main Components
## Epoch Server
- Paxos replicated
- Contains an epoch that it increments periodically
- Their solution to not using time synchronization
- After prepare, ask epoch server for epoch
	- Tells transaction to commit in this epoch
### Ordering Transactions within an Epoch
- Counter within epoch
- Transactions get back epoch number and counter after commit