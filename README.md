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