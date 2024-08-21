
# Data Binding

- Spring MVC forms can make use of data binding

- Automatically setting / retrieving data from a Java object / bean


# Showing Form

In your Spring Controller

- Before you show the form, you must add a *model attribute*
- This is a bean that will hold form data for the *data binding*


# Setting up HTML Form - Data Binding

```HTML
<form th:action="@{/processStudentForm}" th:object="${student}" method="POST">
	First name: <input type="text" th:field="*{firstName}" />
	*{ ... } is shortcut syntax for: ${student.firstName}
	<br><br>
	
	Last name: <input type="text" th:field="*{lastName}" />

	<br><br>

	<input type="submit" value="Submit" />


</form>
```

# Handling Form Submission in the Controller

```Java
@PostMapping("/processStudentForm")
public String processForm(@ModelAttribute("student") Student theStudent) {

	// log the input data
	System.out.println("theStudent: " + theStudent.getFirstName()
					+ " " + theStudent.getLastName());
	return "student-confirmation";
}
```


# Confirmation page

```HTML
<html>

<body>

	The student is confirmed: <span th:text="${student.firstName} + '' + ${student.lastName}" />
</body>

</html>
```

# Development Process

1. Create Student class
2. Create Student controller class
3. Create HTML form
4. Create form processing code


# Spring Boot - Spring MVC Form Data Binding - Drop-Down List - Overview

## Development Process

1. Update HTML form
2. Update Student class - add getter / setter for new property
3. Update confirmation page


# Spring Boot - Spring MVC Validation - Required Fields - Overview

1. Create Customer class and add validation rules
```Java
import jakarta.validation.constraints.NotNull;
import jakarta.validation.constraints.Size;

public class Customer {

	private String firstName;

	@NotNull(message = "is required")
	@Size(min=1, message = "is required")
	private String lastName;

	// getter/setter method ..

}
```



2. Add Controller code to show HTML form

```Java
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.ui.Model;

@Controller
public class CustomerController {

	@GetMappping("/")
	/**
		Model allows us to share information between Controllers
		and view pages (Thymeleaf)
	**/
	public String showForm(Model theModel) {

		theModel.addAttribute("customer", new Customer());

		return "customer-form";
	
	}
}
```

3. Develop HTML form and add validation support

```html
<form th:action="@{/processForm}" th:object="${customer}" method="POST">

	First name: <input type="text" th:field="*{firstName}" />
	
	<br><br>

	Last name (*): <input type="text" th:field="*{lastName}" />

	<!-- Show error message (if present) -->

	<span th:if="${#fields.hasErrors('lastName')}"
		  th:errors="*{lastName}"
		  class="error"></span>
	<br><br>

	<input type="submit" value="Submit" />
	
</form>
```

4. Perform validation in the Controller class

```Java

@PostMapping("/processForm")
public String processForm(
	@Valid @ModelAttribute("customer") Customer theCustomer,
	BindingResult theBindingResult) {

	if (theBindingResult.hasErrors()) {
		return "customer-form";
	}
	else {
		return "customer-confirmation";
	}
	
	}
```


5. Create confirmation class

```HTML
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">

<body>
The customer is confirmed: <span th:text="${customer.firstName + ' ' + customer.lastName}" />
</body>
</html>
```