## Functions

1. **`abs(x)`**: Absolute value  
   Example: `abs(-7) = 7`  

2. **`round(x, d)`**: Rounds `x` to `d` decimal places  
   Example: `round(4.3543, 3) = 4.354`  

3. **`ceiling(x)`**: Rounds `x` up to the nearest integer  
   Example: `ceiling(4.35) = 5`  

4. **`floor(x)`**: Rounds `x` down to the nearest integer  
   Example: `floor(4.35) = 4`  

### Example Query:
```sql
SELECT film_id, 
       round((rental_rate / replacement_cost * 100), 2) AS percentage
FROM film;
```
## CASE Statement
* Acts like an IF/THEN statement.
* Evaluates a set of conditions and returns a value when a condition is met.
```sql
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    ...
    WHEN conditionN THEN resultN
    ELSE result
END
```
Example:
```sql
SELECT amount,
       CASE
           WHEN amount < 2 THEN 'low'
           WHEN amount < 5 THEN 'med'
           ELSE 'high'
       END AS amount_category
FROM payment
WHERE amount > 1  -- Filter rows where amount is greater than 1
ORDER BY amount ASC;
```
```sql
SELECT COUNT(*) AS many_flights,
       CASE
           WHEN actual_departure - scheduled_departure < '00:05' THEN 'on-time'
           ELSE 'late'
       END AS is_late
FROM flights
GROUP BY is_late;
```
```sql
SELECT rating,
       SUM(
           CASE
               WHEN rating IN ('G', 'PG') THEN 1
               ELSE 0
           END
       ) AS count
FROM film
GROUP BY rating;

```
