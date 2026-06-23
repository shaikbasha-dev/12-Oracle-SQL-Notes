# DATABASE OBJECTS

# 1. Stored Procedures

## Definition

* A **Stored Procedure** is a precompiled collection of SQL statements stored in the database.
* Stored Procedures can be executed repeatedly whenever required.
* They improve code reusability and performance.
* Stored Procedures must be called explicitly.

---

## Creating a Stored Procedure

### Syntax

```sql id="7a3pwj"
CREATE PROCEDURE procedure_name(parameters)
AS
BEGIN
    SQL_Query;
END;
```

---

### Example

#### Question

Create a stored procedure named **hike_sal** to increase employee salary based on department id.

### Query

```sql id="h0rfjg"
CREATE PROCEDURE hike_sal(
    sal IN NUMBER,
    did IN NUMBER
)
AS
BEGIN
    UPDATE emp1
    SET salary = salary + sal
    WHERE dept_id = did;
END;
```

### Output

| Result            |
| ----------------- |
| Procedure Created |

---

## Calling a Stored Procedure

### Syntax

```sql id="72i3x8"
BEGIN
    procedure_name(parameter_values);
END;
```

### Example

```sql id="7r8ebg"
BEGIN
    hike_sal(2000, 22);
END;
```

### Output

| Result                          |
| ------------------------------- |
| Procedure Executed Successfully |

---

## Deleting a Stored Procedure

### Syntax

```sql id="7tgm2v"
DROP PROCEDURE procedure_name;
```

### Example

```sql id="rsy2b8"
DROP PROCEDURE hike_sal;
```

### Output

| Result            |
| ----------------- |
| Procedure Dropped |

---

# 2. Triggers

## Definition

* Triggers are special types of Stored Procedures.
* They are executed automatically when a specified event occurs.
* A Trigger contains:

  * **Event**
  * **Action**

---

## Trigger Events

| Event         | Action                         |
| ------------- | ------------------------------ |
| BEFORE INSERT | Executes before inserting data |
| AFTER INSERT  | Executes after inserting data  |
| BEFORE UPDATE | Executes before updating data  |
| AFTER UPDATE  | Executes after updating data   |
| BEFORE DELETE | Executes before deleting data  |
| AFTER DELETE  | Executes after deleting data   |

---

## Creating a Trigger

### Syntax

```sql id="g3qqw2"
CREATE TRIGGER trigger_name
BEFORE INSERT
ON table_name
FOR EACH ROW
BEGIN
    SQL_Query;
END;
```

---

### Example

#### Question

Create a trigger named **dec** that inserts records into table2 whenever data is inserted into table1.

### Query

```sql id="3h8r85"
CREATE TRIGGER dec
BEFORE INSERT
ON table1
FOR EACH ROW
BEGIN
    INSERT INTO table2
    VALUES(:NEW.id, :NEW.name);
END;
```

### Output

| Result          |
| --------------- |
| Trigger Created |

---

## Example Tables

### Table1

| ID | NAME |
| -- | ---- |
| 01 | Cat  |
| 02 | Rat  |

### Table2

| ID | NAME |
| -- | ---- |
| 01 | Cat  |
| 02 | Rat  |

---

## Trigger Pseudo Records

| Operation | Keyword       |
| --------- | ------------- |
| INSERT    | :NEW          |
| UPDATE    | :NEW and :OLD |
| DELETE    | :OLD          |

---

## Deleting a Trigger

### Syntax

```sql id="xxk1bo"
DROP TRIGGER trigger_name;
```

### Example

```sql id="vm6q04"
DROP TRIGGER dec;
```

### Output

| Result          |
| --------------- |
| Trigger Dropped |

---

# Summary

| Object           | Description                      |
| ---------------- | -------------------------------- |
| Stored Procedure | Executed explicitly by calling   |
| Trigger          | Executed automatically on events |
| :NEW             | Represents new values            |
| :OLD             | Represents old values            |
