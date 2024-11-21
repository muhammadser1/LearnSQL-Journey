
# SQL Basics: Day 1

## Schema
We use a **schema** to structure and organize the database.

---

## Delete Table
To delete a table:
```sql
DROP TABLE table_name;
```

---

## Select
We use `SELECT` to return data from a table.

### Syntax:
```sql
SELECT column_names 
FROM table_name;
```

### Examples:
1. Select all columns:
   ```sql
   SELECT * FROM actor;
   ```
2. Select specific columns:
   ```sql
   SELECT first_name, last_name FROM actor;
   ```

---

## Order By
We use `ORDER BY` to sort the results.

### Examples:
1. Sort by `first_name` in ascending order (default):
   ```sql
   SELECT first_name FROM customer ORDER BY first_name;
   ```
2. Sort by `first_name` in descending order:
   ```sql
   SELECT * FROM customer ORDER BY first_name DESC;
   ```
3. Sort by multiple columns:
   - Ascending:
     ```sql
     SELECT first_name, last_name 
     FROM actor 
     ORDER BY first_name, last_name;
     ```
   - Descending:
     ```sql
     SELECT first_name, last_name 
     FROM actor 
     ORDER BY first_name DESC, last_name;
     ```
4. Order by column number:
   ```sql
   SELECT * 
   FROM customer 
   ORDER BY 1; -- First column
   ```

---

## Select Distinct
To see the different (distinct) values in a column:

### Examples:
1. Unique values in a column:
   ```sql
   SELECT DISTINCT rating FROM film;
   ```
2. Unique combinations of values(pairs):
   ```sql
   SELECT DISTINCT rating, rental_duration 
   FROM film;
   ```

---

## Limit
The `LIMIT` clause is used to limit the number of rows in the output.

### Examples:
1. Limit output to 4 rows:
   ```sql
   SELECT DISTINCT rating, rental_duration 
   FROM film 
   LIMIT 4;
   ```
2. Get the last 4 rows by sorting in descending order first:
   ```sql
   SELECT * 
   FROM film 
   ORDER BY some_column DESC 
   LIMIT 4;
   ```

---

## Count
The `COUNT` function is used to count rows in the output.

### Examples:
1. Count all rows:
   ```sql
   SELECT COUNT(*) FROM customer;
   ```
2. Count rows in a specific column:
   ```sql
   SELECT COUNT(column_name) FROM table_name;
   ```
3. Count distinct values:
   ```sql
   SELECT COUNT(DISTINCT first_name) FROM actor;
   ```
4. Count rows with non-NULL values:
   ```sql
   SELECT COUNT(first_name) FROM actor;
   ```
