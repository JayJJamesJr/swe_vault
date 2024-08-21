- A set of web pages to layout UI components
- A collection of Spring beans (controllers, services, etc...)
- Spring configuration (XML, Annotations or Java)

# Spring MVC Front Controller

- Front controller known as DispatcherServlet
	- Part of the Spring Framework
	- Already developed by Spring Dev Team

- You will create
	- Model object (orange)
	- View templates (dark green)
	- Controller classes (yellow)


## Model

- Model: contains your data

- Store / retrieve data via backend systems
	- database, web service, etc..
	- Use a Spring bean if you like

- Place your data in the model
	- Data can be any Java object / collection

## View

- Spring MVC is flexible
	- Supports many view templates
- Recommended: Thymeleaf

- Developer creates a page
	- Displays data
## Controller

- Code created by developer

- Contains your business logic
	- Handle the request
	- Store / retrieve data (db, web service...)
	- Place data in model

- Send to appropriate view template