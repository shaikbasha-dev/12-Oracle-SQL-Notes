# Oracle SQL Datatypes

## Introduction

Datatypes are used to specify the type of data that a column can store in a table.

Choosing the correct datatype helps in:

- Efficient storage of data
- Data validation
- Better performance
- Maintaining data integrity

---

## Types of Datatypes in Oracle SQL

Oracle SQL mainly provides:

1. Numeric Datatypes
2. Character (Alphanumeric) Datatypes
3. Date Datatype

---

# 1. Numeric Datatypes

## INT

- Size: 4 Bytes
- Accepts only integer values.
- Does not accept decimal values.

### Syntax

```sql
column_name INT;
```

### Example

```sql
age INT;
```

### Valid Values

```text
18
25
100
```

### Invalid Values

```text
18.5
25.75
```

---

## NUMBER

- Size: Up to 21 Bytes
- Accepts:

  - Integers
  - Decimal numbers
  - Positive values
  - Negative values

### Syntax

```sql
column_name NUMBER;
```

### Example

```sql
salary NUMBER;
```

---

## NUMBER(P,S)

Where:

- P → Precision
  - Total number of digits.

- S → Scale
  - Number of digits after decimal point.

### Syntax

```sql
percentage NUMBER(4,2);
```

### Examples

| Value | Result |
|------|-------|
| 8 | Valid |
| 73.69 | Valid |
| 61.3 | Valid |
| 61.3267 | Invalid |
| 564 | Invalid |
| 100 | Invalid |

---

# 2. Character Datatypes

Oracle provides two important character datatypes:

1. CHAR(size)
2. VARCHAR2(size)

---

## CHAR(size)

### Features

- Accepts:

  - Alphabets
  - Numbers
  - Special characters

- Fixed length datatype.
- Static in nature.
- Maximum size: 2000 characters.

### Syntax

```sql
column_name CHAR(size);
```

### Example

```sql
name CHAR(10);
```

If we store:

```text
Sachin
```

The remaining memory is reserved and unused.

Hence:

- Memory may be wasted.
- Fixed storage is allocated.

---

## VARCHAR2(size)

### Features

- Accepts:

  - Alphabets
  - Numbers
  - Special characters

- Variable length datatype.
- Dynamic in nature.
- Maximum size: 4000 characters.

### Syntax

```sql
column_name VARCHAR2(size);
```

### Example

```sql
name VARCHAR2(10);
```

If we store:

```text
Sachin
```

Only the required memory is allocated.

Hence:

- Memory is not wasted.
- Better storage utilization.

---

## CHAR vs VARCHAR2

| CHAR | VARCHAR2 |
|------|-----------|
| Fixed Length | Variable Length |
| Static | Dynamic |
| Wastes Memory | Efficient Memory Usage |
| Maximum 2000 Characters | Maximum 4000 Characters |

---

# 3. DATE Datatype

The DATE datatype is used to store:

- Date
- Month
- Year

---

## Oracle Date Format

```text
DD-MM-YYYY
```

### Example

```text
29-May-2000
```

---

## MySQL Date Format

```text
YYYY-MM-DD
```

### Example

```text
2000-05-29
```

---

## Summary Table

| Datatype | Description |
|---------|-------------|
| INT | Stores Integer Values |
| NUMBER | Stores Integers and Decimal Values |
| NUMBER(P,S) | Stores Numbers with Precision and Scale |
| CHAR | Fixed Length Character Data |
| VARCHAR2 | Variable Length Character Data |
| DATE | Stores Date Values |

---

## Repository Goal 

This file provides complete Oracle SQL Datatypes notes including Numeric, Character, and Date datatypes with syntax, examples, differences, and interview-oriented explanations for beginners and SQL learners.

Happy Learning and Keep Practicing SQL!
