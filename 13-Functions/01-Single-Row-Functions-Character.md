# FUNCTIONS

## Definition

In SQL, functions are classified into two types:

1. Single Row Functions
2. Multi Row Functions

### Single Row Functions

Single Row Functions are functions that accept a single row as input or multiple rows as input and return **one result for each row**.

### Types of Single Row Functions

| S.No | Function Type        |
| ---- | -------------------- |
| 1    | General Functions    |
| 2    | Number Functions     |
| 3    | Character Functions  |
| 4    | Date Functions       |
| 5    | Conversion Functions |

---

# Character Functions

## 1. UPPER()

### Definition

The `UPPER()` function converts lowercase characters into uppercase.

---

### Question

Write a query to display uppercase of data 'Akash'.

### Query

```sql id="c17rf9"
SELECT UPPER('Akash')
FROM dual;
```

### Output

| UPPER('AKASH') |
| -------------- |
| AKASH          |

---

### Question

Write a query to display all the first names of employees in uppercase.

### Query

```sql id="ujz5ow"
SELECT UPPER(f_name)
FROM emp;
```

### Output

| UPPER(F_NAME) |
| ------------- |
| AKASH         |
| PRABHAKARAN   |
| DEEP          |
| ASHWIN        |
| JOHN          |
| SHASHI        |
| ANDY          |
| DANIEL        |
| ADAM          |
| MEGHANA       |
| MADAVAN       |
| BRAVEN        |
| MAMATHA       |
| SAVITHA       |
| MRUDUL        |
| PANKAJ        |
| JANARDHAN     |
| SARDHAR       |
| JINNATH       |

---

## 2. LOWER()

### Definition

The `LOWER()` function converts uppercase characters into lowercase.

### Question

Write a query to display lowercase of data 'Pandey'.

### Query

```sql id="m1xwdr"
SELECT LOWER('Pandey')
FROM dual;
```

### Output

| LOWER('PANDEY') |
| --------------- |
| pandey          |

---

## 3. INITCAP()

### Definition

The `INITCAP()` function converts the first letter of each word to uppercase and the remaining letters to lowercase.

### Question

Write a query to display Initial letter capital of data 'kodnest'.

### Query

```sql id="mq7k6a"
SELECT INITCAP('kodnest')
FROM dual;
```

### Output

| INITCAP('KODNEST') |
| ------------------ |
| Kodnest            |

---

## 4. UPPER() with WHERE Clause

### Question

Write a query to display all the first names and last names of employees in uppercase where last name is 'Pandey'.

### Query

```sql id="nwpdbv"
SELECT UPPER(f_name),
       UPPER(l_name)
FROM emp
WHERE l_name = 'Pandey';
```

### Output

| UPPER(F_NAME) | UPPER(L_NAME) |
| ------------- | ------------- |
| AKASH         | PANDEY        |

---

### Question

Write a query to display f_name, l_name and salary whose f_name is 'Akash' in any case.

### Query

```sql id="ylgrnf"
SELECT UPPER(f_name),
       UPPER(l_name),
       salary
FROM emp
WHERE f_name = 'Akash';
```

### Output

| UPPER(F_NAME) | UPPER(L_NAME) | SALARY |
| ------------- | ------------: | -----: |
| AKASH         |        PANDEY |  34000 |

---

## 5. CONCAT()

### Definition

The `CONCAT()` function is used to combine two strings.

---

### Question

Write a query to concatenate data 'Akash' and 'Pandey'.

### Query

```sql id="jlwmrr"
SELECT CONCAT('Akash','Pandey')
FROM dual;
```

### Output

| CONCAT('AKASH','PANDEY') |
| ------------------------ |
| AkashPandey              |

---

### Question

Write a query to concatenate f_name and l_name of all employees.

### Query

```sql id="jlwmrr"
SELECT CONCAT(f_name,l_name)
FROM emp;
```

### Output

| CONCAT(F_NAME,L_NAME) |
| --------------------- |
| AkashPandey           |
| PrabhakaranGaneshan   |
| DEEPNair              |
| AshwinK               |
| JohnWilliams          |
| ShashiRaj             |
| AndyJ                 |
| DanielKing            |
| AdamSam               |
| MeghanaDevraj         |
| MadavanManish         |
| BravenBhupathi        |
| MamathaT              |
| SavithaSingh          |
| MrudulKumar           |
| Pankajpatel           |
| JanardhanTohn         |
| SardharL              |
| JinnathWhala          |

---

### Question

Write a query to combine the data '1111' and '2222'.

### Query

```sql id="z3cb9v"
SELECT CONCAT('1111','2222')
FROM dual;
```

### Output

| CONCAT('1111','2222') |
| --------------------- |
| 11112222              |

---

### Question

Write a query to combine the data '1111' and 'Ramu'.

### Query

```sql id="6njlwm"
SELECT CONCAT('1111','Ramu')
FROM dual;
```

### Output

| CONCAT('1111','RAMU') |
| --------------------- |
| 1111Ramu              |

---

### Question

Write a query to combine the data '1111' with NULL.

### Query

```sql id="34ovvk"
SELECT CONCAT('1111',NULL)
FROM dual;
```

### Output

| CONCAT('1111',NULL) |
| ------------------- |
| 1111                |

---

## 6. LENGTH()

### Definition

The `LENGTH()` function returns the number of characters present in a string.

---

### Question

Write a query to find the length of the string 'Prabhakaran'.

### Query

```sql id="p3gokm"
SELECT LENGTH('Prabhakaran')
FROM dual;
```

### Output

| LENGTH('PRABHAKARAN') |
| --------------------- |
| 11                    |

---

### Question

Write a query to find the length of all the first names.

### Query

```sql id="ajxv1o"
SELECT LENGTH(f_name)
FROM emp;
```

### Output

| LENGTH(F_NAME) |
| -------------- |
| 5              |
| 11             |
| 4              |
| 6              |
| 4              |
| 6              |
| 4              |
| 6              |
| 4              |
| 7              |
| 7              |
| 6              |
| 7              |
| 7              |
| 6              |
| 6              |
| 9              |
| 7              |
| 7              |

---

### Question

Write a query to find the length of 1111.

### Query

```sql id="a6yfy8"
SELECT LENGTH(1111)
FROM dual;
```

### Output

| LENGTH(1111) |
| ------------ |
| 4            |

---

### Question

Write a query to display the length of NULL.

### Query

```sql id="17a9b1"
SELECT LENGTH(NULL)
FROM dual;
```

### Output

| LENGTH(NULL) |
| ------------ |
| NULL         |
