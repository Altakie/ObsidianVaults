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
		- Use leases to ensure there is only one primary
			- View server should enforce leases
				- Allow for extension of lease by pinging primary and backup
					- If primary hasn't responded in a certain amount of time, assume it is down
				- After lease expires, reassign primary to backup, then recruit new backup
				- Inform clients of new primary and backup
	- Everything should go through view server
		- This means client communications
		- This also means server communications
- There will be situations where is better to wait and the system will be stuck