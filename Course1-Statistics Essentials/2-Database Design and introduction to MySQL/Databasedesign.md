Introduction
So far, you have learnt how to perform basic data analysis using Python and Excel.
You have also learnt that it is risky to manage data from different files and that it may lead to inconsistency. 
An organisation cannot track its business activities efficiently by maintaining a large number of files. Hence, databases are used for accessing and managing data efficiently.
A software known as Database Management System (DBMS) is used widely in the industry to analyse data easily.


In this session
You will be introduced to the basic concepts of a data warehouse, star schema, OLAP (Online Analytical Processing), OLTP (Online Transactional Processing), SETL (Select, Extraction, Transformation, and Loading), constraints and ERD (Entity Relationship Diagrams).

What is a Data Warehouse?

Think of yourself as a data analyst working for a company that has the following three departments: Marketing, Sales and Finance. Now, let’s assume that each department maintains a separate database.

This could lead to a situation wherein each department has its own version of the facts. For a question such as 'What is the total revenue of the last quarter?', every department might have a different answer. This is because each department draws information from a different database.

This is where a data warehouse can prove to be useful. It can help with creating a single version of the truth and the facts. A data warehouse would thus be the central repository of data of the entire enterprise.

Now, in the upcoming video, you will learn what a data warehouse is and how it is useful for companies in carrying out data analytics.

########################################
You will also learn about OLAP, which stands for Online Analytical Processing systems.
OLAP is used to extract business-relevant information and perform analysis on the data stored in data warehouses.
#########################################

So, a data warehouse is a collection of data. It has the following properties:
------------
Subject-oriented: A data warehouse should contain information about a few well-defined subjects rather than the enterprise.
Integrated: A data warehouse is an integrated repository of data. It contains information from various systems within an organisation.
Non-volatile: The data values in a database cannot be changed without a valid reason.
Time-variant: A data warehouse contains historical data for analysis.
In the next segment, you will learn about the structure of the data warehouse.
-------------------------------------------------------------------------------
Structure of a Data Warehouse:

In the previous segment, you learnt about the basic concepts of data warehousing. 
Now, one of the primary methods of designing a data warehouse is dimensional modelling.

The two key elements of dimensional modelling include facts and dimensions, which are basically the different types of variables that are used to design a data warehouse. They are arranged in a specific manner, known as a schema diagram.

So, essentially, facts are the numerical data in a data warehouse and dimensions are the metadata (that is, data explaining some other data) attached to the fact variables.
Both facts and dimensions are equally important for generating actionable insights from a data set.

-------------------------------------------------------
Star Schema:

In the previous segment, you learnt about facts and dimensions, which are the two key elements of dimension modelling. 
Now, a typical problem might involve multiple databases with many different variables, but we may not be interested in all of them.
Hence, only some facts and dimensions are combined in a specific manner to build the structure of a data warehouse, called a schema diagram. 


A schema is an outline of the entire data warehouse.
It shows how different data sets are connected and how the different attributes of each data set are used for the data warehouse.


In Star schema we have a fact table and multiple dimention table.
Fact table contains all numeric values as a centralised Fact
Dimention table consists of all metadata about fact table. 

Example 1 centra able about how many product sold who brought as fact and dimention tell us what is the category of product.
-----------------------------------------------------
OLAP vs OLTP

Now that you have developed a fair understanding of databases, you might be wondering how a data warehouse and a database differ from each other.
So, in this segment, you will learn exactly which features of a data warehouse differentiate it from a regular database. In the upcoming video, our expert will talk about the differences between a transactional database and a data warehouse.


Decetion support system(DSS)

Management Information System(MIS):

OLTP: Online transaction processing system.

OLAP: Online analytical processing system. / Data warehouse used for CEO and CXO decision Making 


Teachnical diffrent :
Data warehouse follow ETL process : Extract trans form Load
Database follow DBMS process service side application:


Front end Database:
1. web server 
2. Browser for intaraction 
3. Interface with payment gateway andd payment system.

Front end :
1. BI tools.
    a. Tabelu
    b. Powerbi // cognos.


    Database Design:

    Transactational DB: 
    1. Integrity and normalization 
    2. CRUD operation: 
    Data warehouse:
    1. Based on Dimentional modeling.
    2. Creation of star schema.
    3. Only retriving.

So, in the video, you learnt about the differences between a transactional database (i.e., OLTP, or Online Transactional Processing) and a data warehouse (which is often referred to as OLAP, or Online Analytical Processing).  Notice that the major difference between OLAP and OLTP is apparent in the names themselves: OLTP is used for day-to-day transactions, whereas OLAP is used for analytical purposes. 

Earlier, you were introduced to the terms dimensional modelling and star schema. They are essential for creating the structure of a data warehouse. These techniques involve finding out the variables on which analysis can be performed and then combining them with the metadata to derive meaningful insights. You will learn more about them in the next session.
--------------------------------------------------------------------------
SETL

So far in this module, you have learnt about the different types of databases that are available for solving different problems.
 Now, what is the next step in the process? As you can see, we now need to get the data into the schema to perform relevant operations on it. You might be wondering how that is done. In the upcoming video, Professor Chandrashekhar R will give you the answer to this question.

SETL (SELECT EXTRACT TRANSFORM LOAD ) is a process of loading data from transactional multi database to Data warehouse.
SELECT: what data need from data sources
EXTRACT: COnneting to data and pulling out for further processing.
TRANSFORM: Transforming datatype removing junk values and converting from one unit to another one.
LOAD:


So, in the video, you were introduced to the SETL process, as follows:

 
SETL: Select, Extract, Transform and Load.

Select: Identification of the data that you want to analyse
Extract: Connecting to the particular data source and pulling out the data
Transform: Modifying the extracted data to standardise it
Load: Pushing the data into the data warehouse
 

This process includes the typical operations that are involved in selecting the required data, extracting data from multiple sources, operating on the data so that data from multiple sources is compatible, and loading this data into a data warehouse for analytical purposes.

In this way, you have understood the SETL. In the upcoming segments, you will understand the various constraints.
----------------------------------------------------------------------------------
Entity Constraints:

You have already learnt about the SETL process, which is used to ingest data into a schema and perform operations on it. But can we add just any value that we want to a schema or are there any constraints to maintain the sanctity of the database schema?

Put yourself in the place of a data analyst at Uber. A database at Uber has several tables, which record several details, such as details on the rider, the driver, the vehicle used and transaction details. Each such table has several related attributes, which describe it in detail. Consider the 'Rider' table. You go through the values entered in a column that contains the fares for each ride. It would be right for you to expect that the fares can have a maximum of four digits – a fare more than even? 5,000 would raise concerns. This is definitely an outlier and needs to be replaced with the right value. Ensuring that you implement the right constraints for the right attributes in a table can help you avoid such fallacies.

In the next video, you will learn about the relational data model.

Entity constraint: Unique
Referencial constraint: 
Semantic constraint: 

So, as you learnt in the video, constraints are the rules that are used in MySQL to restrict the values that can be stored in the columns of a database.
This ensures data integrity, which is nothing but the accuracy and consistency of the data stored in the database. Let's continue our discussion on the relational model in the next video.

So, as you learnt in the video, entity constraints are of the following different types:

Unique:   This constraint is used for columns that need unique values. For example, 'employee ids' should be unique in an 'employees' table.

Null:      This constraint is used to determine the columns that can have null values. For example, an employee may not need to specify their location, which means the 'location' column can have null values in an 'employees' table.

Primary Key:   This constraint is used to determine the column that uniquely identifies a table. For example, 'employee ids' uniquely identify every employee. Two employees may have the same name or the same salary, but not the same employee id.


Note that there may be a situation wherein, say, a company wants to store the records of its employees over multiple years. In this case, 'employee id' may not be unique, since an employee will have multiple rows storing details of multiple years. Also, you will need a new column named 'year' in the table.  

 

In this case, a combination of an employee id and a year, i.e., a variable EmpID-Year, can act as a composite primary key. To see how this is done in MySQL, you can refer to this 
http://dba.stackexchange.com/questions/57548/how-to-set-up-multiple-fields-as-primary-key-in-mysql
---------------------------------------------------------------------

Referential Constraints:
In the previous segment, you learnt about the first type of constraint, entity constraints, which pertain to the values in a single table. The second type of constraint is called referential constraints. These are used to restrict the values that are taken by a column in one table based on the values that exist in another table.

 

Consider the tables given below.


Customers

CustomerID	FirstName	LastName	Age
1	John	Wick	52
2	Sheldon	Cooper	41
3	Charlie	Harper	45
 
Orders

OrderID	OrderNumber	CustomerID
1	12345	2
2	31343	2
3	12466	3
4	41234	1
 

CustomerID is a foreign key in the 'Orders' table because it is used to reference the 'Customers' table. 
You can easily determine which customer placed a particular order and find out all the details of that customer by looking up the corresponding customer id in the 'Customers' table. Watch the upcoming videos to understand how foreign keys make it easier to design and query databases.


Foreign Key: This is not unique , 
table can reference multiple other foreign key.
Can insert null value in Foreing key.
So, as you learnt in the video, a referential constraint is a rule between two tables. According to this rule, the value that appears as a foreign key in a table is valid only if it also appears as a primary key in the table to which it refers.

To sum up, a given table has only one primary key but it can have multiple foreign keys. 
Before you assign a column as a foreign key, you need to ensure that the primary key column of the table that it refers to is present and it does not have null or duplicate values.
------------------------------------------------------------------
Semantic Constraints:

Suppose you work at Tata Motors and are asked to analyse the data on the prices of different car models. The values can range from? 2 lakhs to around? 12 lakhs if you are looking to sell the cars to middle-class households. Now, imagine you come across a car model that costs? 1 crore. You would need to get rid of this value as it would negatively affect your analysis and generate misleading insights. How can you ensure such values (also known as outliers) are not present in your data? Let's find out in the upcoming video.

So, as you learnt in the video, semantic constraints impose additional restrictions on the values in a column. For example, all the mobile numbers in India start with '+91', followed by 10 digits. Using a semantic constraint for this requirement ensures that we do not get incorrect data for any row. For example, a row with a phone number +91987654321 would not be allowed to enter the database as it has only 9 digits after the country code.

------------------------------------------------------------------
ERDs:

Now that you have learnt about the various types of constraints that are used to restrict the values in a database, the precursor to designing a database is drawing a well-defined ERD.

An Entity-Relationship Diagram, or ERD, can be thought of as a map of the database schema. We can visualise the structure of the entire schema and answer the following questions just by looking at the ERD:

What are the tables that it contains?
What are the columns that each table contains?
What is/are the data types and constraint/s (if any) for each column?
What are the relationships between the various tables?
 
So, as you can see, ERDs are extremely useful to get an overall idea of a database in very less time. Now, in the upcoming video, you will learn more about them from our expert.

So, as you learnt in the video, the constituents of an ERD are as follows:

Entity Type/Entity: It is nothing but a table in the schema. For example, 'orders' and 'payments' are both entity types.
Attribute: It is a column in an entity type. For example, 'orderNumber' is an attribute in the 'orders' entity type.
Relationship Types: They are the lines between the tables. They define the relationships among the tables. These can be of various types based on their cardinalities, i.e., one-to-one, one-to-many, many-to-many, etc.

Self referential Relationship Type:

1-1
1-many
many -many


So, as you learnt in the video, there is another type of relationship, called self-referential relationship. Here, the table refers to itself.

Take a look at the table given below.

Team India

Player Name	Player Role	Captain	Vice-Captain
K. L. Rahul	Batsman	Kohli	Sharma
Rohit Sharma	Batsman	Kohli	Sharma
Virat Kohli	Batsman	Kohli	Sharma
Shreyas Iyer	Batsman	Kohli	Sharma
Rishabh Pant	Batsman	Kohli	Sharma
Ravindra Jadeja	All-rounder	Kohli	Sharma
R. Ashwin	All-rounder	Kohli	Sharma
Hardik Pandya	All-rounder	Kohli	Sharma
Bhuvneshwar Kumar	Bowler	Kohli	Sharma
Mohammed Shami	Bowler	Kohli	Sharma
Jasprit Bumrah	Bowler	Kohli	Sharma


The table given above has a self-referential relationship because Virat Kohli is the captain of every player, but he is a player himself.
 The same applies to Rohit Sharma, who is the vice-captain of the team.
----------------------------------------------------------
Star Schema: A Demonstration
By now, you must have a fair idea about star schemas, constraints and ERDs. Now, we will go through an example of a star schema and understand how it makes database designing simpler and more intuitive. So, let's watch the upcoming video to learn more about it from our expert.


So, as you learnt in the video, the market star schema consists of five tables: 1 central fact table and 4 dimension tables, which describe the fact table. This structure of one fact table with multiple dimension tables makes data analysis easier because it reduces the number of joins required for querying data. When you learn about joins later in this module, you will better understand the reason why Professor Ramanathan insists that you design a star schema during the database creation phase.
--------------------------------------------------
Summary
In this session, you learnt the following:

What a data warehouse is
The differences between a data warehouse and a transactional database
OLAP (Online Analytical Processing) systems are Subject-oriented, Integrated, Non-volatile and Time-variant
A data warehouse provides an integrated view of the entire organisation and the data is organised for carrying out analysis efficiently
Facts and dimensions and how to arrange them in order to design a data warehouse
Dimension tables act as metadata, which is data about data, and enhance the facts table to enhance the insights from the data
What a star schema is
The advantages of having a star schema in a database
The SETL process: Select, Extract, Transform and Load
The different types of constraints: Entity, Referential and Semantic constraints
ERDs and their constituents
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------





















