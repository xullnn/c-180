Relational database

https://en.wikipedia.org/wiki/Relational_database

Object-relational database

https://en.wikipedia.org/wiki/Object-relational_database

Object database

https://en.wikipedia.org/wiki/Object_database

---

Unstructured data

Structured data
- tabular format

A basic definition of a **database** is simply 'a structured set of data held in a computer'.

---

Tables in a database

database
  - tables
    - columns
    - rows

A table, in the context of a database, can be defined as a list of individual but related data entries (the table rows), each of which store values for a set of defined, shared attributes (the table columns).

columns: a set of standard, shared headers(attribute names)
rows: an entity's information which conforms to the names of columns.

---

RDBMS: relational database management system

According to the name of the term, it's a system/application/software that is used to manage relational database. Manage may mean: install/remove database, interact with database(crud), transfer/move database etc.

---

SQL: standard query language

declarative

Theoretical foundation: relational algebra
https://en.wikipedia.org/wiki/Relational_algebra

---

Key terms:

- relational database
- RDBMS
- Relation
- SQL
  - SQL statement
    - SQL query

---

PostgreSQL is a "client-server" database.

Sushi restaurant.

The ways you send the order to chef may involve different layers of abstractions. But the underlying basic model never change. Different clients also represent different abstractions.

---

PostgreSQL Client Application:

Applications that comes with PostgreSQL. We use them to interact with PostgreSQL via command line.

`psql` is a PostgreSQL interact console, it's just like `irb` to Ruby.

Meta-commands and SQL statements: the former is for performing high level control of the program. The latter is for SQL related operations.

---

Unix and permission issue

---

SQL:

semicolon => multiple-line statement

SQL sub-languages
- DDL
- DML
- DCL

---

Basic operations

- set up
  - how to create a database with a given name
  - what is the extension name of a file that we write sql statements in?
  - how to import an external .sql file into an existent database?

- connect
  - how to connect to a database locally?
  - what does `-d` flag means in a `psql` Meta-commands(check `psql --help`)
  - recall the relationship between database and tables

- identify all components in this sql statement: `SELECT * FROM orders;`
- how to select one or more columns from a table? how to separate the names of columns
- what's the means of database usually used to label a specific row? or say what will be used as unique identifier to a row?
- what should be written before and after the `=` in a sql statement? what is the difference on meaning of this in sql and programing language like Ruby.
- when a column's values are string or integers, how this will influence the sql statement?

---

What is the schema of a database?
What is the data of a database?
What is the relationship between schema and database, database and data?
What sub-languages of SQL will be used to handle schema and data?

---

DDL -- Database Definition Language -- Schema

Create and View database

What DDL handles about within a database? What things DDL will not touch in a database?

How to create a new PostgreSQL database from terminal? And how to do so from psql console?

How to connect to another database in psql console?

Is there any omitted arguments when we are using DDL on the same local machine?

If your psql prompt is `another_database=#`, and you want to delete the `another_database` database, how to do it? Two ways!

What's the difference among:
- PostgreSQL client application(`createdb`, `psql`, `dropdb`)
- meta-commands(`\c db_name`, `\list`)
- SQL statements

---

DDL -- Database Definition Language -- Schema

---

Create and View tables

Point out the different components in this sql statement, which of these components are required.

```
sample_db=# CREATE TABLE users (
  id serial UNIQUE NOT NULL,
  username CHAR(25)
  );
```

Could constraints only be at table column level?
Constraints can apply to a specific column, an entire table, more than one table, or an entire schema.

Why we need constraints?

How to views all tables in a database in psql console?
How to check the schema of a specific table?

Is the 'security settings'(controlled by DCL) of a database part of its schema?

Although database schema is largely a DDL (Data Definition Language) concern, parts of it, such as access and permissions, are determined by DCL (Data Control Language)

If part a sql statement is `(weight DECIMAL(8, 2))` what's the meaning of `8` and `2`? What the max and minimal value for this column?

---

Alter a Table


What's in common on all below syntax?
- rename a table

- rename a column
- change a column's datatype
- adding a constraint(can we alter a constraint? like change `varchar(25)` to `varchar(50)`)
- removing a constraint
- adding a column
- removing a column

It this operation reversible?
- dropping tables


---

Inserting Data into a Table

---

Data and DML

What are the four types of Data Manipulation Statements?

What is the syntax of inserting data?

Does 'Schema' can be used for both database and table?
The structure of the table is also referred to as the schema of a table.

How to add a `CHECK` constraint to a column to let it can't be inserted into empty string?

What's the alternative syntax of `<>` in SQL?

How to insert string `'O' Sullivan'` into a table?

What would cause a "Three State Boolean problem or Three Valued-logic problem" ?

---

Select Queries

---

- understand "clauses" in SQL statements.
  - the operation hierarchy
  - the chain of operation
  - the logic order

What is the basic syntax of a SELECT statement in SQL?

How to let the column used as query condition also to be shown in the response?

What is Identifiers and Key Words in SQL?

If you have a column named just as one of reserved words in SQL, how could you handle this?

If we order query results by a boolean column in ascending order, which ones would be listed first?

What is the sort logic which contains multiple sorting conditions, like:

```
SELECT * FROM users ORDER BY activated ASC, id DESC;
```

Operators are used in which clause in SQL Query?

What are the main 3 types of operator in SELECT query?

The meaning of `"predicates"` in Grammar can be seen as "the part of a sentence that is other than the subject". What's `comparison predicates` in `WHERE` clause?

- subject, verb, object
  - `id = 2`
  - `id IS NOT NULL`

How to get all rows of whose certain column is `NULL`?

Choose logical operator for each word:
- either
- both
- other than

What the wild card character in a SQL matching string? What's the key word used for string matching?

How to match all user names whose name contains `Lee`. like `Mary Lee. S`, `Lee Jhon`, `Wu Lee.`?

Reorganize these words in a logical way:
(ORDER BY clause, `> < <> != >= <=`, SELECT statement, `AND OR`, WHERE clause, Operators, SQL statement, `LIKE`, LIMIT clause, OFFSET clause, DISTINCT qualifier, FUNCTIONS, String function, Date/Time function, Aggregate function, GROUP BY, result filters)

- SQL statement,
  - SELECT statement
    - WHERE clause
      - Operators
        - `> < <> != >= <=`
        - `AND OR`
        - `LIKE`
    - result filters
      - LIMIT clause
      - GROUP BY
      - OFFSET clause
      - ORDER BY clause
    - FUNCTIONS
      - String function
      - Aggregate function
      - Date/Time function
      - DISTINCT qualifier
