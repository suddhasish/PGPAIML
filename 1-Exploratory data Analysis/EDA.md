Sourcing Data :


--> Cleaning 
--> UNIVARIATE ANALYSIS (i.e checking once variable to identify the pattern. Example analyzing students mark for a subject and find out pattern)
--> BIVARIATE ANALYSIS (checcking influence of one variable over another variable ) 
--> DERIVED METRICS (Augment the data with other data. I.E what percent of student got into JEE from each state. So if score getter than cutoff make it to JEE then crate a colum marked as 1 or zero then we can add up and count the values how many student got into JEE)

In this module, we will cover the following topics:

Data sourcing

Data cleaning

Univariate analysis

Bivariate analysis

Derived metrics


Welcome to the session on 'Data sourcing'.

In this session:
To solve a business problem using analytics, you need to have historical data. Data is the key — the better the data, the more insights you can get out of it.


Typically, data comes from various sources and your first job as a data analyst is to procure the data from them. In this session, you will learn about various sources of data and how to source data from public and private sources. The broad agenda for this session is as follows:

Private Data
Public Data

-----------------


Public and Private Data
There are two major kinds of data which can be classified according to the source:

Public data

Private data

A large amount of data collected by the government or other public agencies is made public for the purposes of research. Such data sets do not require special permission for access and are therefore called public data.

On the other hand, private data is that which is sensitive to organisations and is thus not available in the public domain. Banking, telecom, retail, and media are some of the key private sectors that rely heavily on data to make decisions.
------
Private Data : NOt easy to get.We need to sign NDA then get data which invelves lot of trouble to get data as we need to know whome to rach to get it and lot many things.

Public Data : Isnt always relavent.

--------------------------------

Private Data:

A large number of organisations seek to leverage data analytics to make crucial decisions.
As organisations become customer-centric, they utilise insights from data to enhance customer experience, while also optimising their daily processes.


1) Banking data : 
    i) sensitive
    ii) involves customer transaction details
Possible Decision:
 . Giving another loan
 . Sending collection agents
 . Write off the loan 
 . Promoting new product 

2) Telecom Data:
  1) Optimize prepaid and postpaid plans for customer 
  2) Predict and prevent customer churn 
        which customer likely to churn like senio citizen .
EDA is about build understanding of data. example: when comparing curtomer get paperless bill means customer high chances to leave the network we need to analyze this.

3) Human Resource Data : Predict if employee likely to leave or not. example: If employee takig more sick leave then its an indicator that they tend to leave.

-------------------------------------
You learnt the use of data in the banking, telecom and human resources sectors. 
While banks use data to make credit related decisions, telecoms use data to optimise plans for customers and predict customer churn. 
HR data analytics helps identify and predict employee behaviour.
---------------------------------------------------------------------

4) Retail Data: (Retail Market basket analysis)
    a. Product purchasing
    b. product stocking : What likely to sell more.
    c. Product pricing: How to price products. example to provide more feature how much extra shou you charge.
    d. What product tend to brought together.
    c. product which reduce selling of other product.

5) Media Data:

a. TVR/TRP rating
b. Data Journalism (Which party tends to win


While retail data analytics helps drive decisions such as pricing and stocking,
the media industry uses data extensively to target viewers better.
Advertisers use data to identify best avenues for targeting customers, while journalists use data visualisation to aid information.)


---------------------------------------
Public Data:

2000 - 2010 period

Reference Awesome public Dataset: https://github.com/awesomedata/awesome-public-datasets

Finance: 

NYSE Market data 
 Use case: When oil price rise does gold price rise or fall.

 site gov public data :  https://data.gov.in
                         https://censusindia.gov.in/
                         https://github.com/awesomedata/awesome-public-datasets

Data Sourcing Anecdote - Agricultural Commodity Prices
Anand was presented a case by his client where he was tasked with forecasting commodity prices. 
Commodity prices, as the name suggests, are the prices of commodities such as oil, gold, silver, wheat, cotton, coffee, etc. that are traded in global trade markets. 
While an increase in commodity prices is indicative of economic growth, a fall in the same is indicative of a slowdown.

--------------------
Discussion on 1st usecase: 
Forcast comodity prices: buying varity of comodity to predict which comodity going to rise and which going to fall.

aggricultural comodity in india 
download: MKt wise comodity wise daily report for state

Next action : Load the data and convert using scrapping
--------------------------------------------------------------------------------------------------------------------

Data Cleaning :-
----------------------------------------------------------------------------------------------------

You will learn how to identify the various quality issues and techniques to clean data.

Though data cleaning is often done in a somewhat haphazard way and it is too difficult to define a ‘single structured process’, we will study data cleaning in the following steps:

    Fix rows and columns
    Fix missing values
    Standardise values
    Fix invalid values
    Filter data


Fix rows and columns:-

a. delete Incorrect Rows: Un necessary header and footer rows
b. delete summary rows: Total  , subtotal rows
c. Delete extra rows: Column number indicator rows , blank rows
d. Missing column name : Missing Header row
e. rename column consistantly :  Abbribiation , encoded columns 
f. delete unnecessary columns : unidentified , irrelavent columns 
g. split columns for more data split http://host:port/path into [host,port,path]
h. Merge Columns for Identifiers :  Firstname , lastname --> Name state , district --> fulldistrict
i. Align misaligned columns : Shifted columns 

Missing Values:-


In case you can add information from reliable external sources, you should use it to replace missing values. But often, it is better to let missing values be and continue with the analysis rather than extrapolate the available information.


Let us summarise how to deal with missing values:

Set values as missing values: Identify values that indicate missing data, and yet are not recognised by the software as such, e.g treat blank strings, "NA", "XX", "999", etc. as missing.

Adding is good, exaggerating is bad: You should try to get information from reliable external sources as much as possible, but if you can’t, then it is better to keep missing values as such rather than exaggerating the existing rows/columns.

Delete rows, columns: Rows could be deleted if the number of missing values are significant in number, as this would not impact the analysis. Columns could be removed if the missing values are quite significant in number.


Standardising Values:-

Fill partial missing values using business judgement: Missing time zone, century, etc. These values are easily identifiable.

Scaling ensures that the values have a common scale, which makes analysis easier. E.g. let's take a data set containing the grades of students studying at different universities. Some of the universities give grades on a scale of 4, while others give grades on a scale of 10. Therefore, you cannot assume that a GPA of 3 on a scale of 4 is equal to a GPA of 3 on a scale of 10, even though they are same quantitatively. Thus, for the purpose of analysis, these values need to be brought to a common scale, such as the percentage scale.


One of the concepts that surely caught your attention is outliers. Removing outliers is an important step in data cleaning. An outlier may disproportionately affect the results of your analysis. This may lead to faulty interpretations. It is also important to understand that there is no fixed definition of an outlier. It is left up to the judgment of the analyst to decide the criteria on which data would be categorised as abnormal or an outlier. We will look into one such method in the next session.


Let’s summarise what you learned about standardising variables. You could use this as a checklist for future data cleaning exercises.

Standardise units: Ensure all observations under a variable have a common and consistent unit, e.g. convert lbs to kgs, miles/hr to km/hr, etc.

Scale values if required:  Make sure the observations under a variable have a common scale

Standardise precision for better presentation of data, e.g. 4.5312341 kgs to 4.53 kgs.

Remove outliers: Remove high and low values that would disproportionately affect the results of your analysis.


Let us summarise what you learned about standardising text. You could use this as a checklist for future data cleaning exercises.

Remove extra characters like common prefix/suffix, leading/trailing/multiple spaces, etc. These are irrelevant to analysis.

Standardise case: There are various cases that string variables may take, e.g. UPPERCASE, lowercase, Title Case, Sentence case, etc.

Standardise format: E.g. 23/10/16 to 2016/10/23, “Modi, Narendra" to “Narendra Modi", etc.


Invalid Values:-

In the previous segment, you learnt how to standardise values. When standardising values, you do not really pay attention to the validity of the actual values of the variables. 
This is what we will discuss now as you learn to fix invalid values.

A data set can contain invalid values in various forms. Some of the values could be truly invalid, e.g. a string “tr8ml” in a variable containing mobile numbers would make no sense and hence would be better removed. 
Similarly, a height of 11 ft would be an invalid value in a set containing heights of children.

On the other hand, some invalid values can be corrected. E.g. a numeric value with a data type of string could be converted to its original numeric type. 
Issues might arise due to python misinterpreting the encoding of a file, thus showing junk characters where there were valid characters.
This could be corrected by correctly specifying the encoding or converting the data set to the accurate format before importing.

If you have an invalid value problem, and you do not know what accurate values could replace the invalid values, it is recommended to treat these values as missing. E.g. in the case of a string “tr8ml” in a Contact column, it is recommended to remove the invalid value and treat it as a missing value.

 

Let’s summarise what you learnt about fixing invalid values. You could use this as a checklist for future data cleaning exercises.

Encode unicode properly: In case the data is being read as junk characters, try to change encoding, E.g. CP1252 instead of UTF-8.

Convert incorrect data types: Correct the incorrect data types to the correct data types for ease of analysis. E.g. if numeric values are stored as strings,
 it would not be possible to calculate metrics such as mean, median, etc. Some of the common data type corrections are — string to number: "12,300" to “12300”; string to date: "2013-Aug" to “2013/08”; number to string: “PIN Code 110001” to "110001"; etc.

Correct values that go beyond range: If some of the values are beyond logical range, e.g. temperature less than -273° C (0 K), you would need to correct them as required. A close look would help you check if there is scope for correction, or if the value needs to be removed.

Correct values not in the list: Remove values that don’t belong to a list. E.g. In a data set containing blood groups of individuals, strings “E” or “F” are invalid values and can be removed.

Correct wrong structure: Values that don’t follow a defined structure can be removed. E.g. In a data set containing pin codes of Indian cities, a pin code of 12 digits would be an invalid value and needs to be removed. Similarly, a phone number of 12 digits would be an invalid value.

Validate internal rules: If there are internal rules such as a date of a product’s delivery must definitely be after the date of the order, they should be correct and consistent.


Filtering Data:-

In the previous segment, you learnt how to go about fixing invalid values. Now, let’s learn how to filter data.
After you have fixed the missing values, standardised the existing values, and fixed the invalid values, you would get to the last stage of data cleaning.
 Though you have a largely accurate data set by now, you might not need the entire data set for your analysis.
 It is important to understand what you need to infer from the data and then choose the relevant parts of the data set for your analysis. Thus, you need to filter the data to get what you need for your analysis.

Let’s summarise what you learnt about filtering data. You could use this as a checklist for future data cleaning exercises.

Deduplicate data: Remove identical rows, remove rows where some columns are identical
Filter rows: Filter by segment, filter by date period to get only the rows relevant to the analysis
Filter columns: Pick columns relevant to the analysis
Aggregate data: Group by required keys, aggregate the rest


--------------------------------------------------------------------------------------------------------------------

Univariate Analysis :-
----------------------------------------------------------------------------------------------------

META DATA --> UNIVARIATE ANALYSIS -->

Data Description
Given a data set, the first step is to understand what it contains. 
Information about a data set can be gained simply by looking at its metadata. Metadata, in simple terms, is the data that describes each variable in detail. 
Information such as the size of the data set, how and when the data set was created, what the rows and variables represent, etc. are captured in the metadata.  

You learnt the difference between ordered and unordered categorical variables -

Ordered ones have some kind of ordering. Some examples are
Salary = High-Medium-low
Month = Jan-Feb-Mar etc.
Unordered ones do not have the notion of high-low, more-less etc. Example:
Type of loan taken by a person = home, personal, auto etc.
Organisation of a person = Sales, marketing, HR etc.
Apart from the two types of categorical variables, the other most common type is quantitative variables. These are simply numeric variables which can be added up, multiplied, divided etc. For example, salary, number of bank accounts, runs scored by a batsman, the mileage of a car etc.


So far, we have discussed the following types of variables:

Categorical variables
Unordered 
Ordered
Quantitative / numeric variables


Unordered Categorical Variables - Univariate Analysis:-

Let’s now move to the most interesting part of EDA — getting useful insights from the data.
So far, you have seen two types of variables - categorical (ordered / unordered) and quantitative (or numeric).
In this segment, you will learn how to conduct univariate analysis on unordered categorical variables. 


Region shows a Power Law distribution (A graph where we are plotting Region vs number of occurance which is factored as rank  in log log scale: poltting region vs rank ):
In reguler scale it will be a exponential curve and when we draw in log log scale it tend to folow straight line often.

Plotting country rank and frequency on log log scale.
this follows power law equation: Y = ax^b
where liner scale is Y = bx+c


plotting cost code and rank on log scale :

You saw how one can use plots to extract meaningful information from unordered categorical variables. Compare the answer you had given to the question before the lecture - how would your approach of analysing unordered categorical variables change after studying this?
It is important to note that rank-frequency plots enable you to extract meaning even from seemingly trivial unordered categorical variables such as country, name of an artist, name of a github user etc.
The objective here is not to put excessive focus on power laws or rank-frequency plots, but rather to understand that non-trivial analysis is possible even on unordered categorical variables, and that plots can help you out in that process.
Let us now see how a power law distribution is created in Excel.



Why plotting on a log-log scale helps ??

The objective of using a log scale is to make the plot readable by changing the scale. For example, the first ranked item had a frequency of 29000, the second ranked had 3500, the seventh had 700 and most others had very low frequencies such as 100, 80, 21 etc.  The range of frequencies is too large to fit on the plot.

Plotting on a log scale compresses the values to a smaller scale which makes the plot easy to read.

This happens because log(x) is a much smaller number than x. For example, log(10) = 1, log(100) = 2, log(1000) = 3 and so on. Thus, log(29000) is now approx. 4.5, log(3500) is approx. 3.5 and so on. What was earlier varying from 29000 to 1 is now compressed between 4.5 and 0, making the values easier to read on a plot.


To summarise, the major takeaways from this lecture are:

Plots are immensely helpful in identifying hidden patterns in the data 
It is possible to extract meaningful insights from unordered categorical variables using rank-frequency plots
Rank-frequency plots of unordered categorical variables, when plotted on a log-log scale, typically result in a power law distribution.

Ordered Categorical Variables - Univariate Analysis: - 

In the previous lecture, you saw how to conduct univariate analysis on unordered categorical variables. Let's now see how to do the same on ordered categorical variables.
Before that, think about the type of analysis you would do on ordered categorical variables.

You may have had some experience taking power meter readings at least once. 
It would be interesting to see how meter readings vary across households.
Let us look at a case study that Anand did for a power company.

You saw an example of how a simple histogram can reveal interesting insights. This is an extremely important takeaway — whenever you have a continuous or an ordered categorical variable, make sure you plot a histogram or a bar chart and observe any unexpected trends in it.
Let’s look at a few more examples of univariate analysis revealing hidden patterns.

I’m sure you remember the sleepless nights exams gave you. For a student, the examiner is an antagonist most of the times, who prevents you from getting the scores you deserve. You might also have been intrigued by questions such as: how many students obtained marks similar to yours, how many students were ahead, or how many lagged behind. And everyone has an opinion on when and where grace marks are justified.

So, let’s use this typical student experience to help you learn univariate analysis. Let us now look at an interesting analysis that Anand conducted on class X student marks across Tamil nadu.


Quantitative Variables - Univariate Analysis:

Mean and median are single values that broadly give a representation of the entire data. As Anand stated very clearly, it is very important to understand when to use these metrics to avoid doing inaccurate analysis.
While mean gives an average of all the values, median gives a typical value that could be used to represent the entire group. As a simple rule of thumb, always question someone if someone uses the mean, since median is almost always a better measure of ‘representativeness’.

Let’s now look at some other summary descriptive statistics such as mode, interquartile distance, standard deviation, etc.

Quantitative Variables - Summary Metrics:

News Popularity Data Set - Reading Box Plots

You saw that quartiles are a better measure of the spread than the standard deviation. A good way to visualise quartiles is to use a box plot. 
The 25th percentile is represented by the bottom horizontal line of the box, the 75th is the top line of the box, and the median is the line between them.   
In the following questions, let us use the news popularity data set to understand the measures of the deviation of the number of shares of a news article across the days of the week, weekends, and types of articles. 


Let's summarise what you learnt:

Metadata description describes the data in a structured way. 
You should make it a habit of creating a metadata description for whatever data set you are working on.
Not only will it serve as a reference point for you, it will also help other people understand the data better and save time.

Distribution plots reveal interesting insights about the data. You can observe various visible patterns in the plots and try to understand how they came to be.

Summary metrics are used to obtain a quantitative summary of the data. Not all metrics can be used everywhere. 
Thus, it is important to understand the data and then choose what metric to use to summarise the data.

-----------------------------------------------------------------------------------------------------------------------
Segmented Univariate Analysis
-----------------------------------------------------------------------------------------------------------------------

In the previous session, you learnt to conduct univariate analysis on categorical and quantitative variables.
In the segmented univariate analysis, you will learn how to extract useful insights by conducting univariate analysis on segments of data.

 Though the simple univariate analysis is tremendously useful in many cases, the real strength of univariate analysis often lies in segmented univariate analysis.

In this session
We will extend univariate analysis and learn to conduct univariate analysis across ‘segments’. The broad agenda for this session is as follows:

    1.Basis of segmentation
    2.Comparison of averages
    3.Comparison of other metrics

Segmented univariate analysis allows you to compare subsets of data, which is a powerful technique because it helps you understand how a relevant metric varies across different segments.

AGENDA:
1. Basic Segmentation
2. Comparision of average 
3. Comparision of other metric

divide the data into multiple groups or segments based on COUNTRY or Type of training and perfrom analysis on that.

Segmentation: Busisiness or domain driven decision.

Categorical variable is basis of segmentation.[Country / age bucket etc]


You have already done some segmented univariate analysis in the previous lectures, such as in the news popularity example, where you wanted to test the following three hypotheses:
On average, a higher number of articles are shared on weekdays than weekends
Among the weekdays, articles published on Wednesdays get shared more than on any other weekday
Articles of the type (or channel) 'lifestyle' and 'social media' are shared more than the other types on average
In this case, the categorical variables used for grouping were ‘channel type’, ‘day of week’, etc. 
Across these categories or groups, you had then conducted segmented univariate analysis to compare the average number of shares across days, channel types etc.

Basis of Segmentation:-

In the last lecture, you have seen some glimpses of segmented univariate analysis. Now, let’s go deeper into the segmentation process. The entire segmentation process can be divided into four parts:

    1.Take raw data

    2. Group by dimensions

    3. Summarise using a relevant metric such as mean, median, etc.

    4. Compare the aggregated metric across groups/categories

Comprehension: National Achievement Survey
In the examples you just saw, the variables used for grouping were gender, the number of siblings, handicap status, etc. The metric for comparison was the average marks in mathematics.
 Using this process, you can ask interesting questions by choosing various grouping variables and summary metrics, some of which you will see in the following questions.

 
 Quick Way of Segmentation

 In the last lecture, you learnt the process of segmentation. But what if you have a large number of variables in your dataset. 
 It looks very repetitive task to perform the same analysis on the large bunch of variables. One way of solving this problem is to make a table with the categorical variables on one axis and the numeric variables (or measures/facts) on the other. Let’s see what such a table would look like.

        1. Identifying the influence of each parameter on the outcome,

        2. Quantifying and idenfying what are key drivers (comparing the percentage of variation with respect to each column)

        3. Segmenting how the influence is diffrent across diffrent segment.


Comprehension: National achievement Survey Analysis
You saw how various factors have an impact on a student’s performance and marks. 
Let’s analyse how segmented univariate analysis can help you understand the factors affecting class VIII marks in the different states. 
You are required to go to the below website app, play around with the filters (gender, poverty, state, siblings, etc.) and answer the following questions.

https://gramener.com/nas/

Comparison of Averages: -

In the previous lectures, you learnt the process of segmented univariate analysis. Let’s now move on to the next step of segmented univariate analysis — the comparison of averages.
By now, you know how to group the data by categorical variables and compare the averages. But you should be careful while comparing averages, especially if the difference in average values is small. 
Let’s see why this is important.

** We need to avoid incorporating columns in our analysis which are totaly random in nature and added later does not have any significance.

ou would have noticed that both the data sets created by Anand have different distributions of the scores of boys and girls. 
In the first data set, it shows that every girl scored higher marks than every other boy. The difference in means is still 1, but in this case, you can say that girls score higher than boys.

"Don’t blindly believe in the averages of the buckets — you need to observe the distribution of each bucket closely and ask yourself if the difference in means is significant enough to draw a conclusion. 
If the difference in means is small, you may not be able to draw inferences. 
In such cases, a technique called hypothesis testing is used to ascertain whether the difference in means is significant or due to randomness.
“ Don’t worry if you do not get the concept of hypothesis correctly, It will be dealt separately in hypothesis module."

Comparison of Other Metrics:-

Once you have identified the variables based on the business problem for analysing the segments, the next step is to know the distribution of segments and compare the average of each segment. But this is not the only way of comparing segments. There are various metrics which you can use to understand and explain your data easily.

Let's see how Anand compares the other metrics:

Note : At 0:56,it should be 'Bottom shows 25th percentile' instead of 'Bottom shows 50th percentile'.

So far in this session, you have learnt new metrics, concepts and techniques for performing segmented univariate analysis on the variables based on the business understanding. In conclusion, the three steps of segmented univariate analysis are as follows:

        Basis of segmentation
        Comparison of averages
        Comparison of other metrics

-------------------------------------------------------------------
Bivariate Analysis on Continuous Variables
-------------------------------------------------------------------

In the last session, you learnt how to perform segmented univariate analysis e.g. how gender or father’s education impacts student’s percentage in science, maths and reading. But what if you want to analyse pairs of continuous variables at a time? For example, how the sales figure depends on the marketing spends, or, for that matter, how two continuous variables depend on each other. Is there any way or concept to identify the relationship between two variables?

Let’s start with the bivariate analysis on pairs of continuous variable to answer these questions.


Continuous Variable: Mostly numeric 

Categorical Variable: catagory absed on charecter. this can be numeric as well example : age of a person .

You learnt that continuous variables are numeric type variables which you can typically add up. 

But do you think continuous variables can also be used as categorical ones? If yes, provide two examples of continuous variables which you can treat as categorical ones.

Analysis performed on Continuous: Corelation analysis between 2 variable. example hight and weight. Positive corelation means +1 and negetive co-relation in -1

Analysis performed on categorical: 

To summarise, correlation is a number between -1 and 1 which quantifies the extent to which two variables ‘correlate’ with each other.

If one increases as the other increases, the correlation is positive

If one decreases as the other increases, the correlation is negative

If one stays constant as the other varies, the correlation is zero

In general, a positive correlation means that two variables will increase together and decrease together, e.g. an increase in rain is accompanied by an increase in humidity. 
A negative correlation means that if one variable increases the other decreases, e.g. in some cases, as the price of a commodity decreases its demand increases.

Business Problems Involving Correlation:

In the last lecture, you learnt the concept of correlation and its interpretation.
 But it is also important to understand how correlation is used in the industry. 
 Let’s see how correlation is used through a real example of stock market analysis.


There are two things which you would have noticed from the lecture:
The correlation matrix of stock prices of different countries gives a real sense of the relationship between many variables.
The correlated variables are grouped by similarities, and correlation can also be calculated for ‘groups of variables’. This is called ‘clustering’ which you will study in detail later in the machine learning course, but the idea is to form a hierarchy of similar groups of variables.


Bivariate Analysis on Categorical Variables:

So far, you have learnt how to analyse the relationship between two continuous variables.
You will now learn how to quantify and understand the relationship between pairs of categorical and continuous variables.

Categorical variable does not have concept of increase it has bunch of categories .
Degree of edu impact of marks . 

Impact of one perticuler variable in contest of another both of them categorical.



The categorical bivariate analysis is essentially an extension of the segmented univariate analysis to another categorical variable. In segmented univariate analysis, you compare metrics such as ‘mean of X’ across various segments of a categorical variable, e.g. mean marks of a student are higher for ‘degree and above’ than other levels of the mother’s education; or the median income of educated parents is higher than that of uneducated ones, etc.

 

In the categorical bivariate analysis, you extend this comparison to other categorical variables and ask — is this true for all categories of another variable, say, men and women? Take another categorical variable, such as state, and ask — is the median income of educated parents higher than that of uneducated ones in all states?

 

Thus, you are drilling down into another categorical variable and getting closer to the true patterns in the data. In fact, you may also go to the next level and ask — is the median income of educated parents higher than that of uneducated ones (variable 1)  in all states (variable 2) for all age groups (variable 3)? This is what you may call ‘trivariate analysis’, and though it gives you a more granular version of the truth, it gets a bit complex to make sense of and explain to others (and hence it is not usually done in EDA).

Thus, remember that only conducting segmented univariate analysis may deceive you into thinking that a certain phenomenon is true without asking the question — is it true for all sub-populations or is it true only when you aggregate information across the entire population?

 

So in general, there are two fundamental aspects of analysing categorical variables:

To see the distribution of two categorical variables. For example, if you want to compare the number of boys and girls who play games, you can make a ‘cross table’ as given below:

Fig-1: Cross Table
Fig-1: Cross Table
From this table, firstly, you can compare boys and girls across a fixed level of ‘play games’, e.g. a higher number of boys play games every day than girls, a higher number of girls never play games than boys, etc. And secondly, you can compare the levels of ‘play games’ across a fixed value of gender, e.g. most boys play every day and very few play once a month or never.

 

To see the distribution of two categorical variables with one continuous variable. For example, you saw how a student’s percentage in science is distributed based on the father’s occupation (categorical variable 1) and the poverty level (categorical variable 2).

 

Usually, you do not analyse more than two variables at a time, though there are ways to do that. Machine learning models are essentially a way to do that, some of which you will learn in the next course.

In bivariate analysis, there are broadly two types of analysis that you learnt:  

Bivariate analysis on continuous variables

Bivariate analysis on categorical variables


What influences what is key question of bivariate analysis.


Loading data --> cleaning data  > analyzes indicf --> broke data in cheunk and segment  --> bivariate 

-------------------------------------------------------------------------------------
 ‘Derived Metrics’.
 -------------------------------------------------------------------------------------------------------
 In this session
In this session, you will learn how to create new variables using existing ones and get meaningful information by analysing them. In other words, we will discuss some methods to derive new metrics from the existing ones. The agenda for the session is as follows:

    Type-driven metrics

    Business-driven metrics

    Data-driven metrics

What Are Derived Metrics?
Sometimes, you would not get the most valuable insights by analysing the data available to you. You often need to create new variables using the existing ones to get meaningful insights.
New variables could be created based on your business understanding or they can be suggested by your clients. Let’s understand how business understanding plays an important role in deriving new variables.


To summarise, you saw two examples of different problems — analysing restaurant sales and understanding the marks distribution of class XII students.
In the first example, the ‘day of the week’ was a derived variable which was not provided in the original data set (only the date was provided). Using this new variable (day of the week), you can ‘drill down’ to compare the total sales on each day of the week and present the results on the calendar, as shown in figure 1 below.

To summarise, you saw two examples of different problems — analysing restaurant sales and understanding the marks distribution of class XII students.
In the first example, the ‘day of the week’ was a derived variable which was not provided in the original data set (only the date was provided). Using this new variable (day of the week), you can ‘drill down’ to compare the total sales on each day of the week and present the results on the calendar, as shown in figure 1 below.

In the second example, by plotting the marks against the ‘month of birth’ (derived variable), it was observed that the children who were born after June would have missed the cutoff by a few days and gotten admission at the age of 5. The ones born after June (e.g. July, August, etc) were intellectually and emotionally more mature than their peers because of their higher age, resulting in better performance.

This is a classic example of how derived metrics can help you discover unexpected insights.

So far, we have discussed only how to derive a new variable from the date variable. Are there other types of derived metrics as well? And is there a process of deriving new metrics?


Types of Derived Metrics: Type Driven Metrics: -

Broadly, there are three different types of derived metrics:

1.    Type-driven metrics: 

2.    Business-driven metrics

3.    Data-driven metrics

 

Type-Driven Metrics


These metrics can be derived by understanding the variable’s typology. You have already learnt one simple way of classifying variables/attributes — categorical (ordered, unordered) and quantitative or numeric. Similarly, there are various other ways of classification, one of which is Steven's typology.


Steven’s typology classifies variables into four types — nominal, ordinal, interval and ratio:

    Nominal variables: Categorical variables, where the categories differ only by their names; there is no order among categories, e.g. colour (red, blue, green), gender (male, female), department (HR, analytics, sales)
    These are the most basic form of categorical variables

    Ordinal variables: Categories follow a certain order, but the mathematical difference between categories is not meaningful, e.g. education level (primary school, high school, college), height (high, medium, low), performance (bad, good, excellent), etc.
    Ordinal variables are nominal as well


    Interval variables: Categories follow a certain order, and the mathematical difference between categories is meaningful but division or multiplication is not, e.g. temperature in degrees celsius ( the difference between 40 and 30 degrees C is meaningful, but 30 degrees x 40 degrees is not), dates (the difference between two dates is the number of days between them, but 25th May / 5th June is meaningless), etc.
    Interval variables are both nominal and ordinal


    Ratio variables: Apart from the mathematical difference, the ratio (division/multiplication) is possible, e.g. sales in dollars ($100 is twice $50), marks of students (50 is half of 100), etc.
    Ratio variables are nominal, ordinal and interval type


Derived metric from date and time :

Date:

Day - month - Quatar - year - decade - 
summer - winter - monsoon
weekday - weekend - month start - month end
Day since last activity 


Time:
Hour -min - sec-am -pm
Morning, afternoon , evening , night 
working / non working hour.


Derived metric from Location:

City  - ZIp code -pin code
Administation --> North of country east of country etc.
Demographic --> urban rural 
Rulling party --> 


quantititive variable: 

create series of categorical vaiable by binning quantitive variable in bucket binning and univariate anlysis.

Type Based metric:

WEB URL:

Host domain
parameter 
Hashage 

NAMES:

Firstnmae 
surname 
middlename

EMAILS:

Domain .com , co.in 

IMAGE URL:

Format - GIF,JPEG,PNG

Size resolution picture clip art 
pencil sketches.




Business Driven Metrics: -

So far, you've learned how to extract meaningful information from existing variables, e.g. extracting a "month" variable from the date variable.
 But what if you want to extract information that requires business expertise? For example, if you wish to know which students passed based on a list of scores in an exam, 
 you need to know the criteria for passing the exam.

Let’s see how Anand approaches business-driven metrics. 

To summarise, there are three types of derived metrics:

Type-driven: Each of the attribute can create column.
Business-driven: business logic need to be understood and create logic .
Data-driven: Find high co relation in 2 var take ratio
 

Deriving metrics from the business perspective is not an easy task. 
It requires decent domain experience. Without understanding the domain correctly, deriving insights becomes difficult and prone to errors. 

Let's try out an exercise. You have been using the National Achievement Survey data set starting since EDA.
 In case you don't have the data set yet, you can download the National Achievement Survey from the link below to answer the question that follows.

 STUDENTS MARKS:

 pass/ fail
 CGPA / CUTOFF

Banking:

Number of transaction.

min avg balence maintained.

no of card issues equal to target.


Cricket:

Scored century or not.


Modeling singel largest driver is variable one picks more derived column.   



Data Driven Metrics:


In the last lecture, you learnt to create business-driven metrics. Apart from the type-driven and business-driven metrics, there is a third type of metric called data-driven metrics.     

 

Let see how the data-driven metrics can be created from existing data.

To summarise, data-driven metrics can be created based on the variables present in the existing data set. For example, if you have two variables in your data set such as "weight" and "height" which shows a high correlation. So, instead of analysing "weight" and "height" variables separately, you can think of deriving a new metric "Body Mass Index (BMI)". Once you get the BMI, you can easily categorise people based on their fitness, e.g. a BMI below 18.5 should be considered as an underweight category, while BMI above 30.0 is considered as obese, by standard norms. This is how data-driven metrics can help you discover hidden patterns out of the data.







 
 