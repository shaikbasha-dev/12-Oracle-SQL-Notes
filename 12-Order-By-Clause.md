# THE ORDER BY CLAUSE

## Definition

The output of an SQL query can be predicted, but the order in which the rows are displayed cannot be predicted.

If we want to display the output in a specific order, we use the **ORDER BY** clause.

The ORDER BY clause is used to sort the result set:

* **ASC (Ascending Order)** → Default order. Arranges values from smallest to largest or A to Z.
* **DESC (Descending Order)** → Arranges values from largest to smallest or Z to A.

---

## Question 1

### Question

Write a query to display all the first names of employees in ascending order.

### Query

```sql
SELECT f_name
FROM emp
ORDER BY f_name ASC;
```

### Output

| F_NAME      |
| ----------- |
| Adam        |
| Akash       |
| Andy        |
| Ashwin      |
| Braven      |
| DEEP        |
| Daniel      |
| Janardhan   |
| Jinnath     |
| John        |
| Madavan     |
| Mamatha     |
| Meghana     |
| Mrudul      |
| Pankaj      |
| Prabhakaran |
| Sardhar     |
| Savitha     |
| Shashi      |

---

## Question 2

### Question

Write a query to display the hire dates from the oldest date to the newest date.

### Query

```sql
SELECT hire_date
FROM emp
ORDER BY hire_date ASC;
```

### Output

| HIRE_DATE |
| --------- |
| 16-APR-07 |
| 27-SEP-08 |
| 25-OCT-08 |
| 30-DEC-08 |
| 23-FEB-10 |
| 23-APR-10 |
| 29-APR-10 |
| 30-APR-10 |
| 30-APR-10 |
| 24-JUN-10 |
| 25-JUL-10 |
| 25-AUG-10 |
| 15-DEC-10 |
| 27-FEB-11 |
| 28-MAY-11 |
| 29-MAR-12 |
| 19-APR-12 |
| 25-MAY-12 |
| 28-AUG-12 |

---

## Question 3

### Question

Write a query to display salaries of employees in descending order.

### Query

```sql
SELECT salary
FROM emp
ORDER BY salary DESC;
```

### Output

| SALARY |
| -----: |
|  85000 |
|  55000 |
|  53000 |
|  53000 |
|  46000 |
|  45500 |
|  45000 |
|  39500 |
|  36000 |
|  34000 |
|  29500 |
|  29500 |
|  28500 |
|  25000 |
|  19500 |
|  18000 |
|  12000 |
|  12000 |
|   9500 |

---

## Question 4

### Question

Write a query to display commission percentage in ascending order.

### Query

```sql
SELECT commission_pct
FROM emp
ORDER BY commission_pct ASC;
```

### Output

| COMMISSION_PCT |
| -------------: |
|            .15 |
|             .2 |
|             .2 |
|             .3 |
|             .5 |
|            .75 |
|             .9 |
|            1.2 |
|            1.2 |
|            1.2 |
|            1.2 |
|            1.2 |
|            1.2 |
|            1.2 |
|            1.2 |
|            1.2 |
|            1.5 |
|           NULL |
|           NULL |

---

## Question 5

### Question

Write a query to display commission percentage in descending order.

### Query

```sql
SELECT commission_pct
FROM emp
ORDER BY commission_pct DESC;
```

### Output

| COMMISSION_PCT |
| -------------: |
|           NULL |
|           NULL |
|            1.5 |
|            1.2 |
|            1.2 |
|            1.2 |
|            1.2 |
|            1.2 |
|            1.2 |
|            1.2 |
|            1.2 |
|            1.2 |
|             .9 |
|            .75 |
|             .5 |
|             .3 |
|             .2 |
|             .2 |
|            .15 |


