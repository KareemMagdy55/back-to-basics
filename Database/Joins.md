# SQL Joins
SQL joins allow us to combine information from multiple tables based on a related column. 

Here are two tables that we will use for a `JOIN` operation.

| EmployeeID | EmployeeName |
|------------|--------------|
| 1          | John Doe     |
| 2          | Jane Smith   |
| 3          | Emily Jones  |

`Employees Table`


| EmployeeID | Department   |
|------------|--------------|
| 1          | Marketing    |
| 2          | Sales        |
| 4          | HR           |

`Departments Table`

---  
## Inner Join 
Return the records that have matching value in both tables (Intersection)

for example sql query
```sql
SELECT Employees.EmployeeName, Departments.Department
FROM Employees
INNER JOIN Departments
ON Employees.EmployeeID = Departments.EmployeeID;
```

will have result 

| EmployeeName | Department |
|--------------|------------|
| John Doe     | Marketing  |
| Jane Smith   | Sales      |

`Employees' names and thier departments concatenated through EmployeeId`

---
## Outer Joins

### Full Outer Join
Return all records in the two tables, and fill unmatched parts with `null`.

for example sql query
```sql
  SELECT Employees.EmployeeName, Departments.Department
  FROM Employees
  FULL OUTER JOIN Departments
  ON Employees.EmployeeID = Departments.EmployeeID;
```
will result this table
| EmployeeName | Department |
|--------------|------------|
| John Doe     | Marketing  |
| Jane Smith   | Sales      |
| Emily Jones  | NULL       |
| NULL         | HR         |

---
### Left Outer Join

Returns all records from the **left table** and the **matching records** from the **right table**. If there is no match, the result will show `NULL` values for columns from the right table.


for example sql query
```sql
  SELECT Employees.EmployeeName, Departments.Department
  FROM Employees
  Left Join Departments
  ON Employees.EmployeeID = Departments.EmployeeID;
```
will result this table
| EmployeeName | Department |
|--------------|------------|
| John Doe     | Marketing  |
| Jane Smith   | Sales      |
| Emily Jones  | NULL       |


> Left table = table after `FROM` keyword.

> Right table = table after `JOIN` keyword.

---
### Right Outer Join
Returns all records from the **right table** and the **matched records** from the **left table**. If there is no match, the result will contain `NULL` values for columns from the left table.


for example sql query
```sql
  SELECT Employees.EmployeeName, Departments.Department
  FROM Employees
  right Join Departments
  ON Employees.EmployeeID = Departments.EmployeeID;
```
will result this table
| EmployeeName | Department |
|--------------|------------|
| John Doe     | Marketing  |
| Jane Smith   | Sales      |
| NULL         | HR         |

---
### Cross Join
Return all possible combinations of two tables
for example sql query
```sql
  SELECT Employees.EmployeeName, Departments.Department
  FROM Employees
  cross join Departments
```
will result this table

| EmployeeID (Emp) | EmployeeName | EmployeeID (Dept) | Department |
| ---------------- | ------------ | ----------------- | ---------- |
| 1                | John Doe     | 1                 | Marketing  |
| 1                | John Doe     | 2                 | Sales      |
| 1                | John Doe     | 4                 | HR         |
| 2                | Jane Smith   | 1                 | Marketing  |
| 2                | Jane Smith   | 2                 | Sales      |
| 2                | Jane Smith   | 4                 | HR         |
| 3                | Emily Jones  | 1                 | Marketing  |
| 3                | Emily Jones  | 2                 | Sales      |
| 3                | Emily Jones  | 4                 | HR         |






