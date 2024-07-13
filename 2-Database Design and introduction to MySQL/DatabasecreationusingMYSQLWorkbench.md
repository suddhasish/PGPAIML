Introduction to DDL and DML Statements
--------------------------------------------------
In this segment, Professor Ramanathan will demonstrate the MySQL Workbench commands and tools that are used to create the schema and tables. 

You should be able to install the MySQL Workbench on your machines. Please follow the installation instructions provided in the installation guides attached below.

Note that 32-bit installation is available for Windows. Irrespective of your system architecture (whether it is 32/64 bit), please install the 32-bit version.

So, after installing SQL on your machine and learning about the basic components and terms associated with SQL, you will next learn more about the entire set of commands that are available in SQL. So, let's watch the upcoming video and learn about it from our expert.


So, the commands available in SQL can be broadly categorised as follows:

Data Definition Language (DDL)

Data Manipulation Language (DML)

 

DDL, as the name suggests, is used to create a new schema as well as modify an existing schema. The typical commands available in DDL include CREATE, ALTER and DROP. Now, as a data analyst, the majority of your work will focus on insight generation, and you will be working with DML commands, specifically, the SELECT command. In the next segment, Professor Ramanathan will discuss this in detail.

DDL Statements: A Demonstration:-
---------------------------------

In the first video of this segment, you will learn how to create and use a database (also known as a schema) in the MySQL Workbench. You will need to specify the database that you need to use. This is because even after creating a database, the MySQL Workbench does not select your newly created database automatically. The syntax for these operations is given below:

create database <database_name>
use <database_name>

Ex:

create database market_star_schema;
use market_star_schema;

So, you have now created a database. However, it holds no meaning without its constituent tables. Now, in the next video, you will learn about the create table command and create a table containing three columns along with their respective data types.

create table shipping_mode_dimen (
	Ship_Mode varchar(25),
    Vehicle_Company varchar(25),
    Toll_Required boolean
    );

So, you now have a table ready at your disposal. Recall that every table should have a primary key to identify it uniquely.
To fulfil this requirement, in the next video, you will learn how to use the alter table command for adding a primary key constraint to the table that you created in the previous video.

Question:

You are asked to compile data and analyse India's performance in the 2019 Cricket World Cup. The first step that you would perform is to create a table with some columns with appropriate data types. Write a query to create a table named 'India' with columns with the following data types:
---------------

Matches_played – INT

Matches_won – INT

Matches_lost – INT

Net_run_rate – DECIMAL(4,3)

Points – INT
create table India (

  Matches_played int,

  Matches_won int,

  Matches_lost int,

  Net_run_rate decimal(4,3),

  Points int

);
DML Statements: A Demonstration
--------------------------------------------------
In the previous segment, you learnt how to create a table and add the necessary columns with the required data types. 
However, to start analysing data, you need the data in the first place. This is where Data Manipulation Language statements come into the picture. 
In the first video of this segment, you will learn how to insert values in a table using the insert into and values keywords in a query.

insert into shipping_mode_dimen(Ship_Mode,Vehicle_Company,Toll_Required)
values
	('DELIVERY TRUCK','Ashok Leyland',false),
    ('REGULER AIR','Air India',false);


update shipping_mode_dimen 
set Toll_Required = true
where Ship_Mode = 'DEIVERY TRUCK';

delete 
from shipping_mode_dimen
where Vehicle_Company = 'Air India';


Foreign key constraint can block deletion if violated example employee and department table.

Modifying Columns:-
--------------------

Now that you have a complete table with values and constraints, in this segment, you will learn how to:

Add another column using the alter table and add commands,
Update a value in a column using the update and set commands, and
Delete a column using the alter table and drop column commands.
 
alter table shipping_mode_dimen add Vehicle_Number varchar(20);

update shipping_mode_dimen set Vehicle_Number = 'MH-05-R1234';

alter table shipping_mode_dimen drop column Vehicle_Number; 

alter table shipping_mode_dimen
change Toll_Required Toll_Amount int;

alter table shipping_mode_dimen change Toll_Required Toll_Amount int;

It is important that you know how to modify columns so that you can enter the right data immediately if you notice that some value has been incorrectly inserted into a particular column. Doing this will ensure that you get the right insights and make the right business decisions after analysing the correct data.


Summary
In this session, you learnt how to set up a schema and make it ripe for analysis using various DDL (Data Definition Language) and DML (Data Manipulation Language) statements in MySQL.

 

The DDL statements are:

CREATE
ALTER
DROP
 

The DML statements are:

INSERT
UPDATE
DELETE
SELECT
 

While Data Definition Language statements are used to alter the structure of a database, Data Manipulation Language statements are used to change the data itself that is present inside the database.

 

So, now that you are ready to use MySQL for its primary intended purpose, that is, data analysis, it's time to write useful queries to derive actionable insights from the ocean of data that lies in front of you.






