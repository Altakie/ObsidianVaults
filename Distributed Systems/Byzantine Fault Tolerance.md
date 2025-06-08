- Byzantine Failure Model
	- Failed server can do whatever
	- Outnumber bad guys every time you want to make a decision
		- Voting
	- Worst case
		- All bag servers are controlled by single attacker

- Design
	- $3f + 1$ replicas total
		- Need $2f + 1$ replicas to vote on a change
		- Up to $f$ replicas can be bad
		- That means $f + 1$ replicas are good
		- Next change will also include $2f + 1$ replicas, $f$ of which are bad
		- At least one of the good replicas will have also seen the last update
		- At least one good replica common between each majority
	- Primary
		- Picks order for concurrent client requests
		- Detecting a fault primary
			- Primary sends pre-prepare to all replicas
			- Replicas then send a matching prepare to all other replicas
			- If $2f +1$ matching prepares at any replica
				- Send commit to all
					- If get matching commit from $2f + 1$ replicas
						- Execute operation
				- If not just wait
					- If timeout, ask to reelect primary
			- If bad primary is detected, can elect a new one (also requires a majority)
		- Primary re-election
			- Happens after some timeout
				- Primary rotates among servers, there can be $f$ faulty primaries in a row
			- View Change
				- Each replica sends the new primary a prepare for recent ops
				- New primary waits for $2f + 1$ matching prepares
					- New primary waits for $2f + 1$ view change requests
					- New primary fixes log
					- New primary sends New_View Message
						- Contains $2f + 1$ signed prepares
						- List of all operations that contained $2f +1$ prepares
- View Change
	- Needs $2f+1$ replicas to send a prepare to start commit phase
	- Then needs $2f + 1$ commits
	- Only executes after commit phase
	- View change execution:
		1. New primary sends out $2f+1$ prepares for all recent operations
		2. New primary waits for $2f+1$ View Change requests
		3. Fixes the log based on the prepare requests
		4. Now has evidence for View Change
		5. Starts commit phase
		6. Waits for $2f+1$ commits
	- Allows for up to $f$ replicas to be bad, but need $f+1$ replicas to be good
	- Since majority of replicas must be good, there is at least one good replica in common between each majority
	- Communication is bottleneck in this system
- Main takeaways
	- View Change
		- Why is second phase needed?
	- Normal Case
		- What is the protocol?
	- Do not need to know optimizations