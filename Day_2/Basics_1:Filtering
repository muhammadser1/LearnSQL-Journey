
## Purpose of `WHERE`
- Used to filter rows in the output based on specified conditions.
- Always comes after the `FROM` clause.

## General Syntax
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```
## Key Examples

### Basic Filtering
```sql
SELECT * 
FROM payment 
WHERE amount > 10 AND amount < 11 
ORDER BY amount;
```

### Filtering Null Values

```sql
SELECT first_name 
FROM customer 
WHERE first_name IS NOT NULL;
```

### Multiple Conditions (`AND`, `OR`)

```sql
SELECT * 
FROM payment
WHERE (customer_id = 30 OR customer_id = 31) 
AND amount = 2.990;
```
