Absolutely. Below is the **complete solution** for the Employee Management System using Python + MySQL.

## 1. Create Database and Table

Run this SQL in MySQL/phpMyAdmin first:

```sql
CREATE DATABASE company_db;

USE company_db;

CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    department VARCHAR(30),
    salary DECIMAL(10,2),
    city VARCHAR(30)
);
```

---

# 2. Python Program — Complete Solution

Make sure `mysql-connector-python` is installed.

```python
import mysql.connector

# Connect to MySQL
connection = mysql.connector.connect(
    host="localhost",
    user="root",
    password="",
    database="company_db"
)

cursor = connection.cursor()

# ==========================================
# TASK 1: INSERT EMPLOYEE RECORDS
# ==========================================

insert_query = """
INSERT INTO employees (id, name, department, salary, city)
VALUES (%s, %s, %s, %s, %s)
"""

employees = [
    (1, "Rahul", "IT", 45000, "Ludhiana"),
    (2, "Simran", "HR", 38000, "Chandigarh"),
    (3, "Aman", "IT", 52000, "Delhi"),
    (4, "Neha", "Sales", 42000, "Amritsar"),
    (5, "Karan", "IT", 60000, "Ludhiana"),
    (6, "Priya", "HR", 40000, "Delhi")
]

cursor.executemany(insert_query, employees)

connection.commit()

print("Employee records inserted successfully.")


# ==========================================
# TASK 2: SELECT ALL EMPLOYEES
# ==========================================

print("\n--- All Employees ---")

select_query = "SELECT * FROM employees"

cursor.execute(select_query)

records = cursor.fetchall()

for employee in records:
    print(employee)


# ==========================================
# TASK 3(a): IT DEPARTMENT EMPLOYEES
# ==========================================

print("\n--- IT Department Employees ---")

query = """
SELECT *
FROM employees
WHERE department = 'IT'
"""

cursor.execute(query)

records = cursor.fetchall()

for employee in records:
    print(employee)


# ==========================================
# TASK 3(b): SALARY GREATER THAN 45000
# ==========================================

print("\n--- Employees with Salary Greater Than 45000 ---")

query = """
SELECT *
FROM employees
WHERE salary > 45000
"""

cursor.execute(query)

records = cursor.fetchall()

for employee in records:
    print(employee)


# ==========================================
# TASK 3(c): EMPLOYEES FROM LUDHIANA
# ==========================================

print("\n--- Employees from Ludhiana ---")

query = """
SELECT *
FROM employees
WHERE city = 'Ludhiana'
"""

cursor.execute(query)

records = cursor.fetchall()

for employee in records:
    print(employee)


# ==========================================
# TASK 4(a): SALARY LOW TO HIGH
# ==========================================

print("\n--- Employees: Salary Low to High ---")

query = """
SELECT *
FROM employees
ORDER BY salary ASC
"""

cursor.execute(query)

records = cursor.fetchall()

for employee in records:
    print(employee)


# ==========================================
# TASK 4(b): SALARY HIGH TO LOW
# ==========================================

print("\n--- Employees: Salary High to Low ---")

query = """
SELECT *
FROM employees
ORDER BY salary DESC
"""

cursor.execute(query)

records = cursor.fetchall()

for employee in records:
    print(employee)


# ==========================================
# TASK 5: IT + SALARY > 45000 + ORDER BY
# ==========================================

print("\n--- IT Employees with Salary > 45000 ---")

query = """
SELECT *
FROM employees
WHERE department = 'IT'
AND salary > 45000
ORDER BY salary DESC
"""

cursor.execute(query)

records = cursor.fetchall()

for employee in records:
    print(employee)


# ==========================================
# CLOSE CONNECTION
# ==========================================

cursor.close()
connection.close()

print("\nMySQL connection closed.")
```

## Important SQL Concepts Used

### `INSERT`

Used to add records:

```sql
INSERT INTO employees
(id, name, department, salary, city)
VALUES (...);
```

In Python, we use:

```python
cursor.executemany(insert_query, employees)
```

`executemany()` is useful when inserting **multiple records**.

---

### `SELECT`

Retrieves data:

```sql
SELECT * FROM employees;
```

Python:

```python
cursor.execute(query)
records = cursor.fetchall()
```

---

### `WHERE`

Filters records:

```sql
SELECT *
FROM employees
WHERE department = 'IT';
```

Only employees from the IT department are returned.

---

### `ORDER BY`

Sorts records.

Lowest salary first:

```sql
ORDER BY salary ASC;
```

Highest salary first:

```sql
ORDER BY salary DESC;
```

---

### Combined Query

The most important query in this task is:

```sql
SELECT *
FROM employees
WHERE department = 'IT'
AND salary > 45000
ORDER BY salary DESC;
```

It means:

**Select → filter IT → filter salary > 45000 → sort highest salary first.**

### Expected result for the combined query

```text
(5, 'Karan', 'IT', 60000.00, 'Ludhiana')
(3, 'Aman', 'IT', 52000.00, 'Delhi')
```

**Note:** If you run the complete program multiple times, you'll get a **Duplicate entry for primary key** error because IDs 1–6 already exist. In that case, either clear the table first:

```sql
TRUNCATE TABLE employees;
```

and then run the Python program again.
