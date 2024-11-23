# GROUP BY in SQL

The `GROUP BY` clause is used to group rows that have the same values in specified columns into summary rows. It is commonly used with aggregation functions to perform calculations for each group.

## Purpose of `GROUP BY`
- Used to **GROUP aggregations BY specific columns**.
- For example, to find out how much each customer has spent, you can group the results by `customer_id`.

### Syntax Example:
```sql
SELECT
    customer_id,
    SUM(amount)
FROM payment
GROUP BY customer_id;
```
### Using GROUP BY with WHERE and ORDER BY
You can combine GROUP BY with the WHERE and ORDER BY clauses to filter and sort the results.
```sql
SELECT
    customer_id,
    SUM(amount)
FROM payment
WHERE customer_id < 10
GROUP BY customer_id
ORDER BY customer_id;

```
### Important Notes:
1. Order of Clauses: The WHERE clause always comes after the FROM clause and before GROUP BY.
2. When using aggregation functions, you can include both non-aggregated columns (like customer_id) and aggregated columns (like SUM(amount)) in your SELECT statement,
as long as the non-aggregated columns are included in the GROUP BY clause.


```sql
select customer_id,staff_id,sum(amount),count(*) from payment
group by staff_id,customer_id
order by customer_id
```

1. Tracking Payment Metrics: Analyzing total payments made by each customer and handled by each staff member.
2. Performance Review: Understanding which staff members handle the most transactions for specific customers.
3. Customer Insights: Gaining insights into individual customer payment patterns.
