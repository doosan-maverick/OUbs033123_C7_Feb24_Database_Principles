To start, we'll first create a database, say `IBLDB`, and then proceed with creating the `Employee` table within it. After setting up the table, we'll go through each of your queries step-by-step, writing the SQL statements for them.

### Step 1: Create Database

```sql
CREATE DATABASE IBLDB;
GRANT ALL PRIVILEGES ON IBLDB.* TO 'doosan'@'%';
FLUSH PRIVILEGES;
```

### Step 2: Use Database

```sql
USE IBLDB;
```

### Step 3: Create `Employee` Table

```sql
CREATE TABLE Employee (
    eid INT PRIMARY KEY,
    ename VARCHAR(100),
    address VARCHAR(255),
    gender CHAR(1),
    designation VARCHAR(100),
    salary DECIMAL(10, 2),
    department VARCHAR(100),
    years_of_service INT
);
```

Now, let's proceed with your specific SQL queries.

### i. Add a Column Named "Age"

```sql
ALTER TABLE Employee
ADD COLUMN age INT;
```

### ii. List the Name of Male Supervisors

```sql
SELECT ename
FROM Employee
WHERE gender = 'M' AND designation = 'Supervisor';
```

### iii. Display Employee Name and Gender Living in Curepipe or Mahebourg

```sql
SELECT ename, gender
FROM Employee
WHERE address IN ('Curepipe', 'Mahebourg');
```

### iv. List the Details of Female Employee Who Work in the Sales Department

```sql
SELECT *
FROM Employee
WHERE gender = 'F' AND department = 'Sales';
```

### v. List the Details of All Employees Whose Name Start with "F"

```sql
SELECT *
FROM Employee
WHERE ename LIKE 'F%';
```

### vi. Display Details of All Employees Whose Salary Is Between 20000 and 30000

```sql
SELECT *
FROM Employee
WHERE salary BETWEEN 20000 AND 30000;
```

### vii. Display Details of Male Employees Who Have 18 Years of Service or Their Age Is Greater Than 50

```sql
SELECT *
FROM Employee
WHERE (gender = 'M' AND years_of_service >= 18) OR (gender = 'M' AND age > 50);
```

### viii. List the ID and Designation of Employees Whose Salary Is Less Than 50000 in Descending Order of Address

```sql
SELECT eid, designation
FROM Employee
WHERE salary < 50000
ORDER BY address DESC;
```

These SQL statements should help you perform the operations you've described on the `Employee` table. As you practice these queries, you'll get more comfortable with SQL syntax and operations, enhancing your ability to work with databases in MariaDB or any SQL-based database management system.