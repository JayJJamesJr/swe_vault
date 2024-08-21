- **J**arkata **P**ersistence **A**PI (JPA) ... *previously known as Java Persistence API*
	- Standard API for Object-to-Relational-Mapping (ORM)

- Only a specification
	- Defines a set of interfaces
	- Requires an implementation to be usable

## What are Benefits of JPA

- By having a standard API, you are not locket to vendor's implementation

- Maintain portable, flexible code by coding to JPA spec (interfaces)

- Can theoretically switch vendor implementations
	- For example, if Vendor ABC stops supporting their product
	- You could switch to Vendor XYZ without vendor lock in

# Saving a Java Object with JPA

```java
// create Java object
Student theStudent = new Student("Paul", "Doe", "paul@luv2code.com");

// save it to database
entityManager.persist(theStudent);
// Special JPA helper object - The data will be stored in the database SQL insert
```

# Retrieving a Java Object with JPA

```java
// create Java object
Student theStudent = new Student("Paul", "Doe", "paul@luv2code.com");

// save it to database
entityManager.persist(theStudent);
// Special JPA helper object - The data will be stored in the database SQL insert

// now retrieve from database using the primary key
int theId = 1;
Student myStudent = entityManager.find(Student.class, theId);
```


# Querying for Java Objects

```java
TypesQuery<Student> theQuery = entityManager.createQuery("from Student", Student.class);

List<Student> students = theQuery.getResultList();
```

# JPA/Hibernate CRUD Apps

- **C**reate objects
- **R**ead objects
- **U**pdate objects
- **D**elete objects

# How does hibernate relate to JDBC

- Hibernate / JPA uses JDBC for all database communications



# EntityManager Vs JPA Repository

- If you need low-level-control and flexibility, use EntityManager
- If you want high-level of abstraction, use JpaRepository

# Entity Manager

- Need low-level control over the database operations and want to write custom queries

- Provides low-level access to JPA and work directly with JPA entities

- Complex queries that required advanced features such as native SQL queries or stored procedure calls

- When you have custom requirements that are not easily handled by higher-level abstractions

# Jpa-Repository

- Provides commonly used CRUD operations out of the box, reducing the amount of code you need to write

- Additional features such as pagination, sorting

- Generate queries based on method names

- Can also create custom queries using @Query

# Recommendation

- Choice depends on the application requirements and developer preference
- You can also use both in the same project

- For learning purposes, start with EntityManager then learn Jpa-Repository
- This will help you understand the low-level coding behind the scenes
- Knowing BOTH EntityManager and Jpa-Repository will help you on future projects

# Saving a Java Object with JPA

## Student DAO

- Step 1: Define DAO interface

```java
import com.luv2code.cruddemo.entity.Student

public interface StudentDAO {

	void save(Student theStudent);
}
```

- Step 2: Define DAO implementation

- Inject the entity manager

	```java
	package com.luv2code.cruddemo.dao;  
	  
	import com.luv2code.cruddemo.entity.Student;  
	import jakarta.persistence.Entity;  
	import jakarta.persistence.EntityManager;  
	import jakarta.transaction.Transactional;  
	import org.springframework.beans.factory.annotation.Autowired;  
	import org.springframework.stereotype.Repository;  
	  
	@Repository  
	public class StudentDAOImpl implements StudentDAO {  
	  
	    // define field for entity manager  
	    private EntityManager entityManager;  
	  
	    // inject entity manager using constructor injection  
	  
	    @Autowired  
	    public StudentDAOImpl(EntityManager entityManager) {  
	        this.entityManager = entityManager;  
	    }  
	  
	  
	    // implement save method  
	    @Override  
	    @Transactional    public void save(Student theStudent) {  
	        entityManager.persist(theStudent);  
	    }  
	}
	```

# Spring @Transactional

- Spring provides an @Transactional annotation
- Automagically begin and end a transaction for your JPA code
	- No need for you to explicitly do this in your code

- This Spring magic happens behind the scenes


# Specialized Annotations for 

- Applied to DAO implementations

- Spring will automatically register the DAO implementation
	- Thanks to component scanning

- Spring also provides translation of any JDBC related exception

 - Spring provides the @Repository annotation


- Step 3: Update main app
	- Data Access Object


# JPA CRUD Apps

- Create objects
- Read objects
- Update objects
- Delete objects


# Retrieving a Java Object with JPA

```java
// retrieve/read from database using the primary key
// in this example, retrieve Student with primary key: 1

Student myStudent = entityManager.find(Student.class, 1);
```


# Development Process

1. Add new method to DAO interface
2. Add new method to DAO implementation
3. Update main app