# Column Aliases and Additional Operators in SQL

## Column Aliases in SQL

Aliases are the other names given to columns in SQL. Whenever aliases names have to be specified for columns then following syntax has to be used:

### Syntax
```sql
columnname AS aliasname

```

OR

```sql
columnname "alias name"

```

> **Note:** The alias names will never be reflected in the actual tables present on the hard disk of the computer.

---

## 2. Relational Operators

Relational operators are used to compare values and filter records. The operators include: `=`, `>`, `<`, `>=`, `<=`, `!=` or `<>`.

### Query 1

Write a query to display the details of employee whose first name is Akash.

```sql
SELECT * FROM emp WHERE f_name = 'Akash';

```

#### Output

| EMP_ID | F_NAME | L_NAME | EMAIL | PHONE_NUMBER | HIRE_DATE | JOB_ID | SALARY | COMMISSION_PCT | MANAGER_ID | DEPT_ID |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Akash | Pandey | akash@gmail.com | 9997766 | 29-MAR-12 | AD_PRES | 34000 | - | - | 21 |

### Query 2

Write a query to display the details of employees whose department id is greater than 30.

```sql
SELECT * FROM emp WHERE dept_id > 30;

```

#### Output

| EMP_ID | F_NAME | L_NAME | EMAIL | PHONE_NUMBER | HIRE_DATE | JOB_ID | SALARY | COMMISSION_PCT | MANAGER_ID | DEPT_ID |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 4 | Ashwin | K | ash@gmail.com | 66554433 | 27-FEB-11 | IT_PROG | 36000 | 0.75 | - | 110 |
| 10 | Adam | Sam | adam@gmail.com | 325674 | 16-APR-07 | ST_CLERK | 53000 | 1.2 | 196 | 110 |
| 19 | Sardhar | L | Sar@gmail.com | 322378445 | 29-APR-10 | AC_MGR | 29500 | 1.2 | - | 110 |
| 20 | Jinnath | Whala | jinn@gmail.com | 322378445 | 30-APR-10 | AC_ACCOUNT | 9500 | 1.2 | - | 110 |

### Query 3

Write a query to display details of employees whose salary is less than 10000 from emp table.

```sql
SELECT * FROM emp WHERE salary < 10000;

```

#### Output

| EMP_ID | F_NAME | L_NAME | EMAIL | PHONE_NUMBER | HIRE_DATE | JOB_ID | SALARY | COMMISSION_PCT | MANAGER_ID | DEPT_ID |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 20 | Jinnath | Whala | jinn@gmail.com | 322378445 | 30-APR-10 | AC_ACCOUNT | 9500 | 1.2 | - | 110 |

### Query 4

Write a query to display email id, phone number whose commission percentage is greater than or equal to 5 from emp table.

```sql
SELECT email, phone_number FROM emp WHERE commission_pct >= 5;

```

#### Output

```text
no data found

```

### Query 5

Write a query to display emp id, f_name, l_name from emp table whose salary is less than or equal to 34000.

```sql
SELECT email, f_name, l_name FROM emp WHERE salary <= 34000;

```

#### Output

| EMAIL | F_NAME | L_NAME |
| --- | --- | --- |
| akash@gmail.com | Akash | Pandey |
| sfda@gmail.com | John | Williams |
| And@gmail.com | Andy | J |
| sas@gmail.com | Daniel | King |
| mad@gmail.com | Madavan | Manish |
| savi@gmail.com | Savitha | Singh |
| mru@gmail.com | Mrudul | Kumar |
| Tohn@gmail.com | Janardhan | Tohn |
| Sar@gmail.com | Sardhar | L |
| jinn@gmail.com | Jinnath | Whala |

### Query 6

Write a query to display the details of employees who is not clerk (ST_CLERK ) from emp table.

```sql
SELECT * FROM emp WHERE job_id != 'ST_CLERK';

```

#### Output

| EMP_ID | F_NAME | L_NAME | EMAIL | PHONE_NUMBER | HIRE_DATE | JOB_ID | SALARY | COMMISSION_PCT | MANAGER_ID | DEPT_ID |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Akash | Pandey | akash@gmail.com | 9997766 | 29-MAR-12 | AD_PRES | 34000 | - | - | 21 |
| 2 | Prabhakaran | Ganeshan | pk@gmail.com | 77665522 | 25-MAY-12 | AD_VP | 45000 | - | 100 | 22 |
| 3 | DEEP | Nair | deep@gmail.com | 876297 | 19-APR-12 | AD_VP | 55000 | 0.5 | 101 | 24 |
| 4 | Ashwin | K | ash@gmail.com | 66554433 | 27-FEB-11 | IT_PROG | 36000 | 0.75 | - | 110 |
| 5 | John | Williams | sfda@gmail.com | 7456465 | 15-DEC-10 | IT_PROG | 18000 | 1.5 | 110 | 25 |
| 7 | Shashi | Raj | Sac@gmail.com | 9575673 | 25-AUG-10 | ST_MAN | 85000 | 1.2 | - | 22 |
| 12 | Madavan | Manish | mad@gmail.com | 4353213 | 30-DEC-08 | SA_MAN | 25000 | 0.3 | 198 | 23 |
| 13 | Braven | Bhupathi | Brav@gmail.com | 12342231 | 27-SEP-08 | SA_REP | 45500 | 0.2 | 114 | 22 |
| 14 | Mamatha | T | Mam@gmail.com | 53434334 | 25-JUL-10 | SA_REP | 46000 | 0.2 | - | 23 |
| 15 | Savitha | Singh | savi@gmail.com | 3443333 | 23-FEB-10 | SA_REP | 12000 | 0.15 | - | 24 |
| 16 | Mrudul | Kumar | mru@gmail.com | 322378445 | 30-APR-10 | AD_ASST | 19500 | 1.2 | - | 23 |
| 17 | Pankaj | patel | pap@gmail.com | 322378445 | 23-APR-10 | MD_MAN | 39500 | 1.2 | - | 22 |
| 18 | Janardhan | Tohn | Tohn@gmail.com | 322378445 | 28-MAY-11 | MD_REP | 29500 | 1.2 | - | 22 |
| 19 | Sardhar | L | Sar@gmail.com | 322378445 | 29-APR-10 | AC_MGR | 29500 | 1.2 | - | 110 |
| 20 | Jinnath | Whala | jinn@gmail.com | 322378445 | 30-APR-10 | AC_ACCOUNT | 9500 | 1.2 | - | 110 |

---

## 3. Concatenation Operator (||)

The concatenation operator joins character strings or column values together into a single continuous expression.

### Query 1

Write a query to concatenate f_name and l_name from emp table and display it as full name.

```sql
SELECT f_name || ' ' || l_name AS "full name" FROM emp;

```

#### Output

| full name |
| --- |
| Akash Pandey |
| Prabhakaran Ganeshan |
| DEEP Nair |
| Ashwin K |
| John Williams |
| Shashi Raj |
| Andy J |
| Daniel King |
| Adam Sam |
| Meghana Devraj |
| Madavan Manish |
| Braven Bhupathi |
| Mamatha T |
| Savitha Singh |
| Mrudul Kumar |
| Pankaj patel |
| Janardhan Tohn |
| Sardhar L |
| Jinnath Whala |

### Query 2

Write a query to concatenate Sachin and Tendulkar and display it as full name.

```sql
SELECT 'Sachin ' || ' Tendulkar' AS "full name" FROM dual;

```

#### Output

| full name |
| --- |
| Sachin Tendulkar |

```
