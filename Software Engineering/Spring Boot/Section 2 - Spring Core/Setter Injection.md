
# Autowiring Example

 - Injecting a Coach implementation

- Spring will scan for @Components

- Any one implements the Coach interface

- If so, let's inject them. For example: *CricketCoach*


# Development Process - Setter Injection

1. Create setter methods(s) in your class for injections

	```java
@RestController
public class DemoController {

	private Coach myCoach;

	public void setCoach(Coach theCoach) {
		myCoach = theCoach;
	}

}
```


2. Configure the dependency injection with @Autowired annotation

```java
@RestController
public class DemoController {

	private Coach myCoach;

	@Autowired
	public void setCoach(Coach theCoach) {
		myCoach = theCoach;
	}

}
```

The Spring Framework will perform operation behind the scenes for you
# How Spring Processes your application

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

Spring Framework
```java
Coach coach = new CricketCoach();

DemoController demoController = new DemoController();

demoController.setCoach(theCoach);
```


# Injection Types - Which one to use

- Constructor Injection
	- Use this when you have required dependencies
	- Generally recommended by the spring.io development team as first choice

- Setter Injection
	- Use this when you have optional dependencies
	- If dependency is not provided, your app can provide reasonable default


# Spring Injection Types

- Recommended by the spring.io development team
	- Constructor Injection: required dependencies
	- Setter Injection: optional dependencies

- Not recommended by the spring.io development team
	- Field Injection

# Field Injection .. no longer cool

- In the early days, field injection was popular on Spring projects
	- In recent years, it has fallen out of favor

- In general, it makes the code harder to unit test
- As a result, the spring.io team does not recommend field injection
	- However, you will still see it being used on legacy projects

Step 1: Configure the dependency injection with Autowired Annotation

```java
package com.luv2code.springcoredemo;  

import org.springframework.beans.factory.annotation.Autowired;  
 
@RestController  
public class DemoController {  
  
	@Autowired
    private Coach myCoach;  // Not recommended because it makes code harder to unit test
  
    @GetMapping("/dailyworkout")  
    public String getDailyWorkout() {  
        return myCoach.getDailyWorkout();  
    }  
}
```