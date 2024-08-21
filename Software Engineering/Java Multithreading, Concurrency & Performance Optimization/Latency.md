The time to completion of a task. Measured in time units.

## How can we reduce latency when working with threads?

We can take a task, break that task down in to several subtasks and run them in parallel in separate threads.

- Theoretical reduction of latency by N = Performance improvement by a factor of N.
- N = Number of cores
	- How many subtasks / threads to break the original task?

- Does breaking down the original task and aggregating results come for free?
	- No. We're going to have to accept the cost of parallelizing threads for the following reasons:
		- We have to break the task into multiple tasks
		- We have to create threads and pass tasks to those threads.
		- We have to wait for the thread to be started and scheduled.
		- We have to wait until the last thread finishes and signals.
		- We have to wait for the aggregating thread to run
		- We have to aggregate the subresults into a single artifact.
- Can we break any task into subtasks? 
- This method is only optimal if all threads are runnable and can run without interruption (no IO / blocking calls/ sleep etc)
- The assumption is nothing else is running that consumes a lot of CPU
- Hyperthreading - Virtual cores vs physical cores
