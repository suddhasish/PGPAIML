Introduction
------------
So far, you have learnt how to use different commands and tools in SQL. There is, however, one marked difference between the data sets that we used and the ones that are used by the likes of Amazon and Uber.  The difference, of course, is the size of data.

 

We were using a small database for simplicity and ease of understanding. However, real-life data sets, such as those used by Amazon and Uber, would have millions or even billions of rows. Hence, although a 'select' operation on our dummy 'Market' table takes less than a fraction of a second, a similar query when applied on a table with millions of rows, for example, a 'customer' or 'product' table for Amazon, might take hours if not optimised properly.

 

In this session
You will understand the importance of query optimisation and learn about the various tips and techniques used in order to save runtime and the required computational power. You will also learn about some of the best practices that you should follow while writing SQL code.


Best Practices - I
-------------------
Suppose you want to buy a new car. Now, once you enter a showroom, a salesperson will explain the features of various cars to you, including each model's cost, mileage and so on. They will probably also mention an optimum range of speed that you should maintain while driving. But why is this important? Doing so ensures that the car continues to give the best possible mileage.

Similarly, you should follow best practices while writing any SQL code. This makes your code more readable for the people working on it and helps in maximising the output for your company. Let's watch the upcoming video to understand the importance of following best practices while writing queries.


1. Commenting various section of query we can use 
/* MULTI 
LINE */
2. Use table aliases when involve more than 2 table.
3. Simple and descripting names to column and table.

Best Practices - II
-------------------

In the previous segment, you understood the importance of following best practices while writing queries in SQL. 
Now, let's watch the next video to learn about some of the guidelines that you should follow while writing queries.

4. write keywords of SQL in all CAPS and column/table/variable in lower case.
5. Always use column name in order by clause instead of numbers.
6. Maintain Right indentation for diffrent sections of query.
7. use new lines for diffrent sections of query.
8. use new line for each column name.
9. USe the SQL Formatter or the the workbench Beutification Tool to format query.

Summary:
--------
Comment your code by using a hyphen (-) for a single line and (/* ... */) for multiple lines of code.
Always use table aliases when your query involves more than one source table.
Assign simple and descriptive names to columns and tables.
Write SQL keywords in upper case and the names of columns, tables and variables in lower case.

Always use column names in the 'order by' clause, instead of numbers.

Maintain the right indentation for different sections of a query.

Use new lines for different sections of a query.

Use a new line for each column name.

Use the SQL Formatter or the MySQL Workbench Beautification tool (Ctrl+B).


As you learnt in this video, the SQL Formatter is a handy online tool that enables you to customise the formatting of your code.
Make sure you are comfortable using the tool and make it a practice to use it while writing a query.

In the next segment, you will learn the concept of indexing and also understand how it optimises query execution.


http://www.dpriver.com/pp/sqlformat.htm


Indexing - I
-------------
In the previous segment, you learnt about some of the important best practices that you should follow while writing queries and understood the uses of the SQL Formatter. Now, one of the ways in which you can greatly reduce the runtime of your queries is by using indexing.
Indexing is the process of referring to only the required value(s) directly, instead of going through the entire table. 
This prevents the query engine from looking up values one by one; instead, it returns the exact value that you want right away.

In the upcoming video, Professor Ramanathan will explain why indexing is required for querying extremely large data sets.

As explained in this video, indexing is necessary for querying extremely large data sets. A primary key is an index because it helps in identifying each record in a table uniquely. Note that you cannot actually see an index, as it is an internal construct used in database engines to speed up queries.

Indexing - II
---------------

In the previous segment, you understood the importance of indexing in SQL. Now, let's watch the upcoming video to learn how indexing can be implemented in MySQL using the 'where' clause.                  

Make index based on attribute on where clause 

select <columns>
from from employee
where salary < 10000
or Dept_ID=5;  > build on Dept_ID

So, as you learnt in this video, MySQL has a specific DDL statement called CREATE INDEX, which is used for specifying the attribute on which you want to create an index. Generally, you would not have the permission to create such indices on a database. In such cases, you can ask the Database Administrator (DBA) to create the index for you.

 

In the next video, you will learn the syntaxes for creating, adding and dropping an index. You will also learn how to implement these commands to optimise your queries.

The command for creating an index is as follows:

CREATE INDEX index_name
ON table_name (column_1, column_2, ...);
 

The command for adding an index is as follows:

ALTER TABLE table_name
ADD INDEX index_name(column_1, column_2, ...);


Example:

CREATE INDEX filter_index PN market_fact_temp(cust_id.ship_id,prod_id)
 

ALTER TABLE market_fact_temp DROP INDEX filter_index;


The command for dropping an index is as follows:

ALTER TABLE table_name
DROP INDEX index_name;

Clustered vs Non-Clustered Indexing
------------------------------------


As you learnt in the previous segments, indexing is an important aspect of optimising queries. You can speed up query processing by applying filters on an indexed column. In the upcoming video, you will learn about the two types of indices.


SELECT * FROM market_fact_full;

CLUSTERED INDEX:

NON CLUSTERED INDEX:



Page act as primary key act as clustered index 
Chanpter number present in table of contents 
that access cluster key which indicates where perticuler chapter starts.


NON CLUSTER INDEX its a external table various pointers to primary table , s0 non cluster index takes slightly more memory than cluster index.


In this video, you learnt that there are two types of indices: clustered and non-clustered. The major differences between these are summarised in the table given below.

 

Clustered Index	                                        Non-Clustered Index
1. This is mostly the primary key of the table.	        1. This is a combination of one or more columns of the table.
2. It is present within the table.	                    2. The unique list of keys is present outside the table.
3. It does not require a separate mapping.	            3. The external table points to different sections of the main table.
4. It is relatively faster.	                            4. It is relatively slower.
 

In the next segment, you will learn about the order in which the various parts of an SQL query are executed in the database engine. This will enable you to write the most optimal query for a given problem statement.


You have OLTP data that’s used only for transactional reads and writing new rows. You know the primary key is an identity integer column. What type of index would you create for the primary key?

Clustered index — Your queries are probably always going to be looking up by PK to return data. If you store the data in the table ordered by that PK, SQL will be able to do this very quickly. New row additions to the table will always get put at the end because of the auto-incrementing identity column, not creating any overhead for having to insert data in a specific location in the ordered data.

You have a query that wants to return most or all of the columns from a table. What type of index would make this the most efficient?
Clustered index — Since all of the column values are stored in the same location as your indexed fields, SQL won’t have to go do any additional lookups to get all of the data you are requesting from it. If you created a nonclustered index you would have to INCLUDE all nonindexed columns, which would take up lots of space since you are essentially duplicating your entire table’s data.

You have a table that is constantly having values updated. These updated values are used as in your JOINs and WHERE clauses. What type of index would you add?
Nonclustered index — If our values are constantly changing, SQL only has to update the index and pointers while putting the actual data wherever it has available space on disk. Compare this to a clustered index where it has to put the inserted/updated data in the correct order, meaning potentially lots of operations to shift the data around if available free space doesn’t exist at that location.

Order of Query Execution - I
------------------------------

Suppose you are an aspiring singer who wants to make it in the music industry. In order to start your journey, you register to enter the reality TV show Indian Idol. You find yourself waiting in the line for hours with thousands of other contestants. After interacting with some of them, you realise that most of the contestants have no sense of tune, rhythm or music in general.
 

Can you think of a way in which you can make it easier for the judges to filter the applications? Think about it, and watch the next video to find out what Shreyas thinks is a feasible solution to this problem.


In this video, Shreyas explained one of the methods to filter the applications. In the module 'Database Design and Introduction to SQL', you learnt about the different aspects of a query, which appear in a particular order. The order in which the various SQL statements appear in a query is as follows:

SELECT
FROM
[JOIN]
WHERE
GROUP BY
HAVING
WINDOW
ORDER BY

However, the order in which the various statements are executed by the database engine is not the same. 
In the upcoming video, you will learn about the order of query execution, which will help you understand the need for reducing your data set as much as possible before querying it.


In this video, you learnt about the order in which the different SQL statements are executed in a query,

FROM (Including joins) >> WHERE >> GROUP BY >> HAVING >> WINDOW FUNCTION >> SELECT >> DISTINCT >> ORDER BY >> LIMIT and OFFSET


Some of the important points that you should keep in mind while writing a query are as follows:

1.  Use inner joins wherever possible to avoid having any unnecessary rows in the resultant table.
2.  Apply all the required filters to get only the required data values from multiple tables.
3.  Index the columns that are frequently used in the WHERE clause.
4.  Avoid using DISTINCT while using the GROUP BY clause, as it slows down query processing.
5.  Avoid using SELECT * as much as possible. Select only the required columns.
6.  Use the ORDER BY clause only if it is absolutely necessary, as it is processed late in a query.
7.  Avoid using LIMIT and OFFSET as much as possible. Instead, apply appropriate filters using the WHERE clause.


Order of Query Execution - II
----------------------------

Do you remember the problem statement where you wrote a query to determine the top ten customers from the 'market_star' schema using different rank functions? Let's revisit it and try to optimise the query. In the upcoming video, Shreyas will attempt to optimise the query using some optimisation techniques. Watch the upcoming video to understand how this changes the query execution time.


UNOPTIMIZED:

SELECT ord_id,
customer_name
FROM(
    slect m.* , c.customer_name,
RANK() OVER (ORDER BY sales DESC() AS sales_rank)
DENSE_RANK() OVER (ORDER BY sales DESC() AS sales_dense_rank)
ROW_NUMBER() OVER (ORDER BY sales DESC() AS sales_row_num)

FROM 
market_fact_full as m
INNER JOIN 
cust_dimen as c
ON m.cust_id = c.cust_id
ORDER BY sales desc
)
as a

LIMIT 10;


OPTIMIZED:

SELECT ord_id,
customer_name
FROM(
    slect ord_id , c.customer_name, --> selected limited columns
ROW_NUMBER() OVER (ORDER BY sales DESC() AS sales_row_num)  >> removed unnecessary

FROM 
market_fact_full as m
INNER JOIN 
cust_dimen as c
ON m.cust_id = c.cust_id
ORDER BY sales desc
)
as a
WHERE sales_row_num <=10;

>> REMOVED LIMIT

You must have noticed that you obtained the exact same result as you did earlier. However, the execution time of the unoptimised and the optimised queries are 141 ms and 15 ms, respectively. The order of magnitude is 
141
/
15
=
9.4.
 This is obviously a huge improvement and will only become more pronounced in a real-life data set, which will be much larger than what you are dealing with in this module.


Joins vs Nested Queries:

As you learnt previously, nested queries and joins are used for retrieving data from multiple tables. But is one of them more efficient than the other, especially in the case of large data sets? Well, it depends on the query processor. Query processors run optimising operations on your queries to ensure that the runtime is as low as possible. You will learn more about this in the upcoming video.


QUERY PROCESSOR:


When to use what?
--------------------

As you learnt in this video, executing a statement with the 'join' clause creates a join index, which is an internal indexing structure. This makes it more efficient than a nested query. However, a nested query would perform better than a join while querying data from a distributed database.

 

 Summary:
 ---------


 In this video, Shreyas briefly revisited the topics that were covered in this session, which can be summarised as follows:

 

Best practices: Some of the best practices that you should remember while writing an SQL query are as follows:

Comment your code using a hyphen '-' for a single line and '/* ... */' for multiple lines of code.
Always use table aliases when your query involves more than one source table.
Assign simple and descriptive names to columns and tables.
Write SQL keywords in upper case and the names of columns, tables and variables in lower case.

Always use column names in the 'order by' clause instead of numbers.

Maintain the right indentation for different sections of a query.

Use new lines for different sections of a query.

Use a new line for each column name.

Use the SQL Formatter or the MySQL Workbench Beautification tool (Ctrl+B) to clean your code.

 

Indexing: Indexing is an effective way to optimise query execution, as it selects the required data values instead of processing the entire table. The syntaxes for creating, adding and dropping an index are as follows:

CREATE INDEX index_name
ON table_name (column_1, column_2, ...);
 

ALTER TABLE table_name
ADD INDEX index_name(column_1, column_2, ...);
 

ALTER TABLE table_name
DROP INDEX index_name;
 

Clustered vs non-clustered indexing: The major differences between clustered and non-clustered indexing are summarised in the table given below.

 

Clustered Index	Non-Clustered Index
1. This is mostly the primary key of the table.	1. It is a combination of one or more columns of the table.
2. It is present within the table.	2. The unique list of keys is present outside the table.
3. It does not require a separate mapping.	3. The external table points to different sections of the main table.
4. It is relatively faster.	4. It is relatively slower.
 

 

Order of query execution: The order in which the different SQL statements are executed in a query is depicted in the diagram given below.

Order of Query Execution
Order of Query Execution
 

Query optimisation techniques: The points that you should remember while writing a query are as follows:

Use inner joins wherever possible to avoid having any unnecessary rows in the resultant table.
Apply all the required filters to get only the required data values from multiple tables.
Index the columns that are frequently used in the WHERE clause.
Avoid using DISTINCT while using the GROUP BY clause, as it slows down query processing.
Avoid using SELECT * as much as possible. Select only the required columns.
Use the ORDER BY clause only if it is absolutely necessary, as it is processed late in a query.
Avoid using LIMIT and OFFSET as much as possible. Instead, apply appropriate filters using the WHERE clause.
 

Joins vs nested queries: Executing a statement with the 'join' clause creates a join index, which is an internal indexing structure. This makes it more efficient than a nested query. However, a nested query would perform better than a join while querying data from a distributed database.

In a distributed database, tables are stored in different locations instead of a local system. In this case, a nested query would perform better than a join, as we can extract relevant information from different tables located in different computers. We can then merge the values in order to obtain the desired result. In the case of a join, we would need to create a large table from the existing tables, and filtering this large table would require comparatively more time.



