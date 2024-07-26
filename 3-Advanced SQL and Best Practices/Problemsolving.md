Please Reffer :  Adv.+SQL+Actual+Script.sql

Profitability Analysis - I
------------------------------
In this segment, you will solve a business problem using SQL. In the first problem, you will identify the profitable product categories in the 'market star' schema. Let's watch the upcoming video to get an understanding of the problem statement and learn about the metrics that can be used for solving it.



In this video, you were introduced to the problem statement, the required metrics and required tables, which can be summarised as follows:

 

Problem statement: Identify the sustainable (profitable) product categories so that the growth team can capitalise on them to increase sales.

 

Metrics: Some of the metrics that can be used for performing the profitability analysis are as follows:

Profits per product category
Profits per product subcategory
Average profit per order
Average profit percentage per order
 

Tables: The tables that are required for solving this problem are as follows:

'market_fact_full'
'prod_dimen'
'orders_dimen'
 

The ERD for the 'market star' schema is given below for your reference.


Profitability Analysis - II
----------------------------
Let's start solving the business problem by calculating the metrics that we discussed in the previous segment. In the next video, you will write the queries that are required to find the profits for all the product categories and subcategories. Which of the metrics (if any) discussed in the previous segment are actually useful? Let's watch the video and find out.


As you learnt in this video, all the product categories report good profits. Hence, they do not contribute to the solution, as you cannot identify the reasons for any loss that the company is facing. However, the profit per product category is still an important metric that can be used for creating business reports. The profit per product subcategory is a useful metric, as it shows the subcategories that report heavy losses.
Before calculating the third metric, let's first find out if there is any relation between the Order IDs table and the Order Numbers table.



As Shreyas explained in this video, the Order IDs table and the Order Numbers table do not have a one-to-one relation. Why does this matter? It proves that there are customers who have ordered products more than once. It is important to identify frequent customers so that you can offer discount coupons to them in exchange for their loyalty.




Profitability Analysis - III
-------------------------------
You have already calculated the profit for each category and subcategory. In this segment, you will calculate the third metric: average profit per order. Let's watch the next video and find out more about this.



You observed that the average profit per order for furniture products is low (₹75.23) compared with that of the other product categories.
In the next video, let's compute the fourth and last metric: average profit percentage per order. While coding along with Shreyas, you must have observed that he examined each table to check whether there are any other metrics that could be useful for the analysis.


You observed that the average profit percentage per order for furniture products is quite low (2.27%) compared to the other product categories. Such low values of the average profit and profit percentage per order for furniture show that these products are not doing well. Their sale should ideally be stopped or the company should come up with a robust plan to deal with this issue.

 

You have now calculated all the required metrics that were specified in the problem statement. Notice how you derived additional insights by calculating the total number of orders for each product category. While performing any analysis on a data set, you should always look for additional metrics that can help you understand the trends in the data set.

Suggested Answer
Determining the average profit per order helps in estimating the maximum cost that you should incur for each order. This will help ensure that profits are maximised after the required amount of money is spent on delivering each order to the relevant customer.

Profitable Customers - I
-------------------------
Now that you have completed the profitability analysis for product categories and subcategories, it is time to solve the second problem statement. Let's watch the upcoming video and learn more about it.



As you learnt in this video, there is a major difference between this problem statement and the one you solved in the previous segment. You already have the expected output table that contains the required columns. Sometimes, interviewers test whether you can write the exact query that is required for extracting the expected output.

The problem statement, the expected output format and the required tables can be summarised as follows:

Problem statement: Extract the details of the top ten customers in the expected output format.

Expected output format: The expected output format is given in the table below.


Tables: The tables that are required for solving this problem are as follows:

'cust_dimen'
'market_fact_full'


The ERD for the 'market star' schema is given below for your reference.

In the next segment, you will learn how to identify ten of the most profitable customers and extract their details in the required format.

Profitable Customers - II
----------------------------
Now that you are well-versed with the problem statement and the format of the expected output table, in the upcoming video, Shreyas will walk you through the approach and the code that you will use to solve this problem statement.


After extracting the details of the most profitable customers in the required format, you can draw further insights into the city or state to which they belong. This can help you identify some of the major regions where your products are selling the most.

Customers Without Orders - I
----------------------------

In the previous segment, you performed profitability analysis as well as identified the most profitable customers. In this segment, you will be introduced to the final problem statement. Let's watch the upcoming video and learn more about this.


The problem statement, the required columns and the required tables introduced in this video can be summarised as follows:
Problem statement: Extract the required details of the customers who have not placed an order yet.

Expected columns: The columns that are required as the output are as follows:

'cust_id'
'cust_name'
'city'
'state'
'customer_segment'
A flag to indicate that there is another customer with the exact same name and city but a different customer ID.
 

Tables: The tables that are required for solving this problem are as follows:

'cust_dimen'
'market_fact_full'
 

The ERD for the 'market star' schema is given below for your reference.

Customers Without Orders - II
------------------------------
In the previous segment, you were introduced to the second problem statement and also understood the required columns that you need to output. Let's watch the upcoming video and learnt how to extract the details of the customers who have not placed a single order yet.



In this video, you learnt that are no such customers who have not placed a single order. In the next video, you will learn how to solve this problem statement by making slight modifications to it.

In this video, you learnt how to extract the details of the customers who have placed more than one order. In the next segment, you will learn how to extract the 'Fraud Flag' column and understand the importance of this column.

Fraud Detection
----------------------
Suppose you are a senior manager at Domino's Pizza and your job is to manage operations in Mumbai. The company has come up with an attractive offer for new customers: each new customer who signs up can avail a discount of 75% on their first order with a maximum cap of ₹500. Everything seems to be going well in all the areas in Mumbai, except in Chembur. An unexpectedly large number of customers are signing up on a daily basis. What could be the reason for this?

 

In the upcoming video, Shreyas will continue solving the problem statement to determine if there are any fraud customers. Keep the above scenario in mind as you learn how to detect customer fraud in a company.




As you saw in this video, there were many customers who repeatedly tried to sign up to receive discounts on their orders. Recall the scenario that was described earlier in this segment and try to come up with a possible reason why a large number of customers in Chembur are signing up.


One of the reasons can be that the same customers who signed up earlier are using different mobile numbers to avail the 75% discount on their orders. You could prevent this by extracting the customer IDs that have the same email address, residential address and other such details. In such cases, there is a strong likelihood of fraud customers.

With this, we have come to the end of this session as well as this module. You were introduced to and solved three problem statements in this session. Let's summarise the learnings from this session in the final segment.


Summary
In this session, you solved various business problems using SQL. You might encounter similar problems in your daily job role.

 

Profitability analysis: You performed a profitability analysis on the 'market star' schema by identifying sustainable/profitable product categories so that the growth team can capitalise on them and increase sales. You calculated the following metrics:

Profits per product category
Profits per product subcategory
Average profit per order
Average profit percentage per order
 

Profitable customers: You also identified the ten most profitable customers and extracted their details in the format given below.

Output Format
Output Format
Fraud detection: Finally, you found out the details of fraud customers after retrieving their data in the following columns:

'cust_id'
'cust_name'
'city'
'state'
'customer_segment'
A flag to indicate that there is another customer with the exact same name and city but a different customer ID.
 

You must have realised that there are various applications of SQL in the data analytics domain. Hence, it is important for you to have a strong understanding of both basic and advanced SQL concepts to derive useful insights.

 

You can find the script file used in the demonstrations throughout this session in the link provided below.
---------------------------------------------------------------------------------------------------------------

-- Rank Demo

USE market_star_schema;

SELECT  customer_name,
		ord_id,
		ROUND(sales) AS rounded_sales,
        RANK() OVER (ORDER BY sales DESC) AS sales_rank
FROM market_fact_full as m
INNER JOIN
cust_dimen as c
ON m.cust_id = c.cust_id
WHERE customer_name= 'RICK WILSON';

-- Top 10 sales orders from a customer

WITH rank_info AS
(
SELECT  customer_name,
		ord_id,
		ROUND(sales) AS rounded_sales,
        RANK() OVER (ORDER BY sales DESC) AS sales_rank
FROM market_fact_full as m
INNER JOIN
cust_dimen as c
ON m.cust_id = c.cust_id
WHERE customer_name= 'RICK WILSON'
)
SELECT *
FROM rank_info
WHERE sales_rank<=10;

-- Example for Dense Rank
SELECT ord_id,
		discount,
        customer_name,
        RANK() OVER (ORDER BY discount DESC) AS disc_rank,
        DENSE_RANK() OVER (ORDER BY discount DESC) AS disc_dense_rank        
FROM market_fact_full as m
INNER JOIN cust_dimen as c
ON m.cust_id=c.cust_id
WHERE customer_name= 'RICK WILSON';

-- Number of orders each customer has placed

SELECT customer_name,
		COUNT(DISTINCT ord_id) AS order_count,
        RANK() OVER (ORDER BY COUNT(DISTINCT ord_id) DESC) AS order_rank,
        DENSE_RANK() OVER (ORDER BY COUNT(DISTINCT ord_id) DESC) AS order_dense_rank,
        ROW_NUMBER() OVER (ORDER BY COUNT(DISTINCT ord_id) DESC) AS order_row_num
FROM market_fact_full AS m
INNER JOIN
cust_dimen AS c
ON m.cust_id=c.cust_id
GROUP BY customer_name;

-- Partitioning example
WITH shipping_summary AS
(
SELECT ship_mode,
		MONTH(ship_date) AS shipping_month,
        COUNT(*) as shipments
FROM 
shipping_dimen
GROUP BY ship_mode,
		 MONTH(ship_date)
)
 SELECT *,
		row_number() OVER (PARTITION BY ship_mode ORDER BY shipments DESC) AS shipping_rank
FROM shipping_summary;


-- Named windows example

SELECT ord_id,
		discount,
        customer_name,
        RANK() OVER w AS disc_rank,
        DENSE_RANK() OVER w AS disc_dense_rank,
        ROW_NUMBER() OVER w AS disc_row_num
FROM market_fact_full as m
INNER JOIN cust_dimen as c
ON m.cust_id=c.cust_id
WINDOW w AS (PARTITION BY customer_name ORDER BY discount DESC);

-- Frames example
WITH daily_shipping_summary AS
(
SELECT ship_date,
		SUM(shipping_cost) AS daily_total
FROM
market_fact_full AS m
INNER JOIN
shipping_dimen AS s
ON m.ship_id=s.ship_id
GROUP BY ship_date
)
SELECT *,
		SUM(daily_total) OVER w1 AS running_total,
        AVG(daily_total) OVER w2 AS moving_avg
FROM daily_shipping_summary
WINDOW w1 as (ORDER BY ship_date ROWS UNBOUNDED PRECEDING),
w2 AS (ORDER BY ship_date ROWS 6 PRECEDING);

-- Lead and Lag example
WITH cust_order as
(
	SELECT c.customer_name,
			m.ord_id,
			o.order_date
	FROM
	market_fact_full as m
	LEFT JOIN
	orders_dimen as o
	ON m.ord_id=o.ord_id
	LEFT JOIN
	cust_dimen as c
	ON m.cust_id=c.cust_id
	WHERE customer_name='RICK WILSON'
	GROUP BY 
			c.customer_name,
			m.ord_id,
			o.order_date
),
next_date_summary AS 
(
SELECT *,
		LEAD(order_date,1,'2015-01-01') OVER (ORDER BY order_date, ord_id) AS next_order_date
FROM cust_order
ORDER BY customer_name,
		 order_date,
         ord_id
)
SELECT *, DATEDIFF(next_order_date, order_date) as days_diff
FROM next_date_summary;
-- Case when example
/*  profit < -500 -> huge loss
	profit -500 to 0 ->bearable loss
    profit 0 to 500 -> decent profit
    profit >500 -> great profit
*/
SELECT 
	market_fact_id,
    profit,
	CASE
		WHEN profit <-500 THEN 'Huge Loss'
        WHEN profit BETWEEN -500 AND 0 THEN 'Bearable Loss'
        WHEN profit BETWEEN 0 AND 500 THEN 'Decent Profit'
		ELSE 'Great Profit'
    END AS Profit_type
FROM
    market_fact_full;
-- Classify customers on the following criteria
-- Top 10 % of customers as Gold
-- Next 40% of customers as Silver
-- Rest 50% of customers as Bronze
WITH cust_summary AS
(
	SELECT m.cust_id, 
			c.customer_name, 
			ROUND(SUM(m.sales)) as total_sales,
			PERCENT_RANK() OVER( ORDER BY ROUND(SUM(m.sales)) DESC) as perc_rank
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
			WHEN perc_rank<0.1 THEN 'Gold'
            WHEN perc_rank<0.5 THEN 'Silver'
            ELSE 'Bronze'
		END AS customer_category
FROM cust_summary;

-- UDFs
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
$$
DELIMITER ;

SELECT profitType(-20) as Function_output;



-- Stored Procedures

DELIMITER $$

CREATE PROCEDURE get_sales_customers (sales_input INT)
BEGIN
	SELECT DISTINCT cust_id,
					ROUND(sales) AS sales_amount
	FROM
		market_fact_full
	WHERE ROUND(sales)>sales_input
    ORDER BY sales;
    
END $$

DELIMITER ;

CALL get_sales_customers(300);

DROP PROCEDURE get_sales_customers;


-- Query best practices 

-- Comment Section

/*
Comment Section with
multiple lines
*/

SELECT fact.ord_id, order_date
FROM market_fact_full AS fact INNER JOIN orders_dimen AS ord ON fact.ord_id = ord.ord_id
ORDER BY fact.ord_id , order_date;


SELECT fact.ord_id,
       order_date
FROM   market_fact_full AS fact
       INNER JOIN orders_dimen AS ord
               ON fact.ord_id = ord.ord_id
ORDER  BY fact.ord_id,
          order_date;  

-- Index Demo
CREATE TABLE market_fact_temp AS
SELECT * 
FROM
	market_fact_full;

CREATE INDEX filter_index ON market_fact_temp (cust_id, ship_id, prod_id);

ALTER TABLE market_fact_temp DROP INDEX filter_index;


-- Types of Indexes
SELECT * FROM market_fact_full;

-- Query Optimisation with understanding of Order of Query execution
-- Problem: Top 10 order ids and the customers who did them

SELECT ord_id,
		customer_name 
FROM
(
SELECT  m.*,c.customer_name,
        RANK() OVER (ORDER BY sales DESC) AS sales_rank,
        DENSE_RANK() OVER (ORDER BY sales DESC) AS sales_dense_rank,
        ROW_NUMBER() OVER (ORDER BY sales DESC) AS sales_row_num
FROM 
market_fact_full as m
LEFT JOIN
cust_dimen as c
ON m.cust_id = c.cust_id
ORDER BY sales desc
) as a
LIMIT 10;



SELECT ord_id,
		customer_name 
FROM
(
SELECT  ord_id,c.customer_name,
        ROW_NUMBER() OVER (ORDER BY sales DESC) AS sales_row_num
FROM 
market_fact_full as m
INNER JOIN
cust_dimen as c
ON m.cust_id = c.cust_id
) as a
WHERE sales_row_num<=10;











/*-------------------------------------------------------------------------------------------
Problem statement: Growth team wants to understand sustainable(profitable) product categories
Sustainability can be achieved when we make better profits or at least positive profits.
	We can look at the profits per product category.
	We can look at profits per product subcategory. 
	We can check Average profit per order
	Also, consider Average Profit % per order
--------------------------------------------------------------------------------------------*/

-- Summary at Prodcut Category and Sub category
SELECT 
	p.Product_Category,
    p.Product_Sub_Category,
    SUM(m.Profit) AS Profits 
FROM
	market_fact_full as m
INNER JOIN
	prod_dimen as p
ON m.prod_id=p.prod_id
GROUP BY 
	p.Product_Category,
    p.Product_Sub_Category
ORDER BY p.Product_Category, 
			SUM(m.Profit);

-- Exploring order table
SELECT ord_id,
		order_number
FROM
	orders_dimen
GROUP BY
	ord_id,
	order_number
ORDER BY
	ord_id,
	order_number;

SELECT 
	COUNT(*) as rec_count,
	COUNT(DISTINCT ord_id) as ord_id_count,
    COUNT(DISTINCT order_number) as ord_number_count   
FROM
	orders_dimen;

SELECT 
* 
FROM
orders_dimen
WHERE order_number IN
(
SELECT 
	order_number
FROM
	orders_dimen
GROUP BY order_number
HAVING COUNT(ord_id)>1
);

-- Calculating order level avg profit and overall summary
SELECT 
	p.Product_Category,
    SUM(m.Profit) AS Profits,
    COUNT(DISTINCT o.order_number) AS Total_orders,
    ROUND(SUM(m.Profit)/COUNT(DISTINCT o.order_number),2) as Avg_profit_per_order,
	ROUND(SUM(m.Sales)/COUNT(DISTINCT o.order_number),2) as Avg_Sales_per_order,
    ROUND(SUM(m.Profit)/SUM(m.Sales),4)*100 as Profit_perc
FROM
	market_fact_full as m
INNER JOIN
	prod_dimen as p
	ON m.prod_id=p.prod_id
		INNER JOIN
		orders_dimen as o
		ON m.ord_id=o.ord_id
GROUP BY 
	p.Product_Category
ORDER BY p.Product_Category, 
			SUM(m.Profit);

/*---------------------------------------------------------------------------------
Problem statement: Get the details of Top 10 profitable customers in form 
of a table shown below:
cust_id
rank
customer_name
profit
customer_city
customer_state
sales
---------------------------------------------------------------------------------*/

-- Exploring cust_dimen table
SELECT 
	cust_id,
    customer_name,
    city AS customer_city,
    state AS custoer_state
FROM
	cust_dimen
WHERE cust_id like 'cust_1%';

-- Ranking
WITH cust_summary AS
(
	SELECT 
		c.cust_id,
        RANK() OVER (ORDER BY SUM(profit) DESC) as customer_rank,
		customer_name,
		ROUND(SUM(profit),2) as profit,
		city AS customer_city,
		state AS custoer_state,
        ROUND(SUM(sales),2) as sales
	FROM
		cust_dimen AS c
        INNER JOIN
			market_fact_full as m
			ON c.cust_id=m.cust_id
	GROUP BY cust_id
)
SELECT * FROM cust_summary
-- To slect Top 10 customers
WHERE customer_rank<=10;

/*----------------------------------------------------------------------------
Share the following details of the customers who have placed only one order so far:
Cust_id
Customer_Name
City
State
Customer_Segment
Flag to indicate if there is another customer with the exact same name and 
city but a different cust_id (to understand if the same customer signed up again)
---------------------------------------------------------------------------- */

-- Exploring customer dimension tabel

SELECT * 
FROM 
	cust_dimen;

-- List all customers who have not placed any order
SELECT c.* 
FROM 
	cust_dimen AS c
LEFT JOIN
	market_fact_full AS m
    ON c.cust_id=m.cust_id
WHERE m.ord_id IS NULL;

-- Checking if really no such customers exist
SELECT COUNT(cust_id) from cust_dimen;
-- 1832

SELECT COUNT(DISTINCT cust_id) from market_fact_full;
-- 1832

-- Exploring order per user
SELECT c.*,
		COUNT(DISTINCT ord_id) as order_count
FROM 
	cust_dimen AS c
LEFT JOIN
	market_fact_full AS m
    ON c.cust_id=m.cust_id
GROUP BY cust_id
HAVING COUNT(DISTINCT ord_id)<>1;

-- Unique customer name and city check

SELECT customer_name,
		city,
        COUNT(cust_id) as cust_id_count
FROM cust_dimen
GROUP BY
		customer_name,
		city
HAVING COUNT(cust_id)>1;

-- Final Output
WITH cust_details
AS
(
	SELECT c.*,
			COUNT(DISTINCT ord_id) as order_count
	FROM 
		cust_dimen AS c
	LEFT JOIN
		market_fact_full AS m
		ON c.cust_id=m.cust_id
	GROUP BY cust_id
	HAVING COUNT(DISTINCT ord_id)<>1
),
fraud_cust_list AS
(
	SELECT customer_name,
			city,
			COUNT(cust_id) as cust_id_count
	FROM cust_dimen
	GROUP BY
			customer_name,
			city
	HAVING COUNT(cust_id)>1
)
SELECT 
	cd.*,
    CASE WHEN fc.cust_id_count IS NOT NULL 
		THEN 'FRAUD' 
	ELSE 'NORMAL' 
    END AS fraud_flag
FROM 
	cust_details as cd
	LEFT JOIN
    fraud_cust_list as fc
		ON cd.customer_name=fc.customer_name AND
				cd.city=fc.city;
