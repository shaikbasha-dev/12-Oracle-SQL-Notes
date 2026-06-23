# DATA QUERY LANGUAGE (DQL)

## Definition

* DQL stands for **Data Query Language**.
* DQL is used to retrieve, read, or query data from database tables.
* The command used in DQL is:

| Command |
| ------- |
| SELECT  |

---

# SELECT Statement

## Definition

The **SELECT** statement is used to fetch or read data from one or more tables.

It can be used to:

* Retrieve all columns
* Retrieve specific columns
* Filter records using conditions
* Sort records
* Group records
* Join multiple tables

---

## Syntax 1 - Display All Columns

```sql id="s1"
SELECT *
FROM table_name;
```

### Explanation

| Symbol | Meaning                  |
| ------ | ------------------------ |
| *      | Represents all columns   |
| FROM   | Specifies the table name |

---

## Question

Display all records from the EMP table.

### Query

```sql id="q1"
SELECT *
FROM emp;
```

### Output

| EMP_ID | F_NAME      | L_NAME   | EMAIL                                     | PHONE_NUMBER | HIRE_DATE | JOB_ID  | SALARY | COMMISSION_PCT | MANAGER_ID | DEPT_ID |
| -----: | ----------- | -------- | ----------------------------------------- | ------------ | --------- | ------- | -----: | -------------: | ---------: | ------: |
|      1 | Akash       | Pandey   | [akash@gmail.com](mailto:akash@gmail.com) | 9997766      | 29-MAR-12 | AD_PRES |  34000 |           NULL |       NULL |      21 |
|      2 | Prabhakaran | Ganeshan | [pk@gmail.com](mailto:pk@gmail.com)       | 77665522     | 25-MAY-12 | AD_VP   |  45000 |           NULL |        100 |      22 |
|      3 | DEEP        | Nair     | [deep@gmail.com](mailto:deep@gmail.com)   | 876297       | 19-APR-12 | AD_VP   |  55000 |             .5 |        101 |      24 |
|      4 | Ashwin      | K        | [ash@gmail.com](mailto:ash@gmail.com)     | 66554433     | 27-FEB-11 | IT_PROG |  36000 |            .75 |       NULL |     110 |
|    ... | ...         | ...      | ...                                       | ...          | ...       | ...     |    ... |            ... |        ... |     ... |

---

## Syntax 2 - Display Specific Columns

```sql id="s2"
SELECT column_name1,
       column_name2
FROM table_name;
```

### Example

```sql id="q2"
SELECT emp_id,
       f_name,
       salary
FROM emp;
```

### Output

| EMP_ID | F_NAME      | SALARY |
| -----: | ----------- | -----: |
|      1 | Akash       |  34000 |
|      2 | Prabhakaran |  45000 |
|      3 | DEEP        |  55000 |
|      4 | Ashwin      |  36000 |
|      5 | John        |  18000 |
|    ... | ...         |    ... |

---

## Features of SELECT Statement

| Feature                   | Description                         |
| ------------------------- | ----------------------------------- |
| Retrieve All Columns      | SELECT *                            |
| Retrieve Specific Columns | SELECT col1, col2                   |
| Filtering                 | WHERE clause                        |
| Sorting                   | ORDER BY clause                     |
| Grouping                  | GROUP BY clause                     |
| Aggregate Functions       | COUNT(), SUM(), AVG(), MIN(), MAX() |
| Joins                     | INNER, OUTER, CROSS, NATURAL JOIN   |

---

## DQL Summary

| Command | Description                            |
| ------- | -------------------------------------- |
| SELECT  | Retrieves data from one or more tables |

---

## SQL Commands Summary

| Language | Commands                      |
| -------- | ----------------------------- |
| DDL      | CREATE, ALTER, TRUNCATE, DROP |
| DML      | INSERT, UPDATE, DELETE        |
| DQL      | SELECT                        |
| TCL      | COMMIT, ROLLBACK, SAVEPOINT   |
| DCL      | GRANT, REVOKE                 |
