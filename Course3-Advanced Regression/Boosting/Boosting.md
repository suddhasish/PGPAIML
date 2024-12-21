# Introduction
Welcome to the module on Boosting.


Boosting is one of the most powerful ideas introduced in the field of machine learning in the past few years. It was first introduced in 1997 by Yoav Freund and Robert Schapire in the popular algorithm, AdaBoost. It was originally designed for classification problems. Since its inception, many other boosting algorithms that tackle regression problems have also been developed and have become well-known as they are used to design top solutions of many Kaggle competitions. In this module, you will learn the concepts of the most popular boosting algorithms – AdaBoost, Gradient Boosting and XGBoost.

 

In the previous course of Tree models,  you went through different ensemble models. In this particular course, you will focus on one such ensemble model – Boosting. 


Let's start with the introductory video.

In this video, Arihant mentions the different boosting methods which will be discussed in the course:

- Adaptive Boosting

- Gradient Boosting

- XGBoost

In this session
This session will introduce you to the following topics: 

- Ensemble models
- Introduction to boosting
- Building blocks of boosting
- AdaBoost procedure


# Ensemble Models
Before proceeding further, you should revisit the content on Ensemble models explained earlier.

 

This module will focus on boosting but will start with the difference between bagging and boosting.


‘The strength of unity lies in the diversity’ This saying holds the same meaning in the world of machine learning. Ensemble models bring us that flavour of diversity to create powerful models that can handle complex problems. It is a combination of models, each of which are trained to solve the same problem and provide the best result at the end.

For a machine learning task (classification or regression), you need a model that identifies the necessary patterns in the data and does not overfit. In other words, ‘the models should not be so simple as to not be able to identify even the important patterns present in the data; on the other hand, they should not be so complex as to even learn the noise present in the data set’.


This solution can be arrived at either through a single model or an ensemble, i.e., a collection of models. By combining several models, ensemble learning methods create a strong learner, thus reducing the bias and/or variance of the individual models.

Bagging is one such ensemble model which creates different training subsets from the training data with replacement. Then, an algorithm with the same set of hyperparameters is built on these different subsets of data.

 
In this way, the same algorithm with a similar set of hyperparameters is exposed to different subsets of the training data, resulting in a slight difference between the individual models. The predictions of these individual models are combined by taking the average of all the values for regression or a majority vote for a classification problem. Random forest is an example of the bagging method.

Bagging works well when the algorithm used to build our model has high variance. This means the model built changes a lot even with slight changes in the data. As a result, these algorithms overfit easily if not controlled. Recall that decision trees are prone to overfitting if the hyperparameters are not tuned well. Bagging works very well for high-variance models like decision trees.

Now let's understand these concepts clearly in the next video.


Boosting is another popular approach to ensembling. This technique combines individual models into a strong learner by creating sequential models such that the final model has a higher accuracy than the individual models. Let’s understand this.

These individual models are connected in such a way that the subsequent models are dependent on errors of the previous model and each subsequent model tries to correct the errors of the previous models. 

In the next video, you will learn about the application of boosting.

Q1) Base models
With respect to base models in Ensemble learning, which of the following statements is/are true?

- In boosting the base models are parallelly connected to reduce the overall bias of the resulting strong model.
- In bagging the base models are sequentially connected to reduce the overall variance of the resulting strong model.
- In boosting the base models are sequentially connected to reduce the overall bias of the resulting strong model.

# Weak Learners
Before proceeding further on boosting, let’s take a look at the foundation of boosting algorithms — Weak Learners.

 

As discussed earlier, boosting is an approach where the individual models are connected in such a way that they correct the mistakes made by the previous models. Here, these individual models are called weak learners. 

 

Till now, all the models you have learnt are strong learners, where each model performs well on any task that it is assigned to do – classification or regression. 

 

Weak learner, on the other hand, refers to a simple model which performs at least better than a random guesser (the error rate should be lesser than 0.5). It primarily identifies only the prominent pattern(s) present in the data and thus is not capable of overfitting. In boosting, such weak learners can be used to build your ensemble.

In boosting, any model can be a weak learner – linear regression, decision tree or any other model, but more often than not, tree methods are used here.

Note: Decision stump is one such weak learner when talking about a shallow decision tree having a depth of only 1.
In the next video, our expert Arihant will help you in understanding the concept of weak learners.



To summarise: Weak learners are combined sequentially such that each subsequent model corrects the mistakes of the previous model, resulting in a strong overall model that gives good predictions.
Through weak learners, you can do the following:

Reduce the variance of the final model, making it more robust (generalisable) 
Train the ensemble quickly resulting in faster computation time

Q1) Weak learners
Boosting uses weak learners as classifiers because _____

The error is greater than 0.5
The error is lesser than 0.5
Each weak learner is independent of the previous model
Each weak learner is dependent on the previous model

==>

2 & 4 only
Feedback:
The weak learners in boosting algorithm have an error rate less than 0.5 and each model corrects the mistakes of the previous trees.


# Introduction to Boosting - Adaboost
Now that you have gained an overall understanding of what boosting is, let's start with the original boosting algorithm,  AdaBoost.

AdaBoost stands for adaptive boosting and was developed by Schapire and Freund, who later went on to win the 2003 Gödel Prize for their work.

In the next video, Arihant will give you an overview of AdaBoost and why it is used. 



Before starting with a numerical example to understand AdaBoost, let’s see an overview of the steps that need to be taken in this boosting algorithm:

- AdaBoost starts with a uniform distribution of weights over training examples, i.e., it gives equal weights to all its observations. These weights tell the importance of each datapoint being considered.
- We start with a single weak learner to make the initial predictions.
- Once the initial predictions are made, patterns which were not captured by the previous weak learner are taken care of by the next weak learner by giving more weightage to the misclassified datapoints.
- Apart from giving weightage to each observation, the model also gives weightage to each weak learner. More the error in the weak learner, lesser is the weightage given to it. This helps when the ensembled model makes final predictions.
- After getting the two weights for the observations and the individual weak learners, the next weak learner in the sequence trains on the resampled data (data sampled according to the weights) to make the next prediction.
- The model will iteratively continue the steps mentioned above for a pre-specified number of weak learners. 
- In the end, you need to take a weighted sum of the predictions from all these weak learners to get an overall strong learner.


A strong learner is formed by combining multiple weak learners which are trained on the mistakes of the previous model.

Now, let's summarise all these learnings in the next video.

In the next segment, you will learn about implementing Adaboost using a numerical example.

Q1) Adaboost
How do we calculate the final model in the Adaboost algorithm?

==> 
The final model is the weighted sum of the predictions from all these weak learners to get an overall strong learner.

Feedback:
The final model tries to give importance to each weak learner depending on the error it made in predicting all the samples. So the final model is a weighted sum of all the weak learners.

# Adaboost Numerical Example- I

Now that you have an intuitive understanding of AdaBoost, let’s take a look at the inner workings of the algorithm with the help of a numerical example.

Let's continue the Adaboost numerical example in the next video.


In AdaBoost, we start with a base model with equal weights given to every observation. In the next step, the observations which are incorrectly classified will be given a higher weight so that when a new weak learner is trained, it will give more attention to these misclassified observations.


In the end, you get a series of models that have a different say according to the predictions each weak model has made. If the model performs poorly and makes many incorrect predictions, it is given less importance, whereas if the model performs well and makes correct predictions most of the time, it is given more importance in the overall model.


The say/importance each weak learner — in our case the decision tree stump — has in the final classification depends on the total error it made. 

α = 0.5 ln( (1 − Total error)/Total error ) 

You can see the relation of α(alpha) & error  in the following graph

The value of the error rate lies between 0 and 1. So, let’s see how alpha and error is related.

When the base model performs with less error overall, then, as you can see in the plot above, the α is a large positive value, which means that the weak learner will have a high say in the final model. 
If the error is 0.5, it means that it is not sure of the decision, then the α = 0, i.e., the weak learner will have no say or significance in the final model.
If the model produces large errors (i.e., close to 1), then α is a large negative value, meaning that the predictions it makes are incorrect most of the time. Hence, this weak learner will have a very low say in the final model. 
After calculating the say/importance of each weak learner, you must determine the new weights of each observation present in the training data set. Use the following formula to compute the new weight for each observation:

 

new sample weight for the incorrectly classified observation = original sample weight * eα


new sample weight for the correctly classified observation = original  sample weight * e−α

After calculating, we normalise these values to proceed further using the following formula:

Normalised weights =p(xi) / ∑ni  p(xi) , where p(xi) is the weight of each observation.

The samples which the previous stump incorrectly classified will be given higher weights and the ones which the previous stump classified correctly will be given lower weights.

In the next segment, you will understand how to make the final prediction with the  Adaboost algorithm.

-----


Alpha vs Error rate
What is the relationship between alpha (amount of say or importance of a weak learner) and error rate for any model?

==> 

The say/importance of a weak learner decreases with an increase in the error rate of the model.

✓ Correct
Feedback:
If the model performs poorly and makes many incorrect predictions, it is given less significance, whereas if the model performs well and makes correct predictions most of the time, it is given more significance in the overall model.


# Adaboost Numerical Example- II

Now, let's continue our numerical example and observe how the final prediction is made.

NOTE: 

1. Whenever we start with a new model all the samples of the dataset need to have equal distribution (1/n) and of the same size.

2. Also, the new learner should focus more on the samples which are incorrectly classified at the previous iteration.

 

To handle both these bottlenecks, a new dataset will be created by randomly sampling the weighted observations.

We create a new and empty dataset that is the same size as the original one. Then we take the distribution of all the updated weights created by our first model. You can see the visualisation of the weights below.

NOTE: You may observe that the total sum is 1.04 instead of 1. For simplicity, these values are rounded off.

To fill our new empty dataset, we select numbers between 0 and 1 at random. The position where the random number falls determine which observation we place in our new dataset.


Due to the weights given to each observation, the new data set will have a tendency to contain multiple copies of the observation(s) that were misclassified by the previous tree and may not contain all observations which were correctly classified. 

After doing this, the initial weights for each observation will be 1/n, thus we can continue the same process as learnt earlier to build the next weak learner.


This will help the next weak learner give more importance to the incorrectly classified sample so that it can correct the mistake and correctly classify it now. This process will be repeated till a pre-specified number of trees are built, i.e., the ensemble is built. 


The AdaBoost model makes predictions by having each tree in the ensemble classify the sample. Then, the trees are split into groups according to their decisions. For each group, the significance of every tree inside the group is added up. The final prediction made by the ensemble as a whole is determined by the sign of the weighted sum.



The final model is a strong learner made by the weighted sum of all the individual weak learners.

NOTE: Weight is mentioned in two different contexts - one for each observation & the other is in context of the importance/say given to each weak learner in the model.

 
Q1) 
Adaboost
Suppose you are performing a binary classification using Adaboost. There are total of 10 samples and the first tree that the model predicted has 2 misclassifications. 

With this understanding, what will be the say/importance of this tree

(Round off the value up to 3 decimal places)

 0.693

✓ Correct
Feedback:
The say/importance of a decision tree = 0.5*ln((1-0.2)/0.2) 


Q2) Adaboost
Suppose you are performing a binary classification using Adaboost. There are a total of 10 samples and the first tree that the model predicted has 2 misclassifications. 

With this understanding, what will be the total updated weights of all incorrect predictions?

(Round off the value up to 3 decimal places)



==>

In AdaBoost, after each weak learner (e.g., a tree) is trained, the weights of the misclassified samples are updated to give them more importance in the next round of training. The weight update formula for the misclassified samples is:
[ w_i' = w_i \cdot e^{\alpha} ]
where:

( w_i ) is the original weight of the sample.
( \alpha ) is the importance (or "say") of the weak learner, calculated as:

[ \alpha = \frac{1}{2} \ln\left(\frac{1 - \epsilon}{\epsilon}\right) ]
Given:

Total samples: 10
Misclassifications: 2
Initial weights are typically uniform, so ( w_i = \frac{1}{10} = 0.1 ) for each sample.
Error rate (( \epsilon )) = (\frac{2}{10} = 0.2 )

First, calculate the importance (( \alpha )):
[ \alpha = \frac{1}{2} \ln\left(\frac{1 - 0.2}{0.2}\right) = \frac{1}{2} \ln(4) ]
Since ( \ln(4) \approx 1.386 ):
[ \alpha = \frac{1}{2} \times 1.386 = 0.693 ]
Now, update the weights of the misclassified samples:
[ w_i' = 0.1 \cdot e^{0.693} ]
Since ( e^{0.693} \approx 2 ):
[ w_i' = 0.1 \cdot 2 = 0.2 ]
Since there are 2 misclassified samples, the total updated weights of all incorrect predictions are:
[ \text{Total updated weights} = 2 \times 0.2 = 0.4 ]
Therefore, the total updated weights of all incorrect predictions, rounded to three decimal places, is:
[ \text{Total updated weights} = 0.400 ]


Feedback:
The new weights of incorrect predictions = 2*0.1 * e ^ 0.6




# AdaBoost Algorithm
Now that you have understood the intuition behind the algorithm, let’s see the pseudo-code behind it. 

In the next video, Arihant will explain how the pseudo-code works in conjunction with the numerical example we saw earlier.


Correction: The initial weights for each sample is 1/m 

 

Here is the summary of the AdaBoost algorithm you have studied until now.

1. Initialize the probabilities of the distribution as 1/n where n is the number of data points
2. For t = 0 to T, repeat the following (T is the total number of trees):
  1. Fit a tree ht on the training data using the respective probabilities
  2. Compute ϵt=∑niDi[ht(xi)≠yi]  
  3. Compute αt =1/2ln((1−ϵt) / ϵt)
  4. Update Dt+1(i)=Dt(i)∗e−αtyiht(xi) / zt where, zt = ∑ni=1Di∗e−αtyiht(xi)
3. Final Model: 
H(x)=sign(∑Tt=iαtht(x))

You can see here that with each new weak learner, the distribution of the data changes, i.e., the weight given to each observation changes.

Observe the factor: e−αtyiht(xi)


If there is a misclassification done by the model, then the product of 
yi∗ht(xi) = -1

So, the power of the exponential will be positive (growing exponential weight). This indicates that the weight will increase for all misclassified points.


Otherwise, if it is correctly classified, then a product of 
yi∗ht(xi) = 1.

So, it will have a decaying weight because of the negative term in the power of the exponential term. This indicates that the weight will decrease for all correctly classified points.

The point here is to force classifiers (weak learners) to concentrate on observations that are difficult to classify correctly. 

The model continues adding weak learners till a pre-set number of weak learners have been added.


Then, make the final prediction by adding up the weighted prediction for every classifier.
 

H(x)=sign(∑Tt=iαtht(x))

Note: Summarizing the notations in the lecture, at an iteration 
t, there is a distribution 
Dt of the training data 
T on which you can fit a model 
ht  and then use the results to create a new distribution 
Dt+1.

The final model 
H(x) we built is an ensemble of all the individual models 
hi with weights 
αi.

In the next segment, you will learn how we perform these two steps. Before that, try the following questions.


Q1) Error value
Why is the error 
ϵ
t
 always less than 1/2 in AdaBoost?

==> 
 The models used in Adaboost are weak learners but the prediction error they make is less than a random guess. A random guess error is 50% or 0.5. Hence, 
ϵ
t
 < 0.5.


 Q2)

Alpha value
The following table shows the actual value and the predicted value by an intermediate tree 
h
t
 for 5 sample points :

Data points	Actual	Predicted
1	+1	-1
2	-1	-1
3	+1	+1
4	-1	+1
5	+1	+1
If we consider a hypothetical situation such that these data points constitute the complete dataset on which we build the model 
h
t
, what weight 
α
t
 will be attached to 
h
t
?



 
0.2027

✓ Correct
Feedback:
We see that the error 
ϵ
t
 = 0.4. Setting this value into the formula for 
α
, we get 1/2ln(0.6/0.4) = 0.2027


Practical advice: Before you apply the AdaBoost algorithm, you should remove the Outliers. Since AdaBoost tends to boost up the probabilities of misclassified points and there is a high chance that outliers will be misclassified, it will keep increasing the probability associated with the outliers and make the progress difficult. Some of the ways to identify outliers are:

Boxplots
Cook's distance
Z-score.



# AdaBoost Lab - Classification
In the following video, our expert Arihant will give you a walkthrough on the notebook on how to implement the AdaBoost classifier in Python. 

The problem statement that we will be working on is to predict which factors led to employee attrition in a particular company. Please find the dataset here

In the next video, we will continue the classification by applying Standard scaler on the features. 


Now that we have created both train & test datasets, we will move ahead and start building an Adaboost classifier on top of our dataset.


In the next video, we will continue the classification by applying Standard scaler on the features. 

Now that we have created both train & test datasets, we will move ahead and start building an Adaboost classifier on top of our dataset.


So, now that you have gone through the video, download and implement the code in the notebook by yourself to get an understanding of the classifier.

 
# Adaboost Lab - Regression
As we have understood how to implement the Adaboost classifier, Arihant will now give you a walkthrough on the implementation of Adaboost regressor in Python. 


The problem statement that we will be working on is to predict the house sales in a particular location and understand which factors are responsible for higher property value.

Please find the dataset [here](https://ml-course3-upgrad.s3.amazonaws.com/Boosting/Introduction+to+Boosting/kc_house_data.csv).


As we have understood the structure of data and how each variable is correlated with others, we will now look at the EDA & model building pipeline for the given dataset.


So, now that you have gone through the video, download and implement the code in the notebook by yourself to get an understanding of the Adaboost regressor.

Refer to the [documentation](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.AdaBoostRegressor.html) of adaboost regressor if needed.

In the next segment, we will understand the overall summary of this session.



Summary
In this session, you learnt the intuition behind boosting and studied the AdaBoost algorithm in detail.

- AdaBoost starts with a uniform distribution of weights over training examples.
- These weights give the importance of the datapoint being considered.
- You will first start with a weak learner h1(x) to create the initial prediction.
- Patterns which are not captured by previous models become the goal for the next model by giving more weightage.
- The next model (weak learner) trains on this resampled data to create the next prediction.
- This process will be repeated till a pre-specified number of trees/models are built.
- In the end, we take a weighted sum of all the weak classifiers to make a strong classifier.



# Gradient Boosting

# Introduction

Until now, you have learnt the original boosting algorithm, AdaBoost. 

In this session, you will learn about another popular boosting algorithm Gradient Boosting and its modification called XGBoost which is widely used in the industry. We will look at a numerical example to understand the working of each algorithm as we did in Adaboost.

In the next video, you will be introduced to Gradient Boosting Machines (GBM).


# Understanding GBM Regressor
Gradient Boosting, like AdaBoost, trains many models in a gradual, additive and sequential manner. However, the major difference between the two is how they identify and handle the shortcomings of weak learners. In AdaBoost, more weight is given to the datapoints which are misclassified/wrongly predicted earlier. Gradient Boosting performs the same by using gradients in the loss function.

 

In the next video, Arihant will explain the fundamentals of the Gradient Boosting machine with the help of a numerical example for a regression problem.


Let's continue the concept in the next video and understand how we compute the final prediction.


NOTE: New prediction = Initial prediction + Learning Rate*Residuals




To summarise, here are the broader points on how a GBM learns:

- Build the first weak learner using a sample from the training data; you can consider a decision tree as the weak learner or the base model. It may not necessarily be a stump, can grow a bigger tree but will still be weak, i.e., still not be fully grown.
- Then, predictions are made on the training data using the decision tree which was just built.
- The negative gradient, in our case the residuals, are computed and these residuals are the new response or target values for the next weak learner.
- A new weak learner is built with the residuals as the target values and a sample of observations from the original training data.
- Add the predictions obtained from the current weak learner to the predictions obtained from all the previous weak learners. The predictions obtained at each step are multiplied by the learning rate so that no single model makes a huge contribution to the ensemble thereby avoiding overfitting. Essentially, with the addition of each weak learner, the model takes a very small step in the right direction. 
- The next weak learner fits on the residuals obtained till now and these steps are repeated, either for a pre-specified number of weak learners or if the model starts overfitting, i.e., it starts to capture the niche patterns of the training data.
- GBM makes the final prediction by simply adding up the predictions from all the weak learners (multiplied by the learning rate).
 
The details of the mathematics are provided in the optional segment, kindly go through it if you want to take a deep dive into it.

In the next segment, we will look at the GBM classifier.

Question 

Learning rate
What is the reason for introducing the learning rate in GBM?

Feedback:
The final model is a weighted aggregation of all the individual models we have built in GBM. With each additional model, our prediction is getting better and close to the real/target value. We do not want any single weak learner to make a big contribution to the overall model which may result in overfitting. Learning rate helps us in controlling the contribution of each of the weak learners. Without it, the model may suffer from overfitting.


# Understanding GBM Classifier
By now, you would have had some understanding of how the gradient boosting process helps in reducing the error with each iteration. To summarise, the Gradient Boosting algorithm has the following two steps at each iteration:

Find the residual and fit a new model on the residual
Add the new model to the older model and continue the next iteration
This segment will focus on the algorithm of gradient boosting in a classification setting. Let’s now see how Gradient Boosting machine can be implemented for a classification problem with the help of a numerical example.

Once the residuals are calculated, we will now add another model on top of this residual. Let's understand this in detail through the next video.

Let's continue the concept of GBM classifier by understanding how we use this initial prediction to calculate the residuals with the help of the next video.


GBM:
After the new model has given the output value for each sample, we will find the new log(odds) for every sample. What is the formula for calculating the new log(odds)?

=>

New log(odds) = initial log(odds) + LR*(output value given by the Decision tree)

Feedback:
The new log(odds) are calculated by adding the previous log(odds) with the output value for each observation given by the new model.

After the new predictions are made we can move on to calculate the final predictions by doing an aggregate of all the predictions received so far on each sample.

---

To summarise, here are the broader points on how a GBM learns for a classification problem:

Build the first weak learner using a sample from the training data.  The initial prediction for every individual sample will be log(odds)(where odds = number of positive samples/number of negative samples).
Convert the result obtained from log(odds) to a probabilty value by using the sigmoid  function to transform it.

Probability=elog(odds)/ 1+elog(odds)

- Once the predictions are made, calculate the residuals, which will be the new response or target values for the next weak learner. 
- A new weak learner is built with the residuals as the target values and a sample of observations from the original training data.
- Calculate the output of each leaf of the current weak learner to find the new predictions.


- The final prediction is adding the current predictions to the predictions obtained from all the previous weak learners. The predictions obtained at each step are multiplied by the learning rate so that no single model makes a huge contribution to the ensemble thereby avoiding overfitting. Essentially, with the addition of each weak learner, the model takes a very small step in the right direction. 
- The next weak learner fits on the residuals obtained till now and these steps are repeated, either for a prespecified number of weak learners or if the model starts overfitting, i.e., it starts to capture the niche patterns of the training data.
- GBM makes the final prediction by simply adding up the predictions from all the weak learners (multiplied by the learning rate).


The details of the mathematics are provided in the optional segment, kindly go through it if you want to take a deep dive into it.

Reference:
StatQuest. “[Gradient Boost Part 3 (of 4): Classification](https://youtu.be/jxuNLH5dXCs)” YouTube, Joshua Starmer, Apr 8, 2019

Coming up:

In the next segment, you will learn about the implementation of GBM on different problem statements.


# GBM Lab - Classification

In the following video, Arihant will give you a walkthrough on how to implement the GBM classifier in Python. 

The problem statement that we will be working on is the same which we have gone through previously - Employee attrition prediction. Please use the dataset provided earlier.

Let's continue the walkthrough and implement GBM model on the given dataset.

So, now that you have gone through the video, download and implement the code in the notebook by yourself to get an understanding of the classifier.

Please find the code file [here](https://github.com/ContentUpgrad/Boosting/blob/main/Gradient%20Boosting/GBM-Classification.ipynb).

 

Refer to the [documentation](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.GradientBoostingClassifier.html) of GBM classifier if needed.



# GBM Lab - Regression
Now that you have understood how to implement GBM for a classification problem, let's proceed and understand how to implement the GBM regressor in Python. 

The problem statement that we will be working on is the same which we have gone through previously - House sales prediction. Please use the dataset provided earlie

So, now that you have gone through the video, please download and implement the code in the notebook by yourself to get an understanding of the regressor.

 

Please find the code file [here](https://github.com/ContentUpgrad/Boosting/blob/main/Gradient%20Boosting/GBM_Regression.ipynb).

 

Refer to the [documentation](https://github.com/ContentUpgrad/Boosting/blob/main/Gradient%20Boosting/GBM_Regression.ipynb) of GM regressor if needed.



# Understanding XGBoost
Extreme Gradient Boosting (XGBoost) is similar to the gradient boosting framework but more efficient and advanced implementation of the Gradient Boosting algorithm.


It was first developed by Tainqi Chen and became popular in solving the Higgs Boson problem. Due to its robust accuracy, it has been widely used in machine learning competitions as well.


In the next video, with this understanding, let's start with XGBoost.


Let's summarise what Arihant has said and have a recap of the different tree algorithms studied so far.


- AdaBoost is an iterative way of adding weak learners to form the final model. For this, each model is trained to correct the errors made by the previous one. The sequential model does this by adding more weight to cases with incorrect predictions. Using this approach, the ensemble model will correct itself while learning by focusing on cases/datapoints that are hard to predict correctly. 

- Next, let’s discuss gradient boosting. You learnt about gradient descent in the previous module. The same principle applies here as well, where the newly added trees are trained to reduce the errors (loss function) of earlier models. So, in gradient boosting, you can optimise the performance of the boosted model by bringing down the loss one small step at a time. 

- XGBoost is an extended version of gradient boosting, which uses more accurate approximations to tune the model and find the best fit.


Why is XGBoost so good?

- Parallel Computing: When you run XGBoost, by default it would use all the cores of your laptop/machine enabling its capacity to do parallel computation.

- Tree pruning using depth first approach: XGBoost uses ‘max_depth’ parameter as specified instead of criterion first, and starts pruning trees backward. 

- Missing Values: XGBoost is designed to handle missing values internally. The missing values are treated in such a manner that any trend in missing values (if it exists)  is captured by the model.

- Regularization: The biggest advantage of XGBoost is that it uses regularisation in its objective function which helps to controls the overfitting and simplicity of the model,  leading to better performance.



Due to parallel processing (speed) and model performance, we can say that XGBoost is gradient boosting on steroids.

Q1)
Features of XGBoost
Which of the following is/are a mandatory data pre-processing step(s) for an XGBoost model?


==> 
One-hot encoding or dummy variable creation of categorical predictors

✓ Correct
Feedback:
Yes, converting categorical data to numeric format is required.

Q2)
True/False
The major difference between Gradient Boosting and XGBoost is that XGBoost incorporates the regularisation parameter in its objective function to control over-fitting.

==> 

Feedback:
Both 'XGBoost ' and 'GBM' follow the principle of gradient boosting  but they differ in modelling details. XGBoost uses regularisation along with model building to maintain the simplicity of the model which results in better performance.

# Understanding XGBoost - II
In the next video, Arihant will explain the fundamentals of the XGBoost with the help of a numerical example for a regression problem.

Let's continue our understanding of XGBoost and observe how we will grow the tree with the best gain further ahead.

Once we have finalised our tree growth, we need to find the prediction generated by the selected tree. In the next video we will understand how to calculate the output at each leaf to calculate the final prediction.

XGBoost Regularisation
In XGBoost we have different parameters which help us in regularising the overall growth of our decision tree. With respect to these parameters, select the statement which are correct


Q1)
As we increase the values of lambda(λ), the chances of pruning of the branches increases

✓ Correct
Feedback:
Increasing the values of lambda(λ) decreases our similarity score. Lower values of the similarity score will decrease the value of the gain which will lead to pruning


Q2)
As we increase the values of gamma(γ), the chances of pruning of the branches increases

✓ Correct
Feedback:
A branch containing the terminal node is pruned when the gain < γ (or gain-γ = negative), therefore if we increase the values of gamma(γ), the chances of pruning increases


To summarise, here are the broader points on how an XGBoost learns:

- Build the first weak learner which performs the initial prediction on the given dataset. The initial prediction will be 0.5 for both regression & classification tasks.

- The residuals are computed and they will be the new response or target values for the next weak learner.

- A new weak learner is built with the residuals as the target values and a sample of observations from the original training data.
The new weak learner is created by calculating the similarity score and gain for all the constructed trees. The final tree is the one which has the optimal split i.e highest gain.  The various trees are constructed by splitting the data into two partitions of various possible splits or thresholds. This threshold for root is calculated by taking an average of two close points among the split and the residuals go to the respective leaf.

Gain = Similarity score(Left leaf) + Similarity score(right leaf) – Similarity score(root node)

 

- Using the tree with the highest gain, each node will split into further sub-nodes.

The nodes will stop splitting when it has only 1 residual left or based on the user-defined min number of sample data in each node, max iterations or tree depth. Tree pruning prevents overfitting with the help of threshold parameter γ. A branch containing the terminal node is pruned when the gain < γ (or gain-γ = negative).


- Once the tree is built, calculate the output of each leaf to find the new prediction.


Output Value = Sum of residual / member of residual + Lambda


- Add the predictions obtained from the current weak learner to the predictions obtained from all the previous weak learners. The predictions obtained at each step are multiplied by the learning rate so that no single model makes a huge contribution to the ensemble thereby avoiding overfitting. Essentially, with the addition of each weak learner, the model takes a very small step in the right direction. 


The next weak learner fits on the residuals obtained till now and these steps are repeated, either for a prespecified number of weak learners or if the model starts overfitting, i.e., it starts to capture the niche patterns of the training data.


In the next segment, you will learn about the implementation of XGboost for both classification & regression problems.


Reference:
StatQuest. “[XGBoost  Part 1 (of 4): Regression](https://youtu.be/OtD8wVaFm6E) ” YouTube, Joshua Starmer, Dec 16, 2019




# GBoost Lab

The objective of this segment is to learn how to implement the XGBoost algorithm in Python.
Before that, let's look at some of the hyperparameters used in XGBoost.

 

Hyperparameters - Learning Rate, Number of Trees and Subsampling


λt, the learning rate, is also known as shrinkage. It can be used to regularize the gradient tree boosting algorithm. 
λt typically varies from 0 to 1. Smaller values of 
λt lead to a larger number of trees T (called n_estimators in the Python package XGBoost). This is because, with a slower learning rate, you need a larger number of trees to reach the minima.  This, in turn, leads to longer training time. On the other hand, if 
λt is large, we may reach the same point with a lesser number of trees (n_estimators), but there is the risk of actually missing the minima altogether (i.e., cross over it) because of the long stride taken at each iteration.

Some other ways of regularisation are explicitly specifying the number of trees T and doing subsampling. Note that you should not tune both 
λt and number of trees T together since a high 
λt implies a low value of T and vice-versa.


Subsampling is training the model in each iteration on a fraction of data (similar to how random forests build each tree).  A typical value of subsampling is 0.5 while it ranges from 0 to 1. In random forests, subsampling is critical to ensure diversity among the trees, since otherwise, all the trees will start with the same training data and therefore look similar. This is not a big problem in boosting since each tree is any way built on the residual and gets a significantly different objective function than the previous one. 

γ ,Gamma is a parameter used to control the pruning of the tree. A node is split only when the resulting split gives a positive reduction in the loss function. Gamma specifies the minimum loss reduction required to make a split and makes the algorithm conservative. The values can vary depending on the loss function and should be tuned.

Apart from the previously mentioned hyperparameters, there are other parameters of decision trees like the depth of the tree, the minimum number of samples required for split, etc.



Q1) Hyperparameter Tuning in XGBoost
The hyperparameters 
λ
t
 (learning rate) and 
T
 (number of trees):

 Ans==>

 Are dependent on each other - the faster the learning rate, the lower the number of trees

✓ Correct
Feedback:
The faster the learning rate, the faster you move towards the minima, thus requiring a lower number of trees.

Q2)
XGBoost Regularization
What will happen if we increase the regularisation parameter 
γ
?

=>

The number of the leaves will decrease.

✓ Correct
Feedback:
We can see from the regularization formula that as we increase 
γ
, the number of leaf nodes shall decrease.


With all this understanding, let's move to the next video where Arihant will give you a walkthrough on how to do classification with XGBoost. The problem statement that we will be working on is the same which we have gone through previously - Employee attrition prediction. Use the dataset provided earlier



After understanding how to implement the code for building a XGBoost classifier, let's improve the accuracy with the help of Hyperparameter tuning.

Please find the code file [here](https://github.com/ContentUpgrad/Boosting/blob/main/Gradient%20Boosting/Xgboost-Classification%2BExample.ipynb).

Now that you have gone through classification, let's dive into the regression problem. Arihant will explain how to approach the regression problem with XGBoost through a code walkthrough.  The problem statement that we will be working on is the same which we have gone through previously - House sales prediction. Use the dataset provided earlier.

We have now understood the dataset with the help of basic inspection & visualisation, let's go ahead and create the train & test dataset in the next video.


You can implement the code by downloading the attached notebook.
Download and implement the code in the notebook to get an understanding of both XGBoost classification & regression.

Please find the [code](https://github.com/ContentUpgrad/Boosting/blob/main/Gradient%20Boosting/Xgboost-Regression-Example.ipynb) file here.


# Summary
You have come a long way. Let's look at a summary of all that you have covered in the last two sessions.


In the first session, you learnt the concepts of boosting and studied one of the earliest boosting algorithm, AdaBoost. You went through the process of updating the distribution of the datapoint by changing the probabilities attached to them and deciding the weights attached to the individual models that fit on this distribution. 


In the second session, you understood what Gradient Boosting is and its modification, XGBoost.

In the Gradient Boosting algorithm, we start off with a crude model that is the mean of all the target values. The subsequent model trains on the negative gradients of the loss function i.e the residual. With each new iteration, these residuals start decreasing and will continue till we reach a pre-specified number of weak learners. 

To summarise, the Gradient Boosting algorithm has the following two steps at each iteration:

Find the residual and fit a new model on the residual.
Add the new model to the older model and continue the next iteration.
 

After GBM, you have seen a  more efficient and advanced implementation of the Gradient Boosting algorithm i.e XGBoost. It follows the same procedure on trees with additional features like regularisation and parallel tree building to find the best split, which makes it one of the go-to model for any Kaggle competitions.

After understanding the basics, you have seen the numerical example to understand how we can regularise our model with parameters like gamma(
γ
) & lambda(
λ
).

In the XGBoost mechanism, we have more control in growing each individual tree (weak learner) based on the information gain at each split of the node. The final model has multiple such weak learners.

 

You can download the lecture notes for this module from the link below:



Q1)

Gradient Boosting
Consider the following statements w.r.t Gradient Boosting and choose the correct one:

At each iteration, we add an incremental model, which is fitted on the positive gradients of the loss function evaluated at current target values.
We multiply 
λ
t
(learning rate) with the incremental model 
h
t
+
1
  so that the new model does not overfit.


  ==>

  Only 2

✓ Correct
Feedback:
At each iteration, we add an incremental model 
h
t
+
1
, which fits on the negative gradients of the loss function evaluated at current target values. But to generate the final model we multiply 
λ
t
 with the incremental model 
h
t
+
1
  so that the new model doesn't  overfit


  Q2)

  Adaboost
In Adaboost, each model has different say/importance according to the error it has made while predicting the training data.

This is depicted in the following equation: α =  0.5 ln((1-TOTAL ERROR)/(TOTAL ERROR))

With respect to this, consider the following statements and choose the correct:

The classifier weight grows exponentially as the error approaches 0. Better classifiers are given exponentially more weight.
The classifier weight is 0.5 if the error rate is 0.5. This is because the classifier has only 50% accuracy. 
The classifier weight grows exponentially negative as the error approaches 1. These types of classifiers are given a negative weight.

==>

1 & 3 only 

✓ Correct
Feedback:
The classifier weight is zero if the error rate is 0.5. A classifier with 50% accuracy is no better than random guessing, so we ignore it.

Q3) General Expression for Residual
For a gradient boosting algorithm, let's say 
F
0
 is the crude model with which we start off. For a model Ft which is fitted on the training data, the prediction we get for xi is Ft(xi). What is the general expression of the residuals generated once the Ft model is trained? Assume y is the initial target variable.

 ==>

 y - [Fo(xi)+F1(xi) + F2 (xi)+.........+ Ft−2(xi) + Ft−1(xi) + Ft(xi)]

✓ Correct
Feedback:
The residuals created by F1 is y−F0(xi)−F1(xi), for F2 it is  y−F0(xi)−F1(xi) - F2(xi) and so on. In general, Ft trains on the residuals generated by the model Ft−1.  So the residuals created by Ft is y - [Fo(xi)+F1(xi) + F2 (xi)+.........+ Ft−2(xi) + Ft−1(xi) + Ft(xi)].


Q4) 

XGBoost
Which of these features are the advantages of XGBoost algorithm?

More than one option can be correct.



Parallel and distributed computing

✓ Correct
Feedback:
Fast learning through parallel and distributed computing enables quicker model exploration.


Handling of missing values 

✓ Correct
Feedback:
XGBoost handles missing values by treating thenm in such a manner that any trend in missing values (if it exists)  is captured by the model.


Regularisation

✓ Correct
Feedback:
Regularisation  is added in the objective function of XGBoost to penalize the model based on the number of trees and the depth of the model


