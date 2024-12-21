# Ensembles

In this session, you will learn about random forests, one of the most popular algorithms in machine learning. Random forests use a technique known as bagging, which is an ensemble method. So, before you learn about random forests, let's first understand ensembles.


An ensemble refers to a group of things viewed as a whole rather than individually. In an ensemble, a collection of models is used to make predictions, rather than individual models. Arguably, the most popular in the family of ensemble models is the random forest, which is an ensemble made by the combination of a large number of decision trees.

 

In principle, ensembles can be made by combining all types of models. An ensemble can have a logistic regression, a neural network, and a few decision trees working in unison.

 

Now, before you understand how ensembles work, the following questions may arise:

- How does a collection of models work better than individual models?
- How do you choose individual models to form an ensemble such that it is better than any of the individual models?
In the following lectures, you will be able to find answers to these questions.



# Diversity and Acceptability

Ensembles of models are somewhat analogous to teams of individual players. If you were to choose a football team, you would take the following two steps:

- Choose people with different skill sets, such as defenders, attackers and a goalkeeper, to ensure diversity
- Choose good players, i.e., ensure that all players are acceptable from the point of view of their skill sets (and at least better than a regular person)

Diversity ensures that the models serve complementary purposes, which means that the individual models make predictions independent of each other.

For example, a random forest is an ensemble with a large number of trees as individual models. Diversity ensures that even if some trees overfit, the other trees in the ensemble will neutralise the effect. The independence among the trees results in a lower variance of the ensemble compared to a single tree. Ensembles are more robust to the choice of the training data which makes them more stable and less prone to high variance and overfitting. We will soon discuss how the learning algorithm is designed to achieve independence and how it is beneficial.

**Acceptability** implies that each model is at least better than a random model. This is a pretty lenient criterion for each model to be accepted into the ensemble, i.e., it has to be at least better than a random guesser.

Now, let’s watch the following video and hear Rahim explain the different ways in which you can bring in diversity.


There are a number of ways in which you can bring diversity among your models you plan to include in your ensemble.

- 1) Use different subsets of training data
- 2) Use different training hyperparameters
- 3) Use different types of classifiers
- 4) Use different features


Now you have understood the different ways to bring in diversity. But what makes an ensemble better than an individual model? Let’s understand this in the next segment. But first, let's answer some questions based on your learnings so far.

Q1)  Random Model
A binary classification model under consideration is better than a random model when it:

Makes correct predictions with a probability that is statistically better than that of a random model, i.e., 0.5.

✓ Correct
Feedback:
Acceptability means that a model is not making any random guesses, the probability of success of which, i.e., P(success), is 0.50. Thus, we want models for which the probability of success is > 50%

Q2) Diversity
What happens if the models in your ensemble are not diverse enough?

Ans:


Since the models are not diverse, they might give somewhat similar results and hence the ensemble performance might not be much better than the individual models.

✓ Correct
Feedback:
More the diversity, more diverse will be the results in the ensemble and hence, the ensemble will be equipped to handle and make predictions for a more diverse range of attributes. If the diversity is reduced, the models will give similar results and hence the ensemble performance might not be much better than the individual models.

# Comprehension - Ensembles

How can you guarantee that if the two conditions of diversity and acceptability are fulfilled to make an ensemble, it will be better than any individual model? Let's hear about this in the next video from Prof. Raghavan.

In this video, we discussed a few reasons why ensembles work better than individual models.

Now, let’s understand how an ensemble helps in making decisions. Consider an ensemble with 100 models consisting of decision trees, logistic regression models, etc. Given a new data point, each model will predict an output 
y for this data point. If this is a binary classification, then you simply take the majority score. If more than 50% models say 
y = 0, you go with 0, and vice versa.


Now, the question that arises is: Why should you expect the majority vote to perform better on unseen data than any of the 100 individual models? Well, there are a number of convincing arguments to answer this question.


Firstly, if each individual model is acceptable, i.e., if it is wrong with a probability of less than 50%, you can show that the probability of the ensemble being wrong (i.e., the majority vote going wrong) will be much less than that of any individual model. In this way your chance of getting the prediction correct will be higher as compared to the individual models in the ensemble as they pool the opinion of each weak learner. This is done by exploiting and leveraging the predictive power of these models to predict the final outcome.

 
Also, the ensembles cannot be misled by the assumptions made by individual models. For example, ensembles (particularly random forests) successfully reduce the problem of overfitting. If a decision tree in an ensemble overfits, you let it. Chances are extremely low that more than 50% of the models are overfitted. Ensembles ensure that you do not put all your eggs in one basket.

 
In a binary classification task, an ensemble makes decisions by considering the majority vote. This means that if there are n models in the ensemble and more than half of them give you the right answers, you will make the right decision. On the other hand, if more than half of the models give you the wrong answers, you will make a wrong decision. In the coin toss analogy, making a correct prediction corresponds to heads, whereas making an incorrect prediction corresponds to tails.

 
If you can prove that the probability of more than half of the models making a wrong prediction is less than that of any of the individual models, you will know that the ensemble is a better choice than any of the individual models. 

 
Like the professor mentioned, let's assume heads is analogous to making a correct prediction and since it is a biased coin - P(Head) >> P(Tail). Now, let's assume you have an ensemble of, say, 5 models, and let's take P(Head or Right Predicition) to be 0.6 and P(Tail or Wrong Prediction) to be 0.4 for each of the five models for the sake of demonstration. The probability of making a right prediction for the ensemble then turns out to be approximately 68% (basically calculate P(Head >=3) for majority). As you can see, this is higher (by ~8%) than any of the individual model's performance each of which only has a probability of 60% of being right.
 

It is important to remember that each model in an ensemble is acceptable, i.e., the probability of each model being wrong is less than 0.5 (as a random binary classification model is correct 50% of the time).

 
Using the above example, you easily saw that the probability of more than half of the models in an ensemble making the wrong prediction is significantly less than 0.5, i.e., less than a random model. For this you used the (biased) coin toss analogy to do the same, where you can map the predictions made by an ensemble to the two sides of a biased coin. Getting a correct prediction is equivalent to getting heads, and getting a wrong prediction is equivalent to getting tails, i.e., you map heads to success (correct prediction) and tails to failure (an incorrect prediction).


**Experimenting with an Ensemble of Three Models**

Experimenting with an Ensemble of Three Models

To understand why ensembles work better than individual models, let’s take a simple example of three coins (models). Consider an ensemble of three models: m1, m2 and m3, for a binary classification task (say, 1 or 0). Suppose each of these models has a probability of being correct 70% of the time.

 

So, each model is acceptable. Given a data point whose class has to be predicted, the ensemble will predict the class using a majority score. In other words, if two or more models predict class = 1 as the output, the ensemble will predict 1, and vice versa.

 

The following table shows all the possible cases that can occur while classifying a test data point as 1 or 0. The column to the extreme right shows the probability of each case. For example, if you take the first row, all m1, m2, and m3 give the correct output. Hence, the probability for this case becomes (0.7 x 0.7 x 0.7), since each model has a probability of being correct 70% of the times and all three models are completely independent of each other. Similarly, the probability of the second row becomes (0.7 x 0.7 x 0.3) since you have "Correct", "Correct", and "Incorrect". And so on for all the rows.

Ensemble Model
Ensemble Model

 
In this table, there are four cases each where the decision of the final model (ensemble) is either correct or incorrect. Let’s assume that the probability of the ensemble being correct is p, and the probability of the ensemble being incorrect is q.

For the data in the table, p and q can be calculated as follows:

p = 0.343 + 0.147 + 0.147 + 0.147 = 0.784
q = 0.027 + 0.063 + 0.063 + 0.063 = 0.216 = 1 - p
Notice how the ensemble has a higher probability of being correct and a lower probability of being incorrect than any of the individual models (0.78 > 0.70 and 0.216 < 0.30). In this way, you can also calculate the probabilities of the ensemble being correct and incorrect with 4, 5, 100, 1000, and even a million individual models. The difference in probabilities will increase with an increasing number of models, thus improving the overall performance of the ensemble.


# Some Popular Ensembles
Now that you have a good understanding of what ensemble models are, let’s look at some of the popular approaches to ensembling, such as voting, stacking, blending, boosting and bagging.

In the next video, Rahim will explain to you the concepts of voting, stacking and blending.

1) Voting:

Voting combines the output of different algorithms by taking a vote.
 In the case of a classification model, if the majority of the classifiers predict a particular class, then the output of the model would be the same class. 
 In the case of a regression problem, the model output is the average of all the predictions made by the individual models. In this way, 
 every classifier/regressor has an equal say in the final prediction.

2) Stacking and Blending:

Another approach to carry out manual ensembling is to pass the outputs of the individual models to a level-2 classifier/regressor as derived meta features, 
which will decide what weights should be given to each of the model outputs in the final prediction. 
In this way, the outputs of the individual models are combined with different weightages in the final prediction. 
This is the high-level approach behind stacking and blending.

Train Data --> Level 1 ( Classifier1/Model1 + Classifier2/Model2 + Classifier3/Model3 ) --> Level 2 Classifier (eg: Logistic Regrression) --> output

3) Boosting :

Boosting is one of the most popular approaches to ensembling.
 It can be used with any technique and combines the weak learners into strong learners by creating sequential models such that the
  final model has higher accuracy than the individual models.
 You saw the example shown below to see intuitively how adaptive boosting works.

- a. Adaptive boosting : 
Can be used with any technique.
Building secuential model one after another .
Combine weak learner into stronger one.
focus on error of previous model to build new model.

- b. Gradient boosting : 


4) Bagging (Bootstrapped Aggregation): 

Let’s now discuss Bagging (Bootstrapped Aggregation) in the following video. 
Random forests are built on this approach and are very powerful at reducing the variance of an algorithm. 

a. Goal :  reduce variance of the algorithm
b. benefits of bagging: 
 - works well with high variance algorithm like decision tree ,KNN,Neural Network.
 - easy to parallelize 
 - Fast
c. Limitation:
- loss of interpretability
- Feature dominance: if individual feature has more significance or dominence then bagging will not provide best result.

Bagging creates different training subsets from the sample training data with replacement, and an algorithm with the same set of hyperparameters is built
on these different subsets of data. In this way, the same algorithm with a similar set of hyperparameters is exposed to different parts of data, 
resulting in a slight difference between the individual models. The predictions of these individual models are combined by taking the average of all the values for regression
 or a majority vote for a classification problem.

Bagging works well with high variance algorithms and is easy to parallelise. By high variance, we mean algorithms which
change a lot with slight changes in the data as a result of which these algorithms very easily overfit if not controlled. 
If you recall, decision trees are very prone to overfitting if we don't tune the hyperparameters well. 
Hence, bagging works very well for high-variance models like decision trees.

However,  it has got some disadvantages as well. In this approach, you cannot really see the individual trees 
one by one and figure out what is going on behind the ensemble as it is a combination of n number of trees working together.
This leads to a loss of interpretability. Also, it does not work well when any of the features dominate because of which all the trees look similar and 
hence the property of diversity in ensembles is lost. Sometimes bagging can be computationally expensive and is applied depending on the case.

So far you have seen handling classification problems with ensembles. But remember that ensembles work well for regression problems as well.
The working is almost similar except for the aggregation of models the average of the predictions is taken for regression instead of majority 
voting for classification ensembles. To know more about this in detail, please refer the link given in the additional reading. 
An optional demonstration for hands-on practise of ensemble models in Python is given at the end of the module for those who want to explore and understand in detail.
Let’s now understand how random forests are built in the next segment.

For more information on the above methods, please go through the [documentation](https://www.mlsurveys.com/papers/80.pdf) here.

# Introduction to Random Forests

Bagging chooses random samples of observations from a data set. Each of these samples is then used to train each tree in the forest. However, keep in mind that bagging is only a sampling technique and is not specific to random forests.


In the bagging type of ensembles, random forests are by far the most successful. 
They are essentially ensembles of a number of decision trees. 
You can create a large number of models (say, 100 decision trees), each one on a different bootstrap sample from the training set.
To get the result, you can aggregate the decisions taken by all the trees in the ensemble.
Let's watch the following video to understand the same in detail.



Bootstrapping refers to creating bootstrap samples from a given data set.
A bootstrap sample is created by sampling the given data set uniformly and with replacement. 
A bootstrap sample typically contains about 40–70% data from the data set. 
Aggregation implies combining the results of different models present in the ensemble.

 

You learnt that a random forest selects a random sample of data points (bootstrap sample) to build each tree and a random sample of features while splitting a node. 
Randomly selecting features ensures that each tree is diverse and that some prominent features are not dominating in all the trees making them somewhat similar.


Suppose you want to build a random forest of 10 decision trees. 
- a. First, you will create 10 bootstrap samples from the data, and then, you will train each tree on a different bootstrap sample. 
Recall that in a decision tree every data point passes from the root node to the bottom until it is classified in a leaf node. 
- b. A similar process takes place in random forests as well while making predictions. 
Each data point passes through different trees in the ensemble which are built on different training and feature subsets. 
- c. The final outcome of these trees are then combined either by taking the most frequent class prediction 
in case of a classification problem or average in case of a regression problem.


Q1) Building a Random Forest
What is the process of subsetting observations and features for each decision tree in a random forest? (Note: More than one option may be correct.)

A random subset of observations is chosen every time a new tree is built in a forest.
A random subset of features is chosen every time a node is being split inside a tree.

q2) Random Forest vs Bagging
How is a random forest different from bagging? Select from the options given below. (Note: More than one option may be correct.)

In a random forest, a random sample of features is chosen at each node split, which does not happen in bagging.

Ans:

Bagging includes the creation of different bootstrap samples for different models, and aggregating the results of the models. 
Random forests use this technique along with randomly selecting features at each node while splitting it.

Q3) Aggregation in Random Forests
During bagging, or bootstrap aggregation, the test data point is passed through all the trees of the forest, 
and each tree makes its own prediction. How are these predictions aggregated in the case of a regression problem?

Q4) Aggregation in Random Forests
During bagging, or bootstrap aggregation, the test data point is passed through all the trees of the forest, 
and each tree makes its own prediction. How are these predictions aggregated in the case of a regression problem?
Ans:
The final prediction is the mean of all the predictions of the individual decision trees.


Apart from the general advantages of ensembles, random forests (or black box models) 
have significant advantages owing to their origins in decision trees and other linear models.
Let’s watch the next video to learn about the advantages of random forests.



---

It is worth reiterating that random forests have been much more successful than decision trees. 
In fact, as you learnt that ensembles are better than individual models (assuming diversity and acceptability), you can say that random forests 
are almost always better than decision trees, only if the trees are diverse and acceptable.

The advantages of random forests over decision trees and other linear models are manifold; some of them are discussed below.


###Advantages of Blackbox Models Over Tree and Linear Models

**Diversity**: Diversity arises because each tree is created with a subset of the attributes/features/variables, i.e.,
 not all the attributes are considered while making each tree; 
the choice of the attributes is random. This ensures that the trees are independent of each other.


**Stability:** Stability arises because the answers given by a large number of trees average out. A random forest has a lower model variance than an ordinary individual tree.

 
**Immunity to the curse of dimensionality:** Since each tree does not consider all the features, 
the feature space (the number of features that a model has to consider) reduces. 
This makes an algorithm immune to the curse of dimensionality. Also, a large feature space causes computational and complexity issues.

**Parallelization:** You need a number of trees to make a forest. Since two trees are independently built on different data and attributes, they can be built separately. This implies that you can make full use of your multi-core CPU to build random forests. Suppose there are 4 cores and 100 trees to be built; each core can build 25 trees to make a forest.

**Testing/training data and the OOB (out-of-bag) error:** You should always avoid violating the fundamental tenet of learning: 'Not testing a model on what it has been trained on’. While building individual trees, you can choose a random subset of the observations to train them. If you have 10,000 observations, each tree may only be built from 7,000 (70%) randomly chosen observations. OOB is the mean prediction error on each training sample xᵢ, using only the trees that do not have xᵢ in their bootstrap sample used for building the model. This is very similar to a cross-validation (CV) error. In a CV error, you can measure the performance on the subset of data that the model has not seen before.

In fact, it has been proven that using an OOB estimate is as accurate as using a test data set of a size equal to the training set.

 Thus, the OOB error omits the need for set-aside test data (though you can still work with test data like you have been doing, 
 at the cost of eating into the training data).

 ---

 Q1) Bagging
The core idea behind bagging is considering a majority score rather than committing to a set of assumptions made by a single model.
 Which of the following reasons is why the core idea is particularly successful in random forests?

 Trees are typically unstable.


If you have only one tree, you have to rely on the decision that it makes. 
The decision made by a single tree (on unseen data) majorly depends upon the training data, as trees are unstable. On the other hand, in a forest, 
even if a few trees are unstable, averaging out their decisions ensures that you do not make mistakes because of the unstable behaviour of a few trees.

Q2) Random Forests vs Decision Trees
In terms of accuracy, is a random forest always better than a decision tree? 

Ans:

While it is well known that random forests are better than a single decision tree in terms of accuracy,
 it cannot be said that they are better than every possible decision tree; the only issue is that it is more difficult to build a 
 decision tree that is better than a random forest.
 In fact, there may be several trees that provide better predictions on unseen data.

Q3) Variance in Random Forests
Which of the following statements is true?

A larger number of trees will result in a lower variance of the ensemble.

Variance refers to how much a model (here, ensemble) changes with changes in the training data.
 If a large number of trees are at work, then, even if some of them show a high instability (extreme variation in the trees and their predictions), 
the ensemble as a whole will reduce the variance by averaging out the results of each tree.

# Comprehension - OOB (Out-of-Bag) Error

In the last segment, you learnt that the OOB (out-of-bag) error is almost as good as the cross-validation error. 
The final prediction is the aggregation of all the predictions of individual decision trees.
 Remember that each tree in a random forest is trained on a random subset of the training set, which is called a bootstrapped sample. This means that for each sample (observation), 
there are several trees that did not include that sample, and for these trees, this sample is unseen. Let’s understand this better. 

Suppose there are N = 100 observations with 
M = 15 features, and the outcome variable is a categorical variable Y. Also, you build a random forest with 50 trees. The OOB is calculated as follows:

 
For each observation 
Ni,Ni is passed to all the trees that did not have it in their training. These trees then predict the class of 
Ni. The final prediction for 
Ni is decided by a majority vote.

Now let’s apply this to 
N1. Suppose 10 trees did not have 
N1 in their training. So these 10 trees make their prediction for 
N1. Let’s say four trees predicted 0, and the other six predicted 1 as the output. The final prediction for 
N1 will be 1.


Next, we move on to 
N2. Suppose 15 trees did not have 
N2 in their training. So these 15 trees make their prediction for 
N2. Let’s say 12 predicted 0, and the remaining three trees predicted 1 as the ouput. The final prediction for 
N2 will be 0.

This is done for each observation in the training set. Once all the predictions for each observation are calculated, the OOB error is calculated as the number of observations predicted wrongly as a proportion of the total number of observations.

Q1)

OOB Error
Which of the following data sets is used to calculate the OOB error?


Training set

✓ Correct
Feedback:
Only the training set is used while calculating the OOB error, which is why it gives a good idea of model performance on the unseen data without using a test set.

Q2) OOB Error
Which of the following statements is true?


All the observations of the training set are used to calculate the OOB error.

Feedback:
Recall that all the observations of the training set are used to calculate the OOB error.

# Feature Importance in Random Forests


Random forests use multiple trees, reduce variance and allow for more exploration of feature combinations.
Wouldn't it be great if we could use random forests for feature importance? Let’s now watch the following video to understand the notion of variable 
importance in random forests.

The importance of features in random forests, sometimes called ‘Gini importance’ or ‘mean decrease impurity’, 
is defined as the total decrease in node impurity (it is weighted by the probability of reaching that node 
(which is approximated by the proportion of samples reaching that node)) averaged over all the trees of the ensemble.


For each variable, the sum of the Gini decreases across every tree of the forest and is accumulated every time that variable is chosen 
to split a node. The sum is divided by the number of trees in the forest to give an average.

# Random Forests in Python

In this segment, you will understand how to implement random forests in sklearn. You will experiment with hyperparameters, such as the number of trees and the number of variables considered at each split. You will build the random forest classifier on the same heart disease data set.

Please run the code in the notebook and understand the initial few steps – data understanding, multiple regression model and decision tree – before moving on to the video.

Let’s now build a model using a RandomForestClassifier() with some arbitrary parameters for simplicity and better prediction results.


You built the model and looked at some sample trees and got an idea of how decisioning takes place. You also looked at the OOB score to understand how individual trees  perform. Let’s now watch the next video to learn how to tune some hyperparameters using gridsearchcv() to make our ensemble model perform better.

Let’s now watch the following video to look at the notion of variable importance in random forests.

To summarise, you learnt how to build a random forest in sklearn. Apart from the hyperparameters that you have in a decision tree, there are two more hyperparameters in random forests: max_features and n_estimators. The effects of both the hyperparameters are briefly summarised below.

 

The effect of max_features

You learnt that there is an optimal value of max_features, i.e, at very low values, the component trees are too simple to learn about anything useful, while at extremely high values, the component trees become similar to each other (and violate the 'diversity' criterion).

 

The effect of n_estimators

When you observe the plot of n_estimators and training and test accuracies, you will see that as you increase the value of n_estimators, the accuracies of both the training and test sets gradually increase. More importantly, the model does not overfit even when its complexity is increasing. This is an important benefit of random forests: You can increase the number of trees as much as you like without worrying about overfitting (only if your computational resources allow). 

 

Also, as you saw, since there were a lot of models to fit, the time taken was quite high. If you want to gain a better understanding of the time taken to build random forests, you can go through this optional segment.
 

Now try answering the following question and test your understanding.

Q1) 


Random Forest - Hyperparameter max_features
The hyperparameter, max_features, specifies the maximum number of features considered at each node's split. For example, if the data set contains 25 features and you specify max_features = 4, then at each split (in the component trees), only a maximum of four randomly chosen features will be considered. 

According to you, how would the ensemble performance vary as you gradually increase the value of max_features? Compare your guess with that of your batchmates.


Ans:

At very low values of max_features (e.g. 2), both the training and test accuracies will be low; both accuracies will gradually increase with max_features up to a certain point, while at extremely high values (e.g. 19), the training accuracy will continue to increase, while the test accuracy will reduce (and thus, the model will overfit).


If you are comfortable with building random forests now, we recommend you to attempt some optional model building coding exercises on the DoSelect console. The questions can be accessed here.



# Random Forest Regression in Python


In the previous session, you learnt how to use decision trees for regression analysis. However, you know that decision trees have their own limitations, and you need to overcome them to use random forests in order to exploit the predictive power of decision trees and obtain better results. Let's quickly understand how random forest regression is performed.


So now, you have a good understanding of how decision trees and random forests can be used for decision-making whenever you have continuous target variables. You also learnt how to explore the feature importance that is offered by both these models. As an exercise, you can definitely perform more hyperparameter tuning here and improve the performance of the model that you built right now.

## Telecom Churn Prediction

In this segment, you will learn how decision trees and random forests stack up against logistic regression. You will be looking at the telecom churn prediction example that we considered in the earlier module. You will be using the same data set with the same problem statement and build the tree models to understand how they are better than the logistic regression model. Before you step into this, go through the data set and previous Python notebook and recall the initial steps of data cleaning and preparation for building the model. 

 

You will use 21 variables related to customer behaviour (such as monthly bill, internet usage, etc.) to predict whether a particular customer will switch to another telecom provider or not, i.e., whether they will churn or not.

 

**Problem Statement**
You have a telecom firm that has collected data of all its customers. The main types of attributes are as follows:

Demographics (age, gender, etc.)
Services availed (internet packs purchased, special offers taken, etc.)
Expenses (amount of recharge done per month, etc.)
Based on all this past information, you want to build a model that will predict whether a particular customer will churn or not, i.e., whether they will switch to a different service provider or not. So, the variable of interest, i.e., the target variable here is ‘Churn’, which will tell us whether or not a particular customer has churned. It is a binary variable where 1 means that the customer has churned and 0 means that the customer has not churned.
 

Below you will find the churn, internet and customer datasets attached where you can download.


Let’s now watch the following video to learn how to build decision trees over the same data set and understand the trade-offs, benefits and limitations of decision trees over logistic regression.



You saw in the video given above that without putting much effort in scaling, multicollinearity, p-values and feature selection, you got impressive and better results using decision trees as compared to a logistic regression model. However, remember that decision trees are high variance models and that they change quite rapidly with small changes in the data. In such a case, let’s watch the next video to learn how random forests can help you stack better as compared to both logistic and decision tree models against this prediction problem.


Random forests definitely gave a great leverage in the results as compared to both logistic regression and decision trees with much less effort. It has exploited the predictive power of decision trees and learnt much more than a single decision tree could do alone. However, there is not much visibility with respect to the key features and the direction of their effects on the prediction, which is done well by a logistic regression model. If interpretation is not of key significance, random forests definitely do a great job.

 

Rahim has also built a manual ensemble model on the housing price prediction example that you solved in linear regression. If you are curious, you can go through that in [this](https://learn.upgrad.com/course/5802/segment/54830/326887/989934/4947777) optional segment.


# Summary
In this session, you covered some of the popular ensemble models such as Stacking, Blending, Boosting and Bagging. Random forests work around the principle of bagging which is also known as Bootstrap Aggregation.

 

You also saw how random forests are better performers as compared to decision trees and other linear models. Random forests use multiple trees, reduce variance, allow for more exploration of feature combinations.

 

The following is a quick summary of the session.


Graded:

1) 
Random Forests over Decision Trees
Which of the following is/are benefit(s) of random forest over a decision tree? (More than one option may be correct.)

==>

It is more stable than a decision tree

It reduces overfitting

It is immune to the curse of dimensionality

2) Decision Trees
Consider decision tree A learned with min_samples_leaf = 500. Now consider decision tree B trained on the same dataset and parameters, except that the min_samples_leaf=50. Which of the following is/are always true? (More than one option may be correct.)

The number of nodes in B >= the number of nodes in A

✓ Correct
Feedback:
min_samples_leaf guarantees a minimum number of samples in a leaf. Higher no of this parameter means you are stopping early. A lower value allows you to grow further. As the tree grows no of nodes increases.


The training error of B <= the training error of A

✓ Correct
Feedback:
min_samples_leaf guarantees a minimum number of samples in a leaf. Higher no of this parameter means you are stopping early. A lower value allows you to grow further. As the tree grows no of nodes increases. With more nodes and deeper tree , it tends to memorize training data and variance of the model increases.


3)

OOB Error
Select all that apply with regards to OOB or Out of Bag Error. (More than one option may be correct)


All the data points in the training set are considered while calculating the OOB error.

Each data point in the training set is considered only for some of the trees in the random forest while calculating OOB error.


4) 
Feature Importance in Random Forests
How do you calculate feature importance in random forests for a particular attribute?

==>

We take an attribute and check all the trees it was present in and take the average values of the change in the homogeneity on this attribute split. This average value of change in the homogeneity gives us the feature importance of that attribute.

✓ Correct
Feedback:
Recall that we take all the trees that attribute was present in and aggregate the homogeneity measures to calculate feature importance. We basically select all the trees the attribute was present in and calculate the 
Δ
Homogeneity on the attribute split. We then take an average of all of these 
Δ
Homogeneity to arrive at the final feature importance.