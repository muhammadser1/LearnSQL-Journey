# SQL Notes

## `COALESCE`

- Returns the **first non-null value** from a list of values.
- Example: 
  ```sql
  COALESCE(actual_arrival, schedule_arrival)
```
* If actual_arrival is NULL, it will return schedule_arrival.
* You can also use a fixed value instead of schedule_arrival for replacement.
Example:
```sql
SELECT rental_date,
       COALESCE(CAST(return_date AS VARCHAR), 'not arrived') AS return_status
FROM rental
ORDER BY rental_date DESC;
```
---
CAST
- Changes the data type of a value.
Example:
```sql
CAST(column_name AS target_data_type)
```
Converts return_date to a string in the example above.

---
## REPLACE
- Replaces text in a string column with another text.
```sql 
REPLACE(column, old_text, new_text)
```
* Replace all occurrences of "old_text" with "new_text" in a column:
```sql
SELECT REPLACE(column_name, 'old_text', 'new_text') AS modified_column
FROM table_name;

```
