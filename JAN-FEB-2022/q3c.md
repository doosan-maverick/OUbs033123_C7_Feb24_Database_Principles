To begin, we'll first create a database and then proceed with creating the `employee` table within it. Following that, I'll guide you through the SQL statements for each of your specific queries, including modifying the table structure and retrieving data based on various conditions.

### Step 1: Create Database

```sql
CREATE DATABASE CompanyDB1;
```

### Step 2: Use Database

```sql
USE CompanyDB1;
```

### Step 3: Create `employee` Table

```sql
CREATE TABLE employee (
    eid INT PRIMARY KEY,
    ename VARCHAR(100),
    address VARCHAR(255),
    age INT,
    gender CHAR(1),
    department VARCHAR(100),
    designation VARCHAR(100),
    year_joined YEAR,
    salary DECIMAL(10, 2)
);
```

Now let's proceed with your specific SQL queries:

### i. Delete the Column Named "salary"

```sql
ALTER TABLE employee
DROP COLUMN salary;
```

Note: After executing this statement, the `salary` column will be permanently removed from the `employee` table, along with any data it contained.

### ii. List the Name of the Employees from the Store Department

```sql
SELECT ename
FROM employee
WHERE department = 'Store';
```

### iii. List the Employee ID and Name of Male Employees Who Are Supervisor

```sql
SELECT eid, ename
FROM employee
WHERE gender = 'M' AND designation = 'Supervisor';
```

### iv. Display Employee Name and Designation of the Employee Living in Flacq or Moka

```sql
SELECT ename, designation
FROM employee
WHERE address IN ('Flacq', 'Moka');
```

### v. List the Details of All Employees Whose Names Start with "D"

```sql
SELECT *
FROM employee
WHERE ename LIKE 'D%';
```

### vi. Display Details of Female Employees Whose Salary Is Between 20000 and 30000

Since the `salary` column is proposed to be deleted in query i, this and subsequent queries involving the `salary` column should be executed before performing the deletion. If the `salary` column has not been deleted yet, the query would be:

```sql
SELECT *
FROM employee
WHERE gender = 'F' AND salary BETWEEN 20000 AND 30000;
```

### vii. Display Details of Employees Who Are Appointed as Manager Since 2015 or Their Age Is Greater Than 45

```sql
SELECT *
FROM employee
WHERE (designation = 'Manager' AND year_joined >= 2015) OR age > 45;
```

### viii. List the Gender and Designation of Employees Whose Salary Is Less Than 20000 in Descending Order of Address

```sql
SELECT gender, designation
FROM employee
WHERE salary < 20000
ORDER BY address DESC;
```

Please remember to execute the queries involving the `salary` column before deleting it if you intend to follow through with that operation. Each SQL statement is tailored to perform the specified operations on your `employee` table within the `CompanyDB1` database.