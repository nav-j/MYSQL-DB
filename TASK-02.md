Sure. Here is a **beginner-to-intermediate Python + MySQL practical task** focusing specifically on `INSERT`, `SELECT`, `WHERE`, and `ORDER BY`.

## Python + MySQL Practical Task

### Topic: Employee Management System

Create a Python program that connects to a MySQL database and manages employee records.

### Database

Create a database named:

```sql
company_db
```

Create a table named `employees` with:

| Column     | Data Type       |
| ---------- | --------------- |
| id         | INT PRIMARY KEY |
| name       | VARCHAR(50)     |
| department | VARCHAR(30)     |
| salary     | DECIMAL(10,2)   |
| city       | VARCHAR(30)     |

---

### Task 1 — Insert Records

Using Python and `mysql.connector`, insert **at least 6 employees** into the `employees` table.

Example data:

```text
1, Rahul, IT, 45000, Ludhiana
2, Simran, HR, 38000, Chandigarh
3, Aman, IT, 52000, Delhi
4, Neha, Sales, 42000, Amritsar
5, Karan, IT, 60000, Ludhiana
6, Priya, HR, 40000, Delhi
```

Use an SQL `INSERT INTO` query.

---

### Task 2 — Display All Employees

Write a Python program to retrieve and display **all employee records** using:

```sql
SELECT * FROM employees;
```

Display the output in a readable format.

---

### Task 3 — Use WHERE

Write Python queries for the following:

**a.** Display employees who work in the **IT department**.

```sql
WHERE department = 'IT'
```

**b.** Display employees whose salary is **greater than ₹45,000**.

**c.** Display employees who live in **Ludhiana**.

---

### Task 4 — Use ORDER BY

Write Python queries for:

**a.** Display all employees sorted by salary from **lowest to highest**.

```sql
ORDER BY salary ASC
```

**b.** Display all employees sorted by salary from **highest to lowest**.

```sql
ORDER BY salary DESC
```

---

### Task 5 — Combined Query

Write a Python program to display **IT employees whose salary is greater than ₹45,000**, sorted by salary from highest to lowest.

Expected SQL structure:

```sql
SELECT *
FROM employees
WHERE department = 'IT'
AND salary > 45000
ORDER BY salary DESC;
```

### Requirements

Your Python program should:

1. Import `mysql.connector`
2. Connect to MySQL
3. Execute SQL queries using `cursor.execute()`
4. Use `INSERT`, `SELECT`, `WHERE`, and `ORDER BY`
5. Use `fetchall()` to retrieve records
6. Display results using a `for` loop
7. Commit inserted data using `connection.commit()`
8. Close the cursor and database connection at the end.
