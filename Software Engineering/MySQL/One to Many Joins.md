## Relationships


## Types of Joins

## INNER JOIN

- An INNER JOIN returns only the rows that have matching values in both tables

```SQL
SELECT A.column1, B.column2
FROM TableA A
INNER JOIN TableB B ON A.common_column = B.common_column;
```

**Result:** 
Only rows where `common_column` exists in both `TableA` and `TableB`.

## LEFT JOIN

- A LEFT JOIN returns all rows from the left table and the matched rows from the right table. If there is no match, the result is NULL on the side of the right table

```SQL
SELECT A.column1, B.column2 
FROM TableA A 
LEFT JOIN TableB B ON A.common_column = B.common_column;
```

**Result:** 
All rows from `TableA`, and matched rows from `TableB`. If no match, `TableB` columns will have NULL.

## RIGHT JOIN

- A RIGHT JOIN returns all rows from the right table and the matched rows from the left table. If there is no match, the result is NULL on the side of the left table.

```SQL
SELECT A.column1, B.column2
FROM TableA A
RIGHT JOIN TableB B ON A.common_column = B.common_column;
```

**Result:** 
All rows from `TableB`, and matched rows from `TableA`. If no match, `TableA` columns will have NULL.

### 4. FULL JOIN (or FULL OUTER JOIN)

A FULL JOIN returns all rows when there is a match in one of the tables. It returns NULL if there is no match on either side.

```SQL
SELECT A.column1, B.column2
FROM TableA A
FULL JOIN TableB B ON A.common_column = B.common_column;
```

**Result:** 
All rows from both tables. If there is no match, columns from the non-matching table will have NULL.

### 5. CROSS JOIN

A CROSS JOIN returns the Cartesian product of the two tables. This means it will return all possible combinations of rows from the two tables.

**Example:**

```SQL
SELECT A.column1, B.column2
FROM TableA A
CROSS JOIN TableB B;
```

**Result:** 
All combinations of rows from `TableA` and `TableB`.

### 6. SELF JOIN

A SELF JOIN is a regular join but the table is joined with itself.

**Example:**

```SQL
SELECT A.column1, B.column2
FROM TableA A
INNER JOIN TableA B ON A.common_column = B.common_column;
```

**Result:** 
Rows from `TableA` that match other rows within the same table based on the join condition.

These are the basic types of joins in SQL. Each type is useful for different scenarios depending on the desired result set.