# Main Goals

## Availability 
- despite failures
	- Including network failures
## Correctness 
- Act like single server
	- Servers should always be in sync

# Failures
## Types of Failures
- Temporary or permanent loss of connectivity
- Network partition
	- Not everyone can access a server
- Server crashes and recovers
	- Servers keep everything in memory so lose everything when they restart
	- A crashed server can be replaced
## Dealing with Failures
### Agreement
- "View Server"
	- Assume it is never down
	- Decides which server is primary and backup
	- Keeps track of primary and backup
	- Clients and servers ask view server
	- Repair
		- View server can recruit idle servers
			- Make old backup primary
			- Make new server backup
	- Can only have one primary
		- This primary has to have state
	- Everything should go through view server
		- This means client communications
		- This also means server communications
- There will be situations where is better to wait and the system will be stuck