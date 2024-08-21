
- Critical Sections
- Synchronized Monitor/Lock


## Synchronization

- Locking mechanism
- Used to restrict access to a critical section or entire method to a single thread a time.

### Examples

#### 1. Synchronized - Monitor

```java
public class ClassWithCriticalSection {

	public synchronized void method1() {
		... Thread A
	}

	public synchronized void method2() {
		... 
	}
}
```

At the class level synchronization is applied to all synchronized methods even if those methods aren't invoked by other threads. Think of this method as a set of doors where if one door closes all other doors close as well. The moment a thread calls a synchronized method created inside a class definition all other synchronized methods become unavailable to all other threads

Note: Synchronization happens at the object level and not the class level. Take this code block for example: 

```java
public class Main {
	public static void main(String [] args) {
		SharedClass sharedObject1 = new SharedClass();
		SharedClass sharedObject2 = new SharedClass();

		Thread thread1 = new Thread(() -> {
		while (true) {
			sharedObject1.increment();
		}
		});

		Thread thread2 = new Thread(() -> {
		 while (true) {
			sharedObject2.increment();
		 }
		 });
		thread1.start();
		thread2.start();
 }

 static class SharedClass {
	 private int counter = 0;

	 public synchronized void increment() {
		 this.counter++;
	 }
 }
}
```

 `thread1` and `thread2` both have their own instances of `SharedClass` meaning the increment operation that `thread1` performs on `sharedObject1` will not affect the `counter` variable of `sharedObject2` that `thread2` is working on.  We only need to block threads from accessing objects if they're sharing the same object. 