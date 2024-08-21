## DISTINCT

Selects all the unique columns in a query.

```MySQL
SELECT DISTINCT author_fname, author_lname FROM books
```

## ORDER BY

Arranges the selected columns in a specific order.

```MySQL
SELECT author_fname, author_lname FROM books ORDER BY author_lname
```

## LIMIT

Limits the result of a query to `N` records.

```MySQL
SELECT author_fname, author_lname FROM books ORDER BY author_lname LIMIT 5
```

## LIKE

LIKE is a pattern matching function that returns rows that match a specific pattern

```MySQL
-- A % represents any number of characters.
SELECT * FROM books WHERE author_fname LIKE '%a%'; -- any number of characters followed by an a followed by any number of characters

-- An underscore represents a single character an in this case represents a five letter word where any two characters come before the a and any two characters come after it
SELECT * FROM books WHERE author_fname LIKE '__a__'; 

-- Select books where author's first name starts with a
SELECT * FROM books WHERE author_fname LIKE 'a%';

-- Select books where author's name ends with a
SELECT * FROM books WHERE author_fname LIKE '%a'; 
```

## ESCAPING WILDCARDS

```MySQL
SELECT * FROM books WHERE author_fname LIKE '\%%';
```


