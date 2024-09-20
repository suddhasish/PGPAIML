Introduction
-----------------
In the previous sessions, you learnt what databases are, what they are composed of, and how to create a database along with its tables, constraints and values. In this session, we will dive into the core of SQL and you will learn all about the statements that are used for querying data. You will also develop the thought process that is required to extract the data needed for analysis and to drive business decisions.

 

In this session
You will learn how to write queries using the select, from, where, group by, having, order by and limit statements. A query may generally contain all or some of these keywords. You will also get an understanding of the need for the various types of operators and functions, which make it easy to address seemingly complex data requirements.

SQL Statements and Operators
--------------------------

So, in this segment, you will learn about the basic constructs of the SELECT query. You will specifically learn about the following:

'Select' Clause

'From' Clause

'Where' Clause

Operators: Arithmetic, Comparison and Logical

-- print full data 
select * from cust_dimen;
-- select only a column 
select Customer_Name from cust_dimen;
-- print name of all customer along with their city and state
select Customer_Name,City,State from cust_dimen;

So, in the video, you learnt about a few basic queries using the select and from statements. After watching the next couple of videos, you will be able to filter data based on certain given criteria and group it into categories, if required. You will also learn how to use operators in queries. In the next video, you will have hands-on using the basic SQL commands.

-- How Many customer is from west bengal use of where clause with alias
select count(*) as Bengal_Customers
from cust_dimen
where State = 'West Bengal';
-- Print name of all customer along with city and state
Select Customer_Name AS "Customer Full Name",City "Customer City", State
from cust_dimen
where State = 'West bengal' and City = 'Kolkata';

-- or clause 
Select Customer_Name ,City,Customer_Segment
from cust_dimen
where City = 'Mumbai' or Customer_Segment = 'Corporate';

In the next video, you will see more SQL operators' applications.


-- In operator to find south indian customers 
select * from cust_dimen
where state in ('Tamil Nadu','Karnataka','Telengana','Kerala');
-- Not equals
select * from cust_dimen
where Customer_Segment != 'Small Business';

-- Select order id of all those orders which caused losses 
select Ord_id,Profit from market_fact_full where profit < 0;

-- List the orders with '_5' pattern matching operator LIKE and shipping cost between 10 and 15
select Ord_id,Shipping_Cost from market_fact_full where Ord_id like '%\_5%' and Shipping_Cost between 10 and 15;

-- Write a query to display the cities in the 'cust_dimen' table that begin with the letter 'K'.
select City from cust_dimen where City like 'K%';

Operators can be used for various functions: pattern matching, returning a subset of the data based on its properties or comparing different values to get a sense of the distribution of the data. Pattern matching is an important concept in text-based processing. As you learnt, in SQL, certain characters are reserved as wildcards, which can match any number of preceding or trailing characters.

Correct. % is a multi-character wildcard, whereas _ is a single-character wildcard. For example, using "_r%" would return the words with the second character as r, followed by zero or more characters at the end

Aggregate Functions
----------------------

As you go about examining and analysing data of varying magnitudes, you will quickly realise the need for grouping similar types of values together and looking at them as one group. For example, consider a table that has data, which consists of the marks scored by students in their 12th board exams. While you would want to know how the students performed in all the subjects put together, it is equally important to see how they performed in each subject. You can derive even further insights if you group these students by state. Hence, it is imperative that you learn the usage of aggregate functions in your queries. So, let's go ahead and learn about it from our expert in the upcoming video.

count(*) --> This means couning the row count with null value
count(columnname) eliminates null value.

From
where
groupby
having
orderby

-- Find total number of sales made.

select count(sales) as No_of_sales from market_fact_full; 

-- Total number of customer from each city
select count(Customer_Name) as City_Wise_Customer,City from cust_dimen group by city;

select count(Customer_Name) as City_Wise_Customer,city,Customer_Segment from cust_dimen group by City,Customer_Segment;

So, in this segment, you learnt how to use the group by clause. In brief, we use 'group by' when we need to find the aggregate values of a column C1 'grouped by' a certain column C2.

 

count() is just one of many aggregate functions that are available in the MySQL Workbench. Feel free to explore other functions, such as min(), max() and avg(). Try using them in queries and examine the results that you obtain. You will realise that aggregate functions play a crucial role in determining outliers in the data and analysing any existing trends in it.


select count(Ord_id) as Loss_Count from market_fact_full where Profit < 0;


select count(Customer_Name) as Segment_Wise_Customers,State,Customer_Segment
from cust_dimen
where State = 'Bihar'
group by Customer_Segment;

So, as Professor Ramanathan mentioned in the video, please keep this in mind whenever you write any query because not all versions of the MySQL Workbench in all operating systems allow non-aggregate columns in the 'select' clause whenever you use a 'group by' statement.  

-------------------------------
Ordering
--------------------------------

Quite often, you would want to display the retrieved records in a particular order, for example, in increasing order of income, joining date or alphabetical order. 
This is commonly useful when you are making a report or presenting the data to someone else. Let's try to understand this in the next video.;

select Customer_Name from cust_dimen order by Customer_Name;

select distinct Customer_Name from cust_dimen order by Customer_Name desc;

print 3 most ordered products:

select Prod_id,sum(Order_Quantity) from market_fact_full group by Prod_id
order by sum(Order_Quantity) desc
limit 3;

print 3 least ordered products:

select Prod_id,sum(Order_Quantity) from market_fact_full group by Prod_id
order by sum(Order_Quantity)
limit 3;

The Having Clause
------------------

You have already learnt how to filter individual values based on a given condition. But how do you do this for grouped values? Suppose your manager asks you to count all the employees whose salaries are more than the average salary in their respective departments. Now, intuitively, you know that two aggregate functions would be used here: count() and avg(). You decide to apply the 'where' condition on the average salary of the department, but to your surprise, the query fails. This is exactly what the 'having' clause is for.


select Prod_id,sum(Order_Quantity) from market_fact_full group by Prod_id
order by sum(Order_Quantity) desc;


select Prod_id,sum(Order_Quantity) from market_fact_full group by Prod_id
having sum(Order_Quantity) > 20000 
order by sum(Order_Quantity) desc;

String and Date–Time Functions
-----------------------------------
In the video below, you will learn all about string functions. They are used for manipulating string data and make it more understandable for analysis. For example, given two strings 'robertdowneyjr' and 'Robert Downey Jr.', which one is more readable? Of course, the latter one.

--Print the customer name in proper case 
select Customer_Name ,concat(upper(substring(substring_index lower(customer_name),' ',1),1,1)),upper(substring(substring_index(lower(customer_name),'',-1),1,1)) from cust_dimen

-- Print the product names in the following format: Category _Subcategory
select Product_Category,Product_Sub_Category,
concat(Product_Category,'_',Product_Sub_Category) as Product_Name;



Similar to string functions, SQL also has functions to manipulate the date and time values in a database. These are quite useful for analysing time-series data. For example, consider a database pertaining to the students of the university from which you graduated. Now, suppose you have data on the total number of students who used the library every day. You can use date functions to determine whether the library was busier on any particular day of the week as compared with the other days, or maybe a particular month (for example, exam time). In the next video, Professor Ramanathan will take you through queries using such functions.

-- In which month were the most orders shipped ?
select count(Ship_id) as Ship_Count ,month(Ship_Date) as Ship_Month
from shipping_dimen
group by Ship_Month
order by Ship_Count desc
limit 1;

-- which month and year combination saw the most critical order 
select count(Order_id) as Order_Count ,month(Order_Date) as Order_Month,
year(Order_Date) as Order_Year
from orders_dimen
where Order_Priority = 'Critical'
group by Order_Year,Order_Month 
order by Order_Count desc
limit 1;

-- find most commonly used shipment
select Ship_Mode,count(Ship_Mode) as Ship_Mode_Count
from shipping_dimen
where year(Ship_Date) = 2011
group by Ship_Mode
order by Ship_Mode_Count desc;

-- Write a query to find the full name of the actor who has acted in the maximum number of movies.


select concat(FIRST_NAME,' ',LAST_NAME) as Full_name from ACTOR where ACTOR_ID = 
(
select ACTOR_ID from FILM_ACTOR 
group by ACTOR_ID
order by count(FILM_ID) desc 
limit 1
);

select concat(FIRST_NAME,' ',LAST_NAME) as Full_name from ACTOR where ACTOR_ID = 
(
select ACTOR_ID from FILM_ACTOR 
group by ACTOR_ID
order by count(FILM_ID) desc LIMIT 1 OFFSET 2  
);


abs() – Returns the absolute value of a number
ceil() – Returns the smallest integer value greater than or equal to the input number
floor() – Returns the largest integer value not greater than the argument
round() – Rounds a number to a specified number of decimal places
rand() – Returns a random floating-point value between 0 and 1
pow(a, b) – Returns the value a^b

Regular Expressions
--------------------

You have already learnt how to perform pattern matching using the like operator along with wildcards. Now, the 'like' operator and the wildcards may fall short for some advanced use cases. One such example that you can consider is email validation. Given a string, how can you determine whether an email is valid or not? This may not even be possible to achieve using 'like'. In fact, this is a slightly complicated requirement to meet even for regular expressions. It definitely makes the work of an analyst much easier, though.


-- find name with substring car

select Customer_Name from cust_dimen where Customer_Name regexp 'car';

--Print customer name starts with A,B,C or D and ends with er

select Customer_Name from cust_dimen where Customer_Name regexp '^[abcd].*er$';

^ cap symbol means begain with 
[abcd] is pattern which means a or b or c or d
. stands for anything
* stands for 0 or more occurance of previous thing.
$ matches end of pattern.

Additional Resources:

You can refer to this MySQL | Regular expressions (Regexp) link to get an idea about some of the pattern matching that can be achieved using regular expressions.

https://www.geeksforgeeks.org/mysql-regular-expressions-regexp/

Nested Queries
--------------
By now, you know that a database is a collection of multiple related tables. Now, while generating insights from data, you may need to refer to these multiple tables in a query. There are two ways to deal with such types of queries:
Joins
Nested queries/Subqueries
In the upcoming videos, you will learn about nested queries/subqueries. You will learn about joins in the next session.

select Ord_id,Sales,round(Sales) as Rounded_Sales from market_fact_full 
where Sales = (
    select max(Sales)
    from market_fact_full
);

Subqueries are a generic form of writing queries wherein you do not need to specify some value explicitly (either minimum or maximum, or some other value). 
If any update is made to a table, then the subquery would still return the required output as it is independent of any particular value in the table. 
Now, let's move on to the next and learn more about nested queries.


select * from prod_dimen
where Prod_id in (select Prod_id from market_fact_full where Manu_Id is null);

-- Print name of most frequent customer

select Customer_Name,Cust_id
from cust_dimen 
where Cust_id = (
    select Cust_id from market_fact_full 
    group by Cust_id
    order by count(Cust_id) desc 
    limit 1);

To summarise, in this segment, you learnt about nested queries, which are typically used when you have to select columns from one table based on the filter conditions from another table. In such cases, you write a subquery inside the 'where' clause, instead of a specific value.


Given a table named customers with the following columns:

select customerName from customers where creditLimit > 
(
 select creditLimit from customers where customerName regexp "La Rochelle Gift"
 );


CTEs
---------------------------
Imagine you are working as an analyst at a large bank (if you aren't already, that is). Let's say you are required to find out your top 10 clients out of thousands. Of these clients, your company wants to give some cash handouts to the one that has the least turnover in the current year. You can definitely use a simple query to achieve this [by using the min() function and the 'where' clause], but what if you want to derive multiple insights from the data of your top 10 clients? In this case, it is better to use a Common Table Expression (CTE), so that you can get the data of only those clients and perform all of your analysis on a subset of the entire data. In the upcoming video, you will learn more about CTEs from our expert.




with creditline as (
    select creditLimit from customers where customerName regexp "La Rochelle Gift"
)

select * from creditline;



A CTE is used to create a temporary table, which is smaller than the existing table. This smaller table cannot be individually queried, that returns an error. The CTE has to be used as part of the main query.

Views
-------------
In the previous segment, you learnt that CTEs are temporary tables that you can use in order to query data from a part of a huge data set. Now, what if you want to use the same subset of data for multiple queries? In such a case, instead of writing a CTE over and over again, you can store the required data on which you want to perform your analysis. This is what views are used for. You will understand the importance of using views better after watching the upcoming video.


create view order_info as
select Ord_id,Sales,Order_Quantity,Profit,Shipping_Cost
from market_fact_full;

select Ord_id,Profit from order_info where Profit > 1000;

Note that it is not necessary that views would always be preferred to CTEs. When you know for sure that you need to subset data from a table only once, you should use a CTE to avoid extra memory and space usage


select (attributes)

from (table)

where (filter_condition)

group by (attributes_to_be_grouped_upon)

having (filter_condition_on_grouped_values)

order by (values)

limit (no_of_values_to_display);


Write a query to find the film which grossed the highest revenue for the video renting organisation.

select TITLE from FILM where FILM_ID=
(select FILM_ID from INVENTORY where INVENTORY_ID=
(select INVENTORY_ID from RENTAL where RENTAL_ID=
(select rental_id from PAYMENT 
group by rental_id
order by sum(AMOUNT) desc limit 1)))