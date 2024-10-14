# Introduction

Now that we have covered quite a bit on linear regression, let us imagine that we have actually built a model and fit it, and it overfits the data.
This may be because the model is more complex than needed and hence is not performing well on unseen data. 

To reduce the complexity of the model, we can either reduce some of the coefficients selectively and/or remove variables that do not contribute much to the final result. 

To achieve this, we will use regularization.



**In this session**

The topics that will be covered in this session are as follows:

- Revise overfitting.

- Understand the intuition behind regularization.

- Learn about two methods used for regularization in the context of linear regression: Ridge and Lasso.

- Understand the differences between Lasso and Ridge regression.


# Regularization - Introduction

When a model performs really well on the data that is used to train it, but does not perform well with unseen data, we know we have a problem: overfitting. Such a model will perform very well with training data and, hence, will have very low bias; but since it does not perform well with unseen data, it will show high variance. Let’s watch the forthcoming video to understand this better.

NOTE: In the graph presented below, the Optimum Model Complexity line is shifted slightly towards the left. It should intersect with the Bias and Variance.


In other words, bias in a model is high when it does not perform well on the training data itself, and variance is high when the model does not perform well on the test data. Please note that a model failing to fit on the test data means that the model results on the test data varies a lot as the training data changes. This may be because the model coefficients do not have high reliability.

 

You also saw that there is a trade-off between bias and variance with respect to model complexity. As seen in the video, a simple model would usually have high bias and low variance, whereas a complex model would have low bias and high variance. In either case, the total error would be high.


What we need is lowest total error, i.e., low bias and low variance, such that the model identifies all the patterns that it should and is also able to perform well with unseen data. 

 

For this, we need to manage model complexity: It should neither be too high, which would lead to overfitting, nor too low, which would lead to a model with high bias (a biased model) that does not even identify necessary patterns in the data.

Note: Another point to keep in mind is that the model coefficients that we obtain from an ordinary-least-squares (OLS) model can be quite unreliable if among all the predictors that we used to build our model, only a few are related significantly to the response variable. 

 

So, what is regularization and how does it help solve this problem?
Regularization helps with managing model complexity by essentially shrinking the model coefficient estimates towards 0. This discourages the model from becoming too complex, thus avoiding the risk of overfitting.
Let’s try and understand this a bit better now.


We know that when building an OLS model, we want to estimate the coefficients for which the cost/loss, i.e., RSS, is minimum. Optimising this cost function results in model coefficients with the least possible bias, although the model may have overfitted and hence have high variance. 

In case of overfitting, we know that we need to manage the model’s complexity by primarily taking care of the magnitudes of the coefficients. The more extreme values of the coefficients are (high positive or negative values of the coefficients), the more complex the model is and, hence, the higher are the chances of overfitting. Let’s try and understand in the forthcoming video.


When we use regularization, we add a penalty term to the model’s cost function.
# Here, the cost function would be Cost = RSS + Penalty.

Adding this penalty term in the cost function helps suppress or shrink the magnitude of the model coefficients towards 0. This discourages the creation of a more complex model, thereby preventing the risk of overfitting. 

When we add this penalty and try to get the model parameters that optimise this updated cost function (RSS + Penalty), the coefficients that we get given the training data may not be the best (maybe more biased). Although with this minor compromise in terms of bias, the variance of the model may see a marked reduction. Essentially, with regularization, we compromise by allowing a little bias for a significant gain in variance. 



As we saw in the video, when we perform regularization, it has a smoothening effect on the model fit; in other words, when regularization is used, the curve smoothens out and the fit is close to what we want it to be. 



Note that we also need to remember two points about the model coefficients that we obtain from OLS:

These coefficients can be highly unstable – this can happen when only a few of the predictors that we have considered to build our model are related significantly to the response variable and the rest are not very helpful, hence random variables.
There may be a large variability in the model coefficients due to these unrelated random variables such that even a small change in the training data may lead to a large variance in the model coefficients. Such model coefficients are no longer reliable, since we may get different coefficient values each time we retrain the model.
Multicollinearity, i.e., the presence of highly correlated predictors, may be another reason for the variability of model coefficients. Regularization helps here as well.

 

So, to summarise, we use regularization because we want our models to work well with unseen data, without missing out on identifying underlying patterns in the data. For this, we are willing to make a compromise by allowing a little bias for a significant reduction in variance. We also understood that the more extreme the values of the model coefficients are, the higher are the chances of model overfitting. Regularization prevents this by shrinking the coefficients towards 0. In the next two segments, we will discuss the two techniques of regularization: Ridge and Lasso and understand how the penalty term helps with the shrinkage.



# Ridge Regression
So far, you have learnt that we need models that can identify general patterns in data and that they should work well with unseen data. 
In this segment, you will learn how Ridge regression helps us achieve this. 
So, let’s go ahead and learn more in the next video.


high lambda, model will overfit - whereas it will be the opposite as stated earlier around 15 seconds.

Visually, we can see that when lambda is 0, i.e., when there is no regularization, we have a model that is clearly overfitting. The blue line indicates the ideal fit and the red line indicates the way our model fits the data. For a small value of lambda, 0.1, the fitted model comes quite close to the actual data – this is what we want. However, as the lambda value increases further, we notice that the model starts underfitting. We basically want models that do not overfit the data, but they should be able to identify underlying patterns in it. Hence, an appropriate choice of lambda becomes crucial. This can be achieved through hyperparameter tuning. We also observed that for each value of lambda, we will get different sets of coefficients in Ridge regression.

 

One point to keep in mind is that we need to standardise the data whenever working with Ridge regression. We have seen that regularization puts a constraint on the magnitude of the model coefficients. Then the penalty term depends upon the magnitude of each coefficient. This makes it necessary to centre or standardise the variables. Centering the variable means that the intercept term will no longer be in the model. Please refer to this link for an example.    

 

So, to summarise:

Ridge regression has a particular advantage over OLS when the OLS estimates have high variance, i.e., when they overfit. Regularization can significantly reduce model variance while not increasing bias much. 

The tuning parameter lambda helps us determine how much we wish to regularize the model. 
The higher the value of lambda, the lower the value of the model coefficients, and more is the regularization. 

Choosing the right lambda is crucial so as to reduce only the variance in the model, without compromising much on identifying the underlying patterns, i.e., the bias.  

It is important to standardise the data when working with Ridge regression.

Ridge regression does have one obvious disadvantage. 
It would include all the predictors in the final model. 

This may not affect the accuracy of the predictions but can make model interpretation challenging when the number of predictors is very large.  
Let’s see how Lasso regression helps in addressing this in the next couple of segments.

Q1) Cost Function
The cost function in regularized regression models has two terms: the error term and the regularization term. The objective of the learning algorithm is to find the coefficients, betas, such that

The sum of the error term and the regularization term is minimised.

Feedback:
The objective is to minimise the error term and penalise the coefficients in the regularization term in order to obtain a simpler model

Q2) Bias variance tradeoff
Suppose you are fitting a data set with a complex regression model. You are using Ridge regression with the tuning parameter, lambda, to reduce its complexity. What would happen to the bias and variance if you choose a large lambda?


Bias->high, Variance->low

Feedback:
A large lambda implies a simpler model. Therefore, a simpler model would have higher bias and lower variance.

In the next segment, we will look at the implementation of Ridge Regression.


# Ridge Regression - Python Implementation

In this segment, you will see how ridge regression helps reduce the problem of overfitting using a simple dataset:

First, we will build a linear regression model which can be considered as the ideal regression model which we want to obtain. Implementation of the linear regression model is shown in the forthcoming video.


2. Now, we will fit an overfitting polynomial regression model on this linear data and observe the results.
3. Eventually we will apply ridge regularization to the polynomial regression model which we implemented earlier and see how it reduces model complexity to give us better results.



With same value of Polynomial + feature or higher degree of polynomial we can reduce overfitting by performing Ridge Regularization.

As you saw in the video, with increase in λ
, the polynomial regression model becomes progressively simpler as the coefficients are pushed down towards zero. In the next segment, you will learn about another regularisation technique, i.e., Lasso regularisation.


# Lasso Regression

In the previous segment, you learnt that Ridge regression retains all the variables that are present in the data. Now, when the number of variables is very large and the data may have unrelated or noisy variables, we may not want to keep such variables in the model. Lasso regression helps us here by performing feature selection. Let’s watch the forthcoming video and understand how it does so.


The primary difference between Lasso and Ridge regression is their penalty term. The penalty term here is the sum of the absolute values of all the coefficients present in the model. As with Ridge regression, Lasso regression shrinks the coefficient estimates towards 0. However, there is one difference. With Lasso, the penalty pushes some of the coefficient estimates to be exactly 0, provided the tuning parameter, λ, is large enough.

 

Hence, Lasso performs feature selection. Choosing an appropriate value of lambda is critical here as well. Because of this, it is easier to interpret models generated by Lasso as compared with those generated by Ridge. Also, just like with Ridge regression, standardisation of variables is necessary for Lasso as well. Now, in the forthcoming video, we will see how Lasso is implemented using Python.



So, to summarise:

The behaviour of Lasso regression is similar to that of Ridge regression.
With an increase in the value of lambda, variance reduces with a slight compromise in terms of bias.
Lasso also pushes the model coefficients towards 0 in order to handle high variance, just like Ridge regression. But, in addition to this, Lasso also pushes some coefficients to be exactly 0 and thus performs variable selection.
This variable selection results in models that are easier to interpret.
In the forthcoming video, Anjali explains variable selection feature in Python.

Correction: Anjali meant to say lambda value of 0.001 instead of 0.01 at 0:27 and 0:58.

Generally, Lasso should perform better in situations where only a few among all the predictors that are used to build our model have a significant influence on the response variable. So, feature selection, which removes the unrelated variables, should help. But Ridge should do better when all the variables have almost the same influence on the response variable. 

It is not the case that one of the techniques always performs better than the other – the choice would depend upon the data that is used for modelling.


Key take away:

- Lasso performs better in situations where only a few among all the predictors that are used to build our model have a significant influence on the response variable.

- Higher the value of lambda in the shrinkage term, more are the model coefficients pushed towards 0 and hence more the regularization.

- Standardizing variables is necessary before regularization.

In the next segment, we will look at the python implementation of ridge and lasso regression.


# Regularization - Python Demo
In the next video, you will get a walkthrough of our car price prediction python implementation. The entire code has been shared with you at the beginning of this session. Please run through the data cleaning and preparation code before proceeding with the video. In this code, we build Linear, Ridge and Lasso regression models and compare their results. 

 

Note: At 09:15 in the below video, the prof says 'Lasso', it should be 'Ridge'.

So, in this session:

We discussed the need for regularization, which helps models perform well with unseen data while identifying necessary underlying patterns in it. We did this by adding a penalty term to the cost function used by OLS. 

We discussed two methods, Ridge and Lasso regression, which both allow some bias to get a significant decrease in variance, thereby pushing the model coefficients towards 0. 

You learnt that in Lasso, some of these coefficients become 0, thus resulting in model selection and, hence, easier interpretation, particularly when the number of coefficients is very large.



# Graded Questions

Comprehension - Ridge and Lasso Regression

 

Ridge Regression is a technique for analysing multiple linear regression data that suffer from multicollinearity.
When multicollinearity occurs, least squares estimates are unbiased, but their variances are large so they may be far from the true value.
By adding a degree of bias to the regression estimates, ridge regression reduces the standard test errors.

Consider a data set (split into training and test) on which you build a ridge regression model.
Assume that only the raw attributes have been used and no new features have been developed for model building.

Based on the information above, answer the following questions.

Q1)
Regularization
As 
λ
 increases from 0 to infinity, select the correct option that describes the pattern of the residual sum of squares (RSS) of the training dataset. Refer to the image below

Ans:


Steadily increase

✓ Correct
Feedback:
Differentiating the cost function with lambda=0 gives the value of the coefficients which minimizes the RSS. Again, putting λ = infinity gives us a constant model with maximum RSS. Thus, the RSS steadily increases with the variation of lambda.


Q2)
Regularization
As 
λ
 increases from 0 to infinity, select the correct option that describes the pattern of the variance of the model.

 Feedback:
When λ=0, the alphas have their least square estimate values. The actual estimates heavily depend on the training data and hence variance is high. As we increase λ, alphas start decreasing and model becomes simpler. In the limiting case of λ approaching infinity, all betas reduce to zero and model predicts a constant and has no variance.

Q3)
Regularization
As 
λ
 increases from 0 to infinity, select the correct option that describes the pattern of the (squared) bias of the model.

Steadily increase

✓ Correct
Feedback:
When λ=0, alphas have their least-square estimate values and hence have the least bias. As λ increases, alphas start reducing towards zero, the model fits less accurately to training data and hence bias increases. In the limiting case of λ approaching infinity, the model predicts a constant and hence bias is maximum.


Q4) Hyperparameter Value
You decide to use regularization to tackle this problem, that is Ridge and Lasso Regression. What will happen if we use a very large value of the hyperparameter 
λ
?

Check all that apply.


Q5) 
Hyperparameter in Regularization
What is the hyperparameter used in regularisation? Note that the cost function for regularization is given by

RSS=∑ni=1(y−yi)2+λ∑kj=0β2j

Lambda is the hyperparameter used in regularisation models