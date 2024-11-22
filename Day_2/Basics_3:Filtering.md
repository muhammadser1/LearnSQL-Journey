
# SQL Syntax and Examples for `LIKE`, `ILIKE`, and `NOT LIKE`

## Purpose of `LIKE`
- Used to filter rows based on matching patterns in a column.
- **Wildcards**:
  - **`_`**: Matches any **single** character.
  - **`%`**: Matches **any sequence of characters** (including no characters at all).

## General Syntax
```sql
SELECT column1, column2, ...
FROM table_name
WHERE column_name LIKE pattern;
```

## Key Examples

### Matching a Pattern at the Start
```sql
SELECT *
FROM customer
WHERE firstname LIKE 'a%';
```
- This retrieves all first names that start with the letter **`a`**.

### Matching a Pattern Anywhere
```sql
SELECT *
FROM customer
WHERE firstname LIKE '%A%';
```
- This retrieves all first names that contain **`A`** anywhere in the name.

### Matching a Pattern at the End
```sql
SELECT *
FROM customer
WHERE firstname LIKE '%A';
```
- This retrieves all first names that end with the letter **`A`**.

### Matching a Pattern at the Second Position
```sql
SELECT *
FROM customer
WHERE firstname LIKE '_A%';
```
- This retrieves all first names where **`A`** is the **second** character.

### Using Wildcards to Match Any Single Character
```sql
SELECT *
FROM customer
WHERE firstname LIKE '_A%';
```
- This means the name must have **`A`** in the second position, and can be followed by any number of characters.

---

## Purpose of `ILIKE` (PostgreSQL)
- Similar to `LIKE`, but **case-insensitive**.

### General Syntax
```sql
SELECT column1, column2, ...
FROM table_name
WHERE column_name ILIKE pattern;
```

### Key Example
```sql
SELECT *
FROM customer
WHERE firstname ILIKE 'a%';
```
- This retrieves all first names starting with **`a`** or **`A`**, regardless of case.

---

## Purpose of `NOT LIKE`
- Used to filter rows where the value does **not** match the given pattern.

### General Syntax
```sql
SELECT column1, column2, ...
FROM table_name
WHERE column_name NOT LIKE pattern;
```

### Key Example
```sql
SELECT *
FROM customer
WHERE firstname NOT LIKE 'a%';
```
- This retrieves all first names **that do not start** with **`a`**.

---

## Example with `LIKE` and `AND`

```sql
SELECT *
FROM film
WHERE description LIKE '%Drama%' 
  AND title LIKE '_L%';
```
- This query retrieves films where the description contains the word "Drama" and the title starts with **`L`**.
