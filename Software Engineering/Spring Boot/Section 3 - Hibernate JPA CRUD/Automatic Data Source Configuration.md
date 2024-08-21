- In Spring Boot, Hibernate is the default implementation of JPA

- **EntityManager** is main component for creating queries etc ...
- **EntityManager** is from Jarkata Persistence API (JPA)

- Based on configs, Spring boot will automatically create the beans:
	- DataSource, EntityManager, ... 

- You can then inject these into your app, for example your DAO


# Setting up Project with Spring Initialzr

- At Spring Initializr website, start.spring.io
- Add dependencies
	- MySQl Driver: mysql-connector-j
	- Spring Data JPA: spring-boot-starter-data-jpa

# application.properties

```
spring.datasource.url=jdbc:mysql://localhost::3306/student_tracker
spring.datasource.username=springstudent
spring.datasource.password=springstudent
```


# Creating Spring Boot - Command Line App

- We will create a Spring Boot - Command Line App
- This will allow us to focus on Hibernate / JPA

# Terminology

Entity Class

Java class that is mapped to a database table

# Entity Class

- At a minimum, the Entity class
	- Must be annotated with @Entity
	- Must have a public or protected no-argument constructor
		- The class can have other constructors

# Java Annotations

- Step 1: Map class to database table ```
```java

	

	
```

- Step 2: Map fields to database columns


# @Column - Optional

- Actually, the use of @Column is optional
- If not specified, the column name is the same name as Java field
- In general it's not recommended
	- If you refactor the Java code, then it will not match existing database columns
	- This is a breaking change and you will need to update the database column