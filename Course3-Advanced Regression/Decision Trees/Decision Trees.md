# Introduction to Decision Trees

You have learnt some classical machine learning algorithms like linear regression, logistic regression etc. for solving both regression and classification problems. Then what do you think is the need of going ahead with these linear models. Linear models cannot handle collinearity and non linear relationships in the data well. Now here comes the role of decison trees which leverages these properties. You will learn about each of these in detail as you go ahead. 

 

A decision tree, as the term suggests, uses a tree-like model to make predictions. It resembles an upside-down tree and uses a similar process that you do to make decisions in real life, i.e., by asking a series of questions to arrive at a decision.


A decision tree splits data into multiple sets of data. Each of these sets is then further split into subsets to arrive at a decision. Let’s hear from Prof. Raghavan as he explains this process in detail.

As you saw in this video, a decision tree uses a natural decision-making process, i.e., it asks a series of questions in a nested if-then-else structure. On each node, you ask a question to further split the data that is held by the node. If the test passes, you move to the left; otherwise, you move to the right.

The first and top node of a decision tree is called the root node. The arrows in a decision tree always point away from this node.
The node that cannot be further classified or split is called the leaf node. The arrows in a decision tree always point towards this node.

Any node that contains descendant nodes and is not a leaf node is called the internal node.
In the next segment, you will take a look at some real-life examples to understand decision trees better.



# Interpreting a Decision Tree

Before even jumping to the concepts of decision trees and constructing one on your own in Python, it is important that you first understand how a decision tree is interpreted for you to have a better appreciation of the model building process. 

Like we have mentioned earlier as well, a decision tree is nothing but a tree asking a series of questions to arrive at a prediction. The problem at hand is to predict whether a person has heart disease or not. Based on the values that various attributes such as gender, age, cholesterol, the decision trees try to make a prediction and output a flowchart-like diagram. Let's hear Rahim describe this output and how to interpret it.


As you saw, interpreting a decision tree is nothing but asking a series of questions - something similar to what a doctor would do when they are diagnosing their patients. The first question we asked was, "Is the age less than 54.5?". Depending on the answer, we moved to the next step where we asked whether the person is a male or a female, and so on. At the end of this line of question, lies an answer - whether the person has heart disease or not. 

 

Now, if you were a doctor, you could ask these series of questions, and depending on the answers, you can probably make an educated prediction of whether the patient has the disease or not. This prediction here will obviously be based on your past learnings and experiences of treating such patients. A decision tree does the same thing - on the training data, it checks how the patients are doing based on their different attributes (this acts as the algorithm's experience) and based on that experience, it asks the users a series of questions to predict whether a person has heart disease or not.

 Let's now look at the other side of the tree and understand the factors leading to a heart disease.


As you saw in this video, it is easy to interpret a decision tree, and you can almost always identify the various factors that lead to a particular decision. In fact, trees are often underestimated in their ability to relate the predictor variables to their predictions. As a rule of thumb, if interpretability by layman is what you are looking for in a model, then decision trees should be at the top of your list.

 
In a decision tree, you start from the top (root node) and traverse left/right according to the result of the condition. Each new condition adds to the previous condition with a logical ‘and’, and you may continue to traverse further until you reach the final condition’s leaf node. A decision is the value (class/quantity) that is assigned to the leaf node


As depicted in the heart disease example in the image above, the leaf nodes (bottom) are labelled ‘Disease’ (indicating that the person has heart disease) or ‘No Disease’ (which means the person does not have heart disease).


Note that the splits are effectively partitioning the data into different groups with similar chances of heart disease.

 

So, in decision trees, you can traverse the attributes backwards and identify the factors that lead to a particular decision. 


In the heart disease example, the decision tree predicts that if the ‘age’ of a person is less than or equal to 54.5, the person is female, and her cholesterol level is less than or equal to 300, then the person will not have heart disease, i.e., young females with a cholesterol level <= 300 have a low chance of being diagnosed with heart disease.


Similarly, there are other paths that lead to a leaf being labelled Disease/No Disease. In other words, each decision is reached via a path that can be expressed as a series of ‘if’ and logical 'and' conditions that are satisfied together. The final decisions are stored in the form of class labels in leaves.
 

Comprehension - Interpreting a Decision Tree

Mithali is an incredible cricketer. She plays cricket only when the pitch is dry, and the field is well lit. Based on past observations, you also know that she doesn’t play cricket when either the pitch is wet, or the light is dim.

Q1) 
Is the following statement true or false?
An attribute can be present only in one test/node of a decision tree.

False.
we have root node as well which stores attribute.

Feedback:
If you test on age, then you can have ‘age <= 54.5’ as the first test, ‘age <= 40.5’ as the second test, and so on. Check the decision tree just shown to confirm.

Now that you have undetstood how to interpret the end result of a decision tree, let's now learn how to actually construct this tree in the first place.


# Building Decision Trees

Now that you have learnt how to interpret decision trees, you must be wondering how does one exactly build decision trees? What is the tree building process? As expected, it involves performing a series of splits.
Let’s understand this process in detail in the following video.


So, as you saw in the video, constructing a decision tree involves the following steps:

- Recursive binary splitting/partitioning the data into smaller subsets
- Selecting the best rule from a variable/ attribute for the split
- Applying the split based on the rules obtained from the attributes
- Repeating the process for the subsets obtained
- Continuing the process until the stopping criterion is reached
- Assigning the majority class/average value as the prediction

 Now, you might have many questions lingering on your mind like what is the best variable for the split, how do I know what is the stopping criterion, and so on. Don't worry, as the steps you learnt just now is just a high-level view of the tree building process. In the coming sessions, you will learn each of these processes in detail.

Now, the decision tree building process is a top-down approach. The top-down approach refers to the process of starting from the top with the whole data and gradually splitting the data into smaller subsets. 

The reason we call the process greedy is because it does not take into account what will happen in the next two or three steps. The entire structure of the tree changes with small variations in the input data. This, in turn, changes the way you split and the final decisions altogether. This means that the process is not holistic in nature, as it only aims to gain an immediate result that is derived after splitting the data at a particular node based on a certain rule of the attribute.

how do we define best variable for split 
how to know if stopping criterion is reached 


# Comprehension - Decision Tree Classification in Python

Let’s consider the heart disease data set that we discussed in the earlier segment. The data lists various tests that were conducted on patients along with some other details of the patients. Now, given the test results and other attributes, suppose you want to predict whether a person has a heart disease or not.
 
Please find the dataset link here


Heart Disease Data set

Please note that:

Heart disease = 0 means that the person does not have heart disease.
Heart disease = 1 means that the person has heart disease.

 sex = 0 means that the person is female.
sex = 1 means that the person is male.


To keep this simple and focus on building a decision tree only, we are skipping any data preparation or feature manipulation techniques.
You also need to install Graphviz to visualize the decision tree. The steps to be followed are provided towards the end of the page.
Note: In the video above at timestamp [7:07], Rahim meant 81 records in the test set instead of 189.


So you’ve imported the required libraries, read and inspected the data. Also, the entire data set has been split into train and test sets. Let’s now move on to building the decision tree using the default parameters of the DecisionTreeClassifier() function except for the tree depth.

Now that you have built the decision tree and visualised it using the graphviz library, let's now evaluate how the model that we built is performing on the unseen data.


You can see that the model that we have now is not performing well on the test set. This is because we built our model on the default parameters except for the depth and didn’t change any other hyperparameters. Hyperparameter tuning can improve the performance of decision trees to a great extent. So in the upcoming sessions, we will go ahead and exploit these parameters to improve the model and give better prediction results. 

 

What are hyperparameters?

Hyperparameters are simply the parameters that we pass on to the learning algorithm to control the training of the model. Hyperparameters are choices that the algorithm designer makes to ‘tune’ the behaviour of the learning algorithm. The choice of hyperparameters, therefore, has a lot of bearing on the final model produced by the learning algorithm.  

 

So basically anything that is passed on to the algorithm before it begins its training or learning process is a hyperparameter, i.e., these are the parameters that the user provides and not something that the algorithm learns on its own during the training process. Here, one of the hyperparameters you input was "max_depth" which essentially determines how many levels of nodes will you have from root to leaf. This is something that the algorithm is incapable of determining on its own and has to be provided by the user. Hence, it is a hyperparameter.

 

Now, obviously, since hyperparameters can take many values, it is essential for us to determine the optimal values where the model will perform the best. This process of optimising hyperparameters is called hyperparameter tuning. You will learn to do that in the next session. First, let's answer some questions based on your learnings so far.


Installing Graphviz
Python requires the library 'pydotplus' and the external software Graphviz to visualise the decision tree. If you are using Windows, then you will need to specify the path to the pydotplus library in order to access the dot file from Graphviz.

 

Please refer the user guide and the steps below to install Graphviz.


Steps for Windows users:

Download Graphviz from here (ZIP file)
Unzip the file and copy-paste it in C:\Program Files (x86)\
Make sure your file is unzipped and placed in Program Files (x86)
Environment Variable: Add C:\Program Files (x86)\graphviz-2.38\release\bin to the user path
Environment Variable: Add C:\Program Files (x86)\graphviz-2.38\release\bin\dot.exe to the system path
Install the Python Graphviz package - pip install graphviz
Install pydotplus - pip install pydotplus
 

Instructions to add the environment variable: [click here](https://java.com/en/download/help/path.xml)

 

# anaconda users
conda install pydotplus

# pip users
pip install pydotplus




---

Let’s summarise the advantages of tree models one by one in the following order:

- Predictions made by a decision tree are easily interpretable.
- A decision tree is versatile in nature. It does not assume anything specific about the nature of the attributes in a data set. It can seamlessly handle all kinds of data such as numeric, categorical, strings, Boolean, etc.
- A decision tree is scale-invariant. It does not require normalisation, as it only has to compare the values within an attribute, and it handles  multicollinearity better.
- Decision trees often give us an idea of the relative importance of the explanatory attributes that are used for prediction.
They are highly efficient and fast algorithms.
- They can identify complex relationships and work well in certain cases where you cannot fit a single linear relationship between the target and feature variables. This is where regression with decision trees comes into the picture.


In regression problems, a decision tree splits the data into multiple subsets.
The difference between decision tree classification and decision tree regression is that in regression, each leaf represents the average of all the values as the prediction as opposed to a class label in classification trees. For classification problems, the prediction is assigned to a leaf node using majority voting but for regression, it is done by taking the average value. This average is calculated using the following formula:


^yt=1Nt∑iϵDty(i),where 
yi’s represent the observations in a node.



For example, suppose you are predicting the sales your company will have based on various factors such as marketing, no. of products, etc. Now, if you use a decision tree to solve this problem (the process of actually building a regression tree is covered in the next session), and if one of the leaf nodes has, say, 5 data points, 1 Cr, 1.3 Cr, 0.97 Cr, 1.22 Cr, 0.79 Cr. Now, you will just take the average of these five values which comes out to be 1.05 Cr, and that becomes your final prediction.

 

Decision tree classification is what you’ll most commonly work on. However, remember that if you get a data set where you want to perform regression, decision tree regression is also a good idea.

 

This module includes an optional demonstration on regression trees for those who want to explore and understand the process in detail.


Q1) Regression
From the following statements about decision tree classification and regression models, select the ones that are correct.


Leaves in classification contain labels.

✓ Correct
Feedback:
In classification, the target variable is discrete. Hence, each data point in a leaf has an associated class label.


Leaves in regression contain the average predicted value.

✓ Correct
Feedback:
Each leaf in regression contains an average value as the prediction.

Q2) Decision trees
What are the possible reasons for using decision tree regression over a linear model? (More than one option may be correct.)


It is difficult to represent non linear data via a single model; hence, linear regression model cannot be applied in such a case.
Feedback:
Decision tree regression is performed because the entire data set cannot be represented by a single linear regression model


Decision trees do not require any data preparation.
Feedback:
In decision trees, you do not have to treat missing values, outliers and multicollinearity before proceeding with model building.



# Summary:

Let’s summarise some of the concepts that you learnt in this session.
 
Decision trees are easy to interpret, as you can always traverse backwards and identify the various factors that lead to a particular decision. A decision tree requires you to perform certain tests on attributes in order to split the data into multiple partitions.


In classification, each data point in a leaf has a class label associated with it.


You cannot use the linear regression model to make predictions when you need to divide the data set into multiple subsets, as each subset has an independent trend corresponding to it. In such cases, you can use the decision tree model to make predictions because it can split the data into multiple subsets and assign average values as the prediction to each set independently.


--------


# Introduction

Welcome to the session ‘Algorithms for Decision Tree Construction’. In the previous session, you learnt about the underlying concepts of decision trees and their interpretation. You also learnt how to construct a decision tree. You learnt about the advantages of decision trees and also understood how they help in solving the regression problems that cannot be handled by linear regression. In this session, you will learn about the methods for decision tree construction.

 

In this session:
Splitting and homogeneity
Impurity measures
Best split
Regression trees


---

# Splitting and Homogeneity
Recall the scenario from session one where you were a doctor asking a series of questions to determine whether a person has heart disease or not. Based on your past experience with other patients, the answers to these questions would finally lead to a prediction depicting whether the person has heart disease or not. Now, if you're a doctor, you would know which questions to ask first, right? When a person might be at the risk of heart disease, the doctor would probably first ask/measure the cholesterol of the person. If it's higher than 300, the doctor can be pretty sure that the person is at risk. Then he may ask some more questions to confirm his predictions even further.

 

Now suppose instead of asking/measuring the cholesterol, the doctor first asks the age of the person. If the person says, say, 55, the doctor may not be completely sure whether the person has heart disease or not. He/She would need to ask further questions.

 

From both these scenarios, it is easy to infer that to predict the target variable (in this case, heart disease), there are obviously some questions/attributes that are more important for its prediction than others. In our case, you saw that the cholesterol level is a more significant attribute than age in the prediction of heart disease. Why is that? It's so because, for the doctor, it might be evident from past records that people will higher cholesterol levels have a high chance of having heart disease. Say, in his/her experience that doctor has seen that out of every 100 patients who have cholesterol higher than 300, 90 had a heart disease while 10 did not. Also, say, out of 100 patients that the doctor has consulted over the age of 54, fifty of them had a heart disease. Now, it is evident that 'cholesterol' would be better to determine heart disease than 'age' since 90% of the patients having cholesterol greater than 300 were diagnosed with heart disease.

 

You can clearly see that one of the classes (disease) is significantly dominant over the other (non-disease) after splitting on the basis of cholesterol > 300 and this dominance is helping the doctor make a more confident prediction unlike 'age' which gives us a 50-50 split of both classes leaving us in a dilemma again.

 

So we basically arrive at these questions; Given many attributes, how do you decide which rules obtained from the attributes to choose in order to split the data set? From a single feature, you can get many rules and you may use any of these to make the split. Do you randomly select these and split the data set or should there be a selection criterion for choosing one over the other? What are you trying to achieve with the split?

 

All these questions will be covered in the following session and you will learn about the various algorithms and criteria that are involved in constructing a decision tree.

---

If a partition contains data points with identical labels (for example, label 1), then you can classify the entire partition as that particular label (label 1). However, this is an oversimplified example. In real-world data sets, you will almost never have completely homogenous data sets (or even nodes) after splitting the data. Hence, it is important that you try to split the nodes such that the resulting nodes are as homogenous as possible. One important thing to remember is that homogeneity here is always referred to response (target) variable's homogeneity.

 For example, let's suppose we consider the same heart disease example in which you wanted to classify whether a person has a heart disease or not. If one of the nodes is labelled ‘Blood Pressure’, try to split it with a rule such that all the data points that pass the rule have one label and those that do not pass the rule have a different label. Thus, you need to ensure that the response variable's homogeneity in the resultant splits is as high as possible.

A split that results in a homogenous subset is much more desirable than the one that results in a 50-50 distribution (in the case of two labels). In a completely homogenous set, all the data points belong to one particular label. Hence, you must try to generate partitions that result in such sets.

For classification purposes, a data set is completely homogeneous if it contains only a single class label. For regression purposes, a data set is completely homogeneous if its variance is as small as possible. You will understand regression trees better in the upcoming segments.

Let’s take a look at the illustration given below to further understand homogeneity.
Consider a data set ‘D’ with homogeneity ‘H’ and a defined threshold value. When homogeneity exceeds the threshold value, you need to stop splitting the node and assign the prediction to it. As this node does not need further splitting, it becomes the leaf node.

Suppose that you keep the threshold value as 70%. The homogeneity of the node in the illustration given below is clearly above 70% (~86%). The homogeneity value, in this case, falls above the threshold limit. Hence no splitting is required and this node becomes a leaf node.


But what do you do when the homogeneity ‘H’ is less than the threshold value?

 

Now keeping the same threshold value as 70%, you can see from the below illustration that homogeneity of the first node is exactly 50%. The node contains an equal number of data points from both the class labels. Hence, you cannot give a prediction to this node as it does not meet the passing criterion which has been set. There is still some ambiguity existing in this node as there is no clarity on the label that can be assigned as the final prediction. This brings in the need for further splitting and we compare the values of homogeneity and threshold again to arrive at a decision. This is continued until the homogeneity value exceeds the threshold value.


Till the homogeneity ‘H’ is less than the threshold, you need to continue splitting the node. The process of splitting needs to be continued until homogeneity exceeds the threshold value and the majority data points in the node are of the same class.

 
This is an abstract example to give you an intuition on homogeneity and splitting. You will get better clarity in the next segment when you learn how to quantify and measure homogeneity to arrive at a prediction through continuous splitting. You will learn how to use specific methods to measure homogeneity, namely the Gini index, entropy, classification error (for classification), and MSE (for regression).

 

Now, how do you handle best split for different attributes in a decision tree using CART algorithm.

 

A tree can be split based on different rules of an attribute and these attributes can be categorical or continuous in nature. If an attribute is nominal categorical, then there are 
2^(k−1) − 1
 possible splits for this attribute, where 
k is the number of classes. In this case, each possible subset of categories is examined to determine the best split.

 

If an attribute is ordinal categorical or continuous in nature with n different values, there are n - 1 different possible splits for it. Each value of the attribute is sorted from the smallest to the largest and candidate splits based on the individual values is examined to determine the best split point which maximizes the homogeneity at a node.

 
There are various other techniques like calculating percentiles and midpoints of the sorted values for handling continuous features in different algorithms and this process is known as discretization. Although the exact technicalities are out of the scope of this module, curious students can read more about this in detail from the additional resources given below.

 
Now let's answer some questions based on your learnings so far.


# Impurity Measures

Now, you have narrowed down the decision tree construction problem to this: you want to split the data set such that the homogeneity of the resultant partitions is maximum. But how do you measure this homogeneity?

Various methods, such as the **classification error, Gini index and entropy**, can be used to quantify homogeneity. You will learn about each of these methods in the upcoming video.

 
Note: At the timestamp [5:11] in the video, the formula for entropy includes a negative sign along with the expression. Also, at [5:42], the 2nd term will be -0.8 log(0.8) and not -0.8 log(-0.8).


The classification error is calculated as follows:

E=1−max(pi) 

The Gini index is calculated as follows:

G=∑ki=1pi(1−pi) 

Entropy is calculated as follows:

D=−∑ki=1pi.log2(pi) , where pi is the probability of finding a point with the label 
i, and k is the number of classes.


Let's now tweak the above example and try to understand how these impurity measures change with the class distribution.


From the above example, you understood how to calculate different impurity measures and how do they change with different class distributions.

 

Impurity Measures	
Case I

Class 0: 20

Class 1: 80

Case II

Class 0: 50

Class 1: 50

Case III

Class 0: 80

Class 1: 20

Classification Error	0.2	0.5	0.2
Gini Impurity	0.32	0.5	0.32
Entropy	0.72	1	0.72

You can see that for a completely non-homogeneous data with equal class distribution, the value of Classification Error and Gini Impurity are the same i.e. 0.5 and that of Entropy is 1.

 

The scaled version of the entropy in the illustration shown in the video is nothing but entropy/2. It has been used to emphasize that the Gini index is an intermediate measure between entropy and the classification error.

 

In practice, classification error does not perform well. So, we generally prefer using either the Gini index or entropy over it.

 

Gini Index

Gini index is the degree of a randomly chosen datapoint being classified incorrectly. The formula for Gini index can also be written as follows:

 G=∑ki=1pi(1−pi)=∑ki=1(pi−p2i)=∑ki=1pi−∑ki=1p2i=1−∑ki=1p2i

 where pi is the probability of finding a point with the label i, and k  is the number of classes.


(Think why was  ∑ki=1 pi equal to 1?)


Gini index of 0 indicates that all the data points belong to a single class. Gini index of 0.5 indicates that the data points are equally distributed among the different classes.

Suppose you have a data set with two class labels. If the data set is completely homogeneous, i.e., all the data points belong to label 1, then the probability of finding a data point corresponding to label 2 will be 0 and that of label 1 will be 1. So, 
p1 = 1 and p2 = 0. The Gini index, which is equal to 0, will be the lowest in such a case. Hence, the higher the homogeneity, the lower the Gini index.


**Entropy:**

Entropy quantifies the degree of disorder in the given data, its value varies from 0 to 1. Entropy and the Gini index are similar numerically. If a data set is completely homogenous, then the entropy of such a data set will be 0, i.e., there is no disorder in the data. If a data set contains an equal distribution of both the classes, then the entropy of that data set will be 1, i.e., there is complete disorder in the data. Hence, like the Gini index, the higher the homogeneity, the lower the entropy.

Now that you have understood the different methods to quantify the purity/impurity of a node, how do you identify the attribute that results in the best split? Let’s learn more about this in the upcoming video.



The change in impurity or the purity gain is given by the difference of impurity post-split from impurity pre-split, i.e.,


Δ Impurity = Impurity (pre-split) – Impurity (post-split)

 

The post-split impurity is calculated by finding the weighted average of two child nodes. The split that results in maximum gain is chosen as the best split.

 

To summarise, the information gain is calculated by:

Gain=D−DA where  D is the entropy of the parent set (data before splitting),
DA is the entropy of the partitions obtained after splitting on attribute 
A. Note that reduction in entropy implies information gain.

 

Let's understand how do we compute information gain with an example. Suppose you have four data points out of which two belong to the class label '1', and the other two belong to the class label '2'. You split the points such that the left partition has two data points belonging to label '1', and the right partition has the other two data points that belong to label '2'. Now let's assume that you split on some attribute called 'A'.

I3
I3
Entropy of original/parent data set is 

D = −[(24)log2(24)+(24)log2(24)]=1.0.

Entropy of the partitions after splitting is 
DA=−1∗log2(22)−1∗log2(22)=0.
Information gain after splitting is 
Gain=D−DA=1.0.
So, the information gain after splitting the original data set on attribute 'A' is 1.0. You always try to maximise information gain by achieving maximum homogeneity and this is possible only when the value of entropy decreases from the parent set after splitting.

In case of a classification problem, you always try to maximise purity gain or reduce the impurity at a node after every split and this process is repeated till you reach the leaf node for the final prediction. 

Q1) Considering all the data points in a data set have the same label, what will be the Gini index?

Gini Index = 0

Feedback:
The probability of exactly one class will be 1, and the probability of all the other classes will be 0. So, the Gini index, which is given by ​
1-∑ki=1p2i​, will be 0.

Q2)  Gini Index
In a given data set, 50% of the data points belong to label 1, and the other 50% belong to label 2. Calculate the Gini index.
Ans:
The Gini index = 
1-[(12)2+(12)2].

p1 = 0.5, and 
p2 = 0.5. So the Gini index, which is given by 
1-∑ki=1p2i, will be
1-[(12)2+(12)2].

Q3) Gini Index
When is the Gini index of a data set high?

When the data set is non-homogeneous, the Gini index, which is a measure of misclassification of the data points will be maximum. The Gini index is minimum when all the points in the data set belong to one class label. It is given by 
1-∑ki=1pi2.

Q4) Information Gain
When is the information gain maximum? (Select the most appropriate option.)


When the decrease in entropy, from the parent set to the partitions obtained after splitting, is maximum.
Feedback:
The information gain is equal to the entropy change from the parent set to the partitions. So it is maximum when the entropy of the parent set minus the entropy of the partitions is maximum.

Q5) Entropy
How is entropy related to the Gini index?

A high value of entropy and gini index implies that the data is non-homogeneous and further splitting is required to make it as homogeneous as possible.


Q6) Information Gain
Suppose you have a dataset with several attributes for a binary classification problem. If you split on attribute ‘A’, then the information gain is 0.031929, and if you split on attribute ‘B’, then the gain is 0.33697. Which attribute should you split the original data on?

Ans:
You split on the attribute that maximises the information gain. The information gain on attribute 'B' is greater than the information gain on attribute 'A'.

Additional Readings:

If you are curious to know about these topics, you may go through the following link.



# Comprehension: The Gini Index
Let’s consider the heart disease example that was introduced in the earlier segments to understand decision trees. Now, you will calculate the homogeneity measure for some of the features on some numbers using the Gini index to determine the attribute that you should split on first.

Recall that the Gini index is calculated as follows:
 
G=∑ki=1pi(1−pi)=1−∑ki=1p2i where 
pi is the probability of finding a point with the label i, and k is the number of classes.


Now, you can calculate the gini idex for the data before making any splits as follows:

 As you can see, the table above shows the number of diseased/non-diseased person w.r.t. the levels in the two attributes - 'Sex' and 'Cholesterol'. Let's calculate the homogeneity reduction on each attribute individually, starting with 'Sex'.


# Split based on Sex

Let's consider the first candidate split based on sex/gender. As you can see from the first table, of the 100 people, you have 70 males and 30 females. Among the 70 males i.e. the child node containing males, 50 belong to class 0 i.e, they do not have a heart disease and the rest 20 males belong to class 1 having a heart disease. So basically for the split on "Sex", you have something like this —


Split based on Sex

Let's consider the first candidate split based on sex/gender. As you can see from the first table, of the 100 people, you have 70 males and 30 females. Among the 70 males i.e. the child node containing males, 50 belong to class 0 i.e, they do not have a heart disease and the rest 20 males belong to class 1 having a heart disease. So basically for the split on "Sex", you have something like this —

 



 

 

[Note that (x, y) on any node means (# Label 0, # Label 1)]

 
Now the probabilities of the two classes within the male subset comes out to be:

 

p0 = 50/70 = 0.714 and     
p1 = 20 / 70 = 0.286

Now using the same formula, Gini impurity for males becomes:

0.714(1−0.714)+0.286(1−0.286)=0.41

Let's now take the other case i.e. the child node containing females, where there are 30 females out of which 10 belong to class 0 having no heart disease and 20 belong to class 1 having a heart disease. The probabilities of the two classes within the female subset comes out to be:


p0=10/30=0.333     and 
p1=20/30=0.667

Now using the formula, Gini impurity for females becomes:
 

0.333(1−0.333)+0.667(1−0.667)=0.44

Now how do you get the overall impurity for the attribute 'sex' after the split? You can aggregate the Gini impurity of these two nodes by taking a weighted average of the impurities of the male and female nodes. So, you have -


pmale=70/100=0.7 and pfemale=30/100=0.3

This gives the Gini impurity after the split based on gender as:


0.7×0.41+0.3×0.44=0.42 

Thus, the split based on gender gives the following insights:

Gini impurity before split = 0.48
Gini impurity after split = 0.42
Reduction in Gini impurity = 0.48 - 0.42 = 0.06
Hence, you get the following tree after splitting on 'Sex' = 0.48 - 0.42 = 0.06





---

Split based on Cholesterol

Let's now take another candidate split based on cholesterol. You divide the dataset into two subsets: Low Cholesterol (Cholesterol < 250) and High Cholesterol (Cholesterol > 250). There are 60 people belonging to the low cholesterol group and 40 people belonging to the high cholesterol group. 

 

If you see the second table given above, you will notice that among the 60 low cholesterol people, 50 belong to class 0, i.e, they do not have a heart disease and the rest 10 belong to class 1 having a heart disease. So basically for the split on "Cholesterol", you have something like this —

 

Now the probabilities of the two classes within the low cholesterol subset comes out to be:

 

p0=50/60
=
0.833
     and     
p
1
=
10
60
=
0.167

 

Now using the formula, Gini impurity for low cholesterol subset becomes:

 

0.833
(
1
−
0.833
)
+
0.167
(
1
−
0.167
)
≈
0.27

 

Let's now take the other case where there are 40 high cholesterol (Cholesterol > 250) people out of which 10 belong to class 0 having no heart disease and 30 belong to class 1 having a heart disease. The probabilities of the two classes within the high cholesterol subset comes out to be:

 

p
0
=
10
40
=
0.25
    and    
p
1
=
30
40
=
0.75

 

Now using the formula, Gini impurity for high cholesterol subset becomes:

 

0.25
(
1
−
0.25
)
+
0.75
(
1
−
0.75
)
≈
0.37

 

The overall impurity for the data after the split based on cholesterol can be computed by taking a weighted average of the impurities of the high and low cholesterol nodes. So, you have -

 

 
p
l
o
w
−
c
h
o
l
e
s
t
e
r
o
l
=
60
100
=
0.6
    and    
p
h
i
g
h
−
c
h
o
l
e
s
t
e
r
o
l
=
40
100
=
0.4

 

This gives the Gini impurity after the split based on cholesterol as:

 

0.6
×
0.27
+
0.4
×
0.37
≈
0.3

 

Thus, the split based on cholesterol gives the following insights:

Gini impurity before split = 0.48
Gini impurity after split = 0.3
Reduction in Gini impurity = 0.48 - 0.3 = 0.18
Hence, you get the following tree after splitting on 'Cholesterol' —

 



 

 

Hence, from the above example, it is evident that we get a significantly higher reduction in Gini impurity when you split the dataset on cholesterol as compared to when you split on gender.

 

Let's summarise all the steps you performed.

Calculate the Gini impurity before any split on the whole dataset.
Consider any one of the available attributes.
Calculate the Gini impurity after splitting on this attribute for each of the levels of the attribute. In the example above, we considered the attribute 'Sex' and then calculated the Gini impurity for both males and females separately.
Combine the Gini impurities of all the levels to get the Gini impurity of the overall attribute.
Repeat steps 2-5 with another attribute till you have exhausted all of them.
Compare the decrease in Gini impurity across all attributes and select the one which offers maximum reduction.
 

You can also perform the same exercise using Entropy instead of Gini index as your measure.

 

Q1) Gini Index
Suppose you have a movie dataset having 180 different movie names with several features like their ratings, whether they were featured by a renowned cast or not, type of genre and so on. Out of the 180 movies, we have 110 hit and 70 flop movies.Now you need to build a decision tree model to predict whether a movie will go hit or a flop? You want to select the best feature out of these to split the dataset that would result in homogeneous subsets and help in predicting the two classes effectively. Based on the information given below, which variable among 'ratings' and 'renowned cast' would you choose to split the dataset first?

Ans:

Ratings

✓ Correct
Feedback:
The gini impurity for 'ratings' feature comes out to be 0.39 after the split which is lower than the impurity value(0.40) obtained after splitting based on 'renowned cast'. Hence, purity gain for splitting based on ratings is more than that of renowned cast and we will split the data set on ratings first
 

Important: Please note that Gini index is also often referred to as Gini impurity. Also, some sources/websites/books might have mentioned a different formula for the Gini index. There is nothing wrong in using either of the formulas (because the ultimate interpretation regarding the impurity of the feature remains unchanged across both the formulas), but in order to avoid any confusion, we would recommend you to stick to the one mentioned in this session as this is the formula that we will be consistently using throughout the whole module. Here's it again for you!

G=∑ki=1pi(1−pi) 

In the next segment, you will learn about the property of feature importance in decision trees.



Q2)
Gini Index
 	 	
Interested in Music

Not Interested in Music

 	 
Gender

Male

10

20

30

50

Female

10

10

20

Stream

Science 

10

30

40

50

Arts

10

0

10

Consider a sample of 50 students in the age group from 15 to 22 years with some information on their Gender (Boy/ Girl) and Stream( Science/ Arts). 20 out of these 50 are interested in learning music. Now, suppose we are interested in creating a model to predict who will be interested in music?

Now answer the following question based on the above information

What is the Gini index of  the original/ parent data set ?



Ans:


0.48


Feedback:
Calculate Gini index using the formula 
G=∑ki=1pi(1−pi). Out of 50 instances Yes=20(interested in music) and No=30(Not interested in music). Hence 
G=0.4(1−0.4)+0.6(1−0.6)=0.48.


---

Feedback:
Use the formula Gini Index(gender) = (fraction of total observations in male node)*Gini index of male node + (fraction of total observations in female node)*Gini index of female node =
0.6∗0.44 + 0.4∗0.5 ≈ 0.47


Q3)
Consider a sample of 50 students in the age group from 15 to 22 years with some information on their Gender (Boy/ Girl) and Stream( Science/ Arts). 20 out of these 50 are interested in learning music. Now, suppose we are interested in creating a model to predict who will be interested in music?

Now answer the following question based on the above information

If we split the dataset based on stream what is the Gini index for Science node ?


Science node contains 40 entries, out of which 10 are interested in music and 30 are not. Hence G = 
0.25(1−0.25)+0.75(1−0.75)≈0.38


q4)
Consider a sample of 50 students in the age group from 15 to 22 years with some information on their Gender (Boy/ Girl) and Stream( Science/ Arts). 20 out of these 50 are interested in learning music. Now, suppose we are interested in creating a model to predict who will be interested in music?

Now answer the following question based on the above information

If we split the dataset based on stream what is the Gini index for Arts node ?

Ans:

Arts node contains 10 entries, out of which 10 are interested in music and 0 are not. Hence GI = 1(1-1)+0(1-0)= 0


Q4)

Consider a sample of 50 students in the age group from 15 to 22 years with some information on their Gender (Boy/ Girl) and Stream( Science/ Arts). 20 out of these 50 are interested in learning music. Now, suppose we are interested in creating a model to predict who will be interested in music?

Now answer the following question based on the above information

What is the weighted Gini index  for Split on Stream?

Ans:

Use formula Gini Index(stream) = (fraction of total observations in science node)*Gini index of science node + (fraction of total observations in arts node)*Gini index of arts node.

Gini Index(stream) = 0.8*0.375+0.2*0=0.30


# Feature Importance in Decision Trees



Feature importance plays a key role in contributing towards effective prediction, decision-making and model performance. It eliminates the less important variables from a large data set and helps in identifying the key features that can lead to better prediction results.
In this video, let’s understand the notion of variable importance in decision trees.
Note that in the video below, reduction in Gini Impurity based on Gender and cholesterol is 0.06<0.18 instead of 0.06>0.018.


Decision trees help in quantifying the importance of each feature by calculating the reduction in the impurity for each feature at a node. The feature that results in a significant reduction in the impurity is the important variable, and the one that results in less impurity reduction is the less important variable.


In the previous example, the variable ‘cholesterol’ resulted in higher reduction in impurity than ‘gender’. This implies that cholesterol will help distinguish between the two classes better than gender. This is intuitive as well: splitting on cholesterol is expected to be more important and informative than gender; this is because medically, people with high cholesterol have higher chances of developing heart disease than the ones with low cholesterol.


# Summary
In this session, you learnt about the learning algorithms behind decision trees. In a step-by-step manner, you pick an attribute and a rule to split data into multiple partitions to increase the homogeneity of the data set.

 

You also learnt about the various ways in which you can measure the homogeneity of a data set, such as the Gini index, entropy and MSE.

 

Now, let’s summarise your learnings so far:

A decision tree first decides on an attribute to split on.
To select this attribute, it measures the homogeneity of the nodes before and after the split.
You can measure homogeneity in various ways with metrics like Gini index and entropy.
The attribute that results in the increase of homogeneity the most is then selected for splitting.
Then, this whole cycle is repeated until you obtain a sufficiently homogeneous data set.

---
Graded:

Gini Index
X1	X2	Y
1	1	0
1	2	1
2	1	1
2	2	0
2	3	1
3	3	1
 

Consider the above table of 6 observations. Values of X1 and X2 are used to predict the outcome Y. When Y is 1 the outcome is considered to be positive. 

Q1)

What is the Gini impurity of the given data set?

=>

4/9

Feedback:
Calculate Gini impurity as p0(1-p0) + p1(1-p1). Out of 6 instances Yes=4 (Y=1) and No=2(Y=0) . Hence, Gini = (4/6) x (2/6) + (2/6) x (4/6) = 16/36 = 4/9. 

Q2)

X1

X2

Y

1

1

0

1

2

1

2

1

1

2

2

0

2

3

1

3

3

1

 

Consider the above table of 6 observations. Values of X1 and X2 are used to predict the outcome Y. When Y is 1 the outcome is considered to be positive. 

If in the process of making a decision tree X2 is considered as splitting feature and 2.5 is considered as splitting value and values less than 2.5 go to the left node. What will the Gini impurity of the split data be?


Ans:

First, construct the tree to have a better picture.



There are 4 data points in the left node and to on the right node. Hence,

P(X2 < 2.5) = 4/6

P(X2 > 2.5) = 2/6

 

Now, use the formula for Gini = p0(1-p0) + p1(1-p1) for both the nodes, then combine them with the probabilities of a data point falling in a node to calculate the overall Gini impurity.

For the left node: Gini = 1/2(1-1/2) + 1/2(1-1/2) = 1/2

For the right node: Gini = 0(1-0) + 1(1-1) = 0

 

Hence, the new Gini impurity after split = (4/6)*1/2 + (2/6)*0 = 1/3




Q3) 


Gini Index

X1  X2    Y



1    1    0

1    2    1

2    1    1

2    2    0

2    3    1

3    3    1





Consider the above table of 6 observations. Values of X1 and X2 are used to predict the outcome Y. When Y is 1 the outcome is considered to be positive. 



Now, instead of 2.5, if the splitting value of X2 is chosen as 1.5 then what is the Gini impurity of the split data?



Ans:

5/12

✓ Correct
Feedback:
First, construct the tree to have a better picture.



There are 2 data points in the left node and 4 on the right node. Hence,

P(X2 < 1.5) = 2/6

P(X2 > 1.5) = 4/6

 

Now, use the formula for Gini = p0(1-p0) + p1(1-p1) for both the nodes, then combine them with the probabilities of a data point falling in a node to calculate the overall Gini impurity.


Q4)

Decision Trees

Consider the following dataset:



X1	X2	X3	Y

T	T	T	1

F	T	F	0

T	F	T	0

F	F	T	1

 



If we train a decision tree with the above data what feature will we split on at the root?



Ans:

To determine the best feature to split on at the root of a decision tree, we need to evaluate the information gain (or equivalently, the Gini impurity reduction) for each feature. The feature with the highest information gain (or the lowest Gini impurity) will be chosen for the split.
Step 1: Calculate the Gini Impurity of the Entire Dataset
The Gini impurity for the entire dataset is calculated as follows:
[ \text{Gini} = 1 - \sum_{i=1}^{n} (p_i)^2 ]
where ( p_i ) is the proportion of class ( i ) in the dataset.

( Y = 1 ): 2 out of 4 observations
( Y = 0 ): 2 out of 4 observations

[ \text{Gini}_{\text{Total}} = 1 - \left( \left(\frac{2}{4}\right)^2 + \left(\frac{2}{4}\right)^2 \right) = 1 - \left( \frac{1}{4} + \frac{1}{4} \right) = 1 - \frac{1}{2} = 0.5 ]
Step 2: Calculate the Gini Impurity for Each Feature Split
Feature ( X1 )


( X1 = T ): (T, T, T, 1), (T, F, T, 0)

( Y = 1 ): 1 out of 2
( Y = 0 ): 1 out of 2

[ \text{Gini}_{X1=T} = 1 - \left( \left(\frac{1}{2}\right)^2 + \left(\frac{1}{2}\right)^2 \right) = 0.5 ]


( X1 = F ): (F, T, F, 0), (F, F, T, 1)

( Y = 1 ): 1 out of 2
( Y = 0 ): 1 out of 2

[ \text{Gini}_{X1=F} = 1 - \left( \left(\frac{1}{2}\right)^2 + \left(\frac{1}{2}\right)^2 \right) = 0.5 ]


[ \text{Weighted Gini}_{X1} = \left( \frac{2}{4} \times 0.5 \right) + \left( \frac{2}{4} \times 0.5 \right) = 0.5 ]
Feature ( X2 )


( X2 = T ): (T, T, T, 1), (F, T, F, 0)

( Y = 1 ): 1 out of 2
( Y = 0 ): 1 out of 2

[ \text{Gini}_{X2=T} = 1 - \left( \left(\frac{1}{2}\right)^2 + \left(\frac{1}{2}\right)^2 \right) = 0.5 ]


( X2 = F ): (T, F, T, 0), (F, F, T, 1)

( Y = 1 ): 1 out of 2
( Y = 0 ): 1 out of 2

[ \text{Gini}_{X2=F} = 1 - \left( \left(\frac{1}{2}\right)^2 + \left(\frac{1}{2}\right)^2 \right) = 0.5 ]


[ \text{Weighted Gini}_{X2} = \left( \frac{2}{4} \times 0.5 \right) + \left( \frac{2}{4} \times 0.5 \right) = 0.5 ]
Feature ( X3 )


( X3 = T ): (T, T, T, 1), (T, F, T, 0), (F, F, T, 1)

( Y = 1 ): 2 out of 3
( Y = 0 ): 1 out of 3

[ \text{Gini}_{X3=T} = 1 - \left( \left(\frac{2}{3}\right)^2 + \left(\frac{1}{3}\right)^2 \right) = 1 - \left( \frac{4}{9} + \frac{1}{9} \right) = 1 - \frac{5}{9} = \frac{4}{9} \approx 0.444 ]


( X3 = F ): (F, T, F, 0)

( Y = 0 ): 1 out of 1

[ \text{Gini}_{X3=F} = 1 - \left( \left(\frac{1}{1}\right)^2 \right) = 0 ]


[ \text{Weighted Gini}_{X3} = \left( \frac{3}{4} \times 0.444 \right) + \left( \frac{1}{4} \times 0 \right) = 0.333 ]
Step 3: Determine the Best Feature to Split On
Comparing the weighted Gini impurities for each feature:

( \text{Weighted Gini}_{X1} = 0.5 )
( \text{Weighted Gini}_{X2} = 0.5 )
( \text{Weighted Gini}_{X3} = 0.333 )

The feature ( X3 ) has the lowest weighted Gini impurity, so it is the best feature to split on at the root.
Conclusion
The feature to split on at the root of the decision tree is ( X3 ).



Q4)

X1 X2 X3 Y

T  T  T  1
F  T  F  0
T  F  T  0
F  F  T  1

After fully training the tree in the previous question what is the training error of the decision tree?

As can be seen by fully growing the tree that every leaf is a pure leaf (completely homogenous) and hence, the training error is zero.
Feedback:
As can be seen by fully growing the tree that every leaf is a pure leaf (completely homogenous) and hence, the training error is zero.



---

# Introduction
Welcome to the session on 'Hyperparameter Tuning in Decision Trees'. In the previous session, you learnt about the concepts of homogeneity and its various measures. In this session, you will first understand the disadvantages of decision trees. Then, you will learn about various truncation and pruning strategies that are used to overcome one of the biggest disadvantages of trees, that is, overfitting.

 

In this session:
- Disadvantages of decision trees
- Tree truncation
- Tree pruning
- Hyperparameter tuning
- Decision tree regression

# Disadvantages of Decision Trees

Decision trees are quite intuitive and promising algorithms for dealing with both continuous and categorical attributes.
Does this mean that they should be used for every case? Not really. 
Let’s watch the upcoming video to understand the problems associated with decision trees.

Note that you will learn about model selection and other related concepts of overfitting and bias variance trade off in the upcoming modules.


The following is a summary of the disadvantages of decision trees:

- They tend to overfit the data. If allowed to grow with no check on its complexity, a decision tree will keep splitting until it has correctly classified (or rather, mugged up) all the data points in the training set.
- They tend to be quite unstable, which is an implication of overfitting. 
A few changes in the data can considerably change a tree.

# Tree Truncation

Earlier, you learnt that decision trees have a strong tendency to overfit data, which is a serious problem. So, you need to pay attention to the size of the tree. A large tree will have a leaf only to cater to a single data point.


There are two broad strategies to control overfitting in decision trees: truncation and pruning. In this video, you will learn how these two techniques help control overfitting.

There are two ways to control overfitting in trees:

Truncation - Stop the tree while it is still growing so that it may not end up with leaves containing very few data points. Note that truncation is also known as pre-pruning.

Pruning - Let the tree grow to any complexity. Then, cut the branches of the tree in a bottom-up fashion, starting from the leaves. It is more common to use pruning strategies to avoid overfitting in practical implementations.

Please note that this session covers mainly the "Truncation" techniques. In case you also want to learn about "Pruning" techniques (which is completely independent), we have provided an optional segment which can be accessed [here](https://learn.upgrad.com/course/5802/segment/54830/326887/989934/4947775).


We recommend going through it after you have finished this whole session on hyperparameter tuning.


Let’s look into various ways in which you can truncate a tree:



Though there are various ways to truncate or prune trees, the DecisionTreeClassifier() function in sklearn provides the following hyperparameters which you can control:


1. criterion (Gini/IG or entropy): It defines the homogeneity metric to measure the quality of a split. Sklearn supports “Gini” criteria for Gini Index & “entropy” for Information Gain. By default, it takes the value of “Gini”.
2. max_features: It defines the no. of features to consider when looking for the best split. We can input integer, float, string & None value.
- If an integer is inputted then it considers that value as max features at each split.
- If float value is taken then it shows the percentage of features at each split.
- If “auto” or “sqrt” is taken then max_features=sqrt(n_features).
- If “log2” is taken then max_features= log2(n_features).
- If None, then max_features=n_features. By default, it takes “None” value.
3. max_depth: The max_depth parameter denotes the maximum depth of the tree. It can take any integer value or None. If None, then nodes are expanded until all leaves contain just one data point (leading to overfitting) or until all leaves contain less than "min_samples_split" samples. By default, it takes “None” value.
4. min_samples_split: This tells about the minimum no. of samples required to split an internal node. If an integer value is taken then consider min_samples_split as the minimum no. If float, then min_samples_split is a fraction and ceil(min_samples_split * n_samples) are the minimum number of samples for each split. By default, it takes the value "2".
5. min_samples_leaf: The minimum number of samples required to be at a leaf node. If an integer value is taken then consider min_samples_leaf as the minimum no. If float, then it shows the percentage. By default, it takes the value "1".
 

There are other hyperparameters as well in DecisionTreeClassifier. You can read the documentation in python using: 

help(DecisionTreeClassifier)
Later in the session, you will go through a model building exercise in Python which will show you how these hyperparameters affect the tree structure.



Q1) Comprehension - Truncation and Pruning
The process of splitting only when there is a sufficient number of data points in the node is called ______.

Truncation lets you split the data only when the number of data points in the node is greater than or equal to the 'minsplit'.

Q2) Comprehension - Truncation and Pruning
Which hyperparameter controls the minimum no. of samples required to split an internal node?

The min_samples_split specifies the minimum number of data points a node should have for it to be considered for splitting.

Q3) Comprehension - Truncation and Pruning
_________ takes care of the minimum number of samples required to be at a leaf node.

min_samples_leaf

✓ Correct
Feedback:
The minimum number of samples required to be at a leaf node. If an integer value is taken then consider - -min_samples_leaf as the minimum no. If float, then it shows percentage. By default, it takes “1” value.


Q4) Comprehension - Truncation and Pruning
Assume that you have set the min_samples_leaf as 3 and the min_samples_split as 6. Consider a node with 10 data points. On splitting on an attribute, one leaf gets 2 points, and the other one gets 8 data points. This split will not be executed. Why?

Ans: 
The number of data points in one of the leaves < min_samples_leaf.

✓ Correct
Feedback:
The number of data points in one of the leaves is 2, which violates the condition that the number of data points in a leaf should be at least 3 (as specified by the min_samples_leaf).

----

# Building Decision Trees in Python
In the previous session, we built a decision tree on default hyperparameters. Let’s now learn how to tune some of these hyperparameters and check what difference they make to the model performance. 

Please find the code file here and the dataset here
You can download the dataset and Jupyter Notebook from the link given below and practice along.


You are also required to download Graphviz that will be used to visualise decision trees in Python.

Let’s first create some helper functions to evaluate your model, as you would be doing it multiple times and creating these functions would ease the job.


Now that you have created some helper functions, let’s change some of the default hyperparameters, such as max_depth, min_samples_split, min_samples_leaf and criterion (Gini/IG or entropy), and understand how they impact the model performance.


In this video, you learnt how changing the default hyperparameters improve the model performance. Let's now watch the following video to look at how entropy can be used instead of Gini to measure the quality of a split.


Now, what you did so far was just exploring the hyperparameters and see how they affected the model performance. The numbers you chose for the hyperparameters just now was more or less random. However, there should be some way to choose the optimal values for the hyperparameters, right? In the next segment, you will learn how to tune the hyperparameters to find their optimal values using k-fold cross-validation. 



# Choosing Tree Hyperparameters in Python

So far, you have learnt how to tune different hyperparameters manually. However, you cannot always choose the best set of hyperparameters for the model manually. Instead, you can use gridsearchcv() in Python, which uses the cross-validation technique. Now, what exactly is cross-validation, and how is it helpful? Let’s watch the next video and hear what Rahim has to say about it.




As you learnt in this video, the problems with manual hyperparameter tuning are as follows:

Split into train and test sets: Tuning a hyperparameter makes the model 'see' the test data. Also, the results are dependent upon the specific train-test split.
Split into train, validation and test sets: The validation data would eat into the training set.
However, in the cross-validation technique, you split the data into train and test sets and train multiple models by sampling the train set. Finally, you can use the test set to test the hyperparameter once.

 
 Specifically, you can apply the k-fold cross-validation technique, where you can divide the training data into k-folds/groups of samples. If k = 5, you can use k-1 folds to build the model and test it on the kth fold. 

 
It is important to remember that k-fold cross-validation is only applied on the train data. The test data is used for the final evaluation. One extra step that we perform in order to execute cross-validation is that we divide the train data itself into train and test (or validation) data and keep changing it across "k" no. of folds so that the model is more generalised. This is depicted in the image below.


---
The green and blue boxes constitute the training data. Here, the green ones are the actual training data and blue ones are the test (or validation) data points selected within the training dataset. As you can see, the training data is divided into 5 blocks or folds, and each time 4 blocks are being used as training data and the remaining one back is being used as the validation data. Once the training process is complete, you jump to model evaluation on the test data depicted by the yellow box.


Now, coming back to the question, how do you control the complexity (or size) of a tree? A very ‘big’ or complex tree will result in overfitting. On the other hand, if you build a relatively small tree, it may not be able to achieve a good enough accuracy, i.e., it will underfit. So, what values of hyperparameters should you choose? As you would have guessed, you can use grid search with cross-validation to find the optimal hyperparameters.

 

In the next video, Rahim will explain how each hyperparameter affects a tree and how you should choose the optimal set of hyperparameters.


---

You played around with different values of different hyperparameters using GridSearchCV(). This function helped you try out different combinations of hyperparameters which ultimately eased your process of figuring out these best values. It is, however, important to note that the values tried out in the demonstration above may have not necessarily given the best results in terms of accuracy. You may go ahead and try out different combinations as well and see if you can surpass Rahim's test score.

 

Phew! That was surely a lot to take in the past couple of segment. Let’s now watch the next video to recall and summarise what you have learnt so far while building decision trees.




You are required to read the documentation of [sklearn DecisionTreeClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html) and understand the meaning of hyperparameters. The following questions are based on the documentation.




---
Q1) 
Decision Tree Hyperparameters
State whether true or false - the parameter min_samples_split specifies the minimum number of data points required in a node to be considered for further splitting.

Yes, as mentioned in the documentation, min_samples_split is the minimum number of data points required in a node to be considered for further splitting.

Q2) Decision Tree Hyperparameters
Choose the correct option: As you increase the value of the hyperparameter min_samples_leaf, the resulting tree will:

become less complex, and the depth will tend to reduce
Feedback:
Correct - min_samples_leaf is the minimum number of samples required in a (resulting) leaf for the split to happen. Thus, if you specify a high value of min_samples_leaf, the tree will be forced to stop splitting quite early.

Q3) 

**min_sample_split** tells above the minimum no. of samples reqd. to split an internal node. If an integer value is taken then consider min_samples_split as the minimum no. If float, then it shows percentage. By default, it takes the value “2”.

**min_sample_leaf** is the minimum number of samples required to be at a leaf node. If an integer value is taken then consider - -min_samples_leaf as the minimum no. If float, then it shows percentage. By default, it takes the value “1”.


# Decision Tree Regression
So far, you have learnt about splits for discrete target variables. But how is splitting performed for continuous output variables? You calculate the weighted mean square error (WMSE) of data sets (before and after splitting) in a similar manner as you do for linear regression models. In this video, you will learn about this in detail.


In decision tree regression, each leaf represents the average of all the values as the prediction as opposed to taking an majority vote in classification trees. This average is calculated using the following formula:

^yt=1Nt∑iϵDty(i)

This is nothing but the sum of all data points divided by the total number of data points.

 

Also, the impurity measure for a given node is measured by the weighted mean square error (WMSE), also known as variance, which is calculated by the following formula:

MSE(t)=1Nt∑iϵDt(y(i)−^yt)2

This is nothing but the variance of all data points.

 

A higher value of MSE means that the data values are dispersed widely around mean, and a lower value of MSE means that the data values are dispersed closely around mean and this is usually the preferred case while building a regression tree.

 

The regression tree building process can be summarised as follows:

- Calculate the MSE of the target variable.
- Split the data set based on different rules obtained from the attributes and calculate the MSE for each of these nodes.
- The resulting MSE is subtracted from the MSE before the split. This result is called the MSE reduction.
- The attribute with the largest MSE reduction is chosen for the decision node.
- The dataset is divided based on the values of the selected attribute. This process is run recursively on the non-leaf branches, until - you get significantly low MSE and the node becomes as homogeneous as possible.
- Finally, when no further splitting is required, assign this as the leaf node and calculate the average as the final prediction when  the number of instances is more than one at a leaf node.
- So, you need to split the data such that the weighted MSE of the partitions obtained after splitting is lower than that obtained with - the original or parent data set. In other words, the fit of the model should be as ‘good’ as possible after splitting. As you can see, the process is surprisingly similar to what you did for classification using trees.

This module includes an optional demonstration on regression trees for those who want to explore and understand the process in detail.


Q1) Regression
Which of the following homogeneity measures is used in tree regression? 

> The MSE is used to measure the homogeneity in regression where the target variable is continuous.


Q2) Regression
Select all the correct statements about regression trees. (Note: More than one option may be correct.)

- Each leaf in regression contains an average value that is used for prediction.
- The MSE is a measure of the average squared differences between the estimated values and the actual value.
- A decision tree splits a data set on the attribute that results in the maximum increase in homogeneity.

Q3)  Regression

Let’s learn about the steps involved in decision tree construction. Arrange the following steps in the order of their occurrence: 

- 1) Now that the MSE is sufficiently low, stop splitting.
- 2) You have a data set, D with categorical and numerical attributes as well as continuous target variables. So, it is a regression problem. Hence, you apply decision tree regression to it.
- 3) Split the original data set, D, on the selected attribute.
- 4) After selecting the homogeneity measure, you need to decide the first attribute on which you will split the original data set, D.
- 5) Keep splitting the subsequent data sets until you obtain a sufficiently low MSE.
- 6) Select a homogeneity measure for splitting. Since it is regression, let’s choose MSE.
- 7) Each leaf will now represent a linear regression model.
- 8) Split ‘D’ on all the attributes one by one, and select the attribute that results in the maximum increase in homogeneity after splitting.

Ans:

2,
You have a data set, D with categorical and numerical attributes as well as continuous target variables. So, it is a regression problem. Hence, you apply decision tree regression to it.
 6,
Select a homogeneity measure for splitting. Since it is regression, let’s choose MSE. 
 4, 
 After selecting the homogeneity measure, you need to decide the first attribute on which you will split the original data set, D.
 8, 
 Split ‘D’ on all the attributes one by one, and select the attribute that results in the maximum increase in homogeneity after splitting.
 3, 
 Split the original data set, D, on the selected attribute.
 5, 
 Keep splitting the subsequent data sets until you obtain a sufficiently low MSE.
 1, 
 Now that the MSE is sufficiently low, stop splitting.
 7 ,
  Each leaf will now represent a linear regression model.

First, decide if it is a classification problem or a regression problem. Then, select a homogeneity measure for splitting accordingly; of the many attributes, select the first attribute for splitting. After this, split the original data set on the selected attribute, and keep splitting until you obtain a sufficiently low MSE. Once you stop splitting, you will get leaves containing linear regression models.


Additional Readings:

In the next segment, you will learn how to implement decision tree regression in Python. If you wish to read more upon decision tree regression, we have curated some links below which you can go through.

[Decision Tree Regression](https://towardsdatascience.com/machine-learning-basics-decision-tree-regression-1d73ea003fda)
[Regression Trees Calculated Example](https://sefiks.com/2018/08/28/a-step-by-step-regression-decision-tree-example/) (Note that in the given example, standard deviation is computed to calculate the homogeneity of a node which is nothing but the square root of MSE).


# Decision Tree Regression in Python
Now that you have learnt how decision trees can be used to solve regression problems, let’s understand how regression trees are built in Python. For this, you will use the same housing data set that you used in multiple linear regression to predict house prices based on various factors such as area, number of bedrooms, parking space etc.

 

Essentially, the aim is to:

Identify the variables affecting house prices, e.g., the area, the number of rooms, bathrooms, etc. 
Create a linear model that quantitatively relates house prices with variables, such as the number of rooms, area, number of bathrooms; and
Know the variables that significantly contribute towards predicting house prices.


Let’s build the model using a DecisionTreeRegressor() with some arbitrary parameters for the sake of simplicity and more accurate prediction results.

In order to see what the model looks like, let’s plot our decision tree and try to interpret what it conveys about house prices. We also need to evaluate how our decision tree performs. From the video given below, let’s understand model interpretation and evaluation.


So now, you have a good understanding of how decision trees can be used for decision-making whenever you have continuous target variables. As an exercise, you can definitely perform more hyperparameter tuning here and improve the performance of the models that you built right now.



# Summary
In this session, you looked at one of the major drawbacks of decision trees, that is, overfitting, and the various methods that can be used to avoid it. 

You learnt that decision trees are prone to overfitting. There are two ways to avoid overfitting: truncation and pruning.

In truncation, you let the tree grow only to a certain size, while in pruning, you let the tree grow to its logical end and then you chop off the branches that do not increase the accuracy on the validation set.

There are various hyperparameters in the DecisionTreeClassifier that let you truncate the tree, such as minsplit, max_depth, etc.
You also learnt about the effect of various hyperparameters on the decision tree construction. 

You can download the lecture notes for decision trees from the link given below.

Decision Trees

 

Let's attempt some graded questions in the next page. Make sure you have gained an understanding of all the concepts before attempting.

You can download the lecture notes for decision trees from the link given below.

Decision Trees

Let's attempt some graded questions in the next page. Make sure you have gained an understanding of all the concepts before attempting.

Q1)
Gini Index
What is the Gini index of the complete data in the training set?

NO = 1/2
YES = 1/2
GINI = 1/2/(1-1/2) + 1/2(1-1/2) = 1/2
 = 1 -(1/2)^2 - (1/2)^2 = 1/2
There are two class labels in the training data. So the Gini index will be equal to 
pyes(1−pyes)+pno(1−pno).

The probability of class label 1 = 
(15/30) = 0.5, and the probability of class label 2 = 
(15/30) = 0.5.

Hence, you get Gini = 0.5(1-0.5) + 0.5(1-0.5) = 0.5.

Q2) Gini Index
What is the Gini index of the partitions if you split the training set on a1, 
i.e., average delivery rating. Here, take the condition to be a1 < 3. 

(Note: You go left if a1 is less than 3, and you go right if a1 is greater than or equal to 3.)

Ans: 

P(a<3) (NO)= 8/15
P(a<3) (YES)= 7/15

Left gini = 1 - ((8/15)^2 + (7/15)^2) = 1 - 8*8*7*7/15*15*15*15 = (50625 - 3136)/50625 = 47489/50625 = 0.938 


P(a>3) (NO) = 7/15
P(a>3) (YES)= 8/15
Right gini = 1 - ((7/15)^2+(8/15)^2) = 0.938

balenced = 1/2*0.938 + 1/2*0.938 = 0.938


Ans:

Feedback:
There are total 15 data points where a1 < 3 and 15 where a1 >= 3. The Gini index of the partition with a1 < 3 = 
8/15(1−8/15)+7/15(1−7/15)=112/225.  

Similarly, he Gini index of the partition with a1 >= 3 is also 
112/225

Hence, the Gini index of the attribute = 
(15/30)*(Gini index of partition with a1 < 3) + (15/30)*(Gini index of partition with a1 >= 3) which comes out to be 112/225.

Q3) 
Attribute Selection
Which attribute will you split the training data on? 

Note: Find the Gini index for both cases and then decide the split.

Average Orders per Month: (a2) < 20

✓ Correct
Feedback:
The Gini index (a2 < 20) 
≈
 0.32, and the Gini index(a1 < 3) 
≈
 0.50. Since Gini index (a2 < 20) < Gini index(a1 < 3), you split on a2.

 Q4) Can you split the right leaf node, with 2 data points belonging to class label 1 and 10 data points belonging to class label 2, on a1 = 2.5?

 Ans:

 This split violates the 'minimum number of data points that a leaf should have on splitting' condition put up by the min_samples_leaf.

 Q5) 

 Splitting
Let’s say that you further split the left partition on a1 = 1.5, 4.5. You get the following tree on splitting
What is the approximate Gini index of the partitions obtained after splitting on a1 = 1.5, 4.5? 

Ans: 

1 - 1/6^2 + 5/6^2 = 1 - 0.0277 + 0.6944 =  0.2778

1 - 12/12 ^2 + 0/12^2 = 0 


Feedback:
In total, there are 18 data points.
 One partition has 6 data points, 
 and the other partition has 12 data points.
  Hence, Gini index of partition = (fraction of data points with a1=1.5,4.5)*(Gini index of partition with a1=1.5,4.5) + (fraction of data points with a1!=1.5,4.5)*(Gini index of partition with a1!=1.5,4.5).



  0.09

✓ Correct
Feedback:
In total, there are 18 data points. One partition has 6 data points, and the other partition has 12 data points. Hence, Gini index of partition = (fraction of data points with a1=1.5,4.5)*(Gini index of partition with a1=1.5,4.5) + (fraction of data points with a1!=1.5,4.5)*(Gini index of partition with a1!=1.5,4.5).

Hence, P(a1 = 1.5, 4.5) = 6/18 and P(a1 != 1.5, 4.5) = 12/18

Now,

For the left leaf node, Gini = 16(1−1/6)+5/6(1−5/6)=10/36

For the right leaf node, Gini = 0
 (Since all data points belong to the same class).

 

Hence, the final Gini index becomes = 
(6/18×10/36))+(12/18×0)≈0.09


Q6) Splitting
You cannot further split the left node. Why?

(Note: The left node is the node highlighted with a red border in the following tree.)


Ans:

The number of data points in this node is less than the min_samples_split.

✓ Correct
Feedback:
The number of data points in this node is 6. The value of the minsplit, as specified at the beginning, is 10.

Q7)
Homogeneity
What can be said about the homogeneity of the right leaf obtained after splitting on a1 = 1.5, 4.5? The leaf is highlighted with a red border.


Ans:

The right partition is completely homogeneous.

✓ Correct
Feedback:
All the data points belong to the class label "No". There is no data point in the right leaf that belongs to the class label "Yes".