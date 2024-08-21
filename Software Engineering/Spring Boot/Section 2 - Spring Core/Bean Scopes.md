- Scope refers to the lifecycle of a bean

- How long does the bean live

- How are the beans shared


# Default Scope

# Refresher: What is a Singleton?

- Spring Container creates only one instance of the bean by default

- It is cached in memory

- All dependency injections for the bean
	- will reference the SAME bean

# What is a Singleton?


# Additional Spring Bean Scopes


| Scope       | Description                                                 |
| ----------- | ----------------------------------------------------------- |
| singleton   | Create a single shared instance of the bean. Default scope  |
| prototype   | Create a new bean instance for each container request.      |
| request     | Scoped to an HTTP web request. Only used for web apps.      |
| session     | Scoped to an HTTP web session. Only used for web apps.      |
| application | Scoped to a web app ServletContext. Only used for web apps. |
| websocket   | Scoped to a web socket. Only used for web apps.             |

# Prototype Scope Example


# Bean Lifecycle

1.  Container Started
2.  Bean Instantiated
3. Dependencies Injected
4. Internal Spring Processing
5. Your Custom Init Method
6. Bean Is Ready For Use / Container Is Shutdown
7. Your Custom Destroy Method
8. Stop

# Bean Lifecyle Methods

1. Define your methods for init and destroy
2. Add annotations: @PostConstruct and @PreDestroy