# RELATIONAL MODEL - ASSIGNMENT QUERIES

## STATION Table

### Table Structure

| Field  | Data Type    |
| ------ | ------------ |
| ID     | NUMBER       |
| CITY   | VARCHAR2(21) |
| STATE  | VARCHAR2(21) |
| LAT_N  | NUMBER       |
| LONG_W | NUMBER       |

---

## Question 1

### Question

Query a list of CITY and STATE from the STATION table.

### Query

```sql
SELECT CITY,
       STATE
FROM STATION;
```

### Output

| CITY                                              | STATE |
| ------------------------------------------------- | ----- |
| Values depend on records present in STATION table |       |

---

## Question 2

### Question

Let N be the number of CITY entries in STATION, and let N' be the number of distinct CITY names in STATION.

Find:

```text
N - N'
```

### Query

```sql
SELECT COUNT(CITY) - COUNT(DISTINCT CITY) AS DIFFERENCE
FROM STATION;
```

### Output

|            DIFFERENCE |
| --------------------: |
| Depends on table data |

---

## Question 3

### Question

Query the list of CITY names starting with vowels (a, e, i, o, u).

### Query

```sql
SELECT DISTINCT CITY
FROM STATION
WHERE LOWER(CITY) LIKE 'a%'
   OR LOWER(CITY) LIKE 'e%'
   OR LOWER(CITY) LIKE 'i%'
   OR LOWER(CITY) LIKE 'o%'
   OR LOWER(CITY) LIKE 'u%';
```

### Output

| CITY                        |
| --------------------------- |
| Cities starting with vowels |

---

## Question 4

### Question

Query the list of CITY names from STATION whose second character is a vowel.

### Query

```sql
SELECT DISTINCT CITY
FROM STATION
WHERE LOWER(CITY) LIKE '_a%'
   OR LOWER(CITY) LIKE '_e%'
   OR LOWER(CITY) LIKE '_i%'
   OR LOWER(CITY) LIKE '_o%'
   OR LOWER(CITY) LIKE '_u%';
```

### Output

| CITY                                  |
| ------------------------------------- |
| Cities with vowel as second character |

---

## Question 5

### Question

Query the list of CITY names from STATION that do not start with vowels.

### Query

```sql
SELECT DISTINCT CITY
FROM STATION
WHERE LOWER(CITY) NOT LIKE 'a%'
  AND LOWER(CITY) NOT LIKE 'e%'
  AND LOWER(CITY) NOT LIKE 'i%'
  AND LOWER(CITY) NOT LIKE 'o%'
  AND LOWER(CITY) NOT LIKE 'u%';
```

### Output

| CITY                            |
| ------------------------------- |
| Cities not starting with vowels |

---

# EMPLOYEE Table

### Table Structure

| Column      | Data Type |
| ----------- | --------- |
| employee_id | Integer   |
| name        | String    |
| months      | Integer   |
| salary      | Integer   |

---

## Question 6

### Question

Display employee names whose salary is greater than 2000 and who have worked for less than 10 months.

Sort the result by employee_id in ascending order.

### Query

```sql
SELECT name
FROM Employee
WHERE salary > 2000
  AND months < 10
ORDER BY employee_id ASC;
```

### Output

| NAME                           |
| ------------------------------ |
| Depends on Employee table data |

---

# CITY Table

### Table Structure

| Field       | Type         |
| ----------- | ------------ |
| ID          | NUMBER       |
| NAME        | VARCHAR2(17) |
| COUNTRYCODE | VARCHAR2(3)  |
| DISTRICT    | VARCHAR2(20) |
| POPULATION  | NUMBER       |

---

# COUNTRY Table

### Table Structure

| Field          | Type         |
| -------------- | ------------ |
| CODE           | NUMBER       |
| CONTINENT      | VARCHAR2(17) |
| REGION         | VARCHAR2(3)  |
| SURFACEAREA    | VARCHAR2(20) |
| INDEPYEAR      | NUMBER       |
| POPULATION     | NUMBER       |
| LIFEEXPECTANCY | VARCHAR2(4)  |
| GNP            | NUMBER       |
| GNPOLD         | VARCHAR2(9)  |
| LOCALNAME      | VARCHAR2(44) |
| GOVERNMENTFORM | VARCHAR2(44) |
| HEADOFSTATE    | VARCHAR2(32) |
| CAPITAL        | VARCHAR2(4)  |
| CODE2          | VARCHAR2(2)  |

---

## Question 7

### Question

Given the CITY and COUNTRY tables, query the sum of populations of all cities where the continent is **Asia**.

### Query

```sql
SELECT SUM(city.population) AS TOTAL_POPULATION
FROM city
INNER JOIN country
ON city.countrycode = country.code
WHERE country.continent = 'Asia';
```

### Output

|                       TOTAL_POPULATION |
| -------------------------------------: |
| Depends on CITY and COUNTRY table data |

---

# Summary

| Table    | Purpose                              |
| -------- | ------------------------------------ |
| STATION  | Stores city and location information |
| EMPLOYEE | Stores employee details              |
| CITY     | Stores city information              |
| COUNTRY  | Stores country information           |

---

# Important SQL Concepts Used

| Concept    | Example                 |
| ---------- | ----------------------- |
| COUNT      | COUNT(CITY)             |
| DISTINCT   | DISTINCT CITY           |
| LIKE       | CITY LIKE 'A%'          |
| ORDER BY   | ORDER BY employee_id    |
| INNER JOIN | CITY INNER JOIN COUNTRY |
| SUM        | SUM(POPULATION)         |
