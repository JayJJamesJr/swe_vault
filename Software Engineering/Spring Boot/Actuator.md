
The spring boot actuator is a feature that exposes additional information about your service. By default only `/health` is exposed.

The `/info` endpoint can provide information about your application

To expose `/info` 

In the `src/main/resources/application.properties` file add the following:

```
management.endpoints.web.exposure.include=heath,info
management.info.env.enablement=true
```


The `/info` endpoint is empty by default which means we need to customize it with our app info in `application.properties`.

```
info.app.name=My Super Cool App
info.app.description=A crazy and fun app, yoohoo!
info.app.versoin=1.0.0
```

See the official spring boot docs for more documentation on actuator.

## Exposing Endpoints

By default, only `/health` is exposed

To expose all actuator endpoints over HTTP

```
# Use wildcard "*" to expose all endpoints
# Can also expose individual endpoints with a comma-delimited list
```


## What about Security? 

You may not want to expose certain information about your service.
Add Spring Security to project and endpoints are secured 

When we add security to an endpoint, Spring Security will prompt for a login

```
spring.security.user.name=scott
spring.security.user.password=tiger
```



## Excluding Endpoints

To exclude `/health` and  `/info`

```
# Exclude individual endpoints with a comma-delimited list
#
management.endpoints.web.exposure.exclude=health,info
```