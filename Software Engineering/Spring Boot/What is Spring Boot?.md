



## What problems does [[Spring]] Boot solve?

- Make it easier to get started with Spring development
- Minimize the amount of manual configuration
	- Perform auto-configuration based on props files and JAR classpath
- Help to resolve dependency conflicts (Maven or Gradle)
- Provide an embedded HTTP server so you can get started quickly
	- Tomcat, Jetty, Undertow, ...


## Relationship Between [[Spring]] and SpringBoot

- Spring Boot uses Spring behind the scenes
- Spring Boot simply makes it easier to use Spring.

## [[Spring]] Initializr

- Quickly create a started Spring Boot project
- http://start.spring.io


## [[Spring]] Boot Embedded Server

- Provide an embedded HTTP server so you can get started quickly
	- Tomcat, Jetty, Undertow, ...
- No need to install a server separately

## Deploying [[Spring]] Boot Apps

- Spring Boot apps can also be deployed in the traditional way
- Deploy **WAR file** to an external server: Tomcat, JBoss, WebSphere etc ...


## [[Spring]] Initializr

- Quickly create a starter Spring project
- Select your dependencies
- Create a Maven / Gradle project
- Import the project into your IDE
	- Eclipse, Intellij, NetBeans etc ...

## Quick Word on [[Maven]]

- When building your Java project, you may need additional JAR files
	- For example: Spring, Hibernate, Commons Logging, JSON etc....

- One approach is to download the JAR files from each project web site

- Manually add the JAR files to your build path / classpath


## [[Maven]] Solution

- Tell Maven the projects you are working with (dependencies)
	- Spring, Hibernate etc ....

- Maven will go out and download the JAR files for those projects for you

- And Maven will make those JAR files available during compile / run 

## Goals of [[Spring]]

- Lightweight development with Java POJOs (Plain-Old-Java-Objects)
- Dependency injection to promote loose coupling
- Minimize boilerplate Java code






