## Basic MySQL Practical Task

### Task

Create a MySQL database named **`student_db`** and perform the following operations.

### Question 1 — Create Database (3 Marks)

Create a database named:

```sql
student_db
```

Select the database for use.

---

### Question 2 — Create Table (5 Marks)

Inside `student_db`, create a table named **`students`** with the following columns:

| Column     | Data Type     | 
| ---------- | ------------- |  
| student_id | INT           |  
| name       | VARCHAR(50)   |     
| age        | INT           |             
| course     | VARCHAR(50)   |             
| city       | VARCHAR(50)   |             
| fees       | DECIMAL(10,2) |             

---

### Question 3 — Insert Multiple Records (7 Marks)

Insert **at least 5 students** into the `students` table.

Use different values for:

* Student ID
* Name
* Age
* Course
* City
* Fees

---

### Question 4 — Display Records (3 Marks)

Write a query to display **all records** from the `students` table.

Expected format:

```text
student_id | name       | age | course       | city       | fees
----------------------------------------------------------------
1          | Aman       | 20  | Python       | Ludhiana   | 12000
2          | Simran     | 21  | Web Design   | Chandigarh | 15000
...
```
