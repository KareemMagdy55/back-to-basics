## What is SQL ?
Sql is structured query langauage that is used to access and manipulate databases

---
## SQL Commands 
SQL commands are the fundamental building blocks for interacting with a DBMS.
SQL commands are categorized into 5 categories

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
used for performing queries on the data within schema objects.
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



  
  
  

