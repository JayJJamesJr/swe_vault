# Databases
## Creating a database

```MySQL
CREATE DATABASE DATABASE_NAME
```

## Selecting a database

```MySQL
USE DATABASE DATABASE_NAME
```

## Deleting a database

``` MySQL
DROP DATABASE_NAME
```

## Displaying all databases

```MySQL
SHOW DATABASES
```

# Tables
## Creating a Table

```MYSQL
CREATE TABLE TABLENAME (
	ATTRIBUTE TYPE,
	ATTRIBUTE TYPE,
	 .
	 .
	 .
	ATTRIBUTE TYPE
);
```

## Displaying all tables

```MySQL
SHOW TABLES;
```

## Displaying a specific tables

```MySQL
DESC TABLENAME;
SHOW COLUMNS FROM TABLENAME;
```

## Deleting a table

```MySQL
DROP TABLENAME;
```

## Making comments in MySQL

```MySQL
-- This is a MySQL comment. You can make one by adding two consecutive
-- dashes in front of any statement.
```

# Insertions
## Inserting Data into a table

```MySQL
INSERT INTO tablename(column_name1, column_name2) VALUES (value1, value2);
```

## Inserting multiple values into a table

```MySQL
INSERT INTO tablename(column_name1, column_name2, ...) 
VALUES (value1, value1),
(value2, value2),
(value3, value3)

-- example

INSERT INTO tablename(name, age) 
VALUES ('Meatball', 5),
		('Turkey', 1),
		('Potato Face', 15)
```

## Working with Not Null

In the event that we want force the user to enter a value for a specific column in our table, we can specify the NOT NULL attribute upon creating a table column.

```MySQL
CREATE TABLE TABLENAME (
	ATTRIBUTE TYPE NOT NULL,
	ATTRIBUTE TYPE NOT NULL,
	 .
	 .
	 .
	ATTRIBUTE TYPE NOT NULL
);
```

## Sidenote quotes in MySQL

When working with quotes it's preferred to use single quotes because not all query languages support double quotes for text-based data.

```MySQL
INSERT INTO TABLENAME(TEXT_BASED_COLUMN) VALUES ('Marco\'s pizza');
INSERT INTO TABLENAME(TEXT_BASED_COLUMN) VALUES ('she said "haha"');
```

## Primary Keys

Primary keys are unique identifiers for each item in the table. Their values cannot be inserted twice. To mark a specific column as the primary key of the table either add the `PRIMARY KEY` keyword next to the field or specify the primary key using `PRIMARY KEY(attribute)` as the last attribute in the definition of the table.

```MySQL
-- Marking primary key next to the attribute
CREATE TABLE TABLENAME (
	ATTRIBUTE TYPE PRIMARY KEY,
	ATTRIBUTE TYPE,
	 .
	 .
	 .
	ATTRIBUTE TYPE
);

CREATE TABLE TABLENAME (
	ATTRIBUTE TYPE,
	ATTRIBUTE TYPE,
	 .
	 .
	 .
	ATTRIBUTE TYPE
	PRIMARY KEY(attribute)
);

```