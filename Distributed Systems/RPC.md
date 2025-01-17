> Remote procedure call

## What does RPC do for you?
- Marshalling
	- Formatting data into packets
- Binding (to sockets)
	- How does server know who to talk to?
- Threads
- Handlers
- Failures
	- Reply doesn't come back
	- Dealing with failures
		- Resend at least once - still no response -> error
			- Good for idempotent requests
		- At most once (Used by go)
			- Do not process duplicate requests
## How it works
- App uses stub to make call to lock 
- Stub sends to RPC on server
- Server RPC forwards to appropriate handler
- Handler handles appropriately
- Server RPC sends message back to client RPC
## Client Stub
- Put's arguments into packet
- Sends to server
- Waits for reply
- Extract from reply value 
- Returns 
## Server
- Wait for next client request
- Extract arguments
- Call appropriate handle
- Put return value into packet
- Send reply to packet

