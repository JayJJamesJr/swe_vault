- By default, Spring Boot starts component scanning
	- From same package as your main Spring Boot application
	- Also scans sub-packages recursively


- This implicitly defines a base search package
	- Allows you to leverage default component scanning
	- No need to explicitly reference the base package name

- Default scanning is fine if everything is under
	- com.luv2code.springcoredemo

- But what about my other packages?
	- com.luv2code.util
	- org.acme.cart
	- edu.cmu.srs

By default Spring boot uses the applications directory as the the base directory for any component scanning. If we want to extend the base packages used for component scanning
we can do so using the *scanBasePackages={... packages}*


```java
package com.luv2code.springcoredemo;

@SpringBootApplication(
	scanBasePackages={"com.luv2code.springcoredemo",
					  "com.luv2code.util",
					  "org.acme.cart"
					  "edu.cmu.srs"})
public class SpringcoredemoApplication {
 ...
}
```
