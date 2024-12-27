# Revisiting SQL

Structured Query Language - different versions with the same queries, but different libraries.

Table broken up into fields.
Field is a collumn in a table designed to mantain specific inofrmation about every record in the table


A record - is a row is each individual entry that exists in a table

column -  all info for certain feild

database - one or more tables. each table contains records with data

SELECT - extracts data from a database
UPDATE - updates data in a database
DELETE - deletes data from a database
INSERT INTO - inserts new data into a database
CREATE DATABASE - creates a new database
ALTER DATABASE - modifies a database
CREATE TABLE - creates a new table
ALTER TABLE - modifies a table
DROP TABLE - deletes a table
CREATE INDEX - creates an index (search key)
DROP INDEX - deletes an index



##
SELECT DISTINCT - statement to return only distrinct different values
SELECT COUNT(..) FROM CUTSOMERS - return the number
SELECT collumn1, collumn2,.. FROM table_name WHERE condition

## ORDER BY
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;


#
Use AND to add conditions

INSERT INTO table_name
VALUES (value1, value2, value3, ...);
The CustomerID column is an auto-increment field and will be generated automatically when a new record is inserted into the table.

A field with a NULL value is one that has been left blank during record creation.


SELECT column_names
FROM table_name
WHERE column_name IS NULL;


UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;


DELETE FROM table_name WHERE condition;

To remove the whole table:
DROP TABLE Customers;

SELECT TOP 3 * FROM Customers;
SELECT TOP 50 PERCENT * FROM Customers;
c
SELECT MAX(column_name)
FROM table_name
WHERE condition;


SELECT MIN(Price) AS SmallestPrice, CategoryID
FROM Products
GROUP BY CategoryID; 



SELECT COUNT(*) AS [Number of records]
FROM Products;

Name the column "Number of records":


The LIKE operator is used in a WHERE clause to search for a specified pattern in a column.

There are two wildcards often used in conjunction with the LIKE operator:

 The percent sign % represents zero, one, or multiple characters
 The underscore sign _ represents one, single character


 %	Represents zero or more characters
_	Represents a single character
[]	Represents any single character within the brackets *
^	Represents any character not in the brackets *
-	Represents any single character within the specified range *
{}	Represents any escaped character **

Different Types of SQL JOINs
Here are the different types of the JOINs in SQL:

(INNER) JOIN: Returns records that have matching values in both tables
LEFT (OUTER) JOIN: Returns all records from the left table, and the matched records from the right table
RIGHT (OUTER) JOIN: Returns all records from the right table, and the matched records from the left table
FULL (OUTER) JOIN: Returns all records when there is a match in either left or right table

#
SELECT Products.ProductID, Products.ProductName, Categories.CategoryName
FROM Products
INNER JOIN Categories ON Products.CategoryID = Categories.CategoryID

#
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
ORDER BY column_name(s);

eg. The following SQL statement lists the number of customers in each country:

SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country;

The INSERT INTO SELECT statement copies data from one table and inserts it into another table.

The INSERT INTO SELECT statement requires that the data types in source and target tables match.


Example
Copy only the German suppliers into "Customers":

INSERT INTO Customers (CustomerName, City, Country)
SELECT SupplierName, City, Country FROM Suppliers
WHERE Country='Germany';



The following SQL goes through conditions and returns a value when the first condition is met:

ExampleGet your own SQL Server
SELECT OrderID, Quantity,
CASE
    WHEN Quantity > 30 THEN 'The quantity is greater than 30'
    WHEN Quantity = 30 THEN 'The quantity is 30'
    ELSE 'The quantity is under 30'
END AS QuantityText
FROM OrderDetails;



The following SQL will order the customers by City. However, if City is NULL, then order by Country:

Example
SELECT CustomerName, City, Country
FROM Customers
ORDER BY
(CASE
    WHEN City IS NULL THEN Country
    ELSE City
END);



What is a Stored Procedure?
A stored procedure is a prepared SQL code that you can save, so the code can be reused over and over again.

So if you have an SQL query that you write over and over again, save it as a stored procedure, and then just call it to execute it.

You can also pass parameters to a stored procedure, so that the stored procedure can act based on the parameter value(s) that is passed.

Stored Procedure Syntax: 

CREATE PROCEDURE procedure_name
AS sql_statement
GO;
Execute a Stored Procedure
EXEC procedure_name;




CREATE DATABASE testDB;
DROP DATABASE testDB;


CREATE TABLE Persons (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255)
);


CREATE TABLE TestTable AS
SELECT customername, contactname
FROM customers;

The TRUNCATE TABLE statement is used to delete the data inside a table, but not the table itself:  TRUNCATE TABLE table_name;



NOT NULL - Ensures that a column cannot have a NULL value
UNIQUE - Ensures that all values in a column are different
PRIMARY KEY - A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table
FOREIGN KEY - Prevents actions that would destroy links between tables
CHECK - Ensures that the values in a column satisfies a specific condition
DEFAULT - Sets a default value for a column if no value is specified
CREATE INDEX - Used to create and retrieve data from the database very quickly

