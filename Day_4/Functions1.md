This document explains basic string manipulation functions in SQL with examples. These functions only modify the display of the data, not the actual data stored in the database.

---

## **1. `UPPER` Function**
The `UPPER` function converts all characters in a string to uppercase.

### **Example**
```sql
SELECT 
    UPPER(email) AS upper_email, 
    email 
FROM customer;
```
## Explanation
* UPPER(email) displays the email column in all uppercase.
* The data in the database remains unchanged.
  
## **2. LOWER and LENGTH Functions**
* LOWER: Converts all characters to lowercase.
* LENGTH: Returns the number of characters in a string.
* Additional Learning: These are basic SQL string functions. If you want to explore more, search for "SQL string functions" online.
---

## **3. LEFT and RIGHT Functions**
* LEFT: Extracts the first n characters of a string.
* RIGHT: Extracts the last n characters of a string.
* Examples:
  ```sql
-- First 3 characters of the first name
SELECT 
    LEFT(first_name, 3) AS first_three_chars, 
    first_name 
FROM customer;

-- Last 3 characters of the first name
```sql
SELECT 
    RIGHT(first_name, 3) AS last_three_chars, 
    first_name 
FROM customer;
  ```
---
### Combination
You can combine LEFT and RIGHT to extract specific characters.
-- Extract the third character of the first name
```sql
SELECT 
    RIGHT(LEFT(first_name, 3), 1) AS third_char, 
    first_name 
FROM customer;
```
## **4. Concatenation**
Concatenation allows you to merge or combine multiple strings into one.

Example:
```sql
SELECT 
    (first_name || ' ' || last_name) AS full_name 
FROM customer;

```
## **5. POSITION Function**
The POSITION function returns the index of a substring within a string. If the substring does not exist, it returns 0.

Example
```sql
-- Find the position of '@' in the email
SELECT 
    POSITION('@' IN email) AS at_index, 
    email 
FROM customer;

```
## **6. Advanced String Manipulation**
You can combine multiple functions to create more complex string manipulations.

Example
```sql
-- Create a formatted name combining last name and part of the email
SELECT 
    last_name || ', ' || LEFT(email, POSITION(last_name IN email) - 2) AS formatted_name 
FROM customer;

```
---
```sql
select POSITION(last_name in email),email from customer

```
Searching for the word last_name in the email field; if it exists, return the base index, otherwise return 0.
