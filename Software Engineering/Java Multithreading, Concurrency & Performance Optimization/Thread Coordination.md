
## Thread Termination - Why and When?

- Threads consume resources
	- Memory and kernel resources
	- CPU cycles and cache memory
- If a thread finished its work, but the application is still running, we want to clean up the threads resources
- If a thread is misbehaving, we want to stop it.
- By default, the application will not stop as long as at least one thread is still running.

## Thread Coordination - Why do we need it?

- Different threads run independently
- Order of execution is out of our control

