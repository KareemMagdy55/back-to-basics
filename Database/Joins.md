## SQL Joins
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
### Inner Join 
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

