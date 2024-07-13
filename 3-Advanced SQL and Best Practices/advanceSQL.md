Introduction
--------------
In the previous module, you learnt about databases and their various constituents. You also understood the steps involved in designing a database, which are as follows: 

Ideating and designing an ERD
Adding a database schema, its various tables, the values in each table and the constraints
Querying a database using several SQL statements to extract valuable insights from the data
 

So far, you have covered all the basic concepts of SQL. However, you should also be aware of some advanced concepts of SQL such as window functions, query optimisation, case statements, stored functions and cursors and the best practices for writing queries. These are useful tools for handling several use cases and will help you solve complex questions easily.

 

In the previous module, you learnt how to order employees by their salary in an example data set. One method to do this would be to categorise them by their values. For example, you can divide them into the following categories:

Employees earning less than ₹2,50,000 per year
Employees earning greater than or equal to ₹2,50,000 per year
 

The first category of employees would be exempted from paying any tax and need not go through some of the additional checks that the second category of employees would be required to go through. You can solve this problem statement using a filter condition in a 'where' clause.

 

Now, imagine you are working in a bank and need to identify and classify your customers on the following criteria:

Top 10% of customers: Platinum
Next 10% of customers: Gold
Next 20% of customer: Silver
Rest of the customers: Regular
 

Your bank intends to roll out different schemes for these classes of customers in exchange for their loyalty. But how do you solve such a seemingly complex problem statement? You will find the answer to this question in the upcoming sessions.

 

In this session
You will be introduced to the concept of windowing functions. You will learn about the 'over' and 'partition' clauses used to implement windowing. After going through this session, you should be able to use window functions such as rank(), dense_rank() and percent_rank() in your queries.

 

You will also be introduced to the concept of named windows. You will learn about frames and how they move within a window. Next, you will learn about the various applications of windowing, including one to calculate an element known as a moving average. Finally, you will learn about the 'lead' and 'lag' functions that are used to fetch data from succeeding and preceding rows, respectively.





Rank Functions - I
-------------------

In the previous module, you learnt about and executed the 'group by' clause for collecting the facts about certain categories. Now, you may have noticed that using the 'group by' clause reduces the number of rows. It also leads to a loss of individual properties of various rows.


To address the two points mentioned above, i.e., reduction of rows and loss of individual properties of rows, SQL provides a special clause known as the 'over' clause, which displays group characteristics in the form of a new column. This leads to the preservation of the individual characteristics of different rows while displaying the group characteristics simultaneously. Let's watch the upcoming video to understand the need for rank functions in SQL.

##  Rank function is required to analyze top 10 bottom 10 or mid 10 ranked items in efficient manner which cant be possible via limit clause.
##  Rank is kind of advance analytics version of SQL.


In the next video, Shreyas will walk you through the syntax for writing queries with rank functions.


So, as you learnt in this video, the syntax used for writing a rank function is as follows:

RANK() OVER (
  PARTITION BY <expression>[{,<expression>...}]
  ORDER BY <expression> [ASC|DESC], [{,<expression>...}]
)

Note: You will learn more about the 'partition by' clause later in this session. 
In the upcoming video, you will get a demonstration of window functions (also known as analytic functions). 
You will also understand the importance of ranking values based on the required criteria.


select customer_name,
	   ord_id,
       ROUND(sales) as rounded_sales,
       RANK() OVER (ORDER BY sales DESC) AS sales_rank
FROM market_fact_full as m
INNER JOIN 
cust_dimen as c
ON m.cust_id = c.cust_id
WHERE customer_name='RICK WILSON'



-- Top 10 sales order from a customer using common table expression 

WITH rank_info AS
(
select customer_name,
	   ord_id,
       ROUND(sales) as rounded_sales,
       RANK() OVER (ORDER BY sales DESC) AS sales_rank
FROM market_fact_full as m
INNER JOIN 
cust_dimen as c
ON m.cust_id = c.cust_id
WHERE customer_name='RICK WILSON'
)
select * from rank_info 
WHERE sales_rank<=10

--- Write a query to retrieve the ranks of the products in decreasing order of their quantities in stock.


select quantityInStock, 
       RANK() OVER (ORDER BY quantityInStock desc) AS quantityRank
from products;

Rank Functions - II
---------------------
In the previous segment, you learnt how rank functions are implemented to rank values based on certain criteria. 
In the upcoming videos, Shreyas will demonstrate the difference between the 'rank' and 'dense rank' functions. 
You will also learn about another type of rank function, which is known as the 'per cent rank' function.

In this video, you learnt that there are different types of rank functions, which are as follows:

RANK(): Rank of the current row within its partition, with gaps
DENSE_RANK(): Rank of the current row within its partition, without gaps
PERCENT_RANK(): Percentage rank value, which always lies between 0 and 1
 

The syntax for writing the 'dense rank' and 'per cent rank' functions are as follows:

The syntax for writing the 'dense rank' and 'per cent rank' functions are as follows:

DENSE_RANK() OVER (
  PARTITION BY <expression>[{,<expression>...}]
  ORDER BY <expression> [ASC|DESC], [{,<expression>...}]
)
 

PERCENT_RANK() OVER (
  PARTITION BY <expression>[{,<expression>...}]
  ORDER BY <expression> [ASC|DESC], [{,<expression>...}]
)

-- Example for Dense Rank
SELECT ord_id, 
		discount,
        customer_name,
        RANK() OVER (ORDER BY discount DESC) as disc_rank,
        DENSE_RANK() OVER (ORDER BY discount DESC) as disc_dense__rank
        
FROM  market_fact_full m
INNER JOIN cust_dimen as c 
ON m.cust_id = c.cust_id
WHERE customer_name = 'RICK WILSON' ;

So, as you saw in the video, the 'rank' function need not have consecutive values, but the 'dense rank' function must have these values. For example, consider the table given below. It contains the marks obtained by the top three students in the 12th board exams in India conducted by the CBSE board.

 

CBSE Marks (12th)
Name	          Marks (out of 500)	Rank	Dense Rank
Shubham Agarwal	495	                  1	    1
Paritosh Sinha	495	                  1	    1
Dilip Kumar	    492	                  3	    2
 

Notice how Dilip's rank is 3 but his dense rank is 2. This is because the rank increases whenever the previous entries have similar values. If 10 students, instead of two, had scored 495 marks, then his rank would have become 11, but his dense rank would have remained 2.

Rank Functions - III
---------------
In the previous segment, you learnt about the 'rank', 'dense rank' and 'per cent rank' functions. In this segment, you will learn about the fourth type of rank function: the 'row number' function. In the upcoming video, you will learn more about this function and its uses.

So, as Shreyas mentioned, you can use the 'row number' function for the following use cases:

To determine the top 10 selling products out of a large variety of products
To determine the top three winners in a car race
To find the top five areas in different cities in terms of GDP growth
 

The main advantage of the 'row number' function over all the other types of rank functions is that it returns unique values. The syntax for writing the 'row number' function is as follows:


ROW_NUMBER() OVER (
  PARTITION BY <expression>[{,<expression>...}]
  ORDER BY <expression> [ASC|DESC], [{,<expression>...}]
)


-- Number of orders each customer has placed
select customer_name,
		COUNT(DISTINCT ord_id) AS order_count,
		RANK() OVER (ORDER BY COUNT(DISTINCT ord_id) DESC) AS order_rank,
		DENSE_RANK() OVER (ORDER BY COUNT(DISTINCT ord_id) DESC) order_dense_rank,
		ROW_NUMBER() OVER (ORDER BY COUNT(DISTINCT ord_id) DESC) order_row_number
FROM market_fact_full AS m
INNER JOIN
cust_dimen AS c
ON m.cust_id=c.cust_id
GROUP BY customer_name;


customer_name	order_count	order_rank	order_dense_rank	order_row_number
DARREN BUDD	    26	          1	          1             	1
BRAD THOMAS	    24           	2         	2	              2
ED BRAXTON	    22            3	          3             	3
JACK O'BRIANT	  21	          4	          4	              4
CARLOS SOLTERO	20	          5	          5             	5
GIULIETTA DORTCH 19	          6	          6              	6
QUINCY JONES	   19	          6	          6	              7
ADAM HART	      18	          8	          7              	8 --> order_row_number is increasing in sequence but   order_rank and is putting all same value in same rank
MARK COUSINS	  18	          8	          7	              9     order_dense_rank is putting all in sequnce but it is not skiping the rank number like rank does.
NORA PRICE	     18	          8	          7	              10  



Now that you know how to use different rank functions in your query, it's time to understand what the 'partition by' clause does in the multiple queries that you wrote. You will learn more about partitions in the next segment.

Partitioning:
--------------
You must have noticed that there was a 'partition by' clause in the syntax for the rank functions. But what exactly is this clause used for? You will learn more about this in the upcoming video.

As you learnt in this video, the 'rank' and 'dense rank' functions are used with the 'over' clause. However, this may not be enough if you want to rank groups of rows based on certain criteria. For example, you can rank the top 10 batsmen in the world using the 'rank' function. But what if you want to find out the top three batsmen from each team? This is where you would want to use the 'partition' and 'over' clauses together. So, let's watch the next video and learn more about these clauses and their uses.



-- Partitioning example 

WITH shipping_summary AS (
SELECT ship_mode,
	    MONTH(ship_date) AS shipping_month,
        COUNT(*) as shipments
FROM
shipping_dimen
GROUP BY ship_mode,MONTH(ship_date)
)
SELECT *,
RANK() OVER (PARTITION BY ship_mode ORDER BY shipments DESC) AS shipping_rank,
DENSE_RANK() OVER (PARTITION BY ship_mode ORDER BY shipments DESC) AS shipping_dense_rank,
ROW_NUMBER() OVER (PARTITION BY ship_mode ORDER BY shipments DESC) AS shipping_row_number
FROM shipping_summary;


ship_mode	        shipping_month	shipments	shipping_rank	shipping_dense_rank	shipping_row_number
DELIVERY TRUCK	      12	        107	        1	              1	                  1
DELIVERY TRUCK	       3	        105	        2	              2	                  2
DELIVERY TRUCK	       4	        105	        2	              2	                  3
DELIVERY TRUCK	       1	        100	        4	              3                  	4
DELIVERY TRUCK       	7	          95	        5	              4	                   5
DELIVERY TRUCK      	5         	92	        6             	5	                    6
DELIVERY TRUCK      	6	          91	        7	              6                   	7
DELIVERY TRUCK      	2         	89	        8	              7	                    8
DELIVERY TRUCK      	8	          88        	9             	8	                    9
DELIVERY            	9	          86	        10            	9	                    10
DELIVERY TRUCK      	11	        86	        10	            9	                    11
DELIVERY TRUCK	      10	        81	        12	            10	                  12
EXPRESS AIR	          12	        96	        1	              1	                    1
EXPRESS AIR          	7         	91	        2	              2	                    2
EXPRESS AIR         	4	          86	        3               3	                    3
EXPRESS AIR         	5	          86	        3	              3	                    4
EXPRESS AIR         	8	          85	        5	              4                   	5
EXPRESS AIR         	11	        85	        5	              4	                    6
EXPRESS AIR         	10	        80	        7	              5                   	7
EXPRESS AIR	          9	          80	        7	              5                   	8
EXPRESS AIR         	3	          75	        9	              6                   	9
EXPRESS AIR	          6         	73	        10	            7                   	10
EXPRESS AIR         	1         	69        	11	            8	                    11
EXPRESS AIR	          2         	63	        12	            9                   	12
REGULAR AIR	          8	          512	        1	              1	                    1
REGULAR AIR	          5	          504	        2	              2	                    2
REGULAR AIR	          9	          488       	3	              3	                    3
REGULAR AIR	          7	          471	        4	              4	                    4

So, now that you have learnt about window functions and partitioning, try to attempt the following question.


Named Windows
--------------

In the previous segment, you learnt that we can use multiple window functions in the same query. Now, you may have noticed that in one of the queries, we used the same window in both the window functions. This makes the code heavier and difficult to tweak as and when the need arises. So, in this segment, you will learn how to create, store and use named windows.


-- Named window function
select ord_id,discount,customer_name,
		RANK() OVER w AS disc_rank, --> here we are calling the Named window.
		DENSE_RANK() OVER w disc_dense_rank,
		ROW_NUMBER() OVER w disc_row_number
FROM market_fact_full AS m
INNER JOIN
cust_dimen AS c
ON m.cust_id=c.cust_id
WHERE customer_name= 'RICK WILSON'
WINDOW w AS (ORDER BY discount DESC); --> Here we are naming the window as w 

-- Using partition

select ord_id,discount,customer_name,
		RANK() OVER w AS disc_rank,
		DENSE_RANK() OVER w disc_dense_rank,
		ROW_NUMBER() OVER w disc_row_number
FROM market_fact_full AS m
INNER JOIN
cust_dimen AS c
ON m.cust_id=c.cust_id
WINDOW w AS (PARTITION BY customer_name ORDER BY discount DESC); --> Same like above we are Naming the WINDOW by this time including partition.

So, as you learnt in this video, the same window can be used to define multiple 'over' clauses.  You can define the window once, give it a name and then refer to the name in the 'over' clauses. A named window makes it easier to experiment with multiple window definitions and observe their effects on the query results. You only need to modify the window definition in the 'window' clause, rather than using multiple 'over' clause definitions.



The syntax for writing a named window is as follows:

WINDOW window_name AS (window_spec)
  [, window_name AS (window_spec)] ...
 

The order in which the various SQL statements appear in a query is as follows: 

SELECT
FROM
JOIN
WHERE
GROUP BY
HAVING
WINDOW
ORDER BY

SELECT *,
RANK() OVER w 'Rank',
DENSE_RANK() OVER w 'Dense Rank',
PERCENT_RANK() OVER w 'Percent Rank'
FROM shipping_dimen
WINDOW w AS (PARTITION BY ship_mode
  ORDER BY COUNT(*));

Frames - I
------------- 

THIS IS MAINLY USED WHEN SPECIFIC FIELD TO CREATE WINDOW IS NOT AVILABLE AND WE HAVE TO USE FRAME. 
NEED TO DEFINE WINDOW BY PRECEEDING AND FOLLOWING KIND OF INPUTS AND CAN CHANGE THE LENGTH OF THE WINDOW.

In the previous segment, you were introduced to the concept of windowing functions and windows. You also learnt how to use basic aggregate functions, including the 'count()' function, in windowing.

In this segment, you will learn about the concept of frames and understand how frames move while a query is being executed. You will also learn how to implement moving averages in SQL. You can get a rough idea of the importance of calculating moving averages, especially in the stock market sector, by clicking on the link provided below and quickly going through the article on Investopedia.

Note that you will only be calculating simple moving averages in this course. In the upcoming video, Shreyas will explain the concept of frames with the help of an example.

Running total: It add each row value sequentially till we reach the end 
Moving average: This takes some certin fix number point from history and calclate the average.
moving average of 7 record takes 7 rows as frame and shift down by 1 cell.


In this video, you learnt how frames are useful in SQL and when they can be applied to answer relevant questions asked by stakeholders. In the next video, you will see a demonstration of how to use frames in SQL.


Shipping: Summarize entire shipping based on ship date running total shipping cost and moving average.

-- Frame example

WITH daily_shipping_summary AS
(
SELECT ship_date,
    SUM(shipping_cost) AS daily_total

FROM
market_fact_full AS m
INNER JOIN
shipping_dimen s
ON m.ship_id=s.ship_id
GROUP BY ship_date
)
SELECT *,
      SUM(daily_total) OVER w1 AS running_total,            --> This is calculating SUM / running total over the specified window w1
      AVG(daily_total) OVER w2 AS moving_avg                --> This is calculating Moving average over the specified window w1

FROM daily_shipping_summary
WINDOW w1 AS (ORDER BY daily_total ROWS UNBOUNDED PRECEDING),
w2 AS (ORDER BY daily_total ROWS 6 PRECEDING);    ---> This looks for current row+ previous 6 rows = total 7 row moving average.



Question:
---------
The table given below contains the number of runs scored by Virat Kohli over the time period 2008-2019. Add another column which displays the 5-year moving average of the number of runs scored.

+------+------+
| Year | Runs |
+------+------+
| 2008 |  159 |
| 2009 |  328 |
| 2010 |  995 |
| 2011 | 1382 |
| 2012 | 1028 |
| 2013 | 1268 |
| 2014 | 1054 |
| 2015 |  623 |
| 2016 |  739 |
| 2017 | 1460 |
| 2018 | 1202 |
| 2019 | 1377 |
+------+------+

Query:
------
select Year,Runs,
       avg(Runs) OVER w AS Moving_Average
FROM Kohli_Batting
WINDOW w AS (ORDER BY year ROWS 4 PRECEDING);

If you look at the output obtained after writing the correct query, you will notice that Kohli's five-year average has been about 1,000 since 2013. This indicates that he has been a consistent player. Similarly, you can write queries to obtain one-year moving averages to extract and understand any trend in the data in the question given above.

Output:

+------+------+----------------+
| Year | Runs | Moving_Average |
+------+------+----------------+
| 2008 |  159 |       159.0000 |
| 2009 |  328 |       243.5000 |
| 2010 |  995 |       494.0000 |
| 2011 | 1382 |       716.0000 |
| 2012 | 1028 |       778.4000 |
| 2013 | 1268 |      1000.2000 |
| 2014 | 1054 |      1145.4000 |
| 2015 |  623 |      1071.0000 |
| 2016 |  739 |       942.4000 |
| 2017 | 1460 |      1028.8000 |
| 2018 | 1202 |      1015.6000 |
| 2019 | 1377 |      1080.2000 |
+------+------+----------------+

In the next segment, Shreyas will break down the frame clause and analyse its components. This will help you to understand frames better and use the appropriate keywords and solve problems.


Frames - II (LOOK INTO IMAGE IN GIT REPO)
--------------
In the previous segment, you learnt how to write a simple query using a frame. Now, let's watch the upcoming video to understand the structure of a frame in depth and learn about its possible constituents.

ROW1
ROW2
ROW3
ROW4
ROW5 --> Current ROW.
ROW6
ROW7
ROW8
ROW9
ROW10
ROW11

ORDER BY X ROWS 3 PRECEDING --> Operation will be performed on ROW2 to ROW 5.
ORDER BY X ROWS BETWEEN 1 PRECEDING AND 1 FOLLOWING --> Operation will be performed on ROW4 to ROW6
ORDER BY X ASC ROWS BETWEEN 1 FOLLOWING AND 3 FOLLOWING --> ROW 6 to ROW8  --> Assending is default.
ORDR BY X DESC ROWS BETWEEN 1 FOLLOWING AND UNBOUNDED FOLLOWING --> ROW4 to ROW1 as Frame is reversed.


You also learnt about the usage of several keywords in the 'frame' clause such as UNBOUNDED, PRECEDING, FOLLOWING, BETWEEN and so on. Note that the order of the rows gets reversed when you use the DESC keyword in the query. Now, before moving on to the next segment, try to solve the questions given below to test your knowledge of frames.


Lead and Lag Functions:
-----------------------

In the earlier segments, you learnt how to calculate moving averages in SQL using frames. 
Identifying frequent customers is a commonly observed business requirement for retail chains. 
The 'lead' and 'lag' functions can be quite helpful in this case.


So, as explained in this video, another use case of the 'lead' and 'lag' functions is to determine whether consecutive orders were shipped using the same shipping mode. This can be extremely helpful in optimising the shipping and delivery of products.

 
The syntax for using the 'lead' and 'lag' functions are as follows:


LEAD(expr[, offset[, default]])   --> Default value is for last row as nothing is defined after that
  OVER (Window_specification | Window_name) 

LAG(expr[, offset[, default]])
  OVER (Window_specification | Window_name)

LEAD:
-----

SELECT seller_name, sale_value,
  LEAD(sale_value) OVER(ORDER BY sale_value) as next_sale_value
FROM sale;

the LEAD() function takes three arguments: the name of a column or an expression, the offset to be skipped below, and the default value to be returned if the stored value obtained from the row below is empty. Only the first argument is required. The third argument, the default value, can be specified only if you specify the second argument, the offset.

Just like LAG(), LEAD() is a window function and requires an OVER clause. And as with LAG(), LEAD() must be accompanied by an ORDER BY in the OVER clause.

We again look at the table, sale:

id	seller_name	sale_value
3	Stef	7000
1	Alice	12000
2	Mili	25000
Here’s a query with a LEAD() function:


SELECT seller_name, sale_value,
  LEAD(sale_value) OVER(ORDER BY sale_value) as next_sale_value
FROM sale;
Here is the result set:

seller_name	sale_value	next_sale_value
Stef	7000	12000
Alice	12000	25000
Mili	25000	NULL

The rows are sorted by the column specified in ORDER BY (sale_value).

The LEAD() function grabs the sale amount from the row below. For example, Stef’s own sale amount is $7,000 in the column sale_value, and the column next_sale_value in the same record contains $12,000. The latter comes from the sale_value column for Alice, the seller in the next row. Note that the last row does not have a next row, so the next_sale_value field is empty (NULL) for the last row.



LAG:
----
The LAG() function allows access to a value stored in a different row above the current row. The row above may be adjacent or some number of rows above, as sorted by a specified column or set of columns.

As with other window functions, LAG() requires the OVER clause. It can take optional parameters, which we will explain later. With LAG(), you must specify an ORDER BY in the OVER clause, with a column or a list of columns by which the rows should be sorted.

Let’s consider the following table, sale:

id	seller_name	sale_value
3	Stef	7000
1	Alice	12000
2	Mili	25000
And the following query with a LAG() function:


SELECT seller_name, sale_value,
  LAG(sale_value) OVER(ORDER BY sale_value) as previous_sale_value
FROM sale;
Here is the result:

seller_name	sale_value	previous_sale_value
Stef	7000	NULL
Alice	12000	7000
Mili	25000	12000
 

In the next video, you will see a practical example of determining the frequency at which a customer named Rick Wilson orders products, using the 'lead' and 'lag' functions on the 'market star schema'.



########## Lead example UPGRAD COMMON TABLE Expression #########
### Defined 2 commontable expression ########
WITH cust_order as
(
SELECT c.customer_name,
       m.ord_id,
       o.order_date
FROM
market_fact_full as m
LEFT JOIN
orders_dimen as o
on m.ord_id=o.ord_id
LEFT JOIN
cust_dimen as c
on m.cust_id=c.cust_id
WHERE customer_name='RICK WILSON'
GROUP BY
      c.customer_name,
      m.ord_id,
      o.order_date
),
next_date_summary AS
(SELECT *,
        LEAD(order_date,1,'2015-01-01') OVER (ORDER BY order_date,ord_id) AS next_order_date
FROM cust_order
ORDER BY customer_name,
         order_date,
         ord_id
)
SELECT *,DATEDIFF(next_order_date,order_date) as days_diff
FROM next_date_summary;

Output:

customer_name	ord_id	order_date	next_order_date	days_diff
RICK WILSON	Ord_5186	7/31/2009	11/2/2009	94
RICK WILSON	Ord_3841	11/2/2009	11/6/2009	4
RICK WILSON	Ord_3867	11/6/2009	3/11/2010	125
RICK WILSON	Ord_3855	3/11/2010	6/23/2010	104
RICK WILSON	Ord_1207	6/23/2010	7/16/2010	23
RICK WILSON	Ord_3810	7/16/2010	8/14/2010	29
RICK WILSON	Ord_3845	8/14/2010	9/21/2010	38
RICK WILSON	Ord_5202	9/21/2010	11/24/2010	64
RICK WILSON	Ord_3819	11/24/2010	1/13/2011	50
RICK WILSON	Ord_3851	1/13/2011	6/26/2011	164
RICK WILSON	Ord_3828	6/26/2011	7/6/2012	376
RICK WILSON	Ord_1209	7/6/2012	9/22/2012	78
RICK WILSON	Ord_3863	9/22/2012	10/12/2012	20
RICK WILSON	Ord_1213	10/12/2012	1/1/2015	811


########## LAG example UPGRAD COMMON TABLE Expression #########
### Defined 2 commontable expression ########
WITH cust_order as
(
SELECT c.customer_name,
       m.ord_id,
       o.order_date
FROM
market_fact_full as m
LEFT JOIN
orders_dimen as o
on m.ord_id=o.ord_id
LEFT JOIN
cust_dimen as c
on m.cust_id=c.cust_id
WHERE customer_name='RICK WILSON'
GROUP BY
      c.customer_name,
      m.ord_id,
      o.order_date
),
next_date_summary AS
(SELECT *,
        LAG(order_date,1,'2008-01-01') OVER (ORDER BY order_date,ord_id) AS previous_order_date
FROM cust_order
ORDER BY customer_name,
         order_date,
         ord_id
)
SELECT *,DATEDIFF(order_date,previous_order_date) as days_diff
FROM next_date_summary;

customer_name	ord_id	order_date	previous_order_date	days_diff
RICK WILSON	Ord_5186	7/31/2009	             1/1/2008	577
RICK WILSON	Ord_3841	11/2/2009	             7/31/2009	94
RICK WILSON	Ord_3867	11/6/2009	             11/2/2009	4
RICK WILSON	Ord_3855	3/11/2010	             11/6/2009	125
RICK WILSON	Ord_1207	6/23/2010	             3/11/2010	104
RICK WILSON	Ord_3810	7/16/2010	             6/23/2010	23
RICK WILSON	Ord_3845	8/14/2010	             7/16/2010	29
RICK WILSON	Ord_5202	9/21/2010	             8/14/2010	38
RICK WILSON	Ord_3819	11/24/2010	             9/21/2010	64
RICK WILSON	Ord_3851	1/13/2011	             11/24/2010	50
RICK WILSON	Ord_3828	6/26/2011	             1/13/2011	164
RICK WILSON	Ord_1209	7/6/2012	             6/26/2011	376
RICK WILSON	Ord_3863	9/22/2012	             7/6/2012	78
RICK WILSON	Ord_1213	10/12/2012	            9/22/2012	20

In this session, you learnt about some of the advanced concepts in SQL.

Summary:
-------------

Rank functions: The different types of rank functions are as follows:

RANK(): Rank of the current row within its partition, with gaps
DENSE_RANK(): Rank of the current row within its partition, without gaps
PERCENT_RANK(): Percentage rank value; it will always lie between 0 and 1
ROW_NUMBER(): Assigns unique numeric values to each row, starting from 1
 

Rank function syntax: The syntax for the 'rank' function is as follows:

RANK() OVER (
  PARTITION BY <expression>[{,<expression>...}]
  ORDER BY <expression> [ASC|DESC], [{,<expression>...}]
)
 

Named windows: A named window makes it easier to define and reuse multiple window functions. The syntax for a named window is as follows:

WINDOW window_name AS (window_spec)
  [, window_name AS (window_spec)] ...
 

Order of SQL statements: The order in which the various SQL statements appear in a query is as follows:

SELECT
FROM
JOIN
WHERE
GROUP BY
HAVING
WINDOW
ORDER BY
 

Frames: Frames are used to subset a set of consecutive rows and calculate moving averages. A query using a frame has multiple components as shown in the diagram given below.

Structure of a Frame
Structure of a Frame
 

Lead and lag functions: These functions are used to compare a row value with the next or the previous row value. The syntax for the 'lead' function is as follows:

LEAD(expr[, offset[, default]])
  OVER (Window_specification | Window_name) 
 


































