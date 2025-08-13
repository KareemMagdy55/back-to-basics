## Database & DBMS
- Database (DB): orgnaized collection of data managed by DBMS.
- Database Mangement System (DBMS) : a software between user and data that offers user to do several operations on data (e.g. MySql, Microsoft Sql Server, MongoDb).
---
## Relational Databases
In simple terms, it’s a database model that *represents data using tables*. The term "relational" means that these tables are connected to each other (have relations).

for example, here is a ```Client``` and ```Tshirt``` entities represented in two tables, you can see clearly the "relation" between ```Client``` and his ```Tshirt```

|  ID |  Name  | Address | Age | TshirtId |
| :-: | :----: | :-----: | :-: | :------: |
|  1  | Kareem |   Giza  |  20 |     3    |
|  2  |  Magdy |  Cairo  |  40 |     1    |
|  3  | Dawood |   Alex  |  80 |     2    |

|  ID | Size | Price |
| :-: | :--: | ----: |
|  1  |   L  | \$160 |
|  2  |  XL  | \$120 |
|  3  |   M  | \$140 |

> Examples of Relational Database Mangement System (RDBMS) : **MySQL, PostgreSql, Microsoft SQL Server, Oracle Database.**
---
### Key concepts 
- Primary Key : a key uniquely identify each row in a table, and it cannot be null (*See 'ID' in the previous table*).
- 


