# ER SCHEMA

## Definition

**ER Schema (Entity Relationship Schema)** is the structured representation of an **ER Diagram**.

It shows:

* Entities
* Attributes
* Relationships
* Cardinality Ratios
* Primary Keys and Foreign Keys

ER Schema is used to design the database before creating tables.

---

# Components of ER Schema

| Component              | Representation     |
| ---------------------- | ------------------ |
| Entity                 | Rectangle          |
| Attribute              | Ellipse            |
| Key Attribute          | Underlined Ellipse |
| Relationship           | Diamond            |
| Weak Entity            | Double Rectangle   |
| Multi-valued Attribute | Double Ellipse     |
| Derived Attribute      | Dotted Ellipse     |

---

# Example 1: Student ER Schema

### Description

A Student has:

* Student_ID (Primary Key)
* Name
* Age
* Phone Number

### ER Schema Diagram

```text
                  ((PHONE_NO))
                         |
                       (AGE)
                         |
                     __STUDENT_ID__
                           |
                        (NAME)
                           |
                 +----------------+
                 |    STUDENT     |
                 +----------------+
```

**Note:**

* `STUDENT_ID` → Key Attribute
* `PHONE_NO` → Multi-valued Attribute
* `AGE` → Simple Attribute

---

# Example 2: Student and Course ER Schema

### Description

* One Student can enroll in many Courses.
* One Course can have many Students.
* Relationship: ENROLLS
* Cardinality: Many-to-Many (M:M)

### ER Schema Diagram

```text
              +-------------+
              |  STUDENT    |
              +-------------+
                     |
                     | M
               ◇ ENROLLS ◇
                     | M
              +-------------+
              |   COURSE    |
              +-------------+
```

---

# Example 3: Employee and Department ER Schema

### Description

* One Department has many Employees.
* One Employee belongs to one Department.
* Cardinality: One-to-Many (1:M)

### ER Schema Diagram

```text
        1
+---------------+
| DEPARTMENT    |
+---------------+
        |
        | HAS
        |
        M
+---------------+
| EMPLOYEE      |
+---------------+
```

---

# Example 4: Employee and Passport ER Schema

### Description

* One Employee has one Passport.
* One Passport belongs to one Employee.
* Cardinality: One-to-One (1:1)

### ER Schema Diagram

```text
        1
+---------------+
| EMPLOYEE      |
+---------------+
        |
      HAS
        |
        1
+---------------+
| PASSPORT      |
+---------------+
```

---

# Example 5: University Database ER Schema

### Entities

1. STUDENT
2. COURSE
3. PROFESSOR

### Relationships

* STUDENT enrolls in COURSE → Many-to-Many
* PROFESSOR teaches COURSE → One-to-One

### Complete ER Schema

```text

                     ((PHONE_NO))
                           |
                      . . . . .
                     ( AGE )
                      . . . . .
                           |
                     __STUDENT_ID__
                           |
                    +-------------+
                    |   STUDENT   |
                    +-------------+
                           |
                    M      ◇ ENROLLS ◇      M
                           |
                    +-------------+
                    |   COURSE    |
                    +-------------+
                     |      |
             __COURSE_ID__  (COURSE_NAME)
                     |
                     1
                ◇ TEACHES ◇
                     1
                     |
             +---------------+
             |  PROFESSOR    |
             +---------------+
                     |
            __PROFESSOR_ID__
                     |
                 (SALARY)

```

---

# Cardinality Symbols

| Symbol | Meaning      |
| ------ | ------------ |
| 1 : 1  | One-to-One   |
| 1 : M  | One-to-Many  |
| M : 1  | Many-to-One  |
| M : M  | Many-to-Many |

---

# Difference Between ER Diagram and ER Schema

| ER Diagram                      | ER Schema                                          |
| ------------------------------- | -------------------------------------------------- |
| Graphical representation        | Structural representation                          |
| Focuses on visualization        | Focuses on database design                         |
| Uses entities and relationships | Uses entities, keys, attributes, and relationships |
| Used during analysis            | Used before table creation                         |

---

# Summary

| Topic        | Description                             |
| ------------ | --------------------------------------- |
| ER Diagram   | Visual representation of database       |
| ER Schema    | Structured representation of ER Diagram |
| Entity       | Real-world object                       |
| Attribute    | Property of entity                      |
| Relationship | Association between entities            |
| Cardinality  | Number of participating entities        |
