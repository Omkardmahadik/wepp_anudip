 ### 1. Table Creation and Data Insertion

 ```sql
 create table employee
     (
              eid int,
              ename varchar(23),
            did int
     );
 create table department
     (
              did int primary key,
              department varchar(23)
     );
```

### inserting data

```sql
insert into department values(1,"IT");

insert into department values(2,"HR");

insert into department values(3,"Accounts");

insert into department values(4,"Admin");

insert into department values(5,"finance");

insert into employee values(11,"Ran",2);

insert into employee values(12,"shyam",1);

insert into employee values(13,"ghanshyam",1);

insert into employee values(14,"Radheshyam",4);

insert into employee values(15,"Ranshyam",5);
```

### 2. query: select all from employee

```sql
 select * from employee;
+------+------------+------+
| eid  | ename      | did  |
+------+------------+------+
|   11 | Ran        |    2 |
|   12 | shyam      |    1 |
|   13 | ghanshyam  |    1 |
|   14 | Radheshyam |    4 |
|   15 | Ranshyam   |    5 |
+------+------------+------+

 select * from department;```
+-----+------------+
| did | department |
+-----+------------+
|   1 | IT         |
|   2 | HR         |
|   3 | Accounts   |
|   4 | Admin      |
|   5 | finance    |
+-----+------------+

### 3. joints

```sql 
 which employee works in which department
select employee.ename,department.department
from employee
inner join department
on employee.did=department.did;
```

**Output:**
```sql
+------------+------------+
| ename      | department |
+------------+------------+
| shyam      | IT         |
| ghanshyam  | IT         |
| Ran        | HR         |
| Radheshyam | Admin      |
| Ranshyam   | finance    |
+------------+------------+
```