# Introduction
Welcome to the session on 'Hierarchical Clustering'. In the previous sessions, you got a basic understanding of what clustering is and how you can use the K-Means algorithm to create clusters in your data set. You also saw the execution of the K-Means algorithm in Python.

In this session
You will learn about another algorithm to achieve unsupervised clustering. This is called Hierarchical Clustering. Here, instead of pre-defining the number of clusters, you first have to visually describe the similarity or dissimilarity between the different data points and then decide the appropriate number of clusters on the basis of these similarities or dissimilarities.

 

You will learn about:

- Hierarchical clustering algorithm
- Interpreting the dendrogram
- Cutting the dendrogram
- Types of linkages

Hierarchical Clustering Algorithm
One of the major considerations in using the K-means algorithm is deciding the value of K beforehand. The hierarchical clustering algorithm does not have this restriction.


The output of the hierarchical clustering algorithm is quite different from the K-mean algorithm as well. It results in an inverted tree-shaped structure, called the dendrogram. An example of a dendrogram is shown below.

Let's see how hierarchical clustering works.

Q1)

Hierarchical Clustering
You had made clusters for it using the K-Means algorithm. How do you think clusters will be made using hierarchical algorithm on this data?

==>
Suggested Answer
Since now you are looking at the closest distance between clusters, you will get two clusters - one at the center and the one which contains the points at the edges.

Q2)

Hierarchical Clustering
Look at the following matrix. This is the distance matrix between 4 points - A, B,C, D. Find out which 2 clusters will merge first.


 	A	B	C	D
A	 	 	 	 
B	2.24	 	 	 
C	8.06	10.00	 	 
D	5.83	8.06	5.00	 


==>

Look at the data and see that the minimum distance is between A and B

----
Interpreting the Dendrogram


The result of the cluster analysis is shown by a dendrogram, which starts with all the data points as separate cluster and indicates at what level of dissimilarity any two clusters were joined.

As you saw, the y-axis of the dendrogram is some measure of the dissimilarity or distance at which clusters join.


In the dendrogram shown above, samples 4 and 5 are the most similar and join to form the first cluster, followed by samples 1 and 10. The last two clusters to fuse together to form the final single cluster are 3-6 and 4-5-2-7-1-10-9-8. 


 

Determining the number of groups in a cluster analysis is often the primary goal. Typically, one looks for natural groupings defined by long stems. Here, by observation, you can identify that there are 3 major groupings: 3-6, 4-5-2-7 and 1-10-9-8.

 

You also saw that hierarchical clustering can proceed in 2 ways — agglomerative and divisive. If you start with n distinct clusters and iteratively reach to a point where you have only 1 cluster in the end, it is called agglomerative clustering. On the other hand, if you start with 1 big cluster and subsequently keep on partitioning this cluster to reach n clusters, each containing 1 element, it is called divisive clustering.



Comprehension - Hierarchical Clustering Algorithm

Given below are five data points having two attributes x and y.


Comprehension - Hierarchical Clustering Algorithm

Given below are five data points having two attributes x and y.

 

Observation	x	y
1	3	2
2	3	5
3	5	3
4	6	4
5	6	7
 

The distance matrix of the points, indicating the Euclidean distance between points, is as follows.

 

Label	1	2	3	4	5
1	0.00	3.00	2.24	3.61	5.83
2	3.00	0.00	2.83	3.16	3.61
3	2.24	2.83	0.00	1.41	4.12
4	3.61	3.16	1.41	0.00	3.00
5	5.83	3.61	4.12	3.00	0.00
 

Take the distance between two clusters as the minimum distance between the points in the two clusters. Based on this information, answer the following questions.

Q1)
Hierarchical Clustering
How many clusters are there initially (before any fusions have happened)?

==>

5
✓ Correct
Feedback:
Since this is agglomerative clustering, initially, all the points are 1 cluster.


Q2)

Hierarchical Clustering
Which two clusters will be fused first?

==>
3 and 4
✓ Correct
Feedback:
These two points(clusters) have the minimum distance.


Q3)

Hierarchical Clustering
Which clusters will be fused in step two?

==>


1 will be fused with the cluster(3, 4)
✓ Correct
Feedback:
The distance between points 1 and 3 is 2.24 units, which is the minimum among all the new clusters. Hence they will be joined now.

Q4)
Hierarchical Clustering
How many total clusters are there right after point number 1 fuses with the cluster(3, 4)?
==>

3
✓ Correct
Feedback:
Since three points have fused into 1 cluster, total clusters left are (1,3,4) - (2) - (5).

Q5)

Hierarchical Clustering
Which clusters will be fused after 1 fuses with (3, 4)?

==>

2 will fuse with the cluster (1, 3, 4)
✓ Correct
Feedback:
The distance of point 2 from point 3 is 2.83 units, whereas the minimum distance of point 5 from the cluster (1,3,4) is 3 units.

Q6) Hierarchical Clustering
What happens in the last step of the algorithm?

==>
5 fuses with ( 1, 2, 3, 4)
✓ Correct
Feedback:
Since all the other points are already part of one cluster, the last point will also join that cluster at this step.


# Types of Linkages
In our example, we took the minimum of all the pairwise distances between the data points as the representative of the distance between 2 clusters. This measure of the distance is called single linkage. Apart from using the minimum, you can use other methods to compute the distance between the clusters.


Let’s see once again the different types of linkages.

- Single Linkage: Here, the distance between 2 clusters is defined as the shortest distance between points in the two clusters
- Complete Linkage: Here, the distance between 2 clusters is defined as the maximum distance between any 2 points in the clusters
- Average Linkage: Here, the distance between 2 clusters is defined as the average distance between every point of one cluster to every other point of the other cluster.


You have to decide what type of linkage should be used by looking at the data. One convenient way to decide is to look at how the dendrogram looks. Usually, single linkage type will produce dendrograms which are not structured properly, whereas complete or average linkage will produce clusters which have a proper tree-like structure. You will see later what this means when you run the hierarchical clustering algorithm in Python.



Additional reading
You can read more about the type of linkages [here](http://www.saedsayad.com/clustering_hierarchical.htm), [here](https://stats.stackexchange.com/questions/195446/choosing-the-right-linkage-method-for-hierarchical-clustering) and [here](http://www.stat.cmu.edu/~ryantibs/datamining/lectures/05-clus2.pdf).



Q1) Hierarchical Clustering
Select the appropriate option which describes the Complete Linkage method.

==> 

In complete linkage hierarchical clustering, the inter cluster distance is defined as the longest distance between two points (one point in each cluster)
✓ Correct
Feedback:
In the complete linkage, inter cluster distance is calculated as the maximum distance between 2 points (one in each cluster), However, the point is assigned to a new cluster basis it’s minimum distance from the clusters

Q2) Hierarchical Clustering
Select the points which get clustered in the first iteration.(First iteration is defined as the first merging of clusters - ie, from n clusters to n-1 clusters)
==>


C, D
✓ Correct
Feedback:
Look at the distance between 2 points. You will see that the minimum distance is 2.2 units, which is between C and D

Q3) 
Hierarchical Clustering
Select the points which get clustered in the second iteration. Use single linkage method

==> 


A, E
✓ Correct
Feedback:
You can see that the minimum distance now is between point A and E, which is 3.2 units.

Q4) 
Hierarchical Clustering
How many iterations are required to form the final single cluster?
==>
Initially, n clusters are made and in each iteration, the number of clusters gets reduced by 1. So the number of iterations required is n-1. Here n = number of points = 6. So the correct answer is 5.


Let's recall what you have learnt in this session so far. You learnt about another clustering technique called Hierarchical clustering. You saw how it is different from K-Means clustering. One major advantage is that you do not have to pre-define the number of clusters. However, since you compute the distance of each point from every other point, it is time-consuming and needs a lot of processing power.

In the next segment, you will use the hierarchical clustering technique to actually make clusters using Python.


# Hierarchical Clustering in Python
We will use the same online retail case study and data set that we used for the K-Means algorithm. For making the customer segments this time, we will use the hierarchical algorithm.


 

We will start at the point where we are done with the data preparation and already have the RFM dataset which has been treated for missing values and outliers, and is also standardised.

 

The hierarchical clustering involves 2 basic steps:

Creating the dendrogram
Cutting the dendrogram at an appropriate level


Now let's go ahead and utilise the single linkage method for clustering this dataset.

 
 As you can clearly see, single linkage doesn't produce a good enough result for us to analyse the clusters. Hence, we need to go ahead and utilise the complete linkage method and then analyse the clusters once again.



 After we got the clusterIDs for each customer, we then appended the obtained ClusterIDs to the RFM data set, and analysed the characteristics of each cluster to derive the business insights from the different customer segments or clusters, in the same way as you did for the K-Means algorithm.

 

Now look at the following dendrogram and answer the questions that follow.




Q1) Hierarchical Clustering
Consider the above dendrogram for agglomerative clustering and answer the following questions.

 


Find number of clusters if threshold value is 10000. (refer fig)


== >

Feedback:
Draw a horizontal line at that height. It cuts 5 vertical lines, all of which represent a cluster.


Q2) 

Hierarchical Clustering
Find the threshold value if the no. of clusters to be formed is 4. (refer fig)

==>

15000
✓ Correct
Feedback:
Look at the height at which a horizontal line will cut 4 vertical lines.



# Industry Insights

Now let's hear from our industry experts regarding the comparison between the K-Means algorithm and the Hierarchical clustering algorithm, before learning how to choose between the two based on your business problem.



So, you learnt that whether you use k-means or hierarchical clustering algorithm depends on your hardware and the data that you are dealing with.


Now, you will look at a good statistical hack to solve segmentation problems so that you get meaningful segments, where you will use both hierarchical and k-means algorithms to complement each other.


These insights were really helpful. You looked at how these clustering methods can be used to complement each other. You also looked at the differences between these methods, and the cases where you would prefer one method over the other.

Q1) 
Hierarchical vs K-Means
What are the benefits of Hierarchical Clustering over K-Means clustering? What are the disadvantages?

==>

Suggested Answer
Hierarchical clustering generally produces better clusters, but is more computationally intensive.

Q2)

Hierarchical Clustering
Can you use the dendrogram to make meaningful clusters? (By looking at which elements leave and join at what height)

==>

Suggested Answer
Yes. It is a great tool. You can look at what stage an element is joining a cluster and hence see how similar or dissimilar it is to the rest of the cluster. If it joins at the higher height, it is quite different from the rest of the group. You can also see which elements are joining which cluster at what stage and can thus use business understanding to cut the dendrogram more accurately.


Q3)

Hierarchical Clustering
Compare the different linkages. Which one do you think gives a well-separated dendrogram? Are there any advantages of that?

==> Suggested Answer
Average and Complete linkage methods give a well-separated dendrogram, whereas single linkage gives us dendrograms which are not very well separated. We generally want well separated clusters.


For the purpose of creating the above visualisation, we have cleaned the data to include only the 2 factors under consideration. You can download the file below.


Q4)

Hierarchical Clustering
Play around with various linkages and number of clusters. You will be able to see the number of natural clusters from the dendrogram itself. If you want, you can change the scale as well. Which group of parameters give you the best result - For the best result, you can use your general knowledge about various Indian states. (Basically which clusters make logical sense)

==>

Complete linkage and 4 cluster

Graded:

1)

Graded Questions - I
Below is given a set of 6 points which have to be clustered by agglomerative clustering method. Use the single linkage method for clustering.

 

Point Label	X	Y
A	6	0
B	1	2
C	2	7
D	4	6
E	5	3
F	11	1
 


Answer the following questions based on the data given above.


Hierarchical Clustering
What is the distance between points B and E?

4.1
✓ Correct
Feedback:
Distance is sqrt( 5-1)^2 + (3-2)^2)

2) Hierarchical Clustering
Select the appropriate option which describes the Single Linkage method.
==>


In single linkage hierarchical clustering, the distance between two clusters is defined as the shortest distance between two points in each cluster.
✓ Correct
Feedback:
Single linkage cluster takes the distance as the shortest distance between any 2 points in each of the clusters.


3) 

Hierarchical Clustering
Based on the concept of agglomerative clustering, which two points will get clustered first?

==>

C-D
✓ Correct
Feedback:
The distance between C and D is sqrt(5), which is lower than any other pair of clusters.



4)

Hierarchical Clustering
Make the dendrogram using the complete linkage.Cut the tree at k = 4. Which of the following is correct statement

==>

SC Ganguly, R Dravid and SR Tendulkar are in the same cluster

✓ Correct
Feedback:
Look at how the clusters formed are different from k-means cluster. You can plot a scatter plot to observe the clusters more