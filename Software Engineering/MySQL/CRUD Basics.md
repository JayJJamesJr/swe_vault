
# Create
# Read

# Update

# Delete

## Select Statement

The select statement is used to read rows that meet a set of criteria. For example you can filter a row to return a specific set of columns or a set of columns that meet a boolean condition.

```MySQL
SELECT col1, col2, col3 FROM TABLE;
SELECT col1, col2, col3 FROM TABLE WHERE col3 = null;
```

## Aliases

An alias allows you to rename table columns in the result of the `SELECT` statement query.

```MySQL
SELECT cat_id AS id FROM TABLE;
```


## Updating Rows

```MySQL
-- We can set a single column
UPDATE cats SET breed='Shorthair'
WHERE breed='Tabby';
-- We can also set a list of columns
UPDATE employees SET current_status='laid-off', last_name='who cares';
```

## Deleting Rows

The delete statement allows us to remove records from our database

```MySQL
DELETE FROM cats WHERE name='Egg';
```

