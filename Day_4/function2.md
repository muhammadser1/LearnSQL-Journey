## SQL String and Date Functions
### 1. SUBSTRING Function
The SUBSTRING function is used to extract a substring from a string.
```sql
-- Extract a substring starting from the 2nd character and with a length of 3 characters
SELECT SUBSTRING(email FROM 2 FOR 3) 
FROM customer;

-- Extract a substring starting from the 2nd character to the end of the string
SELECT SUBSTRING(email FROM 2) 
FROM customer;

```
* string: The column or string from which you want to extract.
* start: The starting position (1-based index).
* length: The number of characters to extract (optional). If not specified, it extracts from the start to the end of the string.

### 2. EXTRACT Function
The EXTRACT function is used to extract parts from a date or timestamp.
```sql
-- Extract the day from a date
SELECT EXTRACT(DAY FROM rental_date) 
FROM rental;

-- Extract the month from a date and calculate the sum of the amount for each month
SELECT EXTRACT(MONTH FROM payment_date), SUM(amount) 
FROM payment
GROUP BY EXTRACT(MONTH FROM payment_date);

-- Extract the day of the week (0-6) from a date
SELECT EXTRACT(DOW FROM payment_date), SUM(amount) 
FROM payment
GROUP BY EXTRACT(DOW FROM payment_date);

```
### 3. TO_CHAR Function
The TO_CHAR function is used to convert dates, timestamps, or numbers into a custom format.
```sql
-- Convert a date to a custom format (e.g., MM-YYYY)
SELECT TO_CHAR(rental_date, 'MM-YYYY') 
FROM rental;

-- Convert a date to the full name of the day
SELECT TO_CHAR(rental_date, 'Day') 
FROM rental;

-- Convert a date to a custom format including the day abbreviation and full date
SELECT TO_CHAR(payment_date, 'Dy, DD/MM/YYYY') 
FROM rental;

```
### Summary
These SQL functions help you manipulate and extract specific parts of strings and dates:

* SUBSTRING: Extracts a portion of a string.
* EXTRACT: Extracts parts of a timestamp or date (e.g., day, month, or weekday).
* TO_CHAR: Converts dates and timestamps into custom formats.
