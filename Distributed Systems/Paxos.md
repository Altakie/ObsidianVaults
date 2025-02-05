# Benefits

- No single point of failure
- Graceful handling of slow replicas
- General purpose ordering scheme

# How it works
- Log
- Majority must live and communicate for progress
	- Any majority will have at least one overlap with another majority
		- Any later majority can then find out what earlier majority decided
- Can tolerate minority of servers being slow
- Required to agree on one value