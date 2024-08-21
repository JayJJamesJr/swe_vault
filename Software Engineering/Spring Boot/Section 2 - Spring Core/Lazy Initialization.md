
- By default, when your application starts, all beans are initialized
	- @Component, etc ...


- Spring will create an instance of each and make them available


- Instead of creating all beans up front, we can specify lazy initialization

- A bean will only be initialized in the following cases:
	- It is needed for dependency injection
	- Or it is explicitly requested

- Add the @Lazy annotation to a class to make these rules come into play


Is there a way to do this globally? Yes there is.

```java
// File: application.properties
spring.main.lazy-initialization=true
```

- Advantages
	- Only create objects as needed
	- May help with faster startup time if you have a large number of components

- Disadvantages
	- If you have web related components like @RestController, not created until requested
	- May not discover configuration issues until too late
	- Need to make sure you a have enough memory for all beans once created
# Diagnostics: Add println to constructors

