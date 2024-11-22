# Purpose of Commenting
1. Used to make SQL code more readable and understandable.
2. Helps explain logic and reasoning behind specific parts of the query.
3. Can improve collaboration and maintainability of code.
### Types of Comments
1. Single-line Comment (--)
2. Used for commenting a single line of code. /*[code]*/


# Purpose of Aliases
1. Aliases are used to give temporary names to tables or columns.
2. Makes queries more readable, especially when working with long table or column names.
### General Syntax for Column Aliases
```sql
SELECT column_name AS alias_name
FROM table_name;

```
### General Syntax for Table Aliases
```sql
SELECT column_name
FROM table_name AS alias_name;

```

```sql
-- Select customer details
SELECT first_name AS fname, last_name AS lname, email
FROM customer AS c
WHERE c.first_name LIKE 'A%'; /* Filter customers whose first name starts with A */
```
