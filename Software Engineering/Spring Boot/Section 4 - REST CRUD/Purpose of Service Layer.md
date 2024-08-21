- Service Facade design pattern
- Intermediate layer for custom business logic
- Integrate from multiple sources (DAO / repositories)


@RestController
@Repository
@Service

# Specialized Annotation for Services

- ## @Service applied to Service implementations
- ## Spring will automatically register the Service implementation
	- ## Thanks to component-scanning

## Employee Service

1. Define Service interface
2. Define Service implementation
	1. Inject the EmployeeDAO

# Service Layer - Best Practice

- Best practice is to apply transactional boundaries at the service layer
- It is the service layer's responsibility to manage transaction boundariees
- For implementation code
	- Apply @Transactional on service methods
	- Remove @Transactional on DAO methods if they already exist

## Development Process

1. Set up Database Dev Environment
2. Create Spring Boot project using Spring Initializr
3. Get list of employees
4. Get single employee by ID
5. Add a new employee
6. Update an existing employee
7. Delete an existing employee