
### 1. **Retrieve all records from a table**
**Question:** Write a query to fetch all records from the `employees` table.  
```sql
SELECT * FROM employees;
```

---

### 2. **Retrieve unique values**
**Question:** Get unique job titles from the `jobs` table.  
```sql
SELECT DISTINCT job_title FROM jobs;
```

---

### 3. **Filter records using `WHERE`**
**Question:** Fetch details of employees whose salary is greater than 5000.  
```sql
SELECT * FROM employees WHERE salary > 5000;
```

---

### 4. **Using `AND` & `OR` in filtering**
**Question:** Fetch employees whose salary is greater than 5000 and department is 'HR'.  
```sql
SELECT * FROM employees WHERE salary > 5000 AND department = 'HR';
```

---

### 5. **Sort records**
**Question:** Retrieve employee names sorted by their salary in descending order.  
```sql
SELECT name FROM employees ORDER BY salary DESC;
```

---

### 6. **Aggregate using `COUNT`**
**Question:** Count the number of employees in the `employees` table.  
```sql
SELECT COUNT(*) AS employee_count FROM employees;
```

---

### 7. **Aggregate using `SUM`**
**Question:** Calculate the total salary expense for all employees.  
```sql
SELECT SUM(salary) AS total_salary FROM employees;
```

---

### 8. **Aggregate using `AVG`**
**Question:** Find the average salary of employees in the `employees` table.  
```sql
SELECT AVG(salary) AS average_salary FROM employees;
```

---

### 9. **Find maximum salary**
**Question:** Fetch the maximum salary from the `employees` table.  
```sql
SELECT MAX(salary) AS max_salary FROM employees;
```

---

### 10. **Find minimum salary**
**Question:** Retrieve the minimum salary of employees.  
```sql
SELECT MIN(salary) AS min_salary FROM employees;
```

---

### 11. **Group records using `GROUP BY`**
**Question:** Get the total salary paid to each department.  
```sql
SELECT department, SUM(salary) AS total_salary
FROM employees
GROUP BY department;
```

---

### 12. **Filter grouped results using `HAVING`**
**Question:** Get departments with a total salary expense greater than 50,000.  
```sql
SELECT department, SUM(salary) AS total_salary
FROM employees
GROUP BY department
HAVING SUM(salary) > 50000;
```

---

### 13. **Using `LIKE` for pattern matching**
**Question:** Fetch employees whose names start with 'A'.  
```sql
SELECT * FROM employees WHERE name LIKE 'A%';
```

---

### 14. **Using `IN` for multiple values**
**Question:** Retrieve employees from departments 1, 2, or 3.  
```sql
SELECT * FROM employees WHERE department_id IN (1, 2, 3);
```

---

### 15. **Using `BETWEEN`**
**Question:** Fetch employees with salaries between 4000 and 8000.  
```sql
SELECT * FROM employees WHERE salary BETWEEN 4000 AND 8000;
```

---

### 16. **Find null values**
**Question:** Fetch employees who do not have a manager assigned.  
```sql
SELECT * FROM employees WHERE manager_id IS NULL;
```

---

### 17. **Join two tables**
**Question:** Fetch employee names along with their department names.  
```sql
SELECT e.name, d.department_name
FROM employees e
JOIN departments d ON e.department_id = d.department_id;
```

---

### 18. **Left join**
**Question:** Fetch all employees and their department names, including employees without departments.  
```sql
SELECT e.name, d.department_name
FROM employees e
LEFT JOIN departments d ON e.department_id = d.department_id;
```

---

### 19. **Right join**
**Question:** Fetch all departments and their employee names, including departments without employees.  
```sql
SELECT e.name, d.department_name
FROM employees e
RIGHT JOIN departments d ON e.department_id = d.department_id;
```

---

### 20. **Full outer join**
**Question:** Fetch all employees and all departments, including unmatched records.  
```sql
SELECT e.name, d.department_name
FROM employees e
FULL OUTER JOIN departments d ON e.department_id = d.department_id;
```

---

### 21. **Self-join**
**Question:** Fetch employees along with their managers' names.  
```sql
SELECT e.name AS employee_name, m.name AS manager_name
FROM employees e
LEFT JOIN employees m ON e.manager_id = m.employee_id;
```

---

### 22. **Subquery**
**Question:** Fetch employees earning more than the average salary.  
```sql
SELECT * 
FROM employees 
WHERE salary > (SELECT AVG(salary) FROM employees);
```

---

### 23. **Exists clause**
**Question:** Fetch departments with employees.  
```sql
SELECT * 
FROM departments d
WHERE EXISTS (SELECT 1 FROM employees e WHERE e.department_id = d.department_id);
```

---

### 24. **Union of two queries**
**Question:** Combine employees and managers into one list.  
```sql
SELECT name FROM employees
UNION
SELECT name FROM managers;
```

---

### 25. **Intersection**
**Question:** Fetch names appearing in both employees and managers.  
```sql
SELECT name FROM employees
INTERSECT
SELECT name FROM managers;
```

---

### 26. **Delete a record**
**Question:** Delete employees whose department is 'Finance'.  
```sql
DELETE FROM employees WHERE department = 'Finance';
```

---

### 27. **Update a record**
**Question:** Increase the salary of all employees by 10%.  
```sql
UPDATE employees
SET salary = salary * 1.10;
```

---

### 28. **Create a new table**
**Question:** Create a `projects` table with columns for `project_id`, `name`, and `start_date`.  
```sql
CREATE TABLE projects (
    project_id INT PRIMARY KEY,
    name VARCHAR(255),
    start_date DATE
);
```

---

### 29. **Insert records**
**Question:** Insert a new employee into the `employees` table.  
```sql
INSERT INTO employees (name, salary, department_id)
VALUES ('John Doe', 6000, 2);
```

---

### 30. **Drop a table**
**Question:** Remove the `temp_data` table.  
```sql
DROP TABLE temp_data;
```

---

## 1. **Basic Queries**

### **1.1. Retrieve All Data**
**Query:**  
Fetch all records from the `employees` table.  
```sql
SELECT * FROM employees;
```
**Explanation:**  
`SELECT` is used to retrieve data. The `*` wildcard fetches all columns.

---

### **1.2. Retrieve Specific Columns**
**Query:**  
Fetch only `name` and `salary` from `employees`.  
```sql
SELECT name, salary FROM employees;
```
**Explanation:**  
Specify column names to retrieve only those columns.

---

### **1.3. Use Aliases**
**Query:**  
Fetch `name` as `Employee Name` and `salary` as `Earnings`.  
```sql
SELECT name AS "Employee Name", salary AS "Earnings" FROM employees;
```
**Explanation:**  
Aliases rename columns for better readability in the output.

---

## 2. **Filtering Data**

### **2.1. Using `WHERE`**
**Query:**  
Fetch employees with salaries greater than 5000.  
```sql
SELECT * FROM employees WHERE salary > 5000;
```
**Explanation:**  
The `WHERE` clause filters rows based on a condition.

---

### **2.2. Using `AND` & `OR`**
**Query:**  
Fetch employees from the `HR` department earning more than 6000.  
```sql
SELECT * FROM employees WHERE department = 'HR' AND salary > 6000;
```
**Explanation:**  
`AND` combines conditions that must all be true; `OR` is used for alternative conditions.

---

### **2.3. Using `LIKE`**
**Query:**  
Find employees whose names start with "A".  
```sql
SELECT * FROM employees WHERE name LIKE 'A%';
```
**Explanation:**  
`LIKE` is used for pattern matching. `%` matches any number of characters.

---

### **2.4. Using `IN`**
**Query:**  
Fetch employees from departments 1, 2, or 3.  
```sql
SELECT * FROM employees WHERE department_id IN (1, 2, 3);
```
**Explanation:**  
`IN` is used to match values in a list.

---

### **2.5. Using `BETWEEN`**
**Query:**  
Find employees with salaries between 4000 and 8000.  
```sql
SELECT * FROM employees WHERE salary BETWEEN 4000 AND 8000;
```
**Explanation:**  
`BETWEEN` checks if a value lies within a range (inclusive).

---

## 3. **Sorting Results**

### **3.1. Using `ORDER BY`**
**Query:**  
List employees sorted by salary in descending order.  
```sql
SELECT name, salary FROM employees ORDER BY salary DESC;
```
**Explanation:**  
`ORDER BY` sorts results in ascending (`ASC`) or descending (`DESC`) order.

---

## 4. **Aggregate Functions**

### **4.1. Using `COUNT`**
**Query:**  
Count the number of employees.  
```sql
SELECT COUNT(*) AS employee_count FROM employees;
```
**Explanation:**  
`COUNT` counts rows in a table.

---

### **4.2. Using `SUM`**
**Query:**  
Calculate the total salary expense.  
```sql
SELECT SUM(salary) AS total_salary FROM employees;
```
**Explanation:**  
`SUM` calculates the total of a numeric column.

---

### **4.3. Using `AVG`**
**Query:**  
Find the average salary.  
```sql
SELECT AVG(salary) AS average_salary FROM employees;
```
**Explanation:**  
`AVG` calculates the mean value.

---

### **4.4. Using `MAX` and `MIN`**
**Query:**  
Fetch the highest and lowest salary.  
```sql
SELECT MAX(salary) AS max_salary, MIN(salary) AS min_salary FROM employees;
```
**Explanation:**  
`MAX` and `MIN` return the largest and smallest values.

---

## 5. **Grouping Data**

### **5.1. Using `GROUP BY`**
**Query:**  
Find the total salary for each department.  
```sql
SELECT department, SUM(salary) AS total_salary 
FROM employees 
GROUP BY department;
```
**Explanation:**  
`GROUP BY` groups rows sharing the same value, allowing aggregate functions to operate on each group.

---

### **5.2. Using `HAVING`**
**Query:**  
Find departments where the total salary exceeds 50,000.  
```sql
SELECT department, SUM(salary) AS total_salary 
FROM employees 
GROUP BY department 
HAVING SUM(salary) > 50000;
```
**Explanation:**  
`HAVING` filters groups after aggregation.

---

## 6. **Joining Tables**

### **6.1. Inner Join**
**Query:**  
Fetch employee names with their department names.  
```sql
SELECT e.name, d.department_name 
FROM employees e
JOIN departments d ON e.department_id = d.department_id;
```
**Explanation:**  
`JOIN` combines rows from two tables based on a condition.

---

### **6.2. Left Join**
**Query:**  
Fetch all employees and their department names, including employees without a department.  
```sql
SELECT e.name, d.department_name 
FROM employees e
LEFT JOIN departments d ON e.department_id = d.department_id;
```
**Explanation:**  
`LEFT JOIN` includes all rows from the left table, even if there’s no match in the right table.

---

### **6.3. Right Join**
**Query:**  
Fetch all departments and their employees, including departments without employees.  
```sql
SELECT e.name, d.department_name 
FROM employees e
RIGHT JOIN departments d ON e.department_id = d.department_id;
```
**Explanation:**  
`RIGHT JOIN` includes all rows from the right table, even if there’s no match in the left table.

---

### **6.4. Self-Join**
**Query:**  
List employees with their managers.  
```sql
SELECT e.name AS employee_name, m.name AS manager_name 
FROM employees e
LEFT JOIN employees m ON e.manager_id = m.employee_id;
```
**Explanation:**  
Self-joins are used when a table is joined with itself.

---

## 7. **Subqueries**

### **7.1. Simple Subquery**
**Query:**  
Fetch employees earning more than the average salary.  
```sql
SELECT * FROM employees 
WHERE salary > (SELECT AVG(salary) FROM employees);
```
**Explanation:**  
A subquery retrieves data used in the main query.

---

### **7.2. Using `EXISTS`**
**Query:**  
Fetch departments with at least one employee.  
```sql
SELECT * FROM departments d 
WHERE EXISTS (SELECT 1 FROM employees e WHERE e.department_id = d.department_id);
```
**Explanation:**  
`EXISTS` checks if a subquery returns any rows.

---

## 8. **Set Operations**

### **8.1. Union**
**Query:**  
Combine two tables with distinct values.  
```sql
SELECT name FROM employees
UNION
SELECT name FROM contractors;
```
**Explanation:**  
`UNION` merges result sets and removes duplicates.

---

### **8.2. Union All**
**Query:**  
Combine two tables, including duplicates.  
```sql
SELECT name FROM employees
UNION ALL
SELECT name FROM contractors;
```
**Explanation:**  
`UNION ALL` includes all duplicates.

---

## 9. **Modifying Data**

### **9.1. Insert**
**Query:**  
Add a new employee.  
```sql
INSERT INTO employees (name, salary, department_id) 
VALUES ('John Doe', 5000, 2);
```
**Explanation:**  
`INSERT` adds new rows to a table.

---

### **9.2. Update**
**Query:**  
Increase all salaries by 10%.  
```sql
UPDATE employees 
SET salary = salary * 1.10;
```
**Explanation:**  
`UPDATE` modifies existing records.

---

### **9.3. Delete**
**Query:**  
Remove employees from the `Finance` department.  
```sql
DELETE FROM employees 
WHERE department = 'Finance';
```
**Explanation:**  
`DELETE` removes rows matching a condition.

---

## 10. **Schema Management**

### **10.1. Create Table**
**Query:**  
Create a `projects` table.  
```sql
CREATE TABLE projects (
    project_id INT PRIMARY KEY,
    name VARCHAR(100),
    start_date DATE
);
```
**Explanation:**  
`CREATE TABLE` defines a new table.

---

### **10.2. Alter Table**
**Query:**  
Add a `budget` column to the `projects` table.  
```sql
ALTER TABLE projects 
ADD COLUMN budget DECIMAL(10, 2);
```
**Explanation:**  
`ALTER TABLE` modifies table structure.

---

### **10.3. Drop Table**
**Query:**  
Remove the `temp_data` table.  
```sql
DROP TABLE temp_data;
```
**Explanation:**  
`DROP TABLE` deletes a table permanently.

---


| **Feature**                     | **PostgreSQL**                       | **MS SQL Server**                  | **MySQL**                          | **SQLite**                        |
|----------------------------------|---------------------------------------|-------------------------------------|-------------------------------------|------------------------------------|
| **License**                     | Open-source (PostgreSQL License)      | Proprietary (free & paid editions) | Open-source (GPL with exceptions)  | Public domain (SQLite license)    |
| **Best For**                    | Advanced data analysis, extensibility | Enterprise applications            | Web applications, scalability      | Mobile apps, lightweight apps     |
| **SQL Compliance**              | Highly compliant                     | Highly compliant                    | Partially compliant                | Limited compliance                |
| **Storage Model**               | Object-relational                    | Relational                         | Relational                         | Relational                        |
| **Concurrency Control**         | MVCC (Multi-Version Concurrency Control) | Lock-based                         | MVCC                               | Serialized transactions (limited) |
| **Transaction Support**         | Full ACID compliance                 | Full ACID compliance               | Full ACID compliance               | Full ACID compliance              |
| **Replication**                 | Yes (native & logical)               | Yes (always-on, log shipping)      | Yes (native, multi-source)         | Limited (file-based)              |
| **Horizontal Scalability**      | Yes (sharding, distributed extensions like Citus) | Limited                           | Yes (with proxies like MySQL Cluster) | Not supported                    |
| **Indexes**                     | Advanced: B-Tree, GiST, GIN, BRIN, etc. | B-Tree, clustered indexes          | B-Tree, full-text                 | B-Tree                            |
| **JSON Support**                | Extensive (JSON, JSONB)              | Basic                              | Basic                              | Limited                           |
| **Full-Text Search**            | Built-in (advanced)                  | Built-in (good)                    | Limited (plugin support)           | Not available                     |
| **Stored Procedures**           | Yes (PL/pgSQL, PL/Perl, PL/Python)   | Yes (T-SQL)                        | Yes                                | Limited (basic support)           |
| **Geospatial Support**          | Yes (PostGIS extension)              | Yes                                | Limited                            | Not available                     |
| **Performance**                 | High for analytical queries, extensibility | Optimized for enterprise workloads | Fast for read-heavy operations    | Fast for small-scale operations   |
| **Cross-Platform Support**      | Yes                                  | Yes (Windows, Linux, Docker)       | Yes                                | Yes                               |
| **Maximum Database Size**       | Unlimited                            | 524 PB (Enterprise)                | 256 TB                             | Limited by file system (~140 TB)  |
| **Security Features**           | Row-level security, roles, encryption | Advanced (Auditing, TDE)           | Basic                              | Limited                           |
| **Popularity**                  | Popular for analytics, data warehousing | Popular in enterprises            | Widely used for web apps           | Embedded databases                |
| **Community Support**           | Large, active community              | Enterprise-oriented, strong support| Large, active community            | Small community                   |
| **Extensibility**               | Highly extensible (extensions, custom types) | Moderate                          | Limited                           | Not extensible                   |
| **Primary Use Cases**           | Data warehousing, analytics, OLTP    | Enterprise systems, OLTP, OLAP     | Web applications, startups         | Embedded or mobile apps           |
| **Example Query for JSON**      | `SELECT data->>'key' FROM table;`    | `SELECT JSON_VALUE(column, 'key');` | `SELECT JSON_EXTRACT(column, '$.key');` | Not natively supported           |
| **File Size Limitation**        | OS-dependent (unlimited logical size)| Up to 16 TB per filegroup          | Table size up to 64 TB             | 140 TB (file size limit)          |
| **Backup Mechanisms**           | Native, logical (pg_dump), streaming | Native tools (SQL Server Agent)    | Logical (mysqldump), binlogs       | File-based backups                |
| **Cloud Compatibility**         | AWS, GCP, Azure (managed instances)  | Azure (native), AWS, GCP           | AWS, GCP, Azure                    | Limited                           |

---

### **1. Database Basics**
Understanding the core concepts of databases, including:  
- Tables, rows (records), and columns (fields).  
- The difference between relational databases (SQL) and non-relational databases (NoSQL).  
- Basic components like schemas, keys, and relationships.  

---

### **2. Database Design and Normalization**
- **Database Design**: Structuring data logically to minimize redundancy and optimize performance.  
- **Normalization**: Breaking a database into smaller tables to eliminate redundancy and maintain data integrity (e.g., 1NF, 2NF, 3NF).  

---

### **3. Data Types**
Understanding the data types supported by SQL databases, such as:  
- **String types**: `VARCHAR`, `TEXT`, `CHAR`.  
- **Numeric types**: `INT`, `FLOAT`, `DECIMAL`.  
- **Date and Time types**: `DATE`, `DATETIME`, `TIMESTAMP`.  
- **Boolean types**: `BOOLEAN`, `BIT`.  

---

### **4. SQL Queries (CRUD Operations)**
The foundation of interacting with a database using SQL:  
- **Create**: Insert new records into a table using `INSERT`.  
- **Read**: Fetch data using `SELECT`.  
- **Update**: Modify existing records using `UPDATE`.  
- **Delete**: Remove records using `DELETE`.  

---

### **5. Joins (Inner, Outer, Left, Right, Cross)**
Combining data from multiple tables:  
- **Inner Join**: Returns rows with matching values in both tables.  
- **Left Join**: Returns all rows from the left table and matching rows from the right table.  
- **Right Join**: Returns all rows from the right table and matching rows from the left table.  
- **Outer Join**: Combines rows from both tables even if there’s no match.  
- **Cross Join**: Cartesian product of two tables.  

---

### **6. Subqueries**
- A query nested within another SQL query.  
- Used in the `SELECT`, `WHERE`, or `FROM` clauses to break complex problems into smaller parts.  
- Example:  
  ```sql
  SELECT name 
  FROM employees 
  WHERE salary > (SELECT AVG(salary) FROM employees);
  ```

---

### **7. Indexes and Performance Optimization**
- Indexes improve the speed of query execution by providing quick access to data.  
- Types:  
  - **Primary Index**: Based on the primary key.  
  - **Unique Index**: Ensures no duplicates in a column.  
  - **Full-text Index**: For searching text efficiently.  
- Consider trade-offs, as indexes increase storage and slow down `INSERT`/`UPDATE`.

---

### **8. Transactions and ACID Properties**
- **Transactions**: A sequence of operations treated as a single unit.  
  Example: Bank transfers (debit and credit operations).  
- **ACID Properties**:  
  - **Atomicity**: All operations complete or none do.  
  - **Consistency**: Data integrity is maintained.  
  - **Isolation**: Transactions don’t interfere with each other.  
  - **Durability**: Once committed, data is saved permanently.  

---

### **9. Constraints**
Rules enforced at the table level to maintain data integrity:  
- **Primary Key**: Ensures uniqueness and non-null values in a column.  
- **Foreign Key**: Enforces a relationship between two tables.  
- **Unique**: Prevents duplicate values in a column.  
- **Not Null**: Ensures a column cannot have null values.  
- **Check**: Validates data based on conditions (e.g., age > 18).  

---

### **10. Aggregation Functions (SUM, COUNT, AVG, MAX, MIN)**
Used to perform calculations on data:  
- **SUM**: Adds up all values in a column.  
  ```sql
  SELECT SUM(salary) FROM employees;
  ```
- **COUNT**: Counts rows.  
  ```sql
  SELECT COUNT(*) FROM employees;
  ```
- **AVG**: Finds the average value.  
  ```sql
  SELECT AVG(salary) FROM employees;
  ```
- **MAX**/**MIN**: Retrieves the highest/lowest value.  
  ```sql
  SELECT MAX(salary), MIN(salary) FROM employees;
  ```

### **11. GROUP BY and HAVING Clauses**
- **GROUP BY**: Groups rows with the same values into summary rows, often used with aggregate functions.  
  Example: Find the total salary per department:  
  ```sql
  SELECT department, SUM(salary) 
  FROM employees 
  GROUP BY department;
  ```

- **HAVING**: Filters groups based on aggregate functions (unlike `WHERE`, which filters rows).  
  Example: Find departments where the total salary exceeds 50,000:  
  ```sql
  SELECT department, SUM(salary) AS total_salary 
  FROM employees 
  GROUP BY department 
  HAVING SUM(salary) > 50000;
  ```

---

### **12. Stored Procedures and Functions**
- **Stored Procedures**: Precompiled SQL code stored in the database, which can accept input parameters and perform complex tasks.  
  Example: A procedure to add a new employee:  
  ```sql
  CREATE PROCEDURE AddEmployee (IN name VARCHAR(50), IN salary DECIMAL)
  BEGIN
      INSERT INTO employees (name, salary) VALUES (name, salary);
  END;
  ```

- **Functions**: Return a value and are used within SQL queries.  
  Example:  
  ```sql
  CREATE FUNCTION GetEmployeeCount() RETURNS INT
  BEGIN
      RETURN (SELECT COUNT(*) FROM employees);
  END;
  ```

---

### **13. Triggers**
- A trigger automatically executes a block of code in response to certain events on a table, like `INSERT`, `UPDATE`, or `DELETE`.  
  Example: Log changes to an `audit` table whenever an employee record is updated:  
  ```sql
  CREATE TRIGGER log_update
  AFTER UPDATE ON employees
  FOR EACH ROW
  INSERT INTO audit (employee_id, old_salary, new_salary)
  VALUES (OLD.id, OLD.salary, NEW.salary);
  ```

---

### **14. Views**
- A view is a virtual table based on the result of a query. It doesn’t store data but retrieves it dynamically.  
  Example: Create a view of high-salary employees:  
  ```sql
  CREATE VIEW HighSalaryEmployees AS
  SELECT name, salary 
  FROM employees 
  WHERE salary > 10000;
  ```

---

### **15. SQL Injection and Security**
- **SQL Injection**: A type of attack where malicious SQL code is inserted into queries, exploiting vulnerabilities.  
- Prevention:  
  - Use **parameterized queries** or **prepared statements**:  
    ```sql
    SELECT * FROM users WHERE username = ? AND password = ?;
    ```
  - Use ORM frameworks to abstract SQL execution.

---

### **16. Database Backups and Restoration**
- Essential for data recovery in case of failure or corruption.  
- Examples:  
  - **Backup**:  
    ```bash
    mysqldump -u root -p database_name > backup.sql
    ```
  - **Restore**:  
    ```bash
    mysql -u root -p database_name < backup.sql
    ```

---

### **17. Normalization and Denormalization**
- **Normalization**: Organizing data into smaller tables to reduce redundancy and improve integrity.  
  - Example: Splitting an `orders` table into `orders` and `customers`.  
- **Denormalization**: Combining tables to improve read performance, often at the cost of redundancy.  
  - Example: Merging `orders` and `customers` into one table for faster lookups.

---

### **18. Data Modeling**
- The process of defining the structure, relationships, and constraints of data within a database.  
- Tools: Entity-Relationship Diagrams (ERDs).  
- Example:  
  - Tables: `users`, `orders`, `products`.  
  - Relationships: `users` has many `orders`, `orders` contains many `products`.

---

### **19. Entity-Relationship (ER) Diagrams**
- Visual representation of database schema.  
  - **Entities**: Represent tables (e.g., `users`, `orders`).  
  - **Attributes**: Represent columns (e.g., `user_id`, `order_date`).  
  - **Relationships**: Define how entities interact (e.g., `one-to-many`, `many-to-many`).

---

### **20. Foreign Key Relationships**
- **Foreign Key**: A column in one table that refers to the primary key of another table, maintaining referential integrity.  
  Example:  
  ```sql
  CREATE TABLE orders (
      order_id INT PRIMARY KEY,
      user_id INT,
      FOREIGN KEY (user_id) REFERENCES users(user_id)
  );
  ```

- Foreign keys ensure that only valid `user_id` values from the `users` table are allowed in the `orders` table.
  
---

### **21. Pagination with SQL**
- Pagination is used to fetch a limited number of rows from a large dataset and is essential for web applications.
- Example: Retrieve the first 10 rows (page 1) and then the next 10 rows (page 2):  
  - **MySQL/PostgreSQL**:  
    ```sql
    SELECT * FROM employees
    ORDER BY id
    LIMIT 10 OFFSET 0; -- Page 1
    SELECT * FROM employees
    ORDER BY id
    LIMIT 10 OFFSET 10; -- Page 2
    ```
  - **SQL Server**:  
    ```sql
    SELECT * FROM employees
    ORDER BY id
    OFFSET 0 ROWS FETCH NEXT 10 ROWS ONLY; -- Page 1
    ```

---

### **22. Database Indexing Strategies**
- **Indexes**: Improve the speed of data retrieval by reducing the amount of data scanned.
- Strategies:
  - Use indexes on frequently searched columns (`CREATE INDEX idx_name ON table_name(column);`).
  - Avoid excessive indexing as it can slow down writes.
  - Use composite indexes for queries with multiple conditions.
- Example:
  ```sql
  CREATE INDEX idx_name_salary ON employees(name, salary);
  ```

---

### **23. Working with JSON and XML in Databases**
- Many databases support JSON and XML data types for storing semi-structured data.
- **PostgreSQL JSON**:
  ```sql
  SELECT data->>'key' AS value
  FROM json_table
  WHERE data->>'key' = 'value';
  ```
- **MySQL JSON**:
  ```sql
  SELECT JSON_EXTRACT(json_column, '$.key') AS value
  FROM json_table;
  ```
- **XML** (SQL Server):
  ```sql
  SELECT column.value('(/root/child)[1]', 'VARCHAR(50)') AS value
  FROM xml_table;
  ```

---

### **24. Query Optimization and Execution Plans**
- **Query Optimization**: Improves performance by rewriting queries or tuning database settings.
- Use tools like `EXPLAIN` (MySQL, PostgreSQL) or `EXPLAIN PLAN` (SQL Server) to understand how queries are executed.
- Example: Check the execution plan in PostgreSQL:
  ```sql
  EXPLAIN ANALYZE SELECT * FROM employees WHERE salary > 50000;
  ```
- Tips:
  - Avoid `SELECT *`.
  - Use indexes wisely.
  - Optimize joins and subqueries.

---

### **25. Full-Text Search**
- Used for searching text in large datasets efficiently.
- **PostgreSQL**:  
  ```sql
  SELECT * FROM documents
  WHERE to_tsvector(content) @@ to_tsquery('search_term');
  ```
- **MySQL**:
  ```sql
  SELECT * FROM documents
  WHERE MATCH(content) AGAINST('search_term');
  ```
- **SQL Server**:
  ```sql
  SELECT * FROM documents
  WHERE CONTAINS(content, 'search_term');
  ```

---

### **26. Replication and Clustering**
- **Replication**: Copying data from one database server to others for redundancy and load balancing.
  - Types: Master-Slave, Master-Master, Multi-source.
- **Clustering**: Combining multiple servers to act as a single system.
  - Example: PostgreSQL with Citus for distributed data.

---

### **27. Database Scaling (Vertical and Horizontal)**
- **Vertical Scaling**: Adding resources (CPU, RAM) to a single database server.
- **Horizontal Scaling**: Distributing the database across multiple servers.
  - Example: Sharding in MongoDB or MySQL.

---

### **28. Connection Pooling**
- Manages database connections efficiently by reusing a pool of connections.
- Example: Use connection pooling libraries like **pgbouncer** (PostgreSQL) or built-in pooling in frameworks like Django.
- Benefits:
  - Reduces overhead of establishing connections.
  - Improves application performance.

---

### **29. Working with ORMs (e.g., Sequelize, TypeORM, Django ORM)**
- **Object-Relational Mapping (ORM)**: A technique for querying and manipulating data using object-oriented paradigms.
- Examples:
  - **Sequelize** (Node.js):  
    ```javascript
    const Employee = sequelize.define('employee', {
      name: Sequelize.STRING,
      salary: Sequelize.FLOAT,
    });
    Employee.findAll({ where: { salary: { [Op.gt]: 50000 } } });
    ```
  - **Django ORM** (Python):
    ```python
    Employee.objects.filter(salary__gt=50000)
    ```

---

### **30. Database Migrations**
- Migrations manage schema changes, such as adding, modifying, or deleting tables and columns.
- Tools:
  - **Django**:
    ```bash
    python manage.py makemigrations
    python manage.py migrate
    ```
  - **Sequelize**:
    ```bash
    sequelize migration:create --name add-new-column
    ```
- Example: Add a column `email` to the `employees` table:
  ```sql
  ALTER TABLE employees ADD COLUMN email VARCHAR(100);
  ```
  
---

### **31. NoSQL vs SQL Basics**
- **SQL (Relational Databases)**: Structured data stored in tables with relationships.
  - Examples: PostgreSQL, MySQL, MS SQL Server.
  - Use case: Applications with structured data and predefined schemas.
- **NoSQL (Non-Relational Databases)**: Stores unstructured or semi-structured data in formats like JSON, key-value pairs, or graphs.
  - Examples: MongoDB, Cassandra, Redis.
  - Use case: Applications needing flexible schemas or high scalability.

---

### **32. ACID vs BASE**
- **ACID** (Atomicity, Consistency, Isolation, Durability): Ensures reliable transactions in relational databases.
  - Example: Bank transactions where updates should either fully happen or not at all.
- **BASE** (Basically Available, Soft state, Eventual consistency): Focuses on high availability and scalability, often in NoSQL systems.
  - Example: Social media platforms, where updates propagate over time.

---

### **33. Eventual Consistency**
- A consistency model where data changes propagate to all nodes over time but are not guaranteed to be immediate.
  - Example: In distributed databases like Cassandra or DynamoDB, writes might appear consistent only after a delay.
- Use case: Systems requiring high availability, like content delivery networks (CDNs).

---

### **34. Partitioning and Sharding**
- **Partitioning**: Divides a single database table into smaller parts for better performance.
  - Example: Splitting data based on a range of values (`partition by range`).
- **Sharding**: Horizontal scaling by distributing data across multiple database servers.
  - Example: User data is split across servers based on user ID.
  - Use case: High-traffic applications like e-commerce sites.

---

### **35. Temporal Data and Time Zones in SQL**
- Handling time-related data efficiently is critical for global applications.
- **Temporal Data Types**:
  - `DATE`, `TIME`, `TIMESTAMP`, `INTERVAL`.
- **Time Zone Handling**:
  - PostgreSQL:
    ```sql
    SELECT CURRENT_TIMESTAMP AT TIME ZONE 'UTC';
    ```
  - MySQL:
    ```sql
    SELECT CONVERT_TZ(NOW(), 'UTC', 'America/New_York');
    ```

---

### **36. Database Caching Strategies**
- **Caching**: Improves performance by storing frequently accessed data in memory.
  - Tools: Redis, Memcached.
- Examples:
  - Cache results of expensive queries.
  - Use Materialized Views (PostgreSQL) for precomputed query results.

---

### **37. Stored JSON/JSONB Data Types**
- Many modern SQL databases support JSON for semi-structured data.
- **PostgreSQL JSONB** (binary-optimized JSON):
  ```sql
  SELECT data->>'key' AS value
  FROM json_table
  WHERE data->>'key' = 'value';
  ```
- **MySQL JSON**:
  ```sql
  SELECT JSON_EXTRACT(json_column, '$.key') AS value
  FROM json_table;
  ```

---

### **38. Database Security (User Roles, Permissions)**
- Security practices:
  - Create user roles with specific permissions.
  - Use encryption (e.g., Transparent Data Encryption in SQL Server).
- Example: Grant and revoke permissions:
  ```sql
  GRANT SELECT, INSERT ON employees TO 'app_user';
  REVOKE DELETE ON employees FROM 'app_user';
  ```

---

### **39. Cloud Databases (AWS RDS, Azure SQL, Google Cloud SQL)**
- Cloud platforms provide managed database services.
  - **AWS RDS**: Supports MySQL, PostgreSQL, MSSQL, MariaDB, and more.
  - **Azure SQL**: Fully managed SQL Server.
  - **Google Cloud SQL**: Managed MySQL, PostgreSQL.
- Benefits:
  - Automatic backups, scaling, and maintenance.
  - Example: Setting up a PostgreSQL instance on AWS RDS.

---

### **40. Working with Database CLI and Tools**
- Command-line interfaces and tools for database management:
  - **PostgreSQL CLI** (`psql`):  
    ```bash
    psql -U username -d database_name
    ```
  - **MySQL CLI** (`mysql`):  
    ```bash
    mysql -u root -p
    ```
- GUI tools:
  - **pgAdmin** (PostgreSQL).
  - **MySQL Workbench**.
  - **Azure Data Studio** (MSSQL).

---
