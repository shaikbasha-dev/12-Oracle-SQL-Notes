# CROSS JOIN

## Definition

* Cross Join works on the principle that **every row of one table matches with all rows of another table**.
* It returns the **Cartesian Product** of two tables.
* If:

  * Table1 has **m** rows
  * Table2 has **n** rows

Then the result contains:

```text
m × n rows
```

---

## Syntax

```sql
SELECT *
FROM table1
CROSS JOIN table2;
```

---

## Example

### Table1

| A | B |
| - | - |
| 1 | 2 |
| 3 | 4 |
| 5 | 6 |
| 7 | 8 |

### Table2

| B | C |
| - | - |
| 2 | 1 |
| 8 | 1 |
| 9 | 1 |

### Output

| A | B | B | C |
| - | - | - | - |
| 1 | 2 | 2 | 1 |
| 1 | 2 | 8 | 1 |
| 1 | 2 | 9 | 1 |
| 3 | 4 | 2 | 1 |
| 3 | 4 | 8 | 1 |
| 3 | 4 | 9 | 1 |
| 5 | 6 | 2 | 1 |
| 5 | 6 | 8 | 1 |
| 5 | 6 | 9 | 1 |
| 7 | 8 | 2 | 1 |
| 7 | 8 | 8 | 1 |
| 7 | 8 | 9 | 1 |

---

## Question

Write a query to display all the details from table1 and table2 using Cross Join.

### Query

```sql
SELECT *
FROM table1
CROSS JOIN table2;
```

### Output

| Total Rows |
| ---------: |
|         12 |

---

# CARTESIAN JOIN

## Definition

* Cartesian Join is the same as Cross Join.
* It is performed by writing multiple tables in the FROM clause without a joining condition.
* Every row of the first table combines with every row of the second table.

---

## Syntax

```sql
SELECT *
FROM table1, table2;
```

---

## Example

### Table1

| A | B |
| - | - |
| 1 | 2 |
| 3 | 4 |
| 5 | 6 |
| 7 | 8 |

### Table2

| B | C |
| - | - |
| 2 | 1 |
| 8 | 1 |
| 9 | 1 |

### Output

| A | B | B | C |
| - | - | - | - |
| 1 | 2 | 2 | 1 |
| 1 | 2 | 8 | 1 |
| 1 | 2 | 9 | 1 |
| 3 | 4 | 2 | 1 |
| 3 | 4 | 8 | 1 |
| 3 | 4 | 9 | 1 |
| 5 | 6 | 2 | 1 |
| 5 | 6 | 8 | 1 |
| 5 | 6 | 9 | 1 |
| 7 | 8 | 2 | 1 |
| 7 | 8 | 8 | 1 |
| 7 | 8 | 9 | 1 |

---

# SELF JOIN

## Definition

* In Self Join, a table is joined with itself.
* During execution, two copies of the same table are created using aliases.
* It is used to compare rows within the same table.

---

## Syntax

```sql
SELECT f.f_name,
       f.l_name,
       f.salary
FROM emp e,
     emp f
WHERE f.salary > e.salary
  AND e.f_name = 'Pandey';
```

---

## Example

### EMP e

| F_NAME | L_NAME | SALARY |
| ------ | ------ | -----: |
| Akash  | Pandey |   5000 |
| Sachin | Jain   |   8000 |
| Vinod  | J      |   5000 |
| Vikas  | P      |   4000 |
| Anup   | Singh  |   6000 |

### EMP f

| F_NAME | L_NAME | SALARY |
| ------ | ------ | -----: |
| Akash  | Pandey |   5000 |
| Sachin | Jain   |   8000 |
| Vinod  | J      |   5000 |
| Vikas  | P      |   4000 |
| Anup   | Singh  |   6000 |

---

### Query

```sql
SELECT f.f_name,
       f.l_name,
       f.salary
FROM emp e,
     emp f
WHERE f.salary > e.salary
  AND e.f_name = 'Pandey';
```

### Output

| F_NAME | L_NAME | SALARY |
| ------ | ------ | -----: |
| Sachin | Jain   |   8000 |
| Anup   | Singh  |   6000 |

---

# EMP and DEPT Table Examples

## Question

Perform EMP table Cross Join with DEPT table.

### Query

```sql
SELECT *
FROM emp
CROSS JOIN dept;
```

### Output

| Result                                           |
| ------------------------------------------------ |
| Returns Cartesian Product of EMP and DEPT tables |

---

# Important Points

| Join Type      | Description                                                   |
| -------------- | ------------------------------------------------------------- |
| Cross Join     | Every row of first table joins with every row of second table |
| Cartesian Join | Same as Cross Join                                            |
| Self Join      | A table joins with itself                                     |
| Aliases        | Used in Self Join to differentiate copies of the same table   |
