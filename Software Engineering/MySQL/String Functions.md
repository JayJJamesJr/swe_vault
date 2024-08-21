
## CONCAT, CONCAT_WS

The `CONCAT` function combines multiple strings into a single string

The `CONCAT_WS` function combines multiple strings together with a specific separator.

```MySQL
SELECT CONCAT(first_name, ' ', last_name) FROM people;
SELECT CONCAT_WS(',', first_name, last_name) FROM people;
```

## SUBSTR, SUBSTRING

The `SUBSTRING` and `SUBSTR` function are used to select a specific portion of a string

```MySQL
SELECT SUBSTR('Hello World', 1, 5); -- Returns 'Hello'
SELECT SUBSTRING('Hello World', 1); -- Return 'Hello World'
```

## REPLACE

Replaces a sequence of characters in one string with another string.

```MySQL
-- Returns 'I am Mr.Steele'
SELECT REPLACE('I am Colt', 'Colt', 'Mr.Steele');
```

## REVERSE

Reverses the contents of a string.

```MySQL
SELECT REVERSE('racecar');
-- Returns racecar
```

## CHAR_LENGTH

Returns the number of characters in a String.

*Not to be confused with the LENGTH() function  which returns the number of bytes in a string.*

```MySQL
SELECT CHAR_LENGTH('string');
-- Returns 6
```

## UPPER 

Converts a string to uppercase.

```MySQL
SELECT UPPER('Hello World'); -- Returns HELLO WORLD
```

## LOWER

Converts a string to lowercase.

```MySQL
SELECT LOWER('Hello World'); -- Returns hello world
```

## INSERT

Inserts a string into another string starting at a given position. Characters are replaced in the third argument is > 0;

```MySQL
SELECT INSERT('Quadtratic', 3, 4, 'What'); -- 'QuWhattic'
```

## LEFT

Selects the first `N` characters from the beginning of a string.

```MySQL
SELECT LEFT(author_lname, 1) FROM books;
```

## RIGHT

Selects the last `N` characters from the end of a string.

```MySQL
SELECT RIGHT(author_lname, 1) FROM books;
```

## REPEAT

The `REPEAT` function duplicates a particular string n times;

```MySQL
REPEAT('ha', 4);
```


## TRIM

The `TRIM` function removes leading and trailing characters from a string

```MySQL
SELECT TRIM('   BOSTON  '); -- RETURNS BOSTON
SELECT TRIM(' SAN ANTONIO '); -- RETURNS SAN ANTONIO
SELECT TRIM(LEADING 'x' FROM 'xxxbarxxx'); -- RETURNS barxxx
SELECT TRIM(BOTH 'x' FROM 'xxxbarxxx'); -- RETURNS bar
SELECT TRIM(TRAILING 'x' FROM 'xxxbarxxx'); -- RETURNS xxxbar
```

