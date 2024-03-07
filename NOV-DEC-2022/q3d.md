Relational algebra is a theoretical language with operations that work on one or more relations (tables) to define queries. Unlike SQL, which is a concrete querying language used in relational database management systems like MariaDB, relational algebra provides a foundation for understanding query operations at a more abstract level. Below, I'll describe how to represent each of your queries in relational algebra.

### i. Select the Records Where Address is 'Curepipe'

To select records based on a condition, we use the selection operator (σ). The condition is specified as a subscript to this operator.

```
σ_address = 'Curepipe'(Patient)
```

This expression selects rows from the `Patient` table where the `address` is equal to 'Curepipe'.

### ii. Select the Records Where Age is Greater Than 60 and Patients Admitted in ‘General Ward’

Here, we combine two conditions using the AND conjunction within the selection operator.

```
σ_age > 60 AND ward_admitted = 'general ward'(Patient)
```

This selects rows from the `Patient` table where the `age` is greater than 60 and the `ward_admitted` is 'general ward'.

### iii. Select Records from Patient Table Admitted in ‘Surgical Ward’ and Payment is Greater Than Rs 100000 or Those Patients Admitted After 12/10/2022

This query involves a combination of conditions with both AND and OR conjunctions. To handle the OR part, especially since it involves a different condition (date), we would typically perform two selections and then unify them using the union operator (∪).

```
σ_ward_admitted = 'surgical ward' AND payment > 100000(Patient)
∪
σ_date_admitted > '2022-12-10'(Patient)
```

The first part selects patients admitted to the 'surgical ward' with payments over Rs 100,000. The second part selects patients admitted after December 10, 2022. The union of these selections gives the final result set.

### iv. Project the Columns pno and Age from the Patient Table

Projection is used to select specific columns from a relation, and it's denoted by the π operator.

```
π_pno, age(Patient)
```

This expression returns a relation with just the `pno` and `age` columns from the `Patient` table.

These relational algebra expressions abstractly represent the operations needed to execute your queries. In practical database management, SQL is used to implement these operations. Relational algebra helps in understanding the theoretical underpinnings of query operations and optimization.