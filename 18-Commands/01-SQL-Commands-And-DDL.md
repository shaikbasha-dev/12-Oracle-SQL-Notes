# COMMANDS
# SQL COMMANDS

## Definition

SQL commands are instructions used to communicate with the database to perform different operations such as creating tables, inserting data, retrieving data, controlling access, and managing transactions.

---

## Types of SQL Commands

| S.No | Command Type                       | Commands                      |
| ---- | ---------------------------------- | ----------------------------- |
| 1    | Data Definition Language (DDL)     | CREATE, ALTER, TRUNCATE, DROP |
| 2    | Data Manipulation Language (DML)   | INSERT, UPDATE, DELETE        |
| 3    | Data Query Language (DQL)          | SELECT                        |
| 4    | Data Control Language (DCL)        | GRANT, REVOKE                 |
| 5    | Transaction Control Language (TCL) | SAVEPOINT, COMMIT, ROLLBACK   |

---

# CRUD Operations

## Definition

CRUD stands for:

| Operation | Meaning |
| --------- | ------- |
| C         | Create  |
| R         | Read    |
| U         | Update  |
| D         | Delete  |

---

# DATA DEFINITION LANGUAGE (DDL)

## Definition

* DDL commands are used to define the structure of database objects.
* These commands affect the schema of the database.

### DDL Commands

| Command  | Purpose                            |
| -------- | ---------------------------------- |
| CREATE   | Creates database objects           |
| ALTER    | Modifies existing database objects |
| TRUNCATE | Removes all rows from a table      |
| DROP     | Deletes database objects           |

---

# 1. CREATE

## Definition

The CREATE command is used to create databases, tables, and other database objects.

### Syntax

```sql
CREATE TABLE table_name
(
    column_name1 datatype,
    column_name2 datatype,
    column_name3 datatype
);
```

### Example

#### Question

Create a table named `Bank`.

#### Query

```sql
CREATE TABLE Bank
(
    bid INT,
    bname VARCHAR2(10),
    bhq VARCHAR2(12)
);
```

### Output

| Result        |
| ------------- |
| Table Created |

---

# 2. ALTER

## Definition

The ALTER command is used to modify the structure of an existing table.

---

## A. Adding a Column

### Syntax

```sql
ALTER TABLE table_name
ADD column_name datatype;
```

### Example

#### Question

Add phone number column to Bank table.

#### Query

```sql
ALTER TABLE Bank
ADD ph_no NUMBER;
```

### Output

| Result        |
| ------------- |
| Table Altered |

---

## B. Dropping a Column

### Syntax

```sql
ALTER TABLE table_name
DROP COLUMN column_name;
```

### Example

#### Query

```sql
ALTER TABLE Bank
DROP COLUMN ph_no;
```

### Output

| Result         |
| -------------- |
| Column Dropped |

---

## C. Renaming a Column

### Syntax

```sql
ALTER TABLE table_name
RENAME COLUMN old_column_name
TO new_column_name;
```

### Example

#### Query

```sql
ALTER TABLE Bank
RENAME COLUMN bname
TO bankname;
```

### Output

| Result         |
| -------------- |
| Column Renamed |

---

## D. Renaming a Table

### Syntax

```sql
ALTER TABLE table_name
RENAME TO new_table_name;
```

### Example

#### Query

```sql
ALTER TABLE Bank
RENAME TO Bank_Details;
```

### Output

| Result        |
| ------------- |
| Table Renamed |

---

## E. Modify Datatype

### Syntax

```sql
ALTER TABLE table_name
MODIFY column_name datatype;
```

### Example

#### Query

```sql
ALTER TABLE Bank_Details
MODIFY bid VARCHAR2(54);
```

### Output

| Result            |
| ----------------- |
| Datatype Modified |

### Note

The column must be empty to change its datatype.

---

## F. Changing Column Size

### Syntax

```sql
ALTER TABLE table_name
MODIFY column_name datatype(size);
```

### Example

#### Query

```sql
ALTER TABLE Bank_Details
MODIFY bank_name VARCHAR2(97);
```

### Output

| Result        |
| ------------- |
| Size Modified |

---

## G. Adding Constraint

### Syntax

```sql
ALTER TABLE table_name
ADD CONSTRAINT constraint_name
PRIMARY KEY(column_name);
```

### Example

#### Query

```sql
ALTER TABLE Bank_Details
ADD CONSTRAINT b_pk
PRIMARY KEY(bid);
```

### Output

| Result           |
| ---------------- |
| Constraint Added |

---

## H. Dropping Constraint

### Syntax

```sql
ALTER TABLE table_name
DROP CONSTRAINT constraint_name;
```

### Example

#### Query

```sql
ALTER TABLE Bank_Details
DROP CONSTRAINT b_pk;
```

### Output

| Result             |
| ------------------ |
| Constraint Dropped |

---

# 3. TRUNCATE

## Definition

The TRUNCATE command removes all rows from a table at once.

### Syntax

```sql
TRUNCATE TABLE table_name;
```

### Example

#### Query

```sql
TRUNCATE TABLE Bank_Details;
```

### Output

| Result          |
| --------------- |
| Table Truncated |

---

# 4. DROP

## Definition

The DROP command is used to delete tables, databases, or database objects permanently.

### Syntax

```sql
DROP TABLE table_name;
```

### Example

#### Query

```sql
DROP TABLE Bank_Details;
```

### Output

| Result        |
| ------------- |
| Table Dropped |
