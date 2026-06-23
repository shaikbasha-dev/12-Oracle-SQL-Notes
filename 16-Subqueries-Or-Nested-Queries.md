# SUB QUERIES OR INNER QUERY OR NESTED QUERY IN SQL

## Definition

A **Subquery** is a query written inside another SQL query. It is also known as:

* Inner Query
* Nested Query
* Subquery

A subquery is used to return data that will be used by the main query as a condition to further restrict the data to be retrieved.

---

## Properties of Subqueries

1. Subqueries must be enclosed within parentheses `()`.
2. A subquery can have only one column in the `SELECT` clause unless multiple columns are used in the main query.
3. `ORDER BY` cannot be used in a subquery. However, `GROUP BY` can be used when required.
4. Subqueries that return multiple rows can only be used with operators such as:

   * `IN`
   * `ANY`
   * `ALL`
   * `EXISTS`

---

## Question 1

### Question

Write a query to display the last name, first name, and salary of all employees who earn more than Pandey.

### Query

```sql id="hnlmzi"
SELECT l_name,
       f_name,
       salary
FROM emp
WHERE salary >
      (
          SELECT salary
          FROM emp
          WHERE l_name = 'Pandey'
      );
```

### Output

| L_NAME   | F_NAME      | SALARY |
| -------- | ----------- | -----: |
| Ganeshan | Prabhakaran |  45000 |
| Nair     | DEEP        |  55000 |
| K        | Ashwin      |  36000 |
| Raj      | Shashi      |  85000 |
| Sam      | Adam        |  53000 |
| Devraj   | Meghana     |  53000 |
| Bhupathi | Braven      |  45500 |
| T        | Mamatha     |  46000 |
| patel    | Pankaj      |  39500 |

---

## Question 2

### Question

Write a query to display the department id and first name of all employees who work in the same department in which 'Prabhakaran' works.

### Query

```sql id="1bgdsi"
SELECT dept_id,
       f_name
FROM emp
WHERE dept_id =
      (
          SELECT dept_id
          FROM emp
          WHERE f_name = 'Prabhakaran'
      );
```

### Output

| DEPT_ID | F_NAME      |
| ------: | ----------- |
|      22 | Prabhakaran |
|      22 | Shashi      |
|      22 | Andy        |
|      22 | Braven      |
|      22 | Pankaj      |
|      22 | Janardhan   |

---

## Question 3

### Question

Write a query to display the department id, first name, and job id for all employees who work in the Administration department.

### Query

```sql id="2gdtph"
SELECT dept_id,
       f_name,
       job_id
FROM emp
WHERE dept_id IN
      (
          SELECT dept_id
          FROM dept
          WHERE dept_name = 'Admin'
      );
```

### Output

| Result        |
| ------------- |
| No Data Found |

---

## Question 4

### Question

Write a query to display the employee id of all employees whose department id in employee table is equal to the department id in department table.

### Query

```sql id="o8yn2m"
SELECT emp_id
FROM emp
WHERE dept_id IN
      (
          SELECT dept_id
          FROM dept
      );
```

### Output

| EMP_ID |
| -----: |
|      1 |
|      2 |
|      3 |
|      4 |
|      5 |
|      7 |
|      8 |
|      9 |
|     10 |
|     11 |
|     12 |
|     13 |
|     14 |
|     15 |
|     16 |
|     17 |
|     18 |
|     19 |
|     20 |

---

## Question 5

### Question

Write a query to display the last name and job id whose job id is similar to 'King' and whose salary is greater than Singh's salary.

### Query

```sql id="9kafxe"
SELECT l_name,
       job_id
FROM emp
WHERE job_id =
      (
          SELECT job_id
          FROM emp
          WHERE l_name = 'King'
      )
AND salary >
      (
          SELECT salary
          FROM emp
          WHERE l_name = 'Singh'
      );
```

### Output

| Result        |
| ------------- |
| No Data Found |

---

## Important Points

| Point                 | Description                       |
| --------------------- | --------------------------------- |
| Single Row Subquery   | Returns only one row              |
| Multiple Row Subquery | Returns more than one row         |
| IN Operator           | Used with multiple row subqueries |
| Subquery              | Executed first                    |
| Main Query            | Executed after subquery           |
