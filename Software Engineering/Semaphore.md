A synchronization primitive used to control access to shared resource by multiple threads. They're another way of managing the number of threads that can concurrently access a critical section or shared resource. 


## How do semaphores manage threads?

A semaphore maintains a count often referred to as "permits" or "tokens" which determine the maximum number of threads allowed to enter the critical section simultaneously. 

## Types of Semaphores

- Binary Semaphore
	- A binary semaphore restricts the access to the critical section to one thread at time time. It is used to implement mutual exclusion or a (mutex)
- Counting Semaphore
	- A counting semaphore is used to enable access to any number of threads concurrently


