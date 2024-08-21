
## Database Access

- So far, our user accounts were hard coded in Java source code
- We want to add database access

## Recall Our User Roles

| User  | Password | Roles                    |
| ----- | -------- | ------------------------ |
| john  | test123  | EMPLOYEE                 |
| mary  | test123  | EMPLOYEE, MANAGER        |
| susan | test123  | EMPLOYEE, MANAGER, ADMIN |

## Database Support in Spring Security


## Customize Database Access with Spring Security

- Can also customize the table schemas

- Useful if you have custom tables specific to your project / custom

- You will be responsible for developing the code to access the data
	- JDBC, JPA/Hibernate etc ...

## Database Support in Spring Security

## Development Process

1. Develop SQL Script to set up database tables
2. Add database support to our project using Maven POM

```
```

1. Create JDBC properties file
2. Update Spring Security Configuration to use JDBC

```SQL
INSERT INTO `users`
VALUES
('john','{noop}test123',1),
('mary','{noop}test123',1),
('susan','{noop}test123',1)

'---> {encoding id}<password>'
```

## Spring Boot REST API Security - BCrypt Encryption

### Password Storage - Best Practice

- The best practice is store passwords in an encrypted format


| john  | password        | enabled |
| ----- | --------------- | ------- |
| john  | {bcrpyt}$2a$... | 1       |
| mary  | {bcrpyt}$2a$... | 1       |
| susan | {bcrpyt}$2a$... | 1       |

- Spring Security recommends using the popular bcrypt algorithm

- bcrypt
	- Performs one-way encrypted hashing
	- Adds a random salt to the password for additional protection
	- Included support to defeat brute force attacks

### Bcrypt Additional Information

- Why you should use bcrypt to hash passwords
	- www.luv2code.com/why-bcrypt

- Detailed bcrypt algorithm analysis
	- www.luv2code.com/bcrypt-wiki-page

- Password hashing - Best Practices
	- www.luv2code.com/password-hashing-best-practices

### How to Get a Bcrypt password

- You have a plaintext password and you want to encrypt using bcrypt
- Option 1: Use a website utility to perform the encryption
- Option 2: Write Java code to perform the encryption

### How to Get a Bcrypt password

- Visit: www.luv2code.com/generate-bcrypt-password
- Enter your plaintext password
- The website will generate a bcrypt password for you

### Development process 

1. Run SQL Script that contains encrypted passwords
	1. Modify DDL for password field, length should be 68

### Spring Security Password Storage

- In Spring Security, passwords are stored using a specific format
- {bcrypt}encodedPassword
- Password column must be at least 68 characters wide {bcrypt} - 8 chars
- encodedpassword - 60 chars


## For Security Schema Customization

- Tell Spring how to query you custom tables
- Provide query to find user by user name
- Provide query to find authorities / roles by user name

## Development Process

1. Create our custom tables with SQL
2. Update Spring Security Configuration
	1. Provide query to find user by user name
	2. Provide query to find authorities / roles by name
	
