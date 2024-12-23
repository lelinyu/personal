# Lecture 24 SQL I

1. Questions
2. Declarative Programming
    1. You just tell it what to do, not really about how it is
3. Relational Databases
    1. Each table is made up of columns and rows of data
4. Tables
    1. Have rows and columns
    2. Columns have a name and a type of value
    3. Rows have values for each column
5. SQL Overview
    1. select - either create a new table from scratch, or grab data from another table
    2. create table - gives a global name to a table
    3. Union - concatenates tables together to make bigger ones
    4. All statements in SQL must end with a semicolon
6. Select Statements
    1. Select will return 0 or more rows that match our query (the computer will just do it for us)
    2. Return all rows of tables
        1. SELECT * FROM cities
        2. The * means get everything (in this case, every column)
    3. Renaming columns
        1. Select latitude as lat, longitude as lon FROM cities
    4. Manipulate the column value
        1. select city, longitude * 1000 as long_lon
7. SQL Case-sensitive?
    1. Convention - capital letters from the keywords and lowercase for the rest
8. Optional clauses for Select
    1. There are optional clauses for the select statement
9. First Motivation: If
    1. Where keyword in SQL
        1. Lets you filter out rows
        2. SELECT * FROM menu WHERE price < 15;
            1. filtering out where price is less than 15
        3. SELECT item FROM menu WHERE price < 15:
            1. returns the name of items where the price is under 15
10. Second Motivation: Sorting
    1. We can use the order by method
    2. ORDER by will let you specify the order of the rows
    3. When you are sorting, default is ascending
11. Third Motivation: smaller output
    1. We might want to only see the top 3 items by price
    2. LIMIT clause limits the number of rows that are output
12. Combining it together
    1. We can use WHERE, ORDER BY, and LIMIT being used by themselves
    2. SQL has a specific order from each keyword
        1. SELECT - FROM - WHERE - ORDER BY - LIMIT
13. SQL Joins
    1. Combining Related Tables
        1. Usually better to keep tables relatively simple and join them together
        2. Storing everything in 1 table ends up taking far more space than storing them as two smaller tables
14. Joining Tables
    1. We do complete join in CS61a
        1. Every row in table 1 is matched with every row from table 2 and all the columns are kept
    2. Joins
        1. Joining two tables together 3 columns, 50 rows and another table 5 columns, 3 rows
        2. 8 columns, 150 rows
15. Problems with Joining
    1. A lot of rows that we create are useless
    2. This means that WHERE can filter out junk rows
16. Column Names when Joining
    1. Sometimes, we have duplicate names
17. Aliasing
    1. Basically renaming columns
    2.