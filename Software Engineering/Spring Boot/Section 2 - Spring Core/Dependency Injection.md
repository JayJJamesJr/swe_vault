The dependency inversion principle. The client delegates the responsibility of providing it's dependencies to another object.

# Car Factory



# Types of Injection

- Constructor Injection
	- Use this when you have required dependencies.
	- Generally recommended by the spring.io development team as first choice.
- Setter Injection
	- Use this when you have optional dependencies.
	- If dependency is not provided, your app can provide reasonable default logic.


# What is Spring AutoWiring

- For dependency injection, Spring can use auto-wiring

- Spring will look for a class that matches
	- *matches by type*: class or interface

- Spring will inject it automatically .. given that the dependency is auto-wired

# Auto-Wiring Example

- Injecting a Coach implementation
- Spring will scan for @Components

- Any one implements the Coach interface
- If so, let's inject them. For example : *CricketCoach*


# Development Process - Constructor Injection

1.  Define the dependency interface and class
2. Create the Demo REST Controller
3. Create a constructor in your class for injections
4. Add @GetMapping for / dailyworkout


# Step 1: Define the dependency interface and class

```java
package com.luv2code.springcoredemo;

public interface Coach {

	String getDailyWorkout();
}

```

```java
package com.luv2code.springcoredemo;

import org.springframework.stereotype.Component;

@Component
public class CricketCoach implements Coach {

	@Override
	public String getDailyWorkout() {
		return "Practice fast bowling for 15 minutes";
	}
}
```


# Step 2: Create Demo REST Controller

```java
package com.luv2code.springcoredemo;

import org.springframework.web.bind.annotation.RestController;

@RestController
public class DemoController {

}

```


# Step 3: Create a constructor in your class for injections

```java
package com.luv2code.springcoredemo;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class DemoController {

	private Coach myCoach;

	@Autowired // The autowired annotation tells Spring to inject a dependency
	public DemoController(Coach theCoach) {
		myCoach = theCoach;
	}

}

```

# Step 4: Add @GetMapping for /dailyworkout


```java
package com.luv2code.springcoredemo;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class DemoController {

	private Coach myCoach;

	@Autowired // The autowired annotation tells Spring to inject a dependency
	public DemoController(Coach theCoach) {
		myCoach = theCoach;
	}

	@GetMapping("/dailyworkout")
	public String getDailyWorkout() {
		return myCoach.getDailyWorkout();
	}

}
```

# IDE Warning - No Usages

![[IDE Warning - No usages.png]]

Spring Framework is dynamic and our IDE may not be able to determine if a given class/method is used at runtime.


# Spring for Enterprise applications

- Spring is targeted for enterprise, real-time / real-world applications
- Spring provides features such as
	- Database access and Transactions
	- REST APIs and Web MVC
	- Security
	- etc ...