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

How to create a new PostgreSQL database from terminal? And how to do so in psql console?

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

If part an sql statement is `(weight DECIMAL(8, 2))` what's the meaning of `8` and `2`? What the max and minimal value for this column?

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

What's the difference between `char` and `varchar` type when we use match pattern to match content in certain column(s)?

---

Select Queries

---

- understand "clauses" in SQL statements.
  - the operation hierarchy
  - the chain of operation
  - the logic order

What is the basic syntax of a SELECT statement in SQL?

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

What is the wild card character in a SQL to match string?

What's the key word used for string matching?

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

---

Update data in a table

---

What's the basci syntax of updating row(s) in a table?

What would happen if we omit the `WHERE` clause potion of our updating statement?

What's the basic syntax to delete row(s) in a table?

What would happen if we omit the `WHERE` clause potion of our deleting statement?

---

Table Relationships

---

What is normalization of database?

Why we need normalization?

what's the mechanism for carrying out normalization?

How you understand entities and relationships in database design?

What is an Entity Relationship Diagram?

What is primary and foreign key, what are they used for?

What's the meaning of referential integrity?

Why we need `ON DELETE` clause, how it relates to referential integrity?

What a cross-reference table(join table) be used for?

---

SQL joins

---

What's the basic syntax of join tables?

What's the difference between `INNER JOIN`, `LEFT OUTER JOIN`, `RIGHT OUTER JOIN`, `FULL JOIN`, and `CROSS JOIN`, which two of them are less used?

What's the syntax of table name aliasing in SQL?(and shorthand form)

What's the syntax of column name aliasing in SQL?

What's subquery in SQL? Take the below example to explain:

```sql
SELECT u.full_name FROM users u
WHERE u.id NOT IN (SELECT c.user_id FROM checkouts c);
```

In some situations, can JOINs and subqueries interchangeable?

---

---

### Material in courses:

Does SQL only handle data in databases?

What is bit? What is byte?

What are the two ways to load SQL files into PostgreSQL database?

What's the syntax to add multiple new columns to a table within one SQL statement?

How to extract a year number(as integer) from a timestamp/date column?

https://stackoverflow.com/questions/43397871/postgresql-getting-a-year-from-date-type-as-integer

How to split a string in PostgreSQL? How to get substring from a given string position in PostgreSQL?

https://www.postgresql.org/docs/11/functions-string.html

What would be the result if we perform any operator on `NULL` in postgresql?

What are the 3 aspects of restriction we can add to a column?
- type
- existence
- constraint

What's a key used for in database?

What is natural key and surrogate key?

What's the difference between `(id integer PRIMARY KEY)` and `(id serial)`

think of these:
- auto incrementing?
- allow null?
- enforce unique?
- type?

In SQL, is sequence independent to table?

https://www.postgresql.org/docs/11/sql-createsequence.html

https://www.ibm.com/support/knowledgecenter/ssw_ibm_i_71/sqlp/rbafysequence.htm

https://docs.oracle.com/cd/B19306_01/server.102/b14200/statements_6015.htm

If a column was originally set with a `DEFAULT` value, what would happen if we exclude the column name from the column list while performing inserting or updating?

https://www.postgresql.org/docs/11/ddl-default.html

If a column was originally set as `boolean` type and not added with a `NOT NULL` constraint. How to construct an expression to select all rows that are not `false` in this column?(notice the relationship between boolean values and `NULL`, what is the opposite(!=) of `true` or `false`)

If at the end an SQL statement we specified 2 or more columns to `ORDER BY`, how it will ORDER the results?
(sub order by)

---

Relational Data and JOINs

---

How to distinguish relation and relationship?

What is cardinality of a relationship?

https://www.sqa.org.uk/e-learning/SoftDevRDS02CD/page_44.htm

The number of objects on each side of the relationship.

What is modality within a relationship?

The modality of a relationship indicates if that relationship is required or not.

What is crow's foot notation used for? Why it is named crow's foot?

Why we can't use aggregation functions in `WHERE` clause?(think of from what object(s) each them will perform on?)

https://stackoverflow.com/questions/42470849/why-are-aggregate-functions-not-allowed-in-where-clause

What are the two ways to create a foreign key constraint?

Does a foreign key constraint prevent NULL values from being stored in a column?

What is the two basic steps to perform a normalization?

How filter rows based on the results of aggregate function?

Does a newly added foreign key constraint will also enforce a  `NOT NULL` constraint to the column?

At which places we can put a subquery in SQL? What's the main difference?

How indexes work?

https://stackoverflow.com/questions/1108/how-does-database-indexing-work
