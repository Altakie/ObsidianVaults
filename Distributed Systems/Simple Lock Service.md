## Goal

- Even if only one server is up, the service should work (Fail-Stop model)
	- This assumes that one server can crash
	- However, can assume there are no network failures
	- There is no failure recovery, no restart
- If client asks for lock, and the lock is free, the client gets the lock.
- Only one client can have a lock at a time --> no two clients can have ownership of the same lock
- Should behave like a single lock server
- States should be synchronized
- Client server model
	- Client
		- Tries to send message to primary
		- If no response (response timeout), send message to backup
		- Return response to app
	- Server
		- If lock is already locked, return false
		- Else, forward to backup and return true

## How to handle
-  If there is no response from a server, that means that server is down
- If one of the servers crashes, need to identify when it crashed
	- If primary crashes before sending the message to the backup
	- If primary crashes after sending a message to the backup but before sending the message to the client
- Does primary need to wait for backup?
	- Yes - because if it doesn't wait two clients can get the same lock, one from the primary and one from the backup
- Request order
	- If requests arrive to backup in different order than in primary, it could mess up how the backup handles the locks and desync their states
	- <span style="color:rgb(0, 176, 80)">Need primary and backup to process requests in the same order</span>
		-  Add sequence numbers to fix
- Could client send request to primary and backup at the same time?
	- No - Requires additional mechanisms
	- In this scheme, primary should order the requests
- What if primary fails after it sends?
	- Servers may give the lock to the client but the client wouldn't know they got it
- [[RPC]]
- Can also give unique numbers to requests 