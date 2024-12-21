# Introduction

Welcome to the session on 'K-Means Clustering'. In the previous session, you got a basic idea of what unsupervised learning is. You also learnt about one such unsupervised technique called clustering. Now let's dive deeper into the concept and learn about the first common algorithm to achieve this unsupervised clustering — the K-Means algorithm.


In this session

You will learn about:

- The steps in the K-Means algorithm

- How to graphically visualise the steps of K-Means algorithm

- Practical considerations while using the K-Means algorithm


# Euclidean Distance
In the previous segments, you got an idea about how clustering works - it groups the objects on the basis of their similarity or closeness to each other.

Now, the next important thing is to get into the nitty-gritty of how clustering algorithms generally work. You will learn about the 2 types of clustering methods - K-means and Hierarchical and how they go about doing the clustering process.

We have learnt that clustering works on the basis of grouping the observations which are the most similar to each other. What does this exactly mean?

 
In simple terms, the algorithm needs to find data points whose values are similar to each other and therefore these points would then belong to the same cluster. The method in which any clustering algorithm goes about doing that is through the method of finding something called a “distance measure”. The distance measure that is used in K-means clustering is called the Euclidean Distance measure. Let’s look at the following lecture to understand how this value is calculated.

As mentioned in the video above, the Euclidean Distance between the 2 points is measured as follows: If there are 2 points X and Y having n dimensions

 

X=(X1,X2,X3,...Xn)
Y=(Y1,Y2,Y3,....Yn)


Then the Euclidean Distance D is given as 

D=√(X1−Y1)2+(X2−Y2)2+...(Xn−Yn)2

The idea of distance measure is quite intuitive. Essentially, the observations which are closer or more similar to each other would have a low Euclidean distance and the observations which are farther or less similar to each other would have a higher Euclidean distance. So can you now guess how the Clustering process would work based on the Euclidean distance?


Now once you’ve computed the Euclidean distance, the next step is pretty straightforward for the Clustering Algorithm. All it has to do is compute these distances and then find out which observations or points have a low Euclidean distance between them, i.e. are closer to each other and then cluster them together.

 
Now answer the following questions

Q1)
Euclidean Distance.
Consider the 2 points A(7,50) and B(23,34). Compute the Euclidean Distance between the two.

[Round off the answer to 2 decimal places.]
==>

22.63

✓ Correct
Feedback:
Euclidean Distance between the 2 points is given by the formula D = √ [(7-23)^2 +(50-34)^2] = √ (16^2  +16^2) = √(512) = 22.63

Q2)

Euclidean Distance
Consider the same 2 points A(7,50) and B(23,34). Which point is closer to point C(12,12)?

==>

B

✓ Correct
Feedback:
Euclidean Distance between 2 points X (X1, X2) and Y(Y1, Y2) is given by √[(X1-X2)^2 +(Y1-Y2)^2]. Substituting the values for A, C and B, C in the given expression we get the distance AC as √(1469) = 38.33 and BC as √(605) =24.59. Therefore, point B is closer to C.



# Centroid
The next concept that is crucial for understanding how clustering generally works is the idea of centroids. If you remember your high school geometry, centroids are essentially the centre points of triangles. Similarly, in the case of clustering, centroids are the centre points of the clusters that are being formed.

 

Now before going to the formula part, here is an intuition for the need of a centroid. Imagine you have the following clusters of the marks of a group of students in Mathematics and Biology and someone asks you to explain them. From a glance, you can easily interpret the 4 clusters that are being formed 


So the four clusters that are being formed are as follows:

 

Cluster 1: Students who have scored high marks in Bio, but poor marks in Maths
Cluster 2: Students who have scored average  marks in Bio and  Maths
Cluster 3: Students who have scored high marks in both Bio and Maths.
Cluster 4: Students who have scored high marks in Maths, but poor marks in Bio

 

Now the above representation is fine and correct, but it is missing one crucial information - the numerical order. For example, when you want to compare two clusters say Cluster 1 and Cluster 2 can you say by how much marks on average do the students from Cluster 1 outperform or underperform the Cluster 2 students in a particular subject just by taking a look at the above visualisation alone? Is it by 10 marks? Or 15?

 

This is where the concept of Centroids come in handy. Listen to the following lecture to understand its importance and how it is calculated.


Therefore, as mentioned in the video, the Centroids are essentially the cluster centres of a group of observations that help us in summarising the cluster's properties. Thus as you saw in the video, the centroid value in the case of clustering is essentially the mean of all the observations that belong to a particular cluster. For example, in the dataset that you saw here,

 


The centroid is calculated by computing the mean of each and every column/dimension that you have and then ordering them in the same way as above

Therefore, Height-mean = ((175+165+183+172)/)/4  = 173.75
                    Weight-mean = ((83+74+98+80))/4 = 83.75
                    Age - mean = ((22+25+24+24))/4 =23.75

Thus the centroid of the above group of observations is (173.75, 83.75 and 23.75)

 

Now that you've understood how the centroids are calculated, answer the following question.


Q1) 
Centroid Calculations
Find the centroid of the following 5 observations

X	Y	Z
12	23	45
31	31	31
17	15	25
19	27	45
13	11	27


==>

Feedback:
For computing the centroids, for all the five observations, you have to compute the mean of each column X, Y and Z. On calculating the values, the answer comes out to be [18.4, 21.4, 34.6]

# Steps of the Algorithm

Let’s go through the K-Means algorithm using a very simple example. Let’s consider a set of 10 points on a plane and try to group these points into, say, 2 clusters. So let’s see how the K-Means algorithm achieves this goal.

 

[Note: If you don't know what is meant by Euclidean distance, you're advised to go through this link]

Before moving ahead, think about the following problem. Let’s say you have the data of 10 students and their marks in Biology and Math (as shown in the plot below). You want to divide them into two clusters so that you can see what kind of students are there in the class.

The y-axis shows the marks in Biology, and the x-axis shows the marks in Math.

Imagine two clusters dividing this data — one red and the other yellow. How many points would each cluster have?

Fig 1: Random points to be divided into 2 clusters
Fig 1: Random points to be divided into 2 clusters
Centroid

The K-Means algorithm uses the concept of the centroid to create K clusters. Before you move ahead, it will be useful to recall the concept of the centroid.

In simple terms, a centroid of n points on an x-y plane is another point having its own x and y coordinates and is often referred to as the geometric centre of the n points.

For example, consider three points having coordinates (x1, y1), (x2, y2) and (x3, y3). The centroid of these three points is the average of the x and y coordinates of the three points, i.e.

(x1 + x2 + x3 / 3, y1 + y2 + y3 / 3).

Similarly, if you have n points, the formula (coordinates) of the centroid will be:

(x1+x2…..+xn / n, y1+y2…..+yn / n). 


So let’s see how the K-Means algorithm achieves this goal.

Each time the clusters are made, the centroid is updated. The updated centroid is the centre of all the points which fall in the cluster associated with the centroid. This process continues till the centroid no longer changes, i.e. the solution converges.

 

Thus, you can see that the K-means algorithm is a clustering algorithm that takes N data points and groups them into K clusters. In this example, we had N =10 points and we used the K-means algorithm to group these 10 points into K = 2 clusters.


Download the Excel file below. It is designed to give you hands-on practice of k-means clustering algorithm. The file contains a set of 10 points (with x and y coordinates in column A and B respectively) and two initial centres 1 and 2 (in columns F and G). Answer the questions below based on the Excel file.



Q1) K-Means algorithm
Find the distance of each of the 10 points from the two cluster centers (in column H & I) and fill the cells S6:T16. Select the distance formula to be used to find the distance of a point (xi,yi) from a centre (Xi,Yi).

==>

SQRT(((Xi-xi)^2) + (Yi-yi)^2))
✓ Correct
Feedback:
This is the formula for the Euclidean distance. You can see that once the cells S6:T16 are filled with the required distances, the points are assigned to one of the clusters (marked in column E) based on the minimum distance.

Q2) K-Means algorithm
In the next step of k-means clustering, you need to find the new cluster centers (H22:I23). Select the correct method used to find the new cluster centers.

==> 


Calculate the centroid of the points assigned to a particular cluster in the previous step
✓ Correct
Feedback:
The way is new center is calculated in K-Mean clustering is the mean of all the data points belonging to that cluster.Notice that the new centers are already filled in the excel sheet.

Q3) 
K-Means algorithm
Repeating the previous two steps again, you get the new cluster centers (H38:I39).Continue this process until the algorithm converges (Two consecutive iterations have the same center). What are the x and y coordinates of the center of cluster 1 finally?

==>


5.6, 5.4
✓ Correct
Feedback:
Notice the clusters formed on the chart with their centers. You can explore k the -means algorithm by randomly assigning the centers and looking at the number of iterations needed for convergence.





# K Means Algorithm
In the previous segment, we learned about K-means clustering and how the algorithm works using a simple example. We learned about how assignment and the optimisation work in K Means clustering, Now in this lecture, we will look K-means more algorithmically. We will be learning how the K Means algorithm proceeds with the assignment step and then with the optimisation step and will also be looking at the cost of function for the K-means algorithm.


Let's understand the K-means algorithm in more detail.
 
 From the previous lecture, we understood that the algorithm’s inner-loop iterates over two steps:

Assign each observation 
1. Xi to the closest cluster centroid 
2. μk Update each centroid to the mean of the points assigned to it.
In the next lecture, we will learn about the Kmeans cost function and will also see how to compute the cost function for each iteration in the K-means algorithm.

So the cost function for the K-Means algorithm is given as: 

 
J=∑ni=1||Xi−μk(i)||2=∑Kk=1∑iϵCk||Xi−μk||2

Now in the next video, we will learn what exactly happens in the assignment step? and we will also look at how to assign each data point to a cluster using the K-Means algorithm assignment step.

Q1)

K-Means
What is the significance of "argmin" in the assignment step equation?

For a ith data point which is a 2d object and 
μ which is again a 2d object, we compute the distance between these two, this is given by 
d(xi,μk) where k is the number of clusters and then from these k different results we will choose the minimum of all.


In the assignment step, we assign every data point to K clusters. The algorithm goes through each of the data points and depending on which cluster is closer, in our case, whether the green cluster centroid or the blue cluster centroid; It assigns the data points to one of the 2 cluster centroids.

he equation for the assignment step is as follows:

 

Zi=argmin||Xi−μk||2

Now having assigned each data point to a cluster, now we need to recompute the cluster centroids. In the next lecture, Prof.Dinesh will explain how to recompute the cluster centroids or the mean of each cluster.

In the optimisation step, the algorithm calculates the average of all the points in a cluster and moves the centroid to that average location.

 

The equation for optimisation is as follows:

 

μk=1nk∑i:zi=kXi
 
The process of assignment and optimisation is repeated until there is no change in the clusters or possibly until the algorithm converges.


In the next segment, we will learn how to look K-Means algorithm as a coordinate descent problem. We will also learn about the constraint of the K-Means cost function and how to achieve global minima.

 
 Example:

 Clustering in sports analytics segments players into distinct groups based on performance metrics and physical attributes. The process involves data collection, normalization, and feature selection, followed by applying algorithms like K-Means, Hierarchical Clustering, or DBSCAN. These methods identify patterns and similarities among players, aiding in team formation, talent scouting, and strategy development. Cluster validation techniques ensure the quality of the groups formed. By understanding the characteristics of each cluster, coaches and managers can make informed decisions, leading to balanced teams and tailored game strategies, ultimately enhancing competitive performance.


Confused? Let's move to the next segment to understand this in detail.




# K Means++ Algorithm

We looked in the previous segment that for K-Means optimisation problem, the algorithm it iterate between two steps and tries to minimise the objective function given as,

Zi=argmin||Xi−μk||2


To choose the cluster centers smartly, we will learn about K-Mean++ algorithm. K-means++ is just an initialisation procedure for K-means. In K-means++ you pick the initial centroids using an algorithm that tries to initialise centroids that are far apart from each other.

Let's understand the algorithm in detail in the next lecture.




To summarise, In K-Means++ algorithm,

We choose one center as one of the data points at random.
For each data point 
Xi, We compute the distance between 
Xi and the nearest center that had already been chosen.
Now, we choose the next cluster center using the weighted probability distribution where a point 
X is chosen with probability proportional to 
d(X)2 .Repeat Steps 2 and 3 until 
K centers have been chosen.

# Visualising the K Means Algorithm
Let’s see the K-Means algorithm in action using a visualisation tool. This tool can be found on naftaliharris.com. You can go to this link after watching the video below and play around with the different options available to get an intuitive feel of the K-Means algorithm.


Upon trying the different options, you may have noticed that the final clusters that you obtain vary depending on many factors, such as choice of the initial cluster centres and the value of K, i.e. the number of clusters that you want. You will understand these factors and other practical considerations while using the K-means algorithm in more detail in the next segment.

 
Now look at the given image and answer the question that follows:

Intuitively, it looks like 2 clusters are present. If we use K means, then we will get wrong clusters since the points in the outer ring like structure will not be segmented accurately. A reason for that is K-Means looks for how close the points are to a centroid and this distance or measure of closeness is the “linear distance”. One way to correct this can be to see the distance between all the points and then cluster the closest points.

# Practical Consideration in K Means Algorithm
Let’s understand some of the factors that can impact the final clusters that you obtain from the K-means algorithm. This would also give you an idea about the issues that you must keep in mind before you start to make clusters to solve your business problem.

Thus, the major practical considerations involved in K-Means clustering are:

- The number of clusters that you want to divide your data points into, i.e. the value of K has to be pre-determined.

- The choice of the initial cluster centres can have an impact on the final cluster formation.

- The clustering process is very sensitive to the presence of outliers in the data.

- Since the distance metric used in the clustering process is the Euclidean distance, you need to bring all your attributes on the same scale. This can be achieved through standardisation.

- The K-Means algorithm does not work with categorical data.

- The process may not converge in the given number of iterations. You should always check for convergence.

You will understand some of these issues in detail and also see the ways to deal with them when you implement the K-means algorithm in Python.

 
Now let's look in detail how to choose K for K-Means algorithm.



So to compute silhouette metric, we need to compute two measures i.e. 
a(i) and b(i) where,

a(i) is the average distance from own cluster(Cohesion).
b(i) is the average distance from the nearest neighbour cluster(Separation). 
Now, let's look at how to combine cohesion and separation to compute the silhouette metric.

Additional reading
You can read more about K-Mode clustering here, We will be covering it in detail in the next section.


Q1)

K-Means algorithm
If we are worried about K-means getting stuck in bad local optima, one way to solve this problem is if we try using multiple random initializations. Is this true or false? You can read about local optimum and global optimum here

==>
Since each run of K-means is independent, multiple runs can find different local optima, and this can help in choosing the global optimum value.


# Cluster Tendency
Before we apply any clustering algorithm to the given data, it's important to check whether the given data has some meaningful clusters or not? which in general means the given data is not random. The process to evaluate the data to check if the data is feasible for clustering or not is know as the clustering tendency.

 

As we have already discussed in the previous lecture that the clustering algorithm will return K clusters even if that data does not have any clusters or have any meaningful clusters. So before proceeding for clustering, we should not blindly apply the clustering method and we should check the clustering tendency.

 

Let's look in detail how it works.

To check cluster tendency, we use Hopkins test. Hopkins test examines whether data points differ significantly from uniformly distributed data in the multidimensional space.

 

Additional Resources
To read about Hopkins test in detail, please follow this [link1](http://www.sthda.com/english/articles/29-cluster-validation-essentials/95-assessing-clustering-tendency-essentials/#methods-for-assessing-clustering-tendency), [link2](https://stats.stackexchange.com/questions/332651/validating-cluster-tendency-using-hopkins-statistic), remember that the document is described using R programming, please ignore it.


---

We covered a lot in this session. We started with understanding the K-Means intuitively by grouping the 10 random points in 2 clusters.


 

The algorithm begins with choosing K random cluster centres.

 

Then the 2 steps of Assignment and Optimisation continue iteratively till the clusters stop updating. This gives you the most optimal clusters — the clusters with minimum intra-cluster distance and maximum inter-cluster distance.

 

You also saw the different practical issues that need to be considered while employing clustering to your data set. You need to choose how many clusters you want to group your data points into. Secondly, the K-means algorithm is non-deterministic. This means that the final outcome of clustering can be different each time the algorithm is run even on the same data set. This is because, as you saw, the final cluster that you get can vary by the choice of the initial cluster centres.

 

You also saw that the outliers have an impact on the clusters and thus outlier-infested data may not give you the most optimal clusters. Similarly, since the most common measure of the distance is the Euclidean distance, you would need to bring all the attributes into the same scale using standardisation.

 

You also saw that you cannot use categorical data for the K-Means algorithm. There are other customised algorithms for such categorical data.

 

Additional Content - Soft Skills:
Navigate here to access the soft skills content related to the Case Studies


Q1)

K-Means algorithm
Arrange the steps of k-means algorithm in the order in which they occur:

Randomly selecting the cluster centroids
Updating the cluster centroids iteratively
Assigning the cluster points to their nearest center

==>

1-3-2

✓ Correct
Feedback:
First the cluster centers are pre-decided. Then all the points are assigned to their nearest cluster center and then the center is recalculated as the mean of all the points which fall in that cluster. Then the clustering is repeated with the new centers and the centers are updated according to the new cluster points.

Q2) 

K-Means algorithm
Consider three cluster centres A(2,3), B(4,5) and C(6,2). A point (1,2) is to be assigned to one of these clusters. According to k-means clustering concepts and using euclidean distance as the measure of closeness, which cluster should it be assigned to?

==>


A

✓ Correct
Feedback:
According to k-means algorithm, the point should be assigned to the centre with the minimum distance from the point. The distances for A, B, C are sqrt(2), sqrt(18) and sqrt(25)

Q3)

K-Means algorithm
Which of the following options are prerequisites for k-means algorithm:

 


A) initial centers should be very close to each other

B) Choice of number of clusters

C) Choice of initial centroids

==>

B & C

✓ Correct
Feedback:
Note that the k-means algorithm requires the initial centers to be far apart.

# Executing K means - Python 

Data Understanding and Data Cleaning
In this session, you'll learn how to create clusters on the basis of K-means clustering algorithm in Python. Before that, you need to understand the dataset that we'll be using for this demonstration. You can download the data set for the case study from this link here.


Also, you can get the final analysis python notebook from the link given below. 

 

Please find the code file here

Let's hear from Prof. Dinesh as he explains the dataset to us.

Now  let's observe how to understand the data using Python.


Since you'd be doing a pretty huge analysis it is always a good idea to write the steps first.



Now that you've understood what to do with the dataset, it's always a good idea to start with cleaning the data first.

In the next segment, we'll start with the data preparation part.

# Data Preparation - I
Now that you've cleaned the data, the next step is to prepare it for the modelling part. Take a look at the RFM part once again.


The next thing is monetary and frequency column creation.

FInally we need to analyse the recency part once again.

In the next segment we'll take a look at the scaling part of the analysis

# Data Preparation - II

The next important concepts that need to be applied in the data preparation stage are outlier treatment and standardisation of the data. Let's understand both of them in detail.

Now let's about outlier treatment.

Now let's go ahead and complete the preprocessing part of standardisation

---
Hopkins Statistics

 

One more important data preparation technique that we also need to do but have skipped in the demonstration is the calculation of the Hopkins Statistic. In python, you can use the following code snippet to pass a dataframe to the Hopkins statistic function to find if the dataset is suitable for clustering or not. You can simply copy-paste the code present in the code given below to the main dataset and analyse the Hopkins statistic value.

Please find the code file


Notes regarding Hopkins Statistic

- You don't need to know how the algorithm of  Hopkins Statistic works. The algorithm is pretty advanced and hence you don't need to know its workings but rather only interpret the value that it assigns to the dataframe.

- On multiple iterations of Hopkins Statistic, you would be getting multiple values since the algorithm uses some randomisation in the initialisation part of the code. Therefore it is advised to run it a couple of times before confirming whether the data is suitable for clustering or not.


# Making the Clusters
Now let's begin the modelling part by creating the clusters using the SKlearn's K-means algorithm package.

# Optimal Number of Clusters

Now you might be thinking why the number of clusters is taken as 4 and not any other number. To find the optimum number of clusters, we use two techniques - the elbow curve method and the silhouette score method. Let's learn about both of them in detail in the following lecture.


Next take a look at the silhouette score
Let's go  ahead and take it a step further in Python.

Now that you've understood the concept of finding the optimal number of clusters, the next segment would deal with analysing these clusters for further understanding our segmentation process.

# Cluster Analysis
First we need to assign the Cluster IDs that we generated to each of the datapoints that we have with us. Let's go ahead and do that.

The next step is interesting because we need to perform a bit of outlier analysis once again to understand how the dataset works here.

Now once the outlier analysis is completed, let's go ahead and analyse all the clusters that we have with us.



# Let's Have Some Fun
You have learnt about how to make clusters using the K-Means algorithm. Let's use that knowledge to play around with clustering using K-Means.


Please find the dataset here

The data contains state-level information on attributes such as the number of literates, illiterates, the number of literates who are graduate and above, etc.

But there’s a problem — the number of variables is quite large, and after forming the clusters, it may get difficult to describe each cluster’s characteristics.

 The data contains state-level information on attributes such as the number of literates, illiterates, the number of literates who are graduate and above, etc.


 

But there’s a problem — the number of variables is quite large, and after forming the clusters, it may get difficult to describe each cluster’s characteristics.

 

This is not an uncommon problem. You may have noticed data sets having as many as 100-200 variables. There are techniques which are used to ‘reduce the number of variables while retaining as much information as possible’.

 

Two most common techniques, also called variable reduction techniques, are factor analysis and principal component analysis.

 

Lawmakers can cluster the states to find out which states have similar education statistics, and thus assign the budget accordingly. Clustering can also help them figure out the best policies to make for these clusters.

 

You can download the data set and run the K-Means algorithm on this. You can try to make the clusters on different attributes. 


You can see the effect of various elements of the K-Means clustering on the clusters formed. You can zoom in by selecting and double-clicking the map to look at the clusters.

For the purpose of creating the above visualisation, we have cleaned the data to include only the 2 factors under consideration. You could have chosen any other factors as well. Factors here mean the variables that you will use to build the clustering model. You can download the file below to answer the questions that follow:


Q1)  K - Means in Python
Which parameters do you think are the most important for segmenting the states? How did you decide this?

==>

Suggested Answer
The parameters used depend on the question at hand. We can choose different age groups and different categories such as graduate or above etc.

Q2) K - Means in Python
How will you check if the segmenting is good or whether you need to use different factors for segmenting?

==>

One really easy way is to see if the .are logically correct. For example, we can check if states in a similar geography and economic situation are clustered together or not. You can also run hypothesis test to check whether the population of different clusters is significantly different or not, If you look at the data, you can see that some specific customers or some specific states should be grouped together.


Q3)
K - Means in Python
How are the clusters different when we have not scaled compared to clusters formed after scaling?

==>
Illiteracy percentage gets higher weightage when there is no scaling

✓ Correct
Feedback:
Look at the clusters formed with and without scaling. You will see that for the ones formed without scaling, the states with similar literacy rates will fall in the same cluster, even though their graduate percentage differs.


# Other Behavioural Segmentation Types

You have seen what RFM segmentation is. Now, you will look at other segmentation types commonly used in the industry.

You looked at RPI segmentation, which looks at what kind of relationship you have had with the person before, what type of person he/she is, and the intent of the person at the time of buying.

 

You also looked at the CDJ segmentation, which looks at the path that customers take while experiencing your product.

 

Now, let us turn our attention to another clustering technique — hierarchical clustering — in the next session.


# Summary


So what did you learn in this session?

 

You learnt how to create clusters using the K-means algorithm in Python with the analysis of the Online Store data set. We wanted to group the customers of the store into different clusters based on their purchasing habits. The different steps involved were:

Missing values treatment

Data transformation

Outlier treatment

Data standardisation

Finding the optimal value of K

Implementing K Means algorithm

Analysing the clusters of customers to obtain business insights

 


Once we are through with the data preparation, the K-means algorithm is quite easy to implement. All it takes is running the KMeans() function. The only ambiguous point you may notice here is that you need to decide the number of required clusters beforehand and in fact run the algorithm multiple times with a different number K before you can figure out the most optimal number of clusters.

 

This is also what happens in the industry practices that we run the algorithm multiple times with different values of K and then pick the clusters which make the most business sense. In fact, the k-means algorithm finds large application in the industry. For example, it can be used to find out the most optimal centre to install the mobile towers by clustering the customers geographically. Similarly, it has wide application in medical science, where say the patients can be clustered together on the basis of their symptoms, and then analysed to figure out the cause of their illness.

 

However, K means was just one of the clustering algorithm. In the next session, we will learn about another clustering algorithm called hierarchical clustering, which does not require you to decide the number of clusters beforehand.


Graded:

K-Means algorithm
Select the problem sets, where k-means clustering can be applied.

==>

Given an ecom company’s customer details - the products they purchased and the amount spent. The company wants to group it’s customers based on their buying behaviour.
✓ Correct
Feedback:
The given option is correct. The other options are predicting the response based on independent variables.


Q2) K-Means algorithm
Select the correct statement among the following:

=-=>

The results of k-means algorithm get impacted by outliers and range of the attributes.
✓ Correct
Feedback:
Depending on the initial selection of centers, the formed clusters might be different. The value of k has to be decided by the user

Q4)

Cricket
Based on the clustering, choose the correct statement given that the clusters formed are (high SR, high Ave) - A, (low SR, low Ave) - B, (High SR, Low Ave) - C, (Low SR, High Ave) - D

==>

IVA RIchards and SR Tendulkar both belong to group A
✓ Correct
Feedback:
You can even plot the graph after scaling for better separation of points and more intuitive visualisation.