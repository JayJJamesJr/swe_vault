
- The Model is a container for your application data

- In your Controller
	- You can put anything in the **model**
	- Strings, objects, info from database, etc ...

- Your View page can access data from the **model**


## Code Example

- We want to create a new method to process form data

- Read the form data: student's name

- Convert the name to upper case

- Add the uppercase version to the model


```HTML

<html><body>

The message: <span th:text="${message}" />

</body></html>
```


## Reading HTML Form Data with @RequestParam Annotation

### Instead of using HttpServletRequest Bind variable using @RequestParam Annotation

```Java
@RequestMapping("/processFormVersionTwo")
public String letsShoutDude(
	@RequestParam("studentName") String theName,
	Model model) {

	// now we can use the variable: theName
	
	}

```

- Behind the scenes:

	- Spring will read param from request: studentName
	- Bind it to the variable: theName


## GetMapping and PostMapping


| Method | Description                       |
| ------ | --------------------------------- |
| GET    | Requests data from given resource |
| POST   | Submits data to given resource    |

## Sending Data with GET method

```HTML
<form th:action="@{/processForm}" method="GET" ...>
...
</form>
```

- Form data is added to end of URL as name / value pairs
	- theUrl?field1=value1&field2=value...

## Constrain the Request Mapping - GET

```Java
@RequestMapping(path="/processForm", method=RequestMethod.GET)
public String processForm(...) {
	...
}
```

- This mapping ONLY handles GET method
- Any other HTTP REQUEST method will get rejected

## Annotation Short-Cut

```Java
@GetMapping("/processForm")
public String processForm(...) {
	...
}
```

- @GetMapping: this mapping ONLY handles GET method
- Any other HTTP REQUEST method will get rejected

## Sending Data with POST method

```Java
<form th:action="@{/processForm}" method="POST" ...>
...
</form>
```

- Form data is passed in the body of HTTP request message

## Constrain the Request Mapping - POST

```Java
@RequestMapping(path="/processForm", method=RequestMethod.POST)
public String processForm(...) {

}
```

- @PostMapping: This mapping ONLY handles POST method
- Any other HTTP REQUEST method will get rejected


## GET vs POST

## GET

- Good for debugging
- Bookmark or email URL
- Limitations on data length

## POST

- Can't bookmark or email URL
- No limitations on data length
- Can also send binary data