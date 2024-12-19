# Alter:-
The `ALTER` command in SQL is used to change the structure of a table.
1. **Add a new column** to a table.
2. **Change an existing column** (e.g., its data type or size).
3. **Delete a column** from a table.
### 1. Table Creation and Data Insertion
```sql
CREATE TABLE employee (
    Eid INT PRIMARY KEY,
    name VARCHAR(20),
    Gender VARCHAR(10),
    Designation VARCHAR(23),
    Salary INT
);

INSERT INTO employee VALUES (1, 'Vighnesh', 'male', 'Manager', 70000);
INSERT INTO employee VALUES (2, 'Umesha', 'female', 'VP', 40000);
INSERT INTO employee VALUES (3, 'Rani', 'female', 'Accountant', 44000);
```

### 2. Adding a New Column: `experience`
```sql
ALTER TABLE employee ADD COLUMN experience INT;
```

### 3. Updating Experience Values
```sql
UPDATE employee SET experience = 8 WHERE Eid = 2;
UPDATE employee SET experience = 5 WHERE Eid = 1;
UPDATE employee SET experience = 4 WHERE Eid = 3;
```

### 4. Query: Select All from `employee`
```sql
SELECT * FROM employee;
```
**Output:**
| Eid | name      | Gender | Designation | Salary | experience |
|-----|-----------|--------|-------------|--------|------------|
| 1   | Vighnesh  | male   | Manager     | 70000  | 5          |
| 2   | Umesha    | female | VP          | 40000  | 8          |
| 3   | Rani      | female | Accountant  | 44000  | 4          |

---

### 5. Adding a New Column: `phono`
```sql
ALTER TABLE employee ADD COLUMN phono INT;
```

### 6. Attempt to Update `phono` (Error)
```sql
-- Incorrect Syntax:
UPADTE employee SET phono = 9119119119;

-- Error Output:
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'upadte employee set phono=9119119119' at line 1
```

### 7. Modifying Column Type for `phono`
```sql
ALTER TABLE employee MODIFY COLUMN phono BIGINT;
```

### 8. Updating `phono`
```sql
UPDATE employee SET phono = 1234567890 WHERE Eid = 3;
```

### 9. Query: Select All from `employee`
```sql
SELECT * FROM employee;
```
**Output:**
| Eid | name      | Gender | Designation | Salary | experience | phono       |
|-----|-----------|--------|-------------|--------|------------|-------------|
| 1   | Vighnesh  | male   | Manager     | 70000  | 5          | NULL        |
| 2   | Umesha    | female | VP          | 40000  | 8          | NULL        |
| 3   | Rani      | female | Accountant  | 44000  | 4          | 1234567890  |
