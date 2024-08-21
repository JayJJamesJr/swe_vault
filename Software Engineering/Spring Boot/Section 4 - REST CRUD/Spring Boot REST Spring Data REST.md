
- Spring Data REST is the solution
- Leverages your existing JpaRepository
- Spring will give you a REST CRUD implementation for free


# Spring Data REST - How Does it Work?

- Spring Data REST will scan your project for JpaRepository
- Expose REST APIs for each entity type for your JpaRepository

# REST Endpoints

- By default, Spring Data REST will create endpoints based on entity type
- Simple pluralized form
	- First character of Entity type is lowercase
	- Then just adds an "s" to the entity

# Development Process

1. Add Spring Data REST to you Maven POM file


# In A Nutshell

For Spring Data REST, you only need 3 items

1. Your entity: Employee
2. JpaRepository: EmployeeRepository extends JpaRepository
3. Macen POM dependency for: spring-boot-starter-data-rest


# HATEOS

- Spring Data REST endpoints are HATEOAS compliant
	- HATEOAS: Hypermedia as the Engine of Application State

	 - Hypermedia-driven sites provide information to access REST interfaces


# Spring Data REST Operations

## PUT

With PUT Spring Data REST only uses the ID within the URL. Any ID passed into the JSON body is ignored.


# REST Endpoints

- By default, Spring Data REST will create endpoints based on entity type
- Simple pluralized form
	- First character of Entity type is lowercase
	- Then just adds an "s" to the entity

## Problem

 - Spring Data REST does not handle complex pluralized forms
	 - In this case, you need to specify plural names with an annotation

```java
@RepositoryRestResource(path="members") // <---------
public interface EmployeeRepository extends JpaRepository<Employee, Integer> {

}

```


# Pagination

- By default, Spring Data REST will return the first 20 elements
	- Page size = 20
	
- You can navigate to the different pages


# Spring Data REST Configuration

- Following properties available: application.properties


| Name                               | Description                                   |
| ---------------------------------- | --------------------------------------------- |
| spring.data.rest.base-path         | Base path used to expose repository resources |
| spring.data.rest.defualt-page-size | Default size of pages                         |
| spring.data.rest.max-page-size     | Maximum size of pages                         |
|                                    |                                               |
|                                    |                                               |


# Sorting

- You can sort by the property names of you entity
	- In our Employee example, we have: firstName, lastName, and email

- Sort by last name (ascending is default) 
- `http://localhost:8080/employees?sort=lastName`
- Sort by first name, descending 
- `http://localhost:8080/employees?sort=firstName, desc
- Sort by last name, then first name, ascending 
- `http://localhost:8080/employees?sort=firstName, asc`