## **HAVING Clause in SQL**

The `HAVING` clause is used to filter the results of grouped data, typically based on aggregate functions. It works **after** the `GROUP BY` operation and allows filtering of groupings based on conditions applied to the aggregates.

---

### **Key Points**
- The `HAVING` clause filters grouped results **after aggregate calculations** (e.g., `SUM`, `AVG`, `COUNT`).
- It is similar to the `WHERE` clause but operates **on groups**, not individual rows.
- **Use Case**: To filter groupings by aggregation results.

---

### **Usage Example**

```sql
SELECT 
    customer_id, 
    SUM(amount) AS total_amount
FROM payment
GROUP BY customer_id
HAVING SUM(amount) > 200 OR SUM(amount) < 50;
```

## Important Notes
1. Execution Order:
* The HAVING clause is applied after the GROUP BY operation.
* Rows are grouped first, aggregates are calculated, and then the HAVING clause filters the grouped results.
2. Comparison with WHERE:
* Use WHERE to filter rows before grouping.
* Use HAVING to filter aggregated results after grouping.
