# 06-Tables-in-Oracle-SQL

## Introduction

Tables are database objects used to store data in the form of rows and columns. They are the primary storage structures in Oracle Database and are used to organize related information efficiently.

In this repository, the following three tables are used throughout all upcoming topics and examples:

1. EMP Table
2. DEPT Table
3. J_GRADE Table

These tables will be used for:

* Operators
* Order By Clause
* Functions
* Group By Clause
* Having Clause
* Sub Queries
* Joins
* Commands
* Assignment Queries

---

## 1. EMP Table

The EMP table stores employee-related information such as employee details, job role, salary, commission, manager, and department.

### EMP Table Structure

| Column Name    | Description           |
| -------------- | --------------------- |
| EMP_ID         | Employee ID           |
| F_NAME         | First Name            |
| L_NAME         | Last Name             |
| EMAIL          | Email Address         |
| PHONE_NUMBER   | Phone Number          |
| HIRE_DATE      | Date of Joining       |
| JOB_ID         | Job Role              |
| SALARY         | Employee Salary       |
| COMMISSION_PCT | Commission Percentage |
| MANAGER_ID     | Manager ID            |
| DEPT_ID        | Department ID         |

### EMP Table Data

| EMP_ID | F_NAME      | L_NAME   | EMAIL                                     | PHONE_NUMBER | HIRE_DATE | JOB_ID     | SALARY | COMMISSION_PCT | MANAGER_ID | DEPT_ID |
| -----: | ----------- | -------- | ----------------------------------------- | -----------: | --------- | ---------- | -----: | -------------: | ---------: | ------: |
|      1 | Aakash      | Pandey   | [akash@gmail.com](mailto:akash@gmail.com) |      9997766 | 29-MAR-12 | AD_PRES    |  34000 |              - |          - |      21 |
|      2 | Prabhakaran | Han      | [pk@gmail.com](mailto:pk@gmail.com)       |     77665522 | 25-MAY-12 | AD_VP      |  45000 |              - |        100 |      22 |
|      3 | DEEP        | Nair     | [deep@gmail.com](mailto:deep@gmail.com)   |       876297 | 19-APR-12 | AD_VP      |  55000 |             .5 |        101 |      24 |
|      4 | Ashwin      | K        | [ash@gmail.com](mailto:ash@gmail.com)     |     66554433 | 27-FEB-11 | IT_PROG    |  36000 |            .75 |          - |     110 |
|      5 | John        | Williams | [fsda@gmail.com](mailto:fsda@gmail.com)   |      7456465 | 15-DEC-10 | IT_PROG    |  18000 |            1.5 |        110 |      25 |
|      7 | Shashi      | Raj      | [Sac@gmail.com](mailto:Sac@gmail.com)     |      9575673 | 25-AUG-10 | ST_MAN     |  85000 |            1.2 |          - |      22 |
|      8 | Andy        | J        | [And@gmail.com](mailto:And@gmail.com)     |      8579452 | 28-AUG-12 | ST_CLERK   |  28500 |             .9 |          - |      22 |
|      9 | Daniel      | King     | [sas@gmail.com](mailto:sas@gmail.com)     |      5423424 | 24-JUN-10 | ST_CLERK   |  12000 |            1.2 |        117 |      23 |
|     10 | Adam        | Sam      | [adam@gmail.com](mailto:adam@gmail.com)   |       325674 | 16-APR-07 | ST_CLERK   |  53000 |            1.2 |        196 |     110 |
|     11 | Meghana     | Devraj   | [Meg@gmail.com](mailto:Meg@gmail.com)     |      3453424 | 25-OCT-08 | ST_CLERK   |  53000 |            1.2 |        165 |      24 |
|     12 | Madhavan    | Manish   | [mad@gmail.com](mailto:mad@gmail.com)     |      4353213 | 30-DEC-08 | SA_MAN     |  25000 |             .3 |        198 |      23 |
|     13 | Braven      | Bhupathi | [Brav@gmail.com](mailto:Brav@gmail.com)   |     12342231 | 27-SEP-08 | SA_REP     |  45500 |             .2 |        114 |      22 |
|     14 | Mamatha     | T        | [Mam@gmail.com](mailto:Mam@gmail.com)     |     53434334 | 25-JUL-10 | SA_REP     |  46000 |             .2 |          - |      23 |
|     15 | Savitha     | Singh    | [savi@gmail.com](mailto:savi@gmail.com)   |      3443333 | 23-FEB-10 | SA_REP     |  12000 |            .15 |          - |      24 |
|     16 | Mrudul      | Kumar    | [mru@gmail.com](mailto:mru@gmail.com)     |    322378445 | 30-APR-10 | AD_ASST    |  19500 |            1.2 |          - |      23 |
|     17 | Pankaj      | Patel    | [pap@gmail.com](mailto:pap@gmail.com)     |    322378445 | 23-APR-10 | MD_MAN     |  39500 |            1.2 |          - |      22 |
|     18 | Janardhan   | Tohn     | [Tohn@gmail.com](mailto:Tohn@gmail.com)   |    322378445 | 28-MAY-11 | MD_REP     |  29500 |            1.2 |          - |      22 |
|     19 | Sardhar     | L        | [Sar@gmail.com](mailto:Sar@gmail.com)     |    322378445 | 29-APR-10 | AC_MGR     |  29500 |            1.2 |          - |     110 |
|     20 | Jinnath     | Whala    | [jinn@gmail.com](mailto:jinn@gmail.com)   |    322378445 | 30-APR-10 | AC_ACCOUNT |   9500 |            1.2 |          - |     110 |

---

## 2. DEPT Table

The DEPT table stores department details including department name, manager, and location.

### DEPT Table Data

| DEPT_ID | DEPT_NAME   | MANAGER_ID | LOC_ID |
| ------: | ----------- | ---------: | -----: |
|      20 | Admin       |        300 |   2100 |
|      21 | Marketing   |        301 |   2200 |
|      22 | Shipping    |        302 |   2300 |
|      23 | IT          |        303 |   2400 |
|      24 | Sales       |        304 |   2500 |
|      25 | Executive   |        305 |   2600 |
|     110 | Acc         |        306 |   2700 |
|     190 | Contracting |          - |   2800 |
|      26 | Admin       |        307 |   2900 |

---

## 3. J_GRADE Table

The J_GRADE table stores salary grades with their minimum and maximum salary ranges.

### J_GRADE Table Data

| GRADE | LOW_SAL | HIGH_SAL |
| ----- | ------: | -------: |
| A     |    2000 |    60000 |
| B     |    9001 |    19000 |
| D     |    1001 |    25000 |
| F     |   25001 |    35000 |
| H     |   35001 |    89000 |
| I     |   45001 |    99000 |
| J     |   55001 |   199000 |

---

## Conclusion

The EMP, DEPT, and J_GRADE tables serve as the foundation for this Oracle SQL repository. All upcoming topics, examples, and assignment queries will be solved using these tables to maintain consistency and provide practical understanding of Oracle SQL concepts.
