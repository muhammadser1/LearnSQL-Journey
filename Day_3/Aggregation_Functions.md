# Aggregation Functions in SQL

Aggregation functions are used to aggregate values from multiple rows into a single value. They are commonly used to perform calculations on a set of data.

## Most Common Aggregation Functions:
- `SUM()`: Adds up the values in a column.
- `AVG()`: Calculates the average value of a column.
- `MIN()`: Returns the minimum value in a column.
- `MAX()`: Returns the maximum value in a column.
- `COUNT()`: Returns the number of rows in a column.

## Syntax Examples

### 1. `SUM()` Example
```sql
SELECT SUM(amount)
FROM payment;
```
This query will return the sum of the amount column in the payment table.

### 2. Why This Doesn't Work
```sql
SELECT SUM(amount), payment_id
FROM payment;
```
This query doesn't work because when using aggregation functions (like SUM()), all non-aggregated columns (like payment_id here) need to be included in the GROUP BY clause.
To fix this, you can group by payment_id.

### 3. Multiple Aggregation Functions
```sql
SELECT SUM(amount), COUNT(*)
FROM payment;
```
### 4. AVG() with Rounding
```sql
SELECT ROUND(AVG(amount), 2)
FROM payment;
```
