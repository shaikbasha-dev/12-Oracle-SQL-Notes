# TRANSACTION CONTROL LANGUAGE (TCL)

## Definition

* TCL stands for **Transaction Control Language**.
* TCL commands are used to control transactions such as:

  * Insertion
  * Updation
  * Deletion
* TCL commands are generally used along with DML commands.
* DML operations become permanent only after using the **COMMIT** command.

---

## TCL Commands

| S.No | Command   | Purpose                        |
| ---- | --------- | ------------------------------ |
| 1    | COMMIT    | Saves changes permanently      |
| 2    | ROLLBACK  | Undoes uncommitted changes     |
| 3    | SAVEPOINT | Creates a temporary checkpoint |

---

# 1. COMMIT

## Definition

The **COMMIT** command is used to save all DML changes permanently in the database.

### Syntax

```sql id="c1"
COMMIT;
```

### Output

| Result                |
| --------------------- |
| Transaction Committed |

---

# 2. ROLLBACK

## Definition

The **ROLLBACK** command is used to undo DML operations that have not been permanently saved.

### Syntax

```sql id="r1"
ROLLBACK;
```

### Output

| Result                  |
| ----------------------- |
| Transaction Rolled Back |

---

### Rollback to Savepoint

#### Syntax

```sql id="r2"
ROLLBACK TO savepoint_name;
```

### Example

```sql id="r3"
ROLLBACK TO x;
```

### Output

| Result                     |
| -------------------------- |
| Rolled Back To Savepoint X |

---

# 3. SAVEPOINT

## Definition

The **SAVEPOINT** command creates a temporary checkpoint inside a transaction.

It allows rolling back only a portion of the transaction instead of the entire transaction.

---

### Syntax

```sql id="s1"
SAVEPOINT savepoint_name;
```

### Example

```sql id="s2"
SAVEPOINT x;
```

### Output

| Result            |
| ----------------- |
| Savepoint Created |

---

# Complete Example

### Question

Demonstrate COMMIT, SAVEPOINT, and ROLLBACK.

### Query

```sql id="ex1"
INSERT INTO demo1 VALUES(1,'A',22);

INSERT INTO demo1 VALUES(2,'B',23);

INSERT INTO demo1 VALUES(3,'C',23);

COMMIT;

INSERT INTO demo1 VALUES(4,'D',24);

SAVEPOINT x;

INSERT INTO demo1 VALUES(5,'P',25);

ROLLBACK TO x;

ROLLBACK;
```

### Explanation

| Step | Action                        |
| ---- | ----------------------------- |
| 1    | Insert rows 1, 2, 3           |
| 2    | Commit changes                |
| 3    | Insert row 4                  |
| 4    | Create savepoint X            |
| 5    | Insert row 5                  |
| 6    | Rollback to X (removes row 5) |
| 7    | Rollback (removes row 4)      |

---

### Final Data

| ID | NAME | AGE |
| -- | ---- | --: |
| 1  | A    |  22 |
| 2  | B    |  23 |
| 3  | C    |  23 |

---

# TCL Flow Diagram

```text id="flow"
INSERT/UPDATE/DELETE
        ↓
    SAVEPOINT
        ↓
     COMMIT
        ↓
  Permanent Save

OR

INSERT/UPDATE/DELETE
        ↓
    SAVEPOINT
        ↓
ROLLBACK TO SAVEPOINT
        ↓
    ROLLBACK
```

---

# TCL Summary

| Command   | Description                           |
| --------- | ------------------------------------- |
| COMMIT    | Saves DML changes permanently         |
| ROLLBACK  | Undoes uncommitted changes            |
| SAVEPOINT | Creates a checkpoint in a transaction |
