# ER DIAGRAM - CASE STUDY

## Steps to Draw an ER Diagram

Follow these steps while designing an ER Diagram:

| Step | Description                    |
| ---- | ------------------------------ |
| 1    | Identify the Entities          |
| 2    | Identify the Attributes        |
| 3    | Identify the Relationships     |
| 4    | Identify the Cardinality Ratio |

---

# Case Study

## SRS (Software Requirement Specification) of University Database

### Problem Statement

In a University:

* Students enroll into Courses.
* A Student may enroll in one or more Courses.
* Each Course is taught by a single Professor.
* A Professor can teach only one Course.

---

# Step 1: Identify Entities

The entities are:

| Entity    |
| --------- |
| STUDENT   |
| COURSE    |
| PROFESSOR |

---

# Step 2: Identify Attributes

## STUDENT

| Attribute Type         | Attribute    |
| ---------------------- | ------------ |
| Key Attribute          | Student_ID   |
| Simple Attribute       | Age          |
| Composite Attribute    | Name         |
| Derived Attribute      | Age from DOB |
| Multi-valued Attribute | Phone_Number |

### Text Diagram

```text id="stu"
                     (FIRST)
                         |
                   ( NAME )
                  /        \
            (MIDDLE)      (LAST)


                ((PHONE_NO))
                       |
                    . . . .
                   ( AGE )
                    . . . .
                       |
                     (DOB)

                       |
                  (STUDENT_ID)
                       |
               +----------------+
               |    STUDENT     |
               +----------------+
```

---

## COURSE

| Attribute   | Description     |
| ----------- | --------------- |
| Course_ID   | Primary Key     |
| Course_Name | Course Name     |
| Duration    | Course Duration |

### Diagram

```text id="course"
          (COURSE_ID)
                |
          (COURSE_NAME)
                |
           (DURATION)

                |
       +----------------+
       |    COURSE      |
       +----------------+
```

---

## PROFESSOR

| Attribute      | Description |
| -------------- | ----------- |
| Professor_ID   | Primary Key |
| Professor_Name | Name        |
| Salary         | Salary      |

### Diagram

```text id="prof"
        (PROFESSOR_ID)
                |
       (PROFESSOR_NAME)
                |
            (SALARY)

                |
      +----------------+
      |   PROFESSOR    |
      +----------------+
```

---

# Step 3: Identify Relationships

---

## STUDENT and COURSE

### Relationship: ENROLLS

### Cardinality: Many-to-Many (M:M)

```text id="rel1"
+------------+      ◇ ENROLLS ◇      +------------+
|  STUDENT   |-------- M : M --------|   COURSE   |
+------------+                       +------------+
```

Meaning:

* One Student can enroll in many Courses.
* One Course can have many Students.

---

## COURSE and PROFESSOR

### Relationship: TEACHES

### Cardinality: One-to-One (1:1)

```text id="rel2"
+------------+      ◇ TEACHES ◇      +--------------+
|   COURSE   |---------1 : 1---------|  PROFESSOR   |
+------------+                       +--------------+
```

Meaning:

* One Course is taught by one Professor.
* One Professor teaches only one Course.

---

# Complete University ER Diagram

```text id="full"

                     ((PHONE_NO))
                           |
                      . . . . .
                     ( AGE )
                      . . . . .
                           |
                         (DOB)

                           |
                    (STUDENT_ID)
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
            (COURSE_ID)  (COURSE_NAME)
                     |
                     1
                ◇ TEACHES ◇
                     1
                     |
             +---------------+
             |  PROFESSOR    |
             +---------------+
                     |
             (PROFESSOR_ID)
                     |
               (SALARY)

```

---

# Cardinality Summary

| Relationship          | Cardinality        |
| --------------------- | ------------------ |
| Student - Course      | Many-to-Many (M:M) |
| Course - Professor    | One-to-One (1:1)   |
| Department - Employee | One-to-Many (1:M)  |
| Employee - Department | Many-to-One (M:1)  |

---

# Important Symbols in ER Diagram

| Symbol           | Meaning                |
| ---------------- | ---------------------- |
| Rectangle        | Entity                 |
| Double Rectangle | Weak Entity            |
| Ellipse          | Attribute              |
| Double Ellipse   | Multi-valued Attribute |
| Dotted Ellipse   | Derived Attribute      |
| Diamond          | Relationship           |
| 1:1              | One-to-One             |
| 1:M              | One-to-Many            |
| M:1              | Many-to-One            |
| M:M              | Many-to-Many           |
