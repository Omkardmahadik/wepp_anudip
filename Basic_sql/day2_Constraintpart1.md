# MySQL Constraints: Comprehensive Guide

## Constraint Creation, Modification, and Removal Methods

### 1. NOT NULL Constraint
**Definition:** Ensures a column cannot contain NULL (empty) values.

##### Create NOT NULL
```sql
-- During table creation
CREATE TABLE Users (
    username VARCHAR(50) NOT NULL,
    email VARCHAR(100) NOT NULL
);
```

### 2. UNIQUE Constraint
**Definition:** Guarantees unique values across all rows in a column.

##### Create UNIQUE Constraint
```sql
-- During table creation
CREATE TABLE Users (
    id INT,
    username VARCHAR(50) UNIQUE,
    email VARCHAR(100) UNIQUE
);

-- Multiple column unique constraint
CREATE TABLE Orders (
    order_id INT,
    product_code VARCHAR(20),
    UNIQUE (order_id, product_code)
);
```

### 3. PRIMARY KEY Constraint
**Definition:** Uniquely identifies each record in a table.

##### Create PRIMARY KEY
```sql
-- Single column primary key
CREATE TABLE Users (
    id INT PRIMARY KEY,
    username VARCHAR(100)
);

-- Composite primary key
CREATE TABLE OrderItems (
    order_id INT,
    product_id INT,
    PRIMARY KEY (order_id, product_id)
);
```

### 4. FOREIGN KEY Constraint
**Definition:** Creates a link between two tables, ensuring referential integrity.

##### Create FOREIGN KEY
```sql
-- Basic foreign key
CREATE TABLE Orders (
    order_id INT PRIMARY KEY,
    user_id INT,
    FOREIGN KEY (user_id) REFERENCES Users(id)
);

-- Foreign key with additional options
CREATE TABLE Orders (
    order_id INT PRIMARY KEY,
    user_id INT,
    FOREIGN KEY (user_id) 
    REFERENCES Users(id)
    ON DELETE CASCADE
    ON UPDATE RESTRICT
);
```

### 5. DEFAULT Constraint
**Definition:** Assigns a predefined value when no explicit value is specified.

##### Create DEFAULT Constraint
```sql
CREATE TABLE Users (
    id INT,
    status VARCHAR(20) DEFAULT 'active',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### 6. CHECK Constraint
**Definition:** Validates data based on specific logical conditions.

##### Create CHECK Constraint
```sql
-- Single condition check
CREATE TABLE Products (
    product_id INT,
    price DECIMAL(10,2) CHECK (price > 0)
);

-- Multiple condition check
CREATE TABLE Employees (
    employee_id INT,
    age INT,
    salary DECIMAL(10,2),
    CHECK (age >= 18 AND salary > 0)
);
```

### 7. AUTO_INCREMENT Constraint
**Definition:** Automatically generates sequential, unique numeric values.

##### Create AUTO_INCREMENT
```sql
CREATE TABLE Users (
    id INT PRIMARY KEY AUTO_INCREMENT,
    username VARCHAR(100)
);

-- Custom AUTO_INCREMENT start
CREATE TABLE Products (
    id INT PRIMARY KEY AUTO_INCREMENT START WITH 1000,
    product_name VARCHAR(100)
);
```

## Comprehensive Example
```sql
CREATE TABLE CompleteExample (
    id INT PRIMARY KEY AUTO_INCREMENT,
    username VARCHAR(50) NOT NULL UNIQUE,
    email VARCHAR(100) NOT NULL UNIQUE,
    age INT CHECK (age >= 18),
    status VARCHAR(20) DEFAULT 'active',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## Best Practices
- Choose constraints that match business requirements
- Balance data integrity with performance
- Test constraints thoroughly
- Document constraint logic
