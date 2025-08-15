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


> SQL commands is case-insensitive , This means `Alter`, `ALTER`, and `AltEr` are the same.
---
### DQL - Data Query Language
used for performing queries on the data within schema objects.
- `Select`, `From` : Used to retrieve data from database 

  ```sql
  SELECT column1, colums2 FROM table1
  ```
  > if you use * after SELECT you get all columns
- `Where` : Filters rows before any grouping or aggregation
  ```sql
    SELECT price FROM products WHERE price > 23
  ```
  

