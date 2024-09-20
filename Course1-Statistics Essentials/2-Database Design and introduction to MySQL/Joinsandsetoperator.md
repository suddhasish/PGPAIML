Set Theory
There are many set operations in practice, but in this segment, you will learn about union, intersection and difference. 
A set is a collection of distinct values. It is denoted by comma-separated values enclosed by curly braces.


Consider two sets A and B containing even numbers and prime numbers, respectively. For ease of understanding, let's consider only values less than 10. 
Therefore, the sets will be A = { 2, 4, 6, 8} and B = { 2, 3, 5, 7 }.


The union of A and B (denoted by A ∪ B) will contain all the values that are present in either A or B. 
Therefore, A ∪ B = { 2, 3, 4, 5, 6, 7, 8 }.


The intersection of A and B (also denoted by A ∩ B) will contain all the values that are present in both A and B. 
Therefore, A ∩ B = { 2 }.

The set difference of A and B (also denoted by A - B) will contain all the values that are present in A but not in B. Therefore, A - B = { 4, 6, 8 }.


In a class of 50 students, 10 enrolled in both English and Hindi. 32 enrolled in English in total. If the students of the class enrolled in at least one of the two subjects, then how many students enrolled in only Hindi and not English?

You can use a Venn Diagram to solve this question. Go through the link given below carefully, especially the first example problem.

eng hindi = 10
eng = 32
eng = 32 -10 = 22
hindi = 32 -  20

Write a query to find the full name of the actor who has acted in the maximum number of movies.


Types of Joins
----------------
Types of Joins
Consider a database that contains data about a music festival that you are organising. Now, while designing the database, you may have tables pertaining to the following:

Data about the artists who would be performing at the festival
Details of the stages on which the artists would perform
Timings for each performance on each stage
Details of organisers and other details of security guards, volunteers, photographers, etc.
Details of attendees, including name, age, address, ticket category, etc.
 

As you can see, the design of such a database can become quite complicated. How would you analyse the data of the artists and attendees together? This information may be required to calculate the feasibility of the event in terms of cost. This is where joins can be used to combine multiple tables and make the analysis of such data easier for you.

As you learnt in the two videos given above, there are mainly two types of joins: inner joins and outer joins. While an inner join searches tables for matching or overlapping data, an outer join also returns rows for which there is no match between the tables.


Types of Joins: A Demonstration
----------------------------------
Now that you have a theoretical understanding of joins in MySQL, next, Professor Ramanathan will walk you through various examples where you would need to use inner joins. The use case may be as simple as just returning some data from two tables. It may even be as advanced as analysing multiple tables together in a single query and identifying any trends that emerge.

Inner Join:

The general syntax of a query using an inner join statement is as follows:

 

select <column_1>, <column_2>

from table_1 a

inner join table_2 b

on a.<common_column> = b.<common_column>;



-- Print product Category sub category and profit made for each order
select Ord_id,Product_category,Product_sub_category,Profit 
from from prod_dimen p inner join market_fact_full m 
on p.prod_id = m.prod_id


Examples of Multi-Joins
Can you think of an example where you would need to use a multi-join, i.e., query data from more than two tables at once?

Vehicles table containing the columns vehicle id, colour id and customer id
Colours table containing the columns colour id and colour (black, white etc.)
Customers table containing the columns customer id and customer name
You would need to write a query using multi-joins to know which vehicle is owned by which customer as well as which colour that vehicle is.


select Customer_name , sum(Order_quantity) as total _Orders
from cust_dimen c 
inner join market_fact_full m
on c.cust_id=m.cust_id
group by customer_name
order by total_orders desc; 


select Customer_name , sum(Order_quantity) as total _Orders
from cust_dimen 
inner join market_fact_full
using(cust_id)
group by customer_name
order by total_orders desc; 



Earlier in this session, you learnt about inner joins and writing join queries. You must have noticed that only two tables were referred to in the join. But what if you have a complicated problem statement that needs referencing three, four, five or more tables? In such situations, you can write join queries using multi-joins.

Multi join:
-----

select product_category,City,sum(Profit) as city_wise_profit
from prod_dimen p
inner join market_fact_full m
on p.prod_id = m.prod_id
inner join cust_dimen c
on m.Cust_id=c.cust_id
where product_category = 'Office Supply' and City in ('Delhi','Patna')
group by City,Product_Category;


select m.prod_id ,m.profit,p.product_category,s.ship_mode
from market_fact_full m inner join prod_dimen p on m.prod_id = p.prod_id
inner join shipping_dimen s on m.ship_id=s.ship_id

Write a query to find the city which generated the maximum revenue for the organisation.


select ct.CITY
from PAYMENT p inner join CUSTOMER c
on p.CUSTOMER_ID=c.CUSTOMER_ID
inner join ADDRESS a
on c.ADDRESS_ID=a.ADDRESS_ID
inner join CITY ct
on a.CITY_ID = ct.CITY_ID 
group by CITY
order by sum(AMOUNT) desc limit 1

-- Write a query to find out how many times a particular movie category is rented. 
-- Arrange these categories in the decreasing order of the number of times they are rented.

select c.NAME,count(RENTAL_ID) as Rental_count
from CATEGORY c inner join FILM_CATEGORY fc
on c.CATEGORY_ID=fc.CATEGORY_ID
inner join FILM f
on fc.FILM_ID=f.FILM_ID
inner join INVENTORY i
on f.FILM_ID=i.FILM_ID
inner join RENTAL r
on i.INVENTORY_ID=r.INVENTORY_ID
group by NAME
order by count(RENTAL_ID) desc


Write a query to find the full names of customers who have rented sci-fi movies more than 2 times.
Arrange these names in the alphabetical order.





In brief, you can use multi-joins to join multiple tables using common attributes between pairs of tables. This is possible because the result of a join is also a table, which you can join further to another table (with a common attribute).

 

ERDs can be useful for understanding the links between tables, which, in turn, can be quite helpful in writing multi-way join queries.

Write a query to list the names of all customers who have placed at least one order.

select customerName
from Customers
inner join Orders
using(customerNumber)
group by customerName
having count(orderNumber) >= 1 


Write a query to find the full names of customers who have rented sci-fi movies more than 2 times. Arrange these names in the alphabetical order.

select concat(FIRST_NAME,' ',LAST_NAME) as Customer_name
from CATEGORY c inner join FILM_CATEGORY fc
on c.CATEGORY_ID=fc.CATEGORY_ID
inner join FILM f
on fc.FILM_ID=f.FILM_ID
inner join INVENTORY i
on f.FILM_ID=i.FILM_ID
inner join RENTAL r
on i.INVENTORY_ID=r.INVENTORY_ID
inner join CUSTOMER cust
on r.CUSTOMER_ID=cust.CUSTOMER_ID
where NAME='Sci-fi' 
group by Customer_name
having count(RENTAL_ID) > 2
order by Customer_name asc


Write a query to find the full names of those customers who have rented at least one movie and belong to the city Arlington.

select concat(FIRST_NAME,' ',LAST_NAME) as Customer_name
from CUSTOMER cust
inner join RENTAL r
on cust.CUSTOMER_ID=r.CUSTOMER_ID
inner join ADDRESS ad
on cust.ADDRESS_ID=ad.ADDRESS_ID
inner join CITY ct
on ad.CITY_ID=ct.CITY_ID
where CITY='Arlington' 
group by Customer_name
having count(RENTAL_ID) >= 1

Write a query to find the number of movies rented across each country. 
Display only those countries where at least one movie was rented. 
Arrange these countries in the alphabetical order.


select COUNTRY , count(RENTAL_ID) as Rental_count 
from COUNTRY co
inner join CITY ct
on co.COUNTRY_ID=ct.COUNTRY_ID
inner join ADDRESS ad
on ct.CITY_ID=ad.CITY_ID
inner join CUSTOMER cu
on ad.ADDRESS_ID=cu.ADDRESS_ID
inner join RENTAL r
on cu.CUSTOMER_ID=r.CUSTOMER_ID
group by COUNTRY
having count(RENTAL_ID) >= 1
order by COUNTRY asc




Outer Joins: A Demonstration
----------------------------
Now that you know when to use an outer join in a query, Professor Ramanathan will take you through some example queries using left and right joins. Using a left join will return all values from the left table and matching values from the right table. If there is no match for any value, the right table will return null for that value.

To summarise, an outer join is used when you want to display the rows in one table even if they do not have a corresponding entry in the other table. Also, an outer join is of two types: left outer join and right outer join. It does not really matter which table you treat as left or right, i.e., you can choose the table that you are more comfortable with.

select m.manu_name,p.prod_id
from manu m left JOIN prod_dimen p on m.manu_id=p.manu_id;

select m.manu_name,count(prod_id)
from manu m left JOIN prod_dimen p on m.manu_id=p.manu_id
group by m.manu_name;

To summarise, an outer join is used when you want to display the rows in one table even if they do not have a corresponding entry in the other table. Also, an outer join is of two types: left outer join and right outer join. It does not really matter which table you treat as left or right, i.e., you can choose the table that you are more comfortable with.

Views with Joins
--------------------
Imagine you have two tables Menu and Ingredients. The Menu table contains data about different food items and their prices, while the Ingredients table contains data about the ingredients as well as their quantities used in each food item. It turns out that you need to analyse food products that cost above? 200 repeatedly to understand if there is any way to drive down their costs. Is there a way to avoid writing join statements every single time for each query? Well, it turns out there is. Watch the video given below and find out how you can do this.


Views with joins are especially useful if you need to store data from multiple columns in a single place for ready reference. You can even use subqueries and CTEs in views. Feel free to explore such use cases and try writing queries to get the exact results for further analysis.


By now, you have mastered the most important aspect of writing SQL queries, joins. Do keep practising different queries involving multiple joins, as joins form a majority of the questions that are generally asked in interviews.

create view order_details as 
select concat(FIRST_NAME,' ',LAST_NAME) as Customer_name
from CUSTOMER cust
inner join RENTAL r
on cust.CUSTOMER_ID=r.CUSTOMER_ID
inner join ADDRESS ad
on cust.ADDRESS_ID=ad.ADDRESS_ID
inner join CITY ct
on ad.CITY_ID=ct.CITY_ID
where CITY='Arlington' 
group by Customer_name
having count(RENTAL_ID) >= 1


In the next segment, you will learn about the different sets operation with SQL.

Set Operations with SQL
-----------------------
Can you recall the types of set operations that you came across at the beginning of this session? They were union, intersection and difference. In MySQL, these operations are achieved using the keywords 'union' and 'union all'. Unfortunately, MySQL Workbench does not support 'intersect' and 'minus' keywords; these operations are performed with a combination of other SQL clauses that you are familiar with by now. You may find the two links provided below helpful for reading more about these two operations.

From the next video, you will get an understanding of the difference between using the 'union' and 'union all' operators and learn how they are implemented in queries.
union: dosent have duplicate
union all: contains duplicate
intersect: common element
minus: 


As Professor Ramanathan explained in the video given above, always make sure that the tables or the results of your queries are union-compatible before you perform a union operation on them. Two tables are union-compatible if:

They have the same number of attributes, and
The attribute types are compatible, i.e., the corresponding attributes have the same data type.

2 most profitable and 2 least profitable product
---------------


(select prod_id , sum(Profit)
from market_fact_full group by Prod_id
order by sum(profit) desc limit 2)
union
(
    select prod_id,sum(Profit),
    from market_fact_full 
    group by Prod_id
    order by sum(Profit)
    limit 2
);


