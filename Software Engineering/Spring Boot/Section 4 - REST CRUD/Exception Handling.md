## Step 1: Create custom error response class

- The custom error response class will be sent back to client as JSON
- We will define as Java class (POJO)
- Jackson will handle converting it to JSON

## Step 2: Create custom student exception

- The custom student exception will be used by our REST service
- In our code, if we can't find student, then we'll throw an exception

## Step 3: Update REST service to throw exception


## Step 4: Add exception handler method

- Define exception handler methods(s) with @ExceptionHandler annotation
- Exception handler will return a ResponseEntity
- ResponseEntity is a wrapper for the HTTP response object

