Most Productive Month
Description
Write a query to find the month number (Eg: 4 corresponds to April) in which the most number of payments were made.

-- RANK() OVER(ORDER BY COUNT(AMOUNT)) AS No_of_payments

use upgrad;

# Write your code below

select month(PAYMENT_DATE) AS Payment_month,
       COUNT(PAYMENT_ID) AS No_of_payments
from PAYMENT
GROUP BY Payment_month 
ORDER BY COUNT(PAYMENT_ID) DESC
LIMIT 10;

Description
List the rounded average film lengths for each film category. Arrange the values in the decreasing order of the average film lengths.


WITH movie_length AS (
SELECT ROUND(avg(f.length)) as avg_Length,
        c.name,
        ROW_NUMBER() OVER (ORDER BY ROUND(avg(f.length)) DESC) as length_row_num
FROM
film as f
INNER JOIN
film_category as fc
ON f.film_id=fc.film_id
INNER JOIN
category c
ON fc.category_id=c.category_id
GROUP BY name
)
SELECT avg_Length,name from movie_length;




Film Category vs. City
Description
Write a query to find the number of occurrences of each film_category in each city. Arrange them in the decreasing order of their category count.


names,city,category_count


SELECT  c.name,
        ct.city,
        COUNT(c.name) AS category_count
FROM
film_category as fc
INNER JOIN
category c
ON fc.category_id=c.category_id
INNER JOIN 
inventory as i
ON fc.film_id=i.film_id
INNER JOIN
store as s
ON i.store_id=s.store_id
INNER JOIN
address as a 
ON s.address_id=a.address_id
INNER JOIN
city as ct
ON a.city_id=ct.city_id
GROUP BY name,city
ORDER BY category_count DESC


Ad Campaign
Description
Suppose you are running an advertising campaign in Canada for which you need the film_ids and titles of all the films released in Canada. List the films in the alphabetical order of their titles.

+------------------+
| Tables_in_upgrad |
+------------------+
| address          |
| city             |
| country          |
| film             |
| inventory        |
| store            |
+------------------+

use upgrad;

# Write your code below

WITH COUNTRY_SEARCH  AS (
SELECT  
        f.film_id Film_id,
        f.title AS Title
FROM
film as f
INNER JOIN
inventory as i
ON f.film_id=i.film_id
INNER JOIN
store as s
ON i.store_id=s.store_id
INNER JOIN
address as a 
ON s.address_id=a.address_id
INNER JOIN
city as ct
ON a.city_id=ct.city_id
INNER JOIN
country cou
ON ct.country_id=cou.country_id
WHERE country = 'Canada'
)
SELECT DISTINCT Film_id,Title from COUNTRY_SEARCH;


Comedy Movies
Description
Write a query to list all the films existing in the 'Comedy' category and arrange them in the alphabetical order.

+------------------+
| Tables_in_upgrad |
+------------------+
| category         |
| film             |
| film_category    |
+------------------+


SELECT  f.title
FROM
film as f
INNER JOIN
film_category as fc
ON f.film_id=fc.film_id
INNER JOIN
category c
ON c.category_id=fc.category_id
where c.name='Comedy'


Lucky Customers
Description
List 

the first and last names of all customers whose first names start with the letters 'A', 'J' or 'T' or last names end with the substring 'on'. Arrange them alphabetically in the order of their first names.



+------------------+
| Tables_in_upgrad |
+------------------+
| customer         |
+------------------+


SELECT
first_name AS First_name , last_name AS Last_name
FROM customer
WHERE first_name LIKE 'A%' OR first_name LIKE 'J%' OR first_name LIKE 'T%' OR last_name LIKE '%on'
ORDER BY First_name;


















