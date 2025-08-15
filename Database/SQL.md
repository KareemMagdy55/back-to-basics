## What is SQL ?
Sql is structured query langauage that is used to access and manipulate databases

---
## SQL Commands 
SQL commands are the fundamental building blocks for interacting with a DBMS.

They are generally divided into five main categories.

This README will cover three of those categories, while the remaining two will be discussed later....

---
### DDL - Data Definition Language
It simply deals with descriptions of the database schema and is used to create and modify the structure of database objects.

> Database objects such as table, index, function, view, stored prodcedutes and triggers

DDL Commands 
- `CREATE` : Creates DB or its objects.
- `DROP` : Delete objects from database.
- `ALTER` : Change structure of database (add new column, redefinecolumn properties, add or remove constraints, etc.).
- `TRUNCATE` : Remove all records/data from the table (make the table empty).

> `TRUNCATE` Removal Can't be Rolled back (no undo).

> SQL commands is case-insensitive , This means `Alter`, `ALTER`, and `AltEr` are the same.
---
### DQL - Data Query Language
Used for performing queries on the data within schema objects.
- `Select`, `From` : Used to retrieve data from database 

  ```sql
  SELECT column1, colums2 FROM table1
  ```
  > if you use * after SELECT you get all columns
- `Where` : Filters rows before any grouping or aggregation (will be discussed more...)
  ```sql
    SELECT price FROM products WHERE price > 23
  ```
- `GROUP BY` : Groups rows that have the same values in specified columns.
  for example, here is a table that represent customers in different countries
  | CustomerID | Country |
  |------------|---------|
  | 1          | Germany |
  | 2          | Mexico  |
  | 3          | Mexico  |

  after apply the following query that find the number of customer in each countery.
  ```sql
  SELECT Country, COUNT(CustomerID) as CustomerCount
  FROM Customers
  GROUP BY Country
  ```
  it produce this table as a result
  
    | Country | CustomerCount |
    |------------|---------|
    | Germany        | 1 |
    | Mexico         | 2  |
  > The GROUP BY statement is often used with aggregate functions (COUNT(), MAX(), MIN(), SUM(), AVG())

- `Having` : filers results of `Group By`.
- `Order By` : Sorts the result (ascending(default) and descending) by one or more columns.
  ```sql
  SELECT column1
  FROM table_name
  ORDER BY column1 [ASC | DESC];
  ```
- `LIMIT` : Limit the number of records/rows shown in the result table.
  ```sql
  SELECT column
  FROM table
  LIMIT number;
  ```

---
### DML - Data Manipulation Language
Deals with the manipulation of data present in the database

- `INSERT` : insert data into a table 
  ```sql
    INSERT INTO table_name (column1, column2, ...)
    VALUES (value1, value2, ...);
  ```
- `UPDATE` : update existing data within a table
  ```sql
  UPDATE table_name
  SET column1 = value1, column2 = value2
  WHERE condition;
  ```
- `DELETE` : Delete all or specfic records from a database table (removal can be rolled back)
  ```sql DELETE FROM table```; deletes all records
  ```sql Delete FROM table WHERE condition``` deletes specfic records

  
  
  

