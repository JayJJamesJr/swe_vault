What do we do when we have multiple implementations of an injected object?

We use the @Qualifier annotation to tell Spring Boot which implementation to use via constructor or setter injection. We do this by using @Qualifier(<bean_id>). The bean id is the class name of the specific implementation you'd like to use except the first character will be lowercase instead of uppercase.

```java
package com.luv2code.springcoredemo.rest;  
  
import com.luv2code.springcoredemo.common.Coach;  
import org.springframework.beans.factory.annotation.Autowired;  
import org.springframework.web.bind.annotation.GetMapping;  
import org.springframework.web.bind.annotation.RestController;  
  
@RestController  
public class DemoController {  
  
    // Define a private field for the dependency  
  
    private Coach myCoach;  
  
  
     /*  
            @Autowired annotation tells Spring to inject a dependency  
			If you only have one constructor then @Autowired on constructor is
			optional.  
     */    
     
    @Autowired 
    public void setCoach(@Qualifier("cricketCoach") Coach theCoach) {  
        myCoach = theCoach;  
    }  
  
    @GetMapping("/dailyworkout")  
    public String getDailyWorkout() {  
        return myCoach.getDailyWorkout();  
    }  
}
```