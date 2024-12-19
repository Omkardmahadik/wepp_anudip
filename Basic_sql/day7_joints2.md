 ### 1. Table Creation and Data Insertion

  ```sql
create table salesman (
    salesman_id int primary key, -- Unique identifier for each salesman
    name varchar(50), -- Name of the salesman
    city varchar(50), -- City where the salesman operates
    commission decimal(4,2) -- Commission rate for the salesman
);

create table customer (
    customer_id int primary key, -- Unique identifier for each customer
    cust_name varchar(50), -- Name of the customer
    city varchar(50), -- City where the customer is located
    grade int, -- Grade or ranking of the customer
    salesman_id int, -- Foreign key referencing the salesman's ID
    foreign key (salesman_id) references salesman(salesman_id) -- Establishes relationship with salesman table
);

insert into salesman (salesman_id, name, city, commission) values (5001, 'James Hoog', 'New York', 0.15);
insert into salesman (salesman_id, name, city, commission) values (5002, 'Nail Knite', 'Paris', 0.13);
insert into salesman (salesman_id, name, city, commission) values (5005, 'Pit Alex', 'London', 0.11);
insert into salesman (salesman_id, name, city, commission) values (5006, 'Mc Lyon', 'Paris', 0.14);
insert into salesman (salesman_id, name, city, commission) values (5003, 'Lauson Hense', 'San Jose', 0.12);
insert into salesman (salesman_id, name, city, commission) values (5007, 'Paul Adam', 'Rome', 0.13);


insert into customer (customer_id, cust_name, city, grade, salesman_id) values (3002, 'Nick Rimando', 'New York', 100, 5001);
insert into customer (customer_id, cust_name, city, grade, salesman_id) values (3005, 'Graham Zusi', 'California', 200, 5002);
insert into customer (customer_id, cust_name, city, grade, salesman_id) values (3001, 'Fabian Johnson', 'Paris', 300, 5006);
insert into customer (customer_id, cust_name, city, grade, salesman_id) values (3007, 'Brad Davis', 'New York', 200, 5001);
insert into customer (customer_id, cust_name, city, grade, salesman_id) values (3004, 'Geoff Cameron', 'Berlin', 100, 5003);
insert into customer (customer_id, cust_name, city, grade, salesman_id) values (3008, 'Julian Green', 'London', 300, 5002);
insert into customer (customer_id, cust_name, city, grade, salesman_id) values (3009, 'Brad Guzan', 'London', 200, 5005);
insert into customer (customer_id, cust_name, city, grade, salesman_id) values (3003, 'Jozy Altidore', 'Moscow', 200, 5007);

```
# SQL Queries and Outputs

<!-- Query 1: Select salesmen and customers in the same city -->

```sql
select salesman.name as "Salesman", customer.cust_name, customer.city
from salesman, customer
where salesman.city = customer.city; -- Matches salesmen and customers based on the same city
```

### Output:
| Salesman      | cust_name       | city        |
|---------------|-----------------|-------------|
| James Hoog    | Nick Rimando   | New York    |
| James Hoog    | Brad Davis     | New York    |
| Nail Knite    | Fabian Johnson | Paris       |
| Pit Alex      | Brad Guzan     | London      |

---
