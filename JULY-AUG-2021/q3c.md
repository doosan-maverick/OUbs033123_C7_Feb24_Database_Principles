Let's start by creating the schema for the `Student` table according to the detailsprovided. After creating the table, we'll proceed with the SQL statements for each of your requests.

### Creating the `Student` Table

To create the `Student` table with the initial schema, you would use the following SQL statement:

```sql
CREATE TABLE Student (
    sid INT PRIMARY KEY,
    sname VARCHAR(255),
    address VARCHAR(255),
    age INT,
    gender VARCHAR(10),
    faculty VARCHAR(255),
    module VARCHAR(255),
    year_admitted INT,
    lecturer VARCHAR(255)
);
```

### Queries Based on Your Requests

Now, let's address each of your requests with an appropriate SQL statement.

#### i. Add a column named "DOB" to the "Student" table.

```sql
ALTER TABLE Student
ADD COLUMN DOB DATE;
```

#### ii. List the name of the students registered in the faculty of science.

```sql
SELECT sname
FROM Student
WHERE faculty = 'Science';
```

#### iii. List the ID of male students whose lecturer is "Dr Aubeeluck".

```sql
SELECT sid
FROM Student
WHERE gender = 'Male' AND lecturer = 'Dr Aubeeluck';
```

#### iv. Display details of the students living in Mahebourg or Floreal.

```sql
SELECT *
FROM Student
WHERE address IN ('Mahebourg', 'Floreal');
```

#### v. List the details of all students whose name starts with "a" and ends with "y".

```sql
SELECT *
FROM Student
WHERE sname LIKE 'a%y';
```

#### vi. Display details of female students whose age is between 19 and 22.

```sql
SELECT *
FROM Student
WHERE gender = 'Female' AND age BETWEEN 19 AND 22;
```

#### vii. Display details of students who are registered to the faculty of Law and admitted after 2018 or age is greater than 20.

```sql
SELECT *
FROM Student
WHERE (faculty = 'Law' AND year_admitted > 2018) OR age > 20;
```

#### viii. List the gender and id of students whose age is greater than 20 in descending order of address.

```sql
SELECT gender, sid
FROM Student
WHERE age > 20
ORDER BY address DESC;
```

These SQL statements should help you perform the necessary operations and queries on your `Student` table in MariaDB. 