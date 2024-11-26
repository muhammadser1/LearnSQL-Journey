# SQL JOINS

### Overview
Joins are used to combine information from multiple tables in a single query. They allow us to retrieve data from related tables by using a common column.

---

## Types of Joins

### INNER JOIN
- Combines rows from two tables based on a common column (join column).
- Only rows that exist in **both tables** are included in the result.

---

### Syntax
#### Basic INNER JOIN
```sql
SELECT *
FROM TableA
INNER JOIN TableB
ON TableA.employee = TableB.employee;
```
* The result includes only rows where the values in employee match in both tables.
## Using Aliases
* Aliases simplify the query by giving shorter names to tables, making the code easier to write and read.
```sql
SELECT A.name, A.age, B.salary
FROM TableA A
INNER JOIN TableB B
ON A.id = B.id;
```

### INNER JOIN with Multiple Tables
```sql
SELECT A.name, B.salary, C.dept
FROM TableA A
INNER JOIN TableB B
ON A.id = B.user_id
INNER JOIN TableC C
ON B.salary = C.salary_id;
```
