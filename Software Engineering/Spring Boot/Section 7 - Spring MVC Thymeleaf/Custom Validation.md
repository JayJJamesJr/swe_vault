
What if we want our own custom validation? 

# Step 1a: Create @CourseCode annotation

```java
@Constraint(validatedBy = CourseCodeConstraintValidator.class)
@Target({ElementType.METHOD, ElementType.FIELD})
@Retention(RetentionPolicy.RUNTIME)
public @interface CourseCode {

// define default course code
public String value() default "LUV";

// define default error message
public String message() default "must start with LUV";


}
```