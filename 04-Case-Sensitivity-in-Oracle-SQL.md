# Case Sensitivity in Oracle SQL

## Introduction

Case Sensitivity refers to whether Oracle SQL treats uppercase and lowercase letters as the same or different.

Examples:

```text
A and a

B and b

HELLO and hello
```

---

## Is Oracle SQL Case Sensitive?

Oracle SQL is:

- Case Insensitive for SQL Keywords
- Case Insensitive for Table Names
- Case Insensitive for Column Names
- Case Sensitive for Character Data (depending on comparison)

---

## SQL Keywords are Case Insensitive

The following statements are equivalent:

```sql
SELECT * FROM student;
```

```sql
select * from student;
```

```sql
SeLeCt * FrOm student;
```

All produce the same result.

---

## Table Names are Case Insensitive

Example:

```sql
SELECT * FROM STUDENT;
```

```sql
SELECT * FROM student;
```

```sql
SELECT * FROM Student;
```

All are treated as the same table.

---

## Column Names are Case Insensitive

Example:

```sql
SELECT NAME FROM student;
```

```sql
SELECT name FROM student;
```

```sql
SELECT Name FROM student;
```

All return the same output.

---

## Character Data Comparison

Suppose the table contains:

```text
Name

Basha
```

Query:

```sql
SELECT *
FROM student
WHERE name='Basha';
```

Result:

```text
Record Found
```

---

Query:

```sql
SELECT *
FROM student
WHERE name='basha';
```

Result:

```text
No Record Found
```

This is because character comparison is case sensitive.

---

## Making Comparison Case Insensitive

We can use:

### UPPER()

Converts text to uppercase.

Example:

```sql
SELECT *
FROM student
WHERE UPPER(name)='BASHA';
```

---

### LOWER()

Converts text to lowercase.

Example:

```sql
SELECT *
FROM student
WHERE LOWER(name)='basha';
```

---

## Example

Table:

| Name |
|------|
| Basha |
| Ravi |
| Sneha |

Query:

```sql
SELECT *
FROM student
WHERE UPPER(name)='BASHA';
```

Output:

```text
Basha
```

---

## Advantages of UPPER() and LOWER()

- Makes searching easier
- Eliminates case mismatch problems
- Used frequently in WHERE clause
- Useful in search applications

---

## Important Points

- SQL Keywords are not case sensitive.
- Table names are not case sensitive.
- Column names are not case sensitive.
- Character values may be case sensitive during comparison.
- UPPER() and LOWER() help perform case-insensitive searches.

---

## Interview Questions

### Q1. Is Oracle SQL case sensitive?

**Answer:**
Oracle SQL is generally case insensitive for keywords, table names, and column names, but character data comparisons can be case sensitive.

---

### Q2. Which functions are used to ignore case sensitivity?

**Answer:**

```sql
UPPER()

LOWER()
```

---

### Q3. What does UPPER() do?

**Answer:**

Converts all characters to uppercase.

Example:

```sql
UPPER('basha')
```

Output:

```text
BASHA
```

---

### Q4. What does LOWER() do?

**Answer:**

Converts all characters to lowercase.

Example:

```sql
LOWER('BASHA')
```

Output:

```text
basha
```

---

## Repository Goal 

This file explains Case Sensitivity in Oracle SQL, including SQL keywords, table names, column names, character comparisons, and the use of UPPER() and LOWER() functions for case-insensitive searches.

Happy Learning and Keep Practicing Oracle SQL!
