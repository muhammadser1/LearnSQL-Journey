
# SQL Syntax and Examples

## Purpose of `BETWEEN`
- Used to filter rows within a specific range of values.
- Includes both boundary values in the range.
- Can be applied to numbers, text, or dates.

## General Syntax
```sql
SELECT column1, column2, ...
FROM table_name
WHERE column_name BETWEEN value1 AND value2;
```

## Key Examples

### Basic Range Filtering
```sql
SELECT payment_id, amount
FROM payment
WHERE amount BETWEEN 1.99 AND 6.99;
```

### Excluding a Range
```sql
SELECT payment_id, amount
FROM payment
WHERE amount NOT BETWEEN 1.99 AND 6.99;
```

### Date Range Filtering
```sql
SELECT payment_id, payment_date
FROM payment
WHERE payment_date BETWEEN '2023-01-01' AND '2023-12-31';
```

---

## Purpose of `IN`
- Acts as a set to match multiple values in a single condition.
- Simplifies queries compared to writing multiple `OR` conditions.

## General Syntax
```sql
SELECT column1, column2, ...
FROM table_name
WHERE column_name IN (value1, value2, ...);
```

## Key Examples

### Filtering Specific Values
```sql
SELECT *
FROM customer
WHERE firstname IN ('ace', 'luffy');
```

### Using `NOT IN`
```sql
SELECT *
FROM customer
WHERE firstname NOT IN ('zoro', 'nami');
```

---

## Complex Queries with `AND`, `OR`, and Parentheses

## General Syntax
```sql
SELECT column1, column2, ...
FROM table_name
WHERE
    (condition1 AND condition2)
    OR
    (condition3 AND (condition4 OR condition5))
    AND condition6;
```

## Key Example
```sql
SELECT payment_id, amount
FROM payment
WHERE 
    (amount BETWEEN 1.99 AND 6.99 AND customer_id = 12)
    OR
    (customer_id IN (25, 67) AND (amount = 9.99 OR amount > 20))
    AND payment_date >= '2020-01-01';
```
