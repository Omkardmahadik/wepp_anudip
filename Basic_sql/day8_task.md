### SQL Script for Departments and Employees Database

```sql
-- Creating the departments table
CREATE TABLE departments (
    department_id FLOAT,
    department_name VARCHAR(30),
    PRIMARY KEY (department_id)
);

-- Creating the employee table
CREATE TABLE employee (
    employee_id FLOAT,
    employee_name VARCHAR(30),
    department_id FLOAT,
    salary FLOAT,
    PRIMARY KEY (employee_id),
    FOREIGN KEY (department_id) REFERENCES departments (department_id)
);

-- Inserting data into departments table
INSERT INTO departments VALUES (10, "hr");
INSERT INTO departments VALUES (20, "itsupport");

-- Inserting valid data into employee table
INSERT INTO employee VALUES (1, "sam", 10, 10000);
INSERT INTO employee VALUES (2, "lemy", 20, 10000);
```