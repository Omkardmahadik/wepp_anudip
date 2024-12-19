# Group By:
The GROUP BY statement groups rows that have the same values into summary rows, like "find the number of customers in each country"

The GROUP BY statement is often used with aggregate functions (COUNT(), MAX(), MIN(), SUM(), AVG()) to group the result-set by one or more columns.

### 1. Table Creation and Data Insertion
```sql
CREATE TABLE customers (
    cid INT,
    cname VARCHAR(34),
    address VARCHAR(30),
    city VARCHAR(30),
    country VARCHAR(34)
);

INSERT INTO customers VALUES (1, 'Abhi', 'moria', 'Berlin', 'Germany');
INSERT INTO customers VALUES (2, 'Bhushan', 'vora gate', 'Mexico-df', 'Mexico');
INSERT INTO customers VALUES (3, 'Carbon', 'Pqr', 'London', 'UK');
INSERT INTO customers VALUES (4, 'Darwin', 'ABC', 'Urban', 'Mexico');
```

### 2. Query and Output

#### Query: Count of Customers by Country
```sql
SELECT COUNT(cid) AS CUSTOMER_COUNT, country
FROM customers
GROUP BY country;
```
**Output:**
| CUSTOMER_COUNT | country  |
|----------------|----------|
| 1              | Germany  |
| 2              | Mexico   |
| 1              | UK       |

### 3. Table Creation and Data Insertion
```sql
CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    item VARCHAR(30),
    amount INT,
    customer_id INT
);

INSERT INTO orders VALUES (1, 'Keyboards', 400, 4);
INSERT INTO orders VALUES (3, 'Monitor', 1200, 3);
INSERT INTO orders VALUES (4, 'Keyboards', 400, 1);
INSERT INTO orders VALUES (5, 'Mousepad', 250, 2);
```

### 2. Query and Output

#### Query: Total Amount Spent by Each Customer
```sql
SELECT customer_id, SUM(amount) AS TOTAL_AMOUNT
FROM orders
GROUP BY customer_id;
```
**Output:**
| customer_id | TOTAL_AMOUNT |
|-------------|--------------|
| 1           | 400          |
| 2           | 250          |
| 3           | 1200         |
| 4           | 400          |
