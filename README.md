# Structure-quarry-language-
It seems like you are referring to **Structured Query Language (SQL)**, a programming language used for managing and manipulating databases. If this is correct, here’s an overview of SQL:

### What is SQL?

**Structured Query Language (SQL)** is a domain-specific language used in programming for interacting with relational databases. It enables users to create, read, update, and delete (CRUD) data stored in a database. SQL is essential for database management and is supported by most relational database management systems (RDBMS), such as MySQL, PostgreSQL, Oracle Database, and Microsoft SQL Server.

### Key Features of SQL:
1. **Data Manipulation**: Insert, update, delete, and query data.
2. **Data Definition**: Define and modify the database schema, including creating tables and indexes.
3. **Data Control**: Control access to the data using permissions and roles.
4. **Transactions**: Ensure data integrity through transactional support (e.g., COMMIT, ROLLBACK).

### Basic SQL Commands
SQL commands are broadly categorized as:
1. **DDL (Data Definition Language)**:
   - `CREATE`: Creates a new table or database.
   - `ALTER`: Modifies an existing database object.
   - `DROP`: Deletes tables or databases.

2. **DML (Data Manipulation Language)**:
   - `INSERT`: Adds new rows of data.
   - `UPDATE`: Modifies existing data.
   - `DELETE`: Removes data.

3. **DQL (Data Query Language)**:
   - `SELECT`: Retrieves data from the database.

4. **DCL (Data Control Language)**:
   - `GRANT`: Gives permissions to users.
   - `REVOKE`: Removes permissions.

5. **TCL (Transaction Control Language)**:
   - `COMMIT`: Saves the current transaction.
   - `ROLLBACK`: Reverts changes made by the current transaction.
   - `SAVEPOINT`: Creates a point in a transaction to which you can roll back.

### Example Query
Here’s a basic example of an SQL query:
```sql
SELECT first_name, last_name
FROM employees
WHERE department = 'Sales'
ORDER BY last_name ASC;
```

Here are some **important and commonly used SQL examples** that demonstrate different aspects of database management and querying:

---

### 1. **Create a Table**
```sql
CREATE TABLE employees (
    id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    department VARCHAR(50),
    salary DECIMAL(10, 2),
    hire_date DATE
);
```
This creates an `employees` table with columns for employee details.

---

### 2. **Insert Data into a Table**
```sql
INSERT INTO employees (id, first_name, last_name, department, salary, hire_date)
VALUES (1, 'John', 'Doe', 'Sales', 60000.00, '2022-01-15');
```
This adds a new employee record to the `employees` table.

---

### 3. **Retrieve Data (SELECT)**
#### a. Select All Columns
```sql
SELECT * FROM employees;
```
Retrieve all rows and columns from the `employees` table.

#### b. Select Specific Columns
```sql
SELECT first_name, last_name, salary
FROM employees
WHERE department = 'Sales';
```
Get the names and salary of employees in the "Sales" department.

#### c. Use Aggregate Functions
```sql
SELECT AVG(salary) AS average_salary, MAX(salary) AS highest_salary
FROM employees;
```
Calculate the average and highest salary in the `employees` table.

---

### 4. **Update Data**
```sql
UPDATE employees
SET salary = 65000.00
WHERE id = 1;
```
Update the salary of the employee with `id = 1`.

---

### 5. **Delete Data**
```sql
DELETE FROM employees
WHERE department = 'Sales';
```
Delete all employees in the "Sales" department.

---

### 6. **Filtering with WHERE Clause**
```sql
SELECT first_name, last_name
FROM employees
WHERE salary > 50000 AND department = 'Marketing';
```
Get the names of employees in the "Marketing" department with a salary greater than 50,000.

---

### 7. **Sorting Results**
```sql
SELECT first_name, last_name, salary
FROM employees
ORDER BY salary DESC;
```
Retrieve employee details and sort them by salary in descending order.

---

### 8. **Joins**
#### a. Inner Join
```sql
SELECT e.first_name, e.last_name, d.department_name
FROM employees e
INNER JOIN departments d
ON e.department = d.department_id;
```
Join the `employees` table with a `departments` table to get employee names and their department names.

#### b. Left Join
```sql
SELECT e.first_name, d.department_name
FROM employees e
LEFT JOIN departments d
ON e.department = d.department_id;
```
Retrieve all employees and their department names, even if some employees are not assigned to a department.

---

### 9. **Group By and Having**
```sql
SELECT department, COUNT(*) AS employee_count
FROM employees
GROUP BY department
HAVING COUNT(*) > 5;
```
Get the count of employees in each department, showing only departments with more than 5 employees.

---

### 10. **Create a View**
```sql
CREATE VIEW high_earning_employees AS
SELECT first_name, last_name, salary
FROM employees
WHERE salary > 80000;
```
Create a view to display employees earning more than 80,000.

---

### 11. **Transactions**
```sql
BEGIN TRANSACTION;

UPDATE employees SET salary = salary * 1.10 WHERE department = 'IT';

ROLLBACK; -- Undo the changes
-- OR
COMMIT; -- Save the changes
```
Perform a batch operation with the option to either save (`COMMIT`) or undo (`ROLLBACK`) changes.

---

### 12. **Subqueries**
```sql
SELECT first_name, last_name
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
Find employees whose salary is above the average salary.

---

These examples cover basic and advanced SQL usage. Let me know if you need clarification or more specific examples! 😊
