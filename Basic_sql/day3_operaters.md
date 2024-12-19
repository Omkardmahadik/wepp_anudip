
# MySQL Queries with Examples

## 1. Using `BETWEEN` Query

### Query:
```sql
SELECT * FROM employees
WHERE age BETWEEN 25 AND 35;
```

### Explanation:
- This query retrieves all records from the `employees` table where the `age` column value is between 25 and 35, inclusive.

### Output:
| EmployeeID | Name       | Age | Department  |
|------------|------------|-----|-------------|
| 101        | John Doe   | 30  | HR          |
| 102        | Jane Smith | 28  | IT          |

---

## 2. Using `LIKE` Query

### Query:
```sql
SELECT * FROM employees
WHERE name LIKE 'J%';
```

### Explanation:
- This query retrieves all records where the `name` column starts with the letter "J".

### Output:
| EmployeeID | Name       | Age | Department  |
|------------|------------|-----|-------------|
| 101        | John Doe   | 30  | HR          |
| 102        | Jane Smith | 28  | IT          |

---

## 3. Using `NOT LIKE` Query

### Query:
```sql
SELECT * FROM employees
WHERE name NOT LIKE 'J%';
```

### Explanation:
- This query retrieves all records where the `name` column does not start with the letter "J".

### Output:
| EmployeeID | Name        | Age | Department  |
|------------|-------------|-----|-------------|
| 103        | Alice Brown | 40  | Finance     |
| 104        | Bob Martin  | 35  | Marketing   |

---

### Notes:
- `BETWEEN` includes the boundary values.
- `LIKE` supports wildcards (`%` for zero or more characters, `_` for a single character).
- `NOT LIKE` excludes values matching the specified pattern.
