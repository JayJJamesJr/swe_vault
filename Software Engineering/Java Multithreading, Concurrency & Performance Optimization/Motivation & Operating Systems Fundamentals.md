
## Motivation - Why do we need Threads?

1. Responsiveness
	1. Responsiveness is particularly critical in applications with a user interface.
2. Performance
	1. We can create an illusion of multiple tasks executing in parallel using just a single core. 
	2. With multiple cores we can truly run tasks completely in parallel.
	- Impact of Parallelism 
		- Completing a task much faster.
		- Finish more work in the same period of time.
		- For high scale service -
			- Fewer machines
			- Less money spent on hardware
			- More money in your pocket


## What are threads and where do they live?

When a computer is started it loads a special program from the disk into memory called the OS. The OS provides an abstraction in that allows us to interact with the hardware and CPU so that we can focus on developing applications. Each application on our computer is stored as a file on a disk. When the user starts an application, the OS creates an instance of that application in memory called a process/context. Each process is completely isolated from every other process on the system. A process contains metadata, files, a heap, code, and at least one main thread. 

The thread contains:
- A stack
- An instruction pointer

In a multithreaded application each thread comes with its' own stack and instruction pointer. All other resources in the process are shared by all threads.

`Stack` - Region in memory, where local variables are stored, and passed into functions
`Instruction Pointer` - Address of the next instruction to execute


## Multithreading Caveat

- Multithreaded programming is fundamentally different from single threaded programming

## Summary

- Motivation for multithreading
	- Responsiveness achieved by concurrency
	- Performance achieved by parallelism

- What threads are and what they contain
	- Stack
	- Instruction Pointer

- What threads are
	- Files
	- Heap
	- Code


## Context Switch 

The act of starting a thread, stopping it, scheduling it out of the CPU and scheduling another thread in its place is called `Context Switching` 

### Cost
- Context switching is expensive and is the price of multitasking
- Each thread consumes resources in the CPU and memory
- When we switch to a different thread:
	- Store data for one thread
	- Restore data for another thread
#### Caveats
 - Too many threads - Thrashing, spending more time in management than real productive work. 
 - Threads consume less resources than processes
 - Context switching between threads from the same process is cheaper than context switching between different processes

### Thread Scheduling

How are threads scheduled?
The operating system divides the time into moderately sized pieces called epochs
The OS operates a different time slice for each thread. Not all threads get to run in each epoch.

The decision on how to allocate time for each thread is based on Dynamic Priority the OS maintains for each thread. 
Dynamic Priority = Static Priority + Bonus (bonus can be negative)

- Static Priority is set by the developer programmatically
- Bonus is adjusted by the Operating System in every epoch, for each thread
- Using Dynamic Priority, the OS will give preference for interactive threads (such as User Interface threads)
- OS will preference to threads that did not complete in last epoch, or did not get enough time run preventing starvation

### Threads vs Processes

#### When to prefer Multithreaded Architecture
- Prefer if the tasks share a lot of data
- Threads are much faster to create and destroy.
- Switching between threads of the same process is faster. (Shorter context switches)
#### When to prefer Multi-Process Architecture
- Security and stability are of higher importance.
- Tasks are unrelated to each other.

