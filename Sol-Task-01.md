Here is the **complete solution** for the Basic MySQL Practical Task.

## Solution

### Question 1 — Create Database

```sql
-- Create database
CREATE DATABASE student_db;

-- Select database
USE student_db;
```

---

### Question 2 — Create Table

```sql
CREATE TABLE students (
    student_id INT,
    name VARCHAR(50),
    age INT,
    course VARCHAR(50),
    city VARCHAR(50),
    fees DECIMAL(10,2)
);
```

---

### Question 3 — Insert Multiple Records

```sql
INSERT INTO students
(student_id, name, age, course, city, fees)
VALUES
(1, 'Aman', 20, 'Python', 'Ludhiana', 12000.00),
(2, 'Simran', 21, 'Web Design', 'Chandigarh', 15000.00),
(3, 'Rahul', 22, 'Data Science', 'Delhi', 25000.00),
(4, 'Neha', 20, 'Digital Marketing', 'Amritsar', 18000.00),
(5, 'Karan', 23, 'Python', 'Ludhiana', 14000.00),
(6, 'Priya', 21, 'Web Development', 'Jalandhar', 20000.00);
```

---

### Question 4 — Display All Records

```sql
SELECT * FROM students;
```

### Expected Output

```text
+------------+--------+-----+------------------+------------+----------+
| student_id | name   | age | course           | city       | fees     |
+------------+--------+-----+------------------+------------+----------+
| 1          | Aman   | 20  | Python           | Ludhiana   | 12000.00 |
| 2          | Simran | 21  | Web Design       | Chandigarh | 15000.00 |
| 3          | Rahul  | 22  | Data Science     | Delhi      | 25000.00 |
| 4          | Neha   | 20  | Digital Marketing| Amritsar   | 18000.00 |
| 5          | Karan  | 23  | Python           | Ludhiana   | 14000.00 |
| 6          | Priya  | 21  | Web Development  | Jalandhar  | 20000.00 |
+------------+--------+-----+------------------+------------+----------+
```

## Complete SQL Solution

You can also run everything together:

```sql
-- =========================================
-- STUDENT DATABASE PRACTICAL
-- =========================================

-- Q1: Create Database
CREATE DATABASE student_db;

USE student_db;


-- Q2: Create Table
CREATE TABLE students (
    student_id INT,
    name VARCHAR(50),
    age INT,
    course VARCHAR(50),
    city VARCHAR(50),
    fees DECIMAL(10,2)
);


-- Q3: Insert Records
INSERT INTO students
(student_id, name, age, course, city, fees)
VALUES
(1, 'Aman', 20, 'Python', 'Ludhiana', 12000.00),
(2, 'Simran', 21, 'Web Design', 'Chandigarh', 15000.00),
(3, 'Rahul', 22, 'Data Science', 'Delhi', 25000.00),
(4, 'Neha', 20, 'Digital Marketing', 'Amritsar', 18000.00),
(5, 'Karan', 23, 'Python', 'Ludhiana', 14000.00),
(6, 'Priya', 21, 'Web Development', 'Jalandhar', 20000.00);


-- Q4: Display All Records
SELECT * FROM students;
```

**Small improvement for students:** You could also make `student_id` a `PRIMARY KEY`, which prevents duplicate student IDs:

```sql
student_id INT PRIMARY KEY
```

For a **basic practical**, however, the original table definition is perfectly fine.
