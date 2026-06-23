# Date Functions and Conversion Functions

---

## Date Functions

### Definition

Date Functions are used to manipulate and perform operations on date values in SQL.

Common Date Functions:

| S.No | Function         |
| ---- | ---------------- |
| 1    | SYSDATE          |
| 2    | MONTHS_BETWEEN() |
| 3    | ADD_MONTHS()     |
| 4    | NEXT_DAY()       |
| 5    | LAST_DAY()       |

---

## 1. SYSDATE

### Definition

`SYSDATE` returns the current system date and time.

### Question

Write a query to display the system date.

### Query

```sql id="r7w5xg"
SELECT SYSDATE
FROM dual;
```

### Output

| SYSDATE   |
| --------- |
| 29-OCT-23 |

---

## 2. MONTHS_BETWEEN()

### Definition

The `MONTHS_BETWEEN()` function returns the number of months between two dates.

### Question

Write a query to display the number of months between the dates 14-NOV-2014 and 14-FEB-2014.

### Query

```sql id="7q0rkh"
SELECT MONTHS_BETWEEN(
       '14-NOV-2014',
       '14-FEB-2014')
FROM dual;
```

### Output

| MONTHS_BETWEEN('14-NOV-2014','14-FEB-2014') |
| ------------------------------------------- |
| 9                                           |

---

## 3. ADD_MONTHS()

### Definition

The `ADD_MONTHS()` function adds or subtracts months from a date.

---

### Question

Write a query to add 9 months to the date 14-FEB-2014.

### Query

```sql id="7voweg"
SELECT ADD_MONTHS(
       '14-FEB-2014',
       9)
FROM dual;
```

### Output

| ADD_MONTHS('14-FEB-2014',9) |
| --------------------------- |
| 14-NOV-14                   |

---

### Question

Write a query to subtract 9 months from the date 14-FEB-2014.

### Query

```sql id="2hsmhc"
SELECT ADD_MONTHS(
       '14-FEB-2014',
       -9)
FROM dual;
```

### Output

| ADD_MONTHS('14-FEB-2014',-9) |
| ---------------------------- |
| 14-MAY-13                    |

---

## 4. NEXT_DAY()

### Definition

The `NEXT_DAY()` function returns the next specified day after a given date.

### Question

Write a query to find the next Saturday after the date 08-DEC-2012.

### Query

```sql id="cqpl4m"
SELECT NEXT_DAY(
       '08-DEC-2012',
       'SATURDAY')
FROM dual;
```

### Output

| NEXT_DAY('08-DEC-2012','SATURDAY') |
| ---------------------------------- |
| 15-DEC-12                          |

---

## 5. LAST_DAY()

### Definition

The `LAST_DAY()` function returns the last date of the month.

### Question

Write a query to display the last day of the date 18-JUN-2022.

### Query

```sql id="3wws3v"
SELECT LAST_DAY('18-JUN-2022')
FROM dual;
```

### Output

| LAST_DAY('18-JUN-2022') |
| ----------------------- |
| 30-JUN-22               |

---

# Conversion Functions

## Definition

Conversion Functions are used to convert data from one datatype to another.

In this file, we use:

* TO_CHAR(Date)
* TO_CHAR(Number)

---

## 6. TO_CHAR() - Date Format

### Question

Write a query to display l_name and hire_date where hire_date should be displayed in the format dd/mm.

### Query

```sql id="ehbgyg"
SELECT l_name,
       TO_CHAR(hire_date, 'DD/MM')
FROM emp;
```

### Output

| L_NAME   | TO_CHAR(HIRE_DATE,'DD/MM') |
| -------- | -------------------------- |
| Pandey   | 29/03                      |
| Ganeshan | 25/05                      |
| Nair     | 19/04                      |
| K        | 27/02                      |
| Williams | 15/12                      |
| Raj      | 25/08                      |
| J        | 28/08                      |
| King     | 24/06                      |
| Sam      | 16/04                      |
| Devraj   | 25/10                      |
| Manish   | 30/12                      |
| Bhupathi | 27/09                      |
| T        | 25/07                      |
| Singh    | 23/02                      |
| Kumar    | 30/04                      |
| patel    | 23/04                      |
| Tohn     | 28/05                      |
| L        | 29/04                      |
| Whala    | 30/04                      |

---

## 7. TO_CHAR() - Number Format

### Question

Write a query to display l_name and salary where salary should be displayed in the format $99,999.99.

### Query

```sql id="q2lzhn"
SELECT l_name,
       TO_CHAR(salary, '$99,999.99')
FROM emp;
```

### Output

| L_NAME   | TO_CHAR(SALARY,'$99,999.99') |
| -------- | ---------------------------- |
| Pandey   | $34,000.00                   |
| Ganeshan | $45,000.00                   |
| Nair     | $55,000.00                   |
| K        | $36,000.00                   |
| Williams | $18,000.00                   |
| Raj      | $85,000.00                   |
| J        | $28,500.00                   |
| King     | $12,000.00                   |
| Sam      | $53,000.00                   |
| Devraj   | $53,000.00                   |
| Manish   | $25,000.00                   |
| Bhupathi | $45,500.00                   |
| T        | $46,000.00                   |
| Singh    | $12,000.00                   |
| Kumar    | $19,500.00                   |
| patel    | $39,500.00                   |
| Tohn     | $29,500.00                   |
| L        | $29,500.00                   |
| Whala    | $9,500.00                    |
