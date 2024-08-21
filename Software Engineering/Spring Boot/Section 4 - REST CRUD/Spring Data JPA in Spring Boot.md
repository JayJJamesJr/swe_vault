## Development Process

1. Extend JpaRepository interface
```java
												// Entity Type, Primary Key
public interace EmployeeRepository extends JpaRepository<Employee, Integer> {

}
```
1. Use your Repository in your app