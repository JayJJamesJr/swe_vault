- In the database, you most likely will have
	- Multiple Tables
	- Relationships between Tables

- Need to model this Hibernate 

# Advanced Mappings

- One-to-One
- One-to-Many, Many-to-One
- Many-to-Many

# One to One

- An instructor can have an "instructor detail" entity
	- Similar to an "instructor profile"

# One-to-Many Mapping

- An instructor can have many course

# Many-to-Many Mapping

- A course can have many students
- A student can have many courses

# Important Database Concepts

- Primary key and foreign key
- Cascade

- Primary key: identify a unique row in a table
- Foreign key: 
	- Link tables together
	- A field in one table that refers to primary key in another table

- Cascade
- You can cascade operations
- Apply the same operation to related entities
- If we delete an **instructor**, we should also delete their **instructor_detail**
	- This is known as "CASCADE DELETE"

# Fetch Types: Eager vs Lazy Loading

- When we fetch / retrieve data, should we retrieve EVERYTHING?
	- Eager will retrieve everything
	- Lazy will retrieve on request

# Uni-Directional


# Development Process: One-to-One

1. Prep Work - Define database tables
2. Create InstructorDetail class
3. Create Instructor class
4. Create Main App


# More on Foreign Key

- Main purpose is to preserve relationship between tables
	- Referential Integrity

- Prevents operations that would destroy relationship

- Ensures only valid data is inserted into the foreign key column
	- Can only contain valid reference to primary key in other table

# Entity Lifecycle

| Operations  | Description                                                                        |
| ----------- | ---------------------------------------------------------------------------------- |
| **Detach**  | If entity is detached, it is not associated with a Hibernate session               |
| **Merge**   | If instance is detached from session, then merge will reattach to session          |
| **Persist** | Transitions new instances to managed state. Next flush / commit will save in db.   |
| **Remove**  | Transitions managed entity to be removed. Next flush / commit will delete from db. |
| **Refresh** | Reload / synch object with data from db. Prevents stale data                       |

# One-to-One Mapping

- We currently have a uni-directional mapping

# New Use Case

- If we load an InstructorDetail
	- The we'd like to get the associated Instructor

- Can't do this with current uni-directional relationships

# Bi-Directional

- Bi-Directional relationship is the solution
- We can start InstructorDetail and make it back to the Instructor

# Bi-Directional - The Good News

- To use Bi-Directional, we can keep the existing database schema.
	- No changes required to database.

- Simply update the Java code.

# Development Process: One-toOne (Bi-Directional)

1. Make updates to InstructorDetail class:
	1. Add new field to reference Instructor
	2. Add getter / setter methods for Instructor
	3. Add @OneToOne annotation

# More on mappedBy

- mappedBy tells Hibernate
	- Look at the instructorDetail property in the Instructor class
	- Use information from the Instructor class @JoinColumn
	- To help find associated instructor


# One-to-Many Mapping

## Real-Wold Project Requirement

- If you delete an instructor, DO NOT delete the course
- If you delete the course, DO NOT delete the instructor


# Development Process: One-to-Many

1. Prep Work - Define database tables
2. Create Course class
3. Update Instructor class
4. Create main app


# More on mappedBy

- mappedBy tells Hibernate
	- Look at the instructor property in the Course class
	- Use information from the Course class @JoinColumn
	- To help find associated courses for instructor


# Fetch Types - Eager vs Lazy Loading

- When we fetch / retrieve data, should we retrieve EVERYTHING?
	- Eager will retrieve everything
	- Lazy will retrieve on request

# Eager Loading

- Eager loading will load all dependent entities
	- Load instructor and all of their courses at once

- What about course and students?
	- Could easily turn into a performance nightmare

- In our app, if we are searching for a course by keyword
	- Only want a list of matching courses
- Eager loading would still load all students for each course

 - Best Practice
 - Only load data when absolutely needed
 - Prefer lazy loading instead Eager loading

# Lazy Loading

- Lazy loading will load the main entity first
	- Load dependent entities on demand (lazy)


# Fetch Type

- When you define the mapping relationship
	- You can specify the fetch type: EAGER or LAZY

## Default Fetch Types

| Mapping     | Default Fetch Types |
| ----------- | ------------------- |
| @OneToOne   | FetchType.EAGER     |
| @OneToMany  | FetchType.LAZY      |
| @ManyToOne  | FetchType.EAGER     |
| @ManyToMany | FetchType.LAZY      |

## Overriding Default Fetch Type

- Specifying the fetch type, overrides the defaults

# More about Lazy Loading

- When you lazy load, the data is only retrieved on demand

- However, this requires an open Hibernate session
	- Need an connection to database to retrieve data

- If the Hibernate session is closed
	- An you attempt to retrieve lazy data
	- Hibernate will throw an exception

# We have options now

- If you only need Instructor .. and no courses, then call
	- appDAO.findInstructorById(...)

- If you need Instructor AND courses, then call
	- appDAO.findInstructorByIdJoinFetch(...)


# Update Course

- Find a course by ID
- Change the course's data by calling setter method(s)
- Update the course using the DAO

# Add new DAO method to update course

```java
@Override
@Transactional
public void update(Course tempCourse) {
	entityManager.merge(tempCourse);
}
```
