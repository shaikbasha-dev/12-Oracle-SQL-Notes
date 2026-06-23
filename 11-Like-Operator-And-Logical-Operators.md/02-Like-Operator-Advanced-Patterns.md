# LIKE Operator – Advanced Pattern Matching

## Question 1

### Question

Write a query to display details of employees whose first name second character is 'r'.

### Query

```sql
SELECT *
FROM emp
WHERE f_name LIKE '_r%';
```

### Output

| EMP_ID | F_NAME      | L_NAME   |
| -----: | ----------- | -------- |
|      2 | Prabhakaran | Ganeshan |
|     13 | Braven      | Bhupathi |
|     16 | Mrudul      | Kumar    |

---

## Question 2

### Question

Write a query to display details of employees whose mail id third character is '@'.

### Query

```sql
SELECT *
FROM emp
WHERE email LIKE '__@%';
```

### Output

| EMP_ID | F_NAME      | EMAIL                               |
| -----: | ----------- | ----------------------------------- |
|      2 | Prabhakaran | [pk@gmail.com](mailto:pk@gmail.com) |

---

## Question 3

### Question

Write a query to display the details of employees whose last name fourth character from the last is 'n'.

### Query

```sql
SELECT *
FROM emp
WHERE l_name LIKE '%n___';
```

### Output

| EMP_ID | F_NAME  | L_NAME |
| -----: | ------- | ------ |
|      1 | Akash   | Pandey |
|     12 | Madavan | Manish |

---

## Question 4

### Question

Write a query to display the phone number from the employee table whose phone number third digit from last is 3.

### Query

```sql
SELECT phone_number
FROM emp
WHERE phone_number LIKE '%3__';
```

### Output

| PHONE_NUMBER |
| ------------ |
| 53434334     |
| 3443333      |

---

## Question 5

### Question

Write a query to display the last name and salary from emp table whose last name has exactly 5 characters.

### Query

```sql
SELECT l_name, salary
FROM emp
WHERE l_name LIKE '_____';
```

### Output

| L_NAME | SALARY |
| ------ | -----: |
| Singh  |  12000 |
| Kumar  |  19500 |
| patel  |  39500 |
| Whala  |   9500 |

---

# ESCAPE Character

## Definition

The ESCAPE clause is used with the LIKE operator to search for special wildcard characters such as:

* `_` (Underscore)
* `%` (Modulus)

The ESCAPE character treats these wildcards as normal characters.

---

## Question 6

### Question

Display the names from college_student table who have '_' (Underscore) in their names.

### Step 1: Create Table

### Query

```sql
CREATE TABLE college_student (
    id VARCHAR2(54),
    name VARCHAR2(54)
);
```

### Output

| Result        |
| ------------- |
| Table Created |

---

### Step 2: Insert Values

### Query

```sql
INSERT INTO college_student VALUES ('Kod001', 'Sahana_varma');

INSERT INTO college_student VALUES ('Kod002', 'Sindhu_sharma');

INSERT INTO college_student VALUES ('Kod003', 'Swathi%hegde');

INSERT INTO college_student VALUES ('Kod004', 'Shruthi');
```

### Output

| ID     | NAME          |
| ------ | ------------- |
| Kod001 | Sahana_varma  |
| Kod002 | Sindhu_sharma |
| Kod003 | Swathi%hegde  |
| Kod004 | Shruthi       |

---

### Step 3: Find Names Having '_' Character

### Query

```sql
SELECT name
FROM college_student
WHERE name LIKE '%?_%' ESCAPE '?';
```

### Output

| NAME          |
| ------------- |
| Sahana_varma  |
| Sindhu_sharma |

---

## Question 7

### Question

Write a query to display the names from college_student table who have '%' (Modulus) in their names.

### Query

```sql
SELECT name
FROM college_student
WHERE name LIKE '%?%%' ESCAPE '?';
```

### Output

| NAME         |
| ------------ |
| Swathi%hegde |
