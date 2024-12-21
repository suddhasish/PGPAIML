# Understanding Clustering


In the previous modules, you saw various supervised machine learning algorithms. Supervised machine learning algorithms make use of labelled data to make predictions.

 

For example, an email will be classified as spam or ham, or a bank’s customer will be predicted as ‘good’ or ‘bad’. You have a target variable Y which needs to be predicted.

 

On the other hand, in unsupervised learning, you are not interested in prediction because you do not have a target or outcome variable. The objective is to discover interesting patterns in the data, e.g. are there any subgroups or ‘clusters’ among the bank’s customers?

Let’s learn clustering in detail.

So you saw the favourite tourist destinations of Prof. Dinesh and Rohit. You also saw the emerging pattern in the places preferred by the Professor and Rohit. However, how does all this relate to the concept of unsupervised learning?


So you saw the favourite tourist destinations of Prof. Dinesh and Rohit. You also saw the emerging pattern in the places preferred by the Professor and Rohit. However, how does all this relate to the concept of unsupervised learning?



PRACTICAL APPLICATIONS OF CLUSTERING

 

1. Customer Insight: Say, a retail chain with so many stores across locations wants to manage stores at best and increase the sales and performance. Cluster analysis can help the retail chain to get desired insights on customer demographics, purchase behaviour and demand patterns across locations. This will help the retail chain for assortment planning, planning promotional activities and store benchmarking for better performance and higher returns.

2. Marketing: Cluster Analysis can help with In the field of marketing, Cluster Analysis can help in market segmentation and positioning, and to identify test markets for new product development.
Social Media: In the areas of social networking and social media, Cluster Analysis is used to identify similar communities within larger groups.
3. Medical: Cluster Analysis has also been widely used in the field of biology and medical science like human genetic clustering, sequencing into gene families, building groups of genes, and clustering of organisms at species. 


In the next segment, you will be introduced to a real-life application of clustering — grouping customers of an online store into different clusters and making a separate targeted marketing strategy for each group. We will be using this example throughout the module.


# Practical Example of Clustering - Customer Segmentation
In the last segment, you got a basic idea of what clustering is. So let’s consider a real-life application of the unsupervised clustering algorithm.

 Customer segmentation for targeted marketing is one of the most vital applications of the clustering algorithm. Here, as a manager of the online store, you would want to group the customers into different clusters, so that you can make a customised marketing campaign for each of the group. 


 You do not have any label in mind, such as good customer or bad customer. You want to just look at patterns in customer data and then try and find segments. This is where clustering techniques can help you with segmenting the customers. Clustering techniques use the raw data to form clusters based on common factors among various data points. This is exactly what will also be done in segmentation, where various people or products will be grouped together on the basis of similarities and differences between them.


 As a manager, you would have to decide what the important business criteria are on which you would want to segregate the customers. So, you would need a method or an algorithm that itself decides which customers to group together based on this criteria.

 

Sounds interesting? Well, that is the beauty of unsupervised learning, especially clustering. But before we conclude this introductory session, it would be best to get an industry perspective on the application of clustering in the world of analytics.



You saw that, for successful segmentation, the segments formed must be stable. This means that the same person should not fall under different segments upon segmenting the data on the same criteria. You also saw that segments should have intra-segment homogeneity and inter-segment heterogeneity. You will see in later sessions how this can be defined mathematically.


Now you will see what types of market segmentations are commonly used.



You saw that mainly 3 types of segmentation are used for customer segmentation:

- Behavioural segmentation: Segmentation is based on the actual patterns displayed by the consumer
- Attitudinal segmentation: Segmentation is based on the beliefs or the intents of people, which may not translate into similar action
- Demographic segmentation: Segmentation is based on the person’s profile and uses information such as age, gender, residence locality, income, etc.


You will also learn in later sessions about the different types of behavioural segmentations used in the industry.


Additional reading
You can read more about business cases where clustering is used [here](https://dzone.com/articles/10-interesting-use-cases-for-the-k-means-algorithm)



Q1)

Type of Segmentation
A telecom company classifies its prepaid mobile customers into three types mainly based on the number of times they recharge per month. This is a type of:

==> 
Behavioral segmentation
✓ Correct
Feedback:
Recharge is a behaviour which can be observed, opposed to attitude which resides in the mindset of the customer

Q2)

Clustering
An international foods and beverages company wants to look at what products it should launch in India. For that, it has first tried to segment the market. It is known that people living in the same area and having similar salaries will have similar eating habits. Then which of the following can be segmented in 1 group? (All options in 1 bracket are 1 segment)


A. High Earning Individual from Bengaluru

B. Low Earning Individual from Rural Uttar Pradesh

C. Mid Earning Individual from Mumbai

D. High Earning Individual from Hyderabad
==>

(A,D) - (B) - (C)
✓ Correct
Feedback:
You want to ensure that the people in One segment are very similar and the people in different segments are very dissimilar. So Option C is good segment to make

Q3)

Segmentation Factors
You learnt that clustering is commonly used for segmenting customers. Can you think of some features on which you would want to segment the customers of an online store? Go back and check the data ‘online retail’ if needed.

Q4)

Segmentation Types
You are an analyst at a global laptop manufacturer and are given the task of deciding whether the company should enter the Indian Market. You try to estimate the market size by first breaking the market by different types of people who use a laptop such as students, working professionals and their paying capacity to get an estimate of the total market size and the characteristics of each segment. In essence, you are doing:

==>

Demographic Segmentation
✓ Correct
Feedback:
You are doing a demographic segmentation, since you are looking at the income and the profession of people. Notice how this is much simpler than finding data about actual laptop purchasing history of customers and then trying to estimate the market size based on that.

----

Summary
In this session, we covered the basics of unsupervised learning and also got a little idea about how clustering works. In the next sessions, you will go deeper into the details of clustering and learn about the 2 common clustering algorithms —

-  the K-Means algorithm and
- the Hierarchical clustering algorithm.


Q1)

Clustering
Which of the following are applications of clustering?

==>

Looking at social media behaviour to find out what types of online communities are there

Identify consumer segments and their properties to position products appropriately

Identifying patterns of crime in different regions of a city and managing police enforcement based on frequency and type of crime.


