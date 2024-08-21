## Project Object Model file: POM file

- Configuration file for your project
	- Basically your "shopping list" for Maven :-)

- Located in the root of your Maven project

## Pom File Structure

### Project meta data

Project name, version etc
Output file type: JAR, War ..

### Dependencies

List of projects we depend on
Spring, Hibernate, etc...

### Plug ins

Additional custom tasks to run:
generate JUnit rest reports etc ...


## Project Coordinates - Elements

Unique identifiers for our Spring project

```
<groupId>com.luv2code</groupId>
<artifactId>mycoolapp</artifactId>
<version>1.0.FINAL</version>
```

| Name |                                           Description |
| ---- | ---- |
| Group Id | Name of company, group, or organization<br>The convention is to use the reverse domain name: **com.luv2code** |
| Artifact ID | Name for this project: **mycoolapp** |
| Version | A specific release version like: **1.0**, **1.6**, **2.0**   ...<br> If a project is under active development then: **1.0-SNAPSHOT** |
The combination of the **Group ID**, **Artifact ID** and **Version** is called the **GAV**




## Spring Boot [[Actuator]]





