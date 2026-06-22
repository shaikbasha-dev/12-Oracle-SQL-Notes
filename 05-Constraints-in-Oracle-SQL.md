# Constraints in Oracle SQL

## Introduction

Constraints are rules applied on table columns to restrict invalid data and maintain data integrity in the database.

Constraints ensure that only valid and accurate data is stored in the table.

---

## Why do we use Constraints?

Constraints are used to:

- Maintain Data Integrity
- Prevent Duplicate Values
- Restrict NULL Values
- Set Default Values
- Restrict Invalid Data
- Establish Relationships Between Tables

---

## Types of Constraints in Oracle SQL

Oracle SQL provides the following constraints:

1. NOT NULL
2. UNIQUE
3. PRIMARY KEY
4. FOREIGN KEY
5. CHECK
6. DEFAULT

---

# 1. NOT NULL Constraint

NOT NULL ensures that a column cannot contain NULL values.

### Syntax

```sql
column_name datatype NOT NULL
```

### Example

```sql
CREATE TABLE student(

id NUMBER,

name VARCHAR2(30) NOT NULL,

age NUMBER

);
```

### Invalid Insert

```sql
INSERT INTO student
VALUES(101,NULL,23);
```

Output:

```text
ORA-01400:
Cannot insert NULL
```

---

# 2. UNIQUE Constraint

UNIQUE prevents duplicate values.

### Syntax

```sql
column_name datatype UNIQUE
```

### Example

```sql
CREATE TABLE employee(

empid NUMBER,

email VARCHAR2(50) UNIQUE

);
```

### Valid

```text
abc@gmail.com

xyz@gmail.com
```

### Invalid

```text
abc@gmail.com

abc@gmail.com
```

Output:

```text
ORA-00001

Unique Constraint Violated
```

---

# 3. PRIMARY KEY Constraint

PRIMARY KEY uniquely identifies each row.

Properties:

- Unique Values
- Cannot be NULL
- Only one PRIMARY KEY per table

### Syntax

```sql
column_name datatype PRIMARY KEY
```

### Example

```sql
CREATE TABLE student(

id NUMBER PRIMARY KEY,

name VARCHAR2(30),

marks NUMBER

);
```

---

# 4. FOREIGN KEY Constraint

FOREIGN KEY establishes a relationship between two tables.

It references:

```text
Primary Key of Parent Table
```

### Parent Table

```sql
CREATE TABLE department(

deptid NUMBER PRIMARY KEY,

deptname VARCHAR2(30)

);
```

### Child Table

```sql
CREATE TABLE employee(

empid NUMBER,

ename VARCHAR2(30),

deptid NUMBER,

FOREIGN KEY(deptid)

REFERENCES department(deptid)

);
```

---

# 5. CHECK Constraint

CHECK restricts values according to a condition.

### Syntax

```sql
column_name datatype

CHECK(condition)
```

### Example

```sql
CREATE TABLE student(

id NUMBER,

age NUMBER CHECK(age>=18)

);
```

### Valid

```text
18

20

25
```

### Invalid

```text
15
```

Output:

```text
Check Constraint Violated
```

---

# 6. DEFAULT Constraint

DEFAULT assigns a default value to a column when no value is provided during insertion.

### Syntax

```sql
column_name datatype DEFAULT value
```

### Example

```sql
CREATE TABLE employee(

empid NUMBER,

ename VARCHAR2(30),

city VARCHAR2(30) DEFAULT 'Hyderabad'

);
```

---

### Insert Without City

```sql
INSERT INTO employee(empid,ename)

VALUES(101,'Basha');
```

Output:

| EMPID | ENAME | CITY |
|------:|-------|------|
| 101 | Basha | Hyderabad |

---

### Insert With City

```sql
INSERT INTO employee

VALUES(102,'Ravi','Bangalore');
```

Output:

| EMPID | ENAME | CITY |
|------:|-------|------|
| 102 | Ravi | Bangalore |

---

## Multiple Constraints Example

```sql
CREATE TABLE student(

id NUMBER PRIMARY KEY,

name VARCHAR2(30) NOT NULL,

email VARCHAR2(50) UNIQUE,

age NUMBER CHECK(age>=18),

city VARCHAR2(30) DEFAULT 'Hyderabad'

);
```

---

## Difference between PRIMARY KEY and UNIQUE

| PRIMARY KEY | UNIQUE |
|------------|--------|
| No NULL values | Allows one NULL |
| No Duplicate Values | No Duplicate Values |
| Only one per table | Multiple UNIQUE allowed |
| Uniquely identifies rows | Maintains uniqueness |

---

## Difference between PRIMARY KEY and FOREIGN KEY

| PRIMARY KEY | FOREIGN KEY |
|------------|-------------|
| Parent Table | Child Table |
| Unique | Can contain duplicates |
| Cannot be NULL | Can be NULL |
| Identifies records | Creates relationship |

---

## Important Points

- NOT NULL → Prevents NULL values.
- UNIQUE → Prevents duplicate values.
- PRIMARY KEY → Unique + NOT NULL.
- FOREIGN KEY → Creates table relationships.
- CHECK → Restricts values using conditions.
- DEFAULT → Assigns default values automatically.

---

## Frequently Asked Interview Questions

### Q1. What are Constraints in Oracle SQL?

Constraints are rules used to maintain data integrity in a table.

---

### Q2. List all Constraints in Oracle SQL.

1. NOT NULL
2. UNIQUE
3. PRIMARY KEY
4. FOREIGN KEY
5. CHECK
6. DEFAULT

---

### Q3. Which constraint prevents NULL values?

```text
NOT NULL
```

---

### Q4. Which constraint prevents duplicate values?

```text
UNIQUE
```

---

### Q5. Which constraint uniquely identifies each row?

```text
PRIMARY KEY
```

---

### Q6. Which constraint creates relationships between tables?

```text
FOREIGN KEY
```

---

### Q7. Which constraint validates data using conditions?

```text
CHECK
```

---

### Q8. Which constraint assigns a value automatically when no value is provided?

```text
DEFAULT
```

---

## Repository Goal 

This file provides complete Oracle SQL Constraints notes covering NOT NULL, UNIQUE, PRIMARY KEY, FOREIGN KEY, CHECK, and DEFAULT constraints with syntax, examples, comparisons, and interview questions for beginners and placement preparation.

Happy Learning and Keep Practicing Oracle SQL!
