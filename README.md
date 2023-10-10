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

Count 

The COUNT function is used to calculate the number of rows that match a specific condition or the number of non-null values in a specified column.

SELECT COUNT(column_name)

Example

SELECT COUNT(DISTINCT job_title)
FROM employees;

Where 

 The WHERE clause is used to limit the results of a SQL query to only include rows that match a particular condition or set of conditions.

 Syntax

SELECT column1, column2, ...
FROM table_name
WHERE condition;

Example

SELECT * FROM employees 
WHERE department = 'Sales';

Order By

It is used to sort the result set of a query in a specified order based on one or more columns in the result set.

Syntax

SELECT column1, column2, ...
FROM table_name
ORDER BY column1 [ASC | DESC], column2 [ASC | DESC], ...;


Example

SELECT *
FROM products
ORDER BY price DESC;


Limit

It is used to restrict the number of rows returned by a query

Syntax

SELECT column1, column2, ...
FROM table_name
LIMIT number_of_rows;


Example

SELECT *
FROM students
LIMIT 10;


In Between

It is used to filter rows from a database table based on a range of values for a specified column. 

Syntax

SELECT column1, column2, ...
FROM table_name
WHERE column_name BETWEEN value1 AND value2;


Example

SELECT *
FROM employees
WHERE age BETWEEN 25 AND 35;


Like and ILike

the "LIKE" operator is used to perform pattern matching within text data. The "ILIKE" operator is used for case-insensitive pattern matching, which means it matches text patterns regardless of case

Syntax

SELECT column1, column2, ...
FROM table_name
WHERE column_name LIKE pattern;

SELECT column1, column2, ...
FROM table_name
WHERE column_name ILIKE pattern;

Example

SELECT *
FROM products
WHERE product_name LIKE 'Apple%';

SELECT *
FROM customers
WHERE last_name ILIKE 'smith%';

Aggregate Functions

Aggregate functions in SQL are functions that perform a calculation on a set of values and return a single value as a result.
Example - count, sum, average, min, max

Syntax

SELECT SUM(column_name) FROM table_name;

SELECT AVG(column_name) FROM table_name;

SELECT MIN(column_name) FROM table_name;

SELECT MAX(column_name) FROM table_name;

Example

SELECT SUM(Sales) FROM Electronics;

SELECT AVG(Sales) FROM Electronics;

SELECT MIN(Sales) FROM Electronics;

SELECT MAX(Sales) FROM Electronics;

Group By

It is used to group rows from a database table based on one or more columns.

Syntax

SELECT column1, column2, aggregate_function(column_name)
FROM table_name
GROUP BY column1, column2;

Example

SELECT department, AVG(salary) as avg_salary
FROM employees
GROUP BY department;

Having By

 It is used in conjunction with the "GROUP BY" clause to filter the results of a grouped query based on a specified condition.

 Syntax

SELECT column1, column2, aggregate_function(column_name)
FROM table_name
GROUP BY column1, column2
HAVING condition;

Example

SELECT column1, column2, aggregate_function(column_name)
FROM table_name
GROUP BY column1, column2
HAVING condition;


AS statement

It is used to assign an alias or alternative name to a column or table in the result set of a query. 

Syntax

SELECT column_name AS alias_name
FROM table_name;

Example

SELECT first_name AS "First Name", last_name AS "Last Name"
FROM employees;

Join 

It is used to combine rows from two or more tables based on a related column between them.

INNER JOIN:

In INNER JOIN returns only the rows that have matching values in both tables.

Syntax

SELECT columns
FROM table1
INNER JOIN table2 ON table1.column = table2.column;


Example

SELECT orders.order_id, orders.order_date, customers.customer_name
FROM orders
INNER JOIN customers ON orders.customer_id = customers.customer_id;


LEFT JOIN:

A LEFT JOIN returns all rows from the left table and the matching rows from the right table.

Syntax

SELECT columns
FROM table1
LEFT JOIN table2 ON table1.column = table2.column;

Example

SELECT orders.order_id, orders.order_date, customers.customer_name
FROM orders
LEFT JOIN customers ON orders.customer_id = customers.customer_id;


Right Join:

A RIGHT JOIN is the opposite of a LEFT JOIN. It returns all rows from the right table and the matching rows from the left table.

Syntax

SELECT columns
FROM table1
RIGHT JOIN table2 ON table1.column = table2.column;


Example

SELECT customers.customer_name, orders.order_id, orders.order_date
FROM customers
RIGHT JOIN orders ON customers.customer_id = orders.customer_id;

FULL JOIN :

A FULL JOIN returns all rows when there is a match in either the left or the right table. If there's no match in one of the tables, NULL values are returned for columns from the table without a match.

Syntax

SELECT columns
FROM table1
FULL JOIN table2 ON table1.column = table2.column;


Example

SELECT customers.customer_name, orders.order_id, orders.order_date
FROM customers
FULL JOIN orders ON customers.customer_id = orders.customer_id;

SELF JOIN:

A SELF JOIN is used when you want to combine rows from the same table.

Syntax

SELECT columns
FROM table AS t1
INNER JOIN table AS t2 ON t1.column = t2.column;

Example

SELECT e.employee_name, m.employee_name AS manager_name
FROM employees e
LEFT JOIN employees m ON e.manager_id = m.employee_id;


Cross Join:

A CROSS JOIN (also known as a Cartesian join) returns the Cartesian product of rows from two tables, resulting in every possible combination of rows.

Syntax

SELECT columns
FROM table1
CROSS JOIN table2;


Example

SELECT colors.color_name, sizes.size_name
FROM colors
CROSS JOIN sizes;


Conditinal Statement

onditional statements are used to control the flow of execution based on specified conditions. The primary conditional statement in SQL is the "CASE" expression, which allows you to perform conditional logic within a query to determine the values returned or the actions to be taken based on certain conditions. 

Syntax

CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    ...
    ELSE else_result
END


Example

SELECT
    employee_name,
    salary,
    CASE
        WHEN salary < 30000 THEN 'Low Salary'
        WHEN salary >= 30000 AND salary < 60000 THEN 'Medium Salary'
        WHEN salary >= 60000 THEN 'High Salary'
        ELSE 'Unknown'
    END AS salary_category
FROM employees;
