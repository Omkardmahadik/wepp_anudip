

### 1. Table Creation and Data Insertion
```sql
CREATE TABLE staff (
    sid INT PRIMARY KEY,
    sname VARCHAR(29),
    salary INT,
    dept VARCHAR(49),
    deptcnt INT
);

INSERT INTO staff VALUES (1, 'Raju', 23000, 'Marketing', 10);
INSERT INTO staff VALUES (2, 'Anju', 30000, 'HR', 5);
INSERT INTO staff VALUES (3, 'Kaju', 35000, 'Accountant', 5);
INSERT INTO staff VALUES (4, 'Mr.India', 50000, 'CEO', 2);
INSERT INTO staff VALUES (5, 'Mr.GGGo', 40000, 'HR', 5);
```

### 2. Queries and Outputs

#### Query 1: Employees with Salary < 35000 and Department = HR
```sql
SELECT * FROM staff WHERE salary < 35000 AND dept = "HR";
```
**Output:**
| sid | sname | salary | dept | deptcnt |
|-----|-------|--------|------|---------|
| 2   | Anju  | 30000  | HR   | 5       |

---

#### Query 2: Employees with Salary < 35000 or Department = HR
```sql
SELECT * FROM staff WHERE salary < 35000 OR dept = "HR";
```
**Output:**
| sid | sname  | salary | dept       | deptcnt |
|-----|--------|--------|------------|---------|
| 1   | Raju   | 23000  | Marketing  | 10      |
| 2   | Anju   | 30000  | HR         | 5       |
| 5   | Mr.GGGo| 40000  | HR         | 5       |

---

### Aggregate function:
  Aggregate functions in SQL are used to perform calculations on multiple rows of data and return a single value. Below are examples of commonly used aggregate functions
#### Query 3: Minimum Salary
```sql
SELECT MIN(salary) AS MINIMUM_SALARY FROM staff;
```
**Output:**
| MINIMUM_SALARY |
|----------------|
| 23000          |

---

#### Query 4: Maximum Salary
```sql
SELECT MAX(salary) AS MAXIMUM_SALARY FROM staff;
```
**Output:**
| MAXIMUM_SALARY |
|----------------|
| 50000          |

---

#### Query 5: Average Salary
```sql
SELECT AVG(salary) AS AVERAGE_SALARY FROM staff;
```
**Output:**
| AVERAGE_SALARY |
|----------------|
| 35600          |

---

#### Query 6: Total Salary
```sql
SELECT SUM(salary) AS TOTAL_SALARY FROM staff;
```
**Output:**
| TOTAL_SALARY |
|--------------|
| 178000       |

---

#### Query 7: Count of Employees
```sql
SELECT COUNT(sname) AS COUNT FROM staff;
```
**Output:**
| COUNT |
|-------|
| 5     |

---

#### Query 8: Count of Departments
```sql
SELECT COUNT(dept) AS DEPT_COUNT, dept FROM staff GROUP BY dept;
```
**Output:**
| DEPT_COUNT | dept       |
|------------|------------|
| 1          | Marketing  |
| 2          | HR         |
| 1          | Accountant |
| 1          | CEO        |
