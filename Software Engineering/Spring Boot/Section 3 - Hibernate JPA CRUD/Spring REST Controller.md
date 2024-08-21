## Spring REST Hello World

REST Client --- /test/hello ---> REST Service

REST Client< --- Hello World! --- REST Service

```java
@RestController
@RequestMapping("/test")
public class DemoRestController {

	@GetMapping("/hello")
	public String sayHello() {
		return "Hello World";
	}
}
```

## Testing with REST Client - Postman

## Testing with REST Client - Postman

## Web Browser vs Postman

- For simple REST testing for GET requests
	- Web Browser and Postman are similar

- However, for advanced REST testing: POST, PUT etc ...
	- Postman has much better support
	- POSTing JSON data, setting content type
	- Passing HTTP request headers, authentication etc ...

## Spring REST Controller Development Process

1. Add Maven dependency for Spring Boot Starter Web
	At Spring Initializr website can also select the "Web" dependency

```XML
<!-- Add Spring Boot Starter Web -->
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-web</artifactId>
</dependency>
```

2. Create Spring REST Service using @RestController
	
```java
@RestController
@RequestMapping("/test")
public class DemoRestController {

	@GetMapping("/hello")
	public String sayHello() {
		return "Hello World";
	}
}
```


