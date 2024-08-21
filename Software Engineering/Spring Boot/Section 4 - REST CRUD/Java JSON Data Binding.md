- Data binding is the process of converting JSON data to a Java POJO
- Also known as Mapping, Serialization / Deserialization, Marshalling / Unmarshalling

# JSON Data Binding with Jackson

- Spring uses the Jackson Project behind the scenes
- Jackson handles data binding between JSON and Java POJO 
- Details on Jackson Project: https://github.com/FastXML/jackson-databind 
- Spring Boot Starter Web automatically includes dependency for Jackson

# Jackson Data Binding

- By default, Jackson will call appropriate getter / setter method


# JSON to Java POJO

- Convert JSON to Java POJO ... call setter method on POJO

# Java POJO to JSON

- Now, let's go the other direction
- Convert Java POJO to JSON ... call getter methods on POJO

# Spring and Jackson Support

- When building Spring REST application
- Spring will automatically handle Jackson Integration
- JSON data being passed to REST controller is converted to POJO
- Java object being returned from RESt controller is converted to JSON

# Development Process

1. Create Java POJO class for Student
2. Create Spring REST Service using @RestController