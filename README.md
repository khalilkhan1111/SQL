# SQL
RDBMS

It is a software system that allows users to create, maintain, and access databases. RDBMSs are based on the relational model, which organizes data into tables. Each table is made up of rows and columns, and each row represents a single record. 


Non Relational Database


A non-relational database (also known as a NoSQL database) is a database that does not use the tabular structure of rows and columns found in most traditional database systems. Instead, non-relational databases use a storage model that is optimized for the specific requirements of the type of data being stored.
Example Graph database, document database.


SQL

Structured query language (SQL) is a programming language for storing and processing information in a relational database. A relational database stores information in tabular form, with rows and columns representing different data attributes and the various relationships between the data values. You can use SQL statements to store, update, remove, search, and retrieve information from the database. You can also use SQL to maintain and optimize database performance.


Data definition language 
Data definition language (DDL) refers to SQL commands that design the database structure. Database engineers use DDL to create and modify database objects based on the business requirements. For example, the database engineer uses the CREATE command to create database objects such as tables, views, and indexes.

Data query language
Data query language (DQL) consists of instructions for retrieving data stored in relational databases. Software applications use the SELECT command to filter and return specific results from a SQL table. 

Data manipulation language
Data manipulation language (DML) statements write new information or modify existing records in a relational database. For example, an application uses the INSERT command to store a new record in the database.

Data control language
Database administrators use data control language (DCL) to manage or authorize database access for other users. For example, they can use the GRANT command to permit certain applications to manipulate one or more tables. 

Create

syntax

CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
   ....
);

example

CREATE TABLE Persons (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255)
);

The ALTER TABLE statement is used to add, delete, or modify columns in an existing table.

ALTER TABLE - ADD Column

To add a column in a table, use the following syntax:

ALTER TABLE table_name
ADD column_name datatype;

Example

ALTER TABLE Customers
ADD Email varchar(255);

ALTER TABLE - DROP COLUMN
To delete a column in a table, use the following syntax (notice that some database systems don't allow deleting a column):

ALTER TABLE table_name
DROP COLUMN column_name;

Example
ALTER TABLE Customers
DROP COLUMN Email;

To rename a column in a table, use the following syntax:

ALTER TABLE table_name
RENAME COLUMN old_name to new_name;



INSERT
Insert command is used to insert data into a table.

The syntax for INSERT command is as follows −

Syntax

Insert into <table_name> (column list) values (column values);

Example

Insert into Employee(Emp_id, Emp_name) values (001, “ bhanu”);

SELECT
Select command is used to retrieve data from the database.

The syntax for the select command is as follows −

Syntax

SELECT * from <table_name>;

Example

SELECT * from Employee;

DELETE
Delete command is used to delete records from a database table.

 Delete from <table_name>WHERE condition;

 Example

 DELETE from Employee WHERE Emp_id=002;

 UPDATE
Update command is used to update existing data within a table.

Syntax

UPDATE <table_name> SET column_number =value_number WHERE condition;

Example

UPDATE Employee SET Emp_name= Ram WHERE Emp_id= 001;

The SELECT DISTINCT statement is used to return only distinct (different) values.

SELECT DISTINCT Syntax

SELECT DISTINCT column1, column2, ...
FROM table_name;

Example

SELECT DISTINCT Country FROM Customers;


