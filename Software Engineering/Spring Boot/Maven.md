Maven is a build management and dependency tool

## What problems does Maven solve?

- When building your Java project, you may need additional Jar files
	- For example: Spring, Hibernate, Commons Logging, JSON etc


- One approach is to download the JAR files from each project web site

- Manually add those files to your build path or classpath


## Maven Solution

- Tell Maven the projects you are working with (dependencies)
	- Spring, Hibernate etc ...

- Maven will go out and download the JAR files for those projects you

- And Maven will make those JAR files available during compile / run

- Think of Maven as your friendly helper / personal shopper


## Maven - How it Works

Maven reads the dependencies you asked for in the [[pom]].xml and checks the local maven repository first. If the local maven repository doesn't have the required dependencies, maven will look at the remote repository and download those dependencies into your local repository. 
Maven will then use those dependencies to build and run your project.


