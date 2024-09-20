Introduction
So far, you have learnt about some of the basic and advanced SQL concepts.
So, let's continue with this module and learn more about case statements and stored routines.
You will also understand the importance of using these and other SQL features in this session.

 

In this session
You will learn about case statements, which are used for classifying your results based on certain conditions.
You will also learn about stored routines such as user-defined functions and stored procedures, which are used for storing and reusing large queries to solve complex problem statements efficiently. Finally, you will learn about cursors and their uses.

Case Statements - I
--------------------
You may have encountered if-else and case statements in some programming languages. Now, suppose you are in school and have to follow a set time-table, according to which you need to bring the textbooks of certain subjects on certain days to class. Consider the following time-table:

Monday: English and Hindi
Tuesday: English and Maths
Wednesday: Science and Social Science
Thursday: Maths and Social Science
Friday: Hindi and Science
 

This is a basic example where you can determine the subjects that you would be studying in class on certain days by just looking at the list. 
However, the data around us is enormous and complex. There may be several conditions that you may need to set and many actions to be performed according to each of these conditions.

In the upcoming video, you will learn about case statements in detail.

As you learnt in the video, the syntax for writing a case statement is as follows:

CASE
  WHEN condition1 THEN result1
  WHEN condition2 THEN result2
  .
  .
  WHEN conditionN THEN resultN
  ELSE result
END AS column_name;
 

So, now that you know the syntax for writing a case statement, in the next video, Shreyas will walk you through a practical example where you will classify orders based on the amount of profit or loss incurred.

-- CAse when Example
/* profit < -500 huge loss
   profit -500 to 0 --> bearable loss
   profit 0 to 500 --> decent profit
   profit  > 500 --> great profit
*/
SELECT
    market_fact_id,
    profit,
    CASE
        WHEN profit < -500 THEN 'Huge Loss'
        WHEN profit BETWEEN -500 AND 0 THEN 'Bearable Loss'
        WHEN profit BETWEEN 0 AND 500 THEN 'Decent profit' 
        ELSE 'Great Profit'
    END AS Profit_type
FROM
    market_fact_full;

----

SELECT 
    Name,Salary,
    CASE 
        WHEN Salary <= 2.5 THEN 'A'
        WHEN Salary BETWEEN 2.51 AND 5 THEN 'B'
        WHEN Salary BETWEEN 5.01 AND 10 THEN 'C'
        ELSE 'D'
    END AS "Tax Slab"
FROM
    Salaries



Case Statements - II
----------------------
In the previous segment, you saw a relatively simple example of a case statement. In the video, you will learn how a complex problem can be solved using case statements, CTEs(COMMON TABLE EXPRESSION) and joins in conjunction. While solving this problem, you will realise how important it is to understand basic SQL concepts and when and where to apply them.

-- Classify customers on the following criteria 
-- Top 10% of customers as Gold 
-- Next 40% of customers as Silver
-- Rest 50% of customers as Bronze 

WITH cust_summary AS
(
SELECT  m.cust_id,
        c.customer_name,
        ROUND(SUM(m.sales)) as total_sales,
        PERCENT_RANK() OVER(ORDER BY ROUND(SUM(m.sales)) ASC) as perc_rank
FROM
    market_fact_full as m
    LEFT JOIN
    cust_dimen as c
ON
    m.cust_id=c.cust_id
GROUP BY cust_id
)
SELECT *,
        CASE
            WHEN perc_rank >= 0.1 THEN 'Gold'
            WHEN perc_rank BETWEEN 0.05 AND 0.09 THEN 'Silver'
            ELSE 'Bronze'
        END AS customer_category
FROM cust_summary;


UDFs:
-----
You already know how to deploy various in-built MySQL functions, such as sum(), avg() and concat(), to make querying easier. Now, it is possible to find the sum of two numbers in MySQL without using the sum() function. You can use the arithmetic addition operator (+) for this purpose. Similarly, you can use the arithmetic addition and division operators to find the average of two numbers. 

 

The sum() and avg() functions are preferred because they are easier to use and also increase the readability of the code. Another important factor is reusability. You do not need to see the entire definition behind the sum() function every time you use it; all you need is the name sum() to invoke the function whenever you want to determine the sum of two numbers.

 

However, there are operations that you may want to repeat multiple times in a piece of code because they do not have an in-built function. This is where you must use user-defined functions (UDFs) or stored functions. In the upcoming video, Shreyas will explain the syntax of UDFs.


As you learnt in this video, the syntax for writing a UDF is as follows:

DELIMITER $$

CREATE FUNCTION function_name(func_parameter1, func_parameter2, ...)
  RETURN datatype [characteristics]
/*      func_body      */
  BEGIN
    <SQL Statements>
    RETURN expression;
END ; $$

DELIMITER ;
 

CALL function_name;



Remember the following points:

The CREATE FUNCTION is also a DDL statement.
The function body must contain one RETURN statement.


So, now that you have understood the importance of UDFs and are familiar with the syntax, in the upcoming video, you will see a practical demonstration of the same. You will solve the same problem statement that was discussed in the segments on case Statements.


-- This is determining profit and loss category .

DELIMITER $$

CREATE FUNCTION profitType(profit int)
RETURNS VARCHAR(30) DETERMINISTIC 
BEGIN
DECLARE message VARCHAR(30);
IF profit<-500 THEN
    SET message = 'Huge Loss';
ELSEIF profit BETWEEN -500 AND 0 THEN
    SET message = 'Bearable Loss';
ELSEIF profit BETWEEN 0 AND 500 THEN
    SET message = 'Decent Profit';
ELSE 
    SET message = 'Great Profit';
END IF;

RETURN message;
END;

DELIMITER;

SELECT profitType(10) as Function_output;

Stored functions Dont always return the same result for the same input parameters by default to do that we need to specify 
the Deterministic keyword to ensure that the output is the same for the same input values. This is disabled in MySQL by default.


UDFs vs Case Statements
-----------------------
You learnt how to categorise orders based on the profit or loss incurred. This problem statement was solved using two methods - case statements and UDFs. Are there any advantages of using one method over the other? If so, what are they?


A case statement is preferable if you just need to categorise existing data values based on certain parameters.

A UDF using case statements is preferable if you need to categorise existing as well as incoming data values based on certain parameters.


Stored Procedures:
----------------------
In the previous segment, you were introduced to a UDF, which is a type of stored routine. There is another type of stored routine in SQL: a stored procedure. This is similar to a UDF but differs in certain ways. Watch the next video to learn more about stored procedures.


Why to use Stored proc:
---------
UDF has limited scope Stored proc is advance way of calling 
multiple select statement in query like 10 line select statement again and again.


As you learnt in this video, the syntax for writing a stored procedure is as follows:

DELIMITER $$

CREATE PROCEDURE Procedure_name (<Paramter List>)
BEGIN
  <SQL Statements>
END $$

DELIMITER ;
 

CALL Procedure_name;

In the next video, you will see a demonstration of how stored procedures are used in SQL. Note that this is a simple example, but stored procedures can become quite complex according to the business use case.

-- Procedure which returns customer IDand rounded sales grettar than sales_input provided and order by sales in assending order.

DELIMITTER $$
CREATE PROCEDURE get_sales_customer (sales_input INT)
BEGIN
    SELECT DISTINCT cust_id,
                    ROUND(sales) AS sales_amount
    FROM 
        market_fact_full
    WHERE ROUND(sales)>sales_input
    ORDER BY sales;
END $$
DELIMITER;

CALL get_sales_customer(300);

DROP PROCEDURE get_sales_customer;


In this video, you learnt how to use stored procedures in SQL. Although the syntax of a stored procedure is similar to that of UDFs, there are many differences between the two. In the next video, you will learn about these differences in detail.


The differences between UDFs and stored procedures are summarised in the table given below.

 

UDF	                                                            Stored Procedure
1. It supports only the input parameter, not the output.	1. It supports input, output and input-output parameters.
2. It cannot call a stored procedure.	                    2. It can call a UDF.
3. It can be called using any SELECT statement.         	3. It can be called using only a CALL statement.
4. It must return a value.	                                4. It need not return a value.
5. Only the 'select' operation is allowed.              	5. All database operations are allowed.


Cursors:
---------
While stored routines are a great way to store and reuse logic in code as required, they do have some disadvantages. 
You will learn what these are. You will also be introduced to the concept of cursors. 
Cursors are used to individually process each row that is returned in a query. 
In the upcoming video, Professor Ramanathan will take you through an example and explain how cursors are used in it.

Ability look at each row and do very specific processing on each row. Example loan prcessing if certain condition match then loan approved.
It may require complex logic which is not possible to express as simple IF statement.

We can setup cursor which contains all loan application and will iterate through that cursor one by one and process individually.
another programming construct which not found in normal SQL only there in stored function where in I can Iterate.
looked at condition in format of if and setup iteration using cursors as well.

Stored functions and procedures are not portable across DBMS products.

The DECLARE Statement
Using the DECLARE statement you can declare a cursor and associate It with the SELECT statement which fetches the desired records from a table. This SELECT statement associated with a cursor does not allow INTO clause.

Once you declare a cursor you can retrieve records from it using the FETCH statement. You need to make sure the cursor declaration precedes handler declarations. You can create use cursors in a single stored program.

Syntax
-------
Following is the syntax of the MySQL Cursor DECLARE Statement −

DECLARE cursor_name CURSOR FOR select_statement;
Example
Assume we have created a table with name tutorials in MySQL database using CREATE statement as shown below −

CREATE TABLE tutorials (
   ID INT PRIMARY KEY,
   TITLE VARCHAR(100),
   AUTHOR VARCHAR(40),
   DATE VARCHAR(40)
);
Now, we will insert 5 records in tutorials table using INSERT statements −

Insert into tutorials values
(1, 'Java', 'Krishna', '2019-09-01'),
(2, 'JFreeCharts', 'Satish', '2019-05-01'),
(3, 'JavaSprings', 'Amit', '2019-05-01'),
(4, 'Android', 'Ram', '2019-03-01'),
(5, 'Cassandra', 'Pruthvi', '2019-04-06');
Let us create another table to back up the data −

CREATE TABLE backup (
   ID INT,
   TITLE VARCHAR(100),
   AUTHOR VARCHAR(40),
   DATE VARCHAR(40)
);
Following procedure backups the contents of the tutorials table to the backup table using cursors −

DELIMITER //
CREATE PROCEDURE ExampleProc()
   BEGIN
      DECLARE done INT DEFAULT 0;
      DECLARE tutorialID INTEGER;
      DECLARE tutorialTitle, tutorialAuthor, 
	  tutorialDate VARCHAR(20);
      DECLARE cur CURSOR FOR SELECT * FROM tutorials;
      DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = 1;
      OPEN cur;
      label: LOOP
      FETCH cur INTO tutorialID, tutorialTitle, tutorialAuthor, 
	  tutorialDate;
      INSERT INTO backup VALUES(tutorialID, tutorialTitle, 
	  tutorialAuthor, tutorialDate);
      IF done = 1 THEN LEAVE label;
      END IF;
      END LOOP;
      CLOSE cur;
   END//
DELIMITER ;


You can call the above procedure as shown below −

CALL ExampleProc;
If you verify the contents of the backup table you can see the inserted records as shown below −

select * from backup;
Output
The above query produces the following output −

ID	TITLE	AUTHOR	DATE
1	Java	Krishna	2019-09-01
2	JFreeCharts	Satish	2019-05-01
3	JavaSprings	Amit	2019-05-01
4	Android	Ram	2019-03-01
5	Cassandra	Pruthvi	2019-04-06


You can use cursors for bank account transactions to move money back and forth between the bank and a customer's account in that bank in real-time. You can do this individually for each customer at all times, by processing each banking request individually.
































