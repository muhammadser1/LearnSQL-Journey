## LEFT JOIN

1. Includes all rows from Table A and the matching rows from Table B.
2. Non-matching rows from Table B appear as NULL.
---

## RIGHT JOIN

1. Includes all rows from Table B and the matching rows from Table A.
2. Non-matching rows from Table A appear as NULL.
---

## FULL OUTER JOIN

1. Includes all rows from both Table A and Table B.
2. Non-matching rows from either table appear as NULL.
---

## INNER JOIN

1. Includes only the rows that have matches in both Table A and Table B.

---
## LEFT JOIN with unmatched rows

1. Retrieves only rows from Table A that do not have a matching row in Table B (WHERE B.Value IS NULL).
---
## RIGHT JOIN with unmatched rows

1. Retrieves only rows from Table B that do not have a matching row in Table A (WHERE A.Value IS NULL).
---
## FULL OUTER JOIN with unmatched rows

1. Retrieves rows that do not have matches in either table (WHERE A.Value IS NULL OR B.Value IS NULL).
