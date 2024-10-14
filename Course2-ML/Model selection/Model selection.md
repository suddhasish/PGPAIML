# Introduction to Model Selection

In the previous course, you may have come across situations wherein a model performs well on training data but not on the test data. You would have also faced confusion regarding the model to be used for a given problem. For example, by now, you have learnt about many classification models. Given a problem that requires classification, how would you decide which model is the best?

 
Questions such as these frequently arise irrespective of the choice of the model, data or the problem itself. The aim of this session is to answer such questions.

As Professor Raghavan mentioned, in these sessions, you will learn about some thumb rules and some general pointers regarding the selection of appropriate models. This session is only a discussion on such thumb rules. In subsequent sessions, these rules will be applied in the context of various problems and algorithms. 


The central issue in all of machine learning is how do we extrapolate learnings from a finite amount of available data to all possible inputs ‘of the same kind’? Training data is always finite, and yet, the model is supposed to learn all about the task at hand from it and perform well on unseen data. 



Consider the car pricing data set in linear regression, for example, which was trained using a few thousand observations. How do you ensure, and be confident, that the model is as good as it seems on the training data and deploy it to make predictions on real, unseen data?

Often, it is mistaken that if a model performs well on training data, it will produce good results on test data as well, and quite often, that is not the case.


Occam's razor is perhaps the most important thumb rule in machine learning and is incredibly 'simple' at the same time. When in dilemma, choose the simpler model. The question then is 'how do we define simplicity?'. In the next segment, you will learn about some objective ways to measure model simplicity and understand why simplicity is preferred over sophistication and complexity using various examples.



Ocams Razor: 
What does Occam's razor, a fundamental principle, suggest?

Occam’s razor does not suggest that a model should be unjustly simplified until no further simplification is possible. It suggests that when faced with a trade-off between a complex and a simple model, with all other things being roughly equal, you are better off choosing the simpler one. The reason for this will be explained shortly.

--
The central issue in machine learning can be said to be the study of How to extrapolate learnings from a finite amount of data to explain or predict all possible inputs of the same type


# Model and Learning Algorithm:

Before you dive into the concept of a simple model and learn about its benefits, we will take a short detour to reiterate some terminologies and the machine learning framework. You will now learn about the process of using training data, learning from it and then building a model to describe a system that performs a task at hand, such as classification or regression. The key objectives to be understood are as follows:

Meaning of a model, learning algorithm, system and hypothesis class
Difference between a learning algorithm and a model (often misunderstood)
Meaning of ‘class of models’ 

You revised the basic machine learning framework. You will now learn about a basic property of a learning algorithm, which is that it can only produce models of a certain type within its boundaries. This means that an algorithm designed to produce a linear class of models, such as linear / logistic regression, will never be able to produce a decision tree or a neural network. The class of the model becomes critical because a wrong class will yield a sub-optimal model. Let's understand this point in more detail.


Note: The linearity of SVMs will be discussed in detail in a later module. For now, remember that all SVMs (with any kernel or type of problem) are fundamentally linear problems.


Having understood the terminology and differences among algorithms, models and classes of models, you are now ready to learn about model simplicity, complexity and common issues such as overfitting.


#  Simplicity, Complexity and Overfitting
We will now discuss the notion of model simplicity and complexity in detail
and use some examples and analogies to gain an understanding of the pros and cons of simple and complex models. 

Now, you will gain an understanding of the type of learning model to be chosen. Suppose we choose regression, what type of regression will we use?

From your school or college, you can probably recall those few fellows who seemed to study less but understood much more than others. They never seemed to care about memorising or mechanically practising the concepts taught but were able to explain complex problems in physics or mathematics with simplicity and elegance. 


Assuming that people learn using ‘mental models’, do these students have remarkably different mental models than those who solve a bunch of books and focus on memorisation? How can they learn so much from a finite amount of information provided and apply the same to solve unseen, complex problems? 


In this segment, Prof. Raghavan will explain the meaning of model simplicity and complexity along with the pros and cons associated with them. As a by-product, you will also understand that the best way to ‘learn’ is ‘to keep your mental models simple’. 

Simpler models make a higher number of errors in training. In the next video, you will learn how to handle these.


# Overfitting

Overfitting is a phenomenon wherein a model becomes highly specific to the data on which it is trained and fails to generalise to other unseen data points in a larger domain. A model that has become highly specific to a training data set has ‘learnt’ not only the hidden patterns in the data but also the noise and the inconsistencies in it. In a typical case of overfitting, a model performs quite well on the training data but fails miserably on the test data. 

# Bias-Variance Tradeoff

So far, we have discussed the pros and cons of simple and complex models. On one hand, simplicity is generalisable and robust, and on the other hand, some problems are inherently complex in nature. There is a trade-off between the two, which is known as the bias-variance tradeoff in machine learning. You will learn about this in more detail in the upcoming modules. In the next video, Prof. Raghavan will introduce this topic.

Bias and Variance

We considered the example of a model memorising the entire training data set. If you change the data set slightly, this model will also need to change drastically. The model is, therefore, unstable and sensitive to changes in training data, and this is called high variance.

 

The ‘variance’ of a model is the variance in its output on some test data with respect to the changes in the training data. In other words, variance here refers to the degree of changes in the model itself with respect to changes in the training data.

 

Bias quantifies how accurate the model is likely to be on future (test) data. Extremely simple models are likely to fail in predicting complex real-world phenomena. Simplicity has its own disadvantages.

 

Imagine solving digital image processing problems using simple linear regression when much more complex models such as neural networks are typically successful for such problems. We say that a linear model has a high bias because it is quite simple to be able to learn the complexity involved in the task.

 

Ideally, we want to reduce both bias and variance because the expected total error of a model is the sum of the errors in bias and variance, as shown in the figure given below.

Bias Variance Tradeoff
Bias Variance Tradeoff
In practice, however, we often cannot have a model with a low bias and a low variance. As the model complexity increases, the bias reduces, whereas the variance increases and, hence, the trade-off.

 

Recall that in the competitive exam analogy, the first person learns using a much more complex mental model than the second one.

Q1)

Bias and Variance
What do the mental models of the first and the second person, respectively, have? (Note: More than one option may be correct.)

Q2)
Model Variance - Regression
Suppose Rohit builds two linear regression models to solve the car pricing problem. Model 1 has three features, and model 2 has 11 features. Which of these two models is likely to undergo a larger change when a new training data set is used?

Ans:

An artificially generated data set was used to generate data of the form (x, 2x + 55 + e), where e is a normally distributed noise with a mean of zero and variance of 1. The following three regression models have been created to fit the data: linear, a degree-15 polynomial and a higher degree polynomial that passes through all the training points.

# Comprehension - Bias Variance Tradeoff
An artificially generated data set was used to generate data of the form (x, 2x + 55 + e), where e is a normally distributed noise with a mean of zero and variance of 1. The following three regression models have been created to fit the data: linear, a degree-15 polynomial and a higher degree polynomial that passes through all the training points.


# Regularization
Having established that we need to find the correct balance between model bias and variance or between simplicity and complexity,
we need tools that can reduce or increase the complexity. 
In this segment, you will learn about regularization methods that are used to carefully observe model complexity.

Regularization is the process of deliberately simplifying models to achieve the correct balance between keeping the model simple and not too naive. Recall that a few objective ways of measuring simplicity are as follows: choice of simpler functions, fewer model parameters and usage of lower degree polynomials.


# Summary
In this session, you learnt about the most fundamental principles of machine learning that you should now be able to apply while building models. The most important points to re-iterate are as follows:

 

Occam's Razor

A model should be as simple as necessary but not simpler than that.
When in doubt, choose a simpler model.
Advantages of simplicity are generalisability, robustness, requirement of a few assumptions and less data required for learning
Bias-Variance Tradeoff

Bias measures how accurately a model can describe the actual task at hand.
Variance measures how flexible the model is with respect to changes in the training data.
As complexity increases, bias reduces and variance increases, and we aim to find the optimal point where the total model error is the least.
Overfitting

A model memorises the data rather than intelligently learning the underlying trends in it.
This is because it is possible to memorise data, and this is a problem because the real test happens on unseen, real-world data. 
 

Additional content - soft skills
Navigate here to access the soft skills content related to a job interview.


# Introduction
So far, the discussion has been regarding the choice of models. Once you decide the class of models to be used, you need to evaluate it. In this session, we will discuss two evaluation strategies corresponding to the cases wherein we have abundant and limited (or little) training data. 

In this session
This session will cover the following:

    - Meaning and use of hyperparameters
    - Meaning and use of validation data
    - Cross-validation
    - Hold-Out Strategy

# Regularization and Hyperparameters

Regularization discourages the model from becoming highly complex even if it explains the (training) observations better. 
In the previous session, you were introduced to this term that is used to find the optimal point between extreme complexity and simplicity.
In this context, we will discuss the use of the hyperparameters of a model.

Note: Regularization will be covered in depth in the optional module on Advanced Regression.
This session intends to introduce regularization as a concept.

Regularization discourages the model from becoming highly complex even if it explains the (training) observations better. In the previous session, you were introduced to this term that is used to find the optimal point between extreme complexity and simplicity. In this context, we will discuss the use of the hyperparameters of a model.

Hyperparameters are parameters that we pass on to the learning algorithm to control the complexity of the final model. They are choices that the algorithm designer makes to ‘tune’ the behaviour of the learning algorithm. Therefore, the choice of hyperparameters has a lot of bearing on the final model produced by the learning algorithm.

Hyperparameters are part of most learning algorithms that are used for training and regularization. In linear regression, hyperparameters are used to regularize models so that they do not become more complex than they should be. In the next video, you will learn about this in detail.



---
we have to break data into 3 parts Training // Validation // Test Data .
This is to avoid model to have sneak peak on test data multiple times while doing hyperparameter tuning.
---

From the video given above, the concept of hyperparameters has been summarised below.

Hyperparameters are used to 'fine-tune' or regularize the model to keep it optimally complex.
The learning algorithm is given the hyperparameters as the input, and it returns the model parameters as the output.
Hyperparameters are not part of the final model output.


# Model Evaluation and Cross Validation

We will now shift our attention to model evaluation. The key point to remember here is that a model should never be evaluated on data that it has already seen before. With that in mind, you will have either one of the 
    following two cases:
    1) the training data is abundant and 
    2) the training data is limited. 

 
The first case is straightforward because you can use as many observations as per your preference to train and test the model. In the second case, however, you will need to find some ‘hack’ so that the model can be evaluated on unseen data and, simultaneously, does not eat up the data available for training. This hack is called cross-validation. In the next video, you will gain a detailed understanding of this.

Partitioning should not be biased and should not alter basic charecteristics of data 

Example: 

Clssification problem :

in categorical problem where class label is 50:50 distributed 

we should not make training data 60:40 and test data 80:20.
Basic charecteristics of data is preserved when we make segrigation on training validation / test.

What if data is limited ?

We have populer idea Cross validation : - 

Random reshuffle the data split data into equal pieces.

example divide into 6 pieces then:

Model1:
1 - > test data
2-6 > Train data 

Model2:
2 > test
13456 --> train 

... continue


Generate 6 diffrent model each using 6 diffrent train and test data 
pick best among these model thats the model we select and output.

All high performing ML algorithm is train through Cross Validation.
---

# Model Evaluation: Python Demonstration - I

In the previous few segments, you learnt about regularization and hyperparameters. You also learnt about cross-validation. In the next few segments, you will learn how to carry out hyperparameter tuning and cross-validation in Python.

For demonstration, you will use cross-validation with linear regression. Then, you will tune the hyperparameter for the linear regression model. The hyperparameter for the linear regression model is the number of features being used for training.

 In the next video, you will gain an understanding of all the topics covered in this session.
In the next segment, you will conduct polynomial regression on the training data, which will result in overfitting.


# Model Evaluation: Python Demonstration - II
In the previous segment, you performed pre-processing on the housing data set.

 

Apart from using a straight line, you can also fit a polynomial to the training data with only one input variable. Fitting a polynomial to the data is known as polynomial regression. In the next video, you will first learn how you can conduct polynomial regression on the training data.

For linear regression of degree 1, you fit the curve of the following form:

y=β0+β1x1

For polynomial regression of degree n, you fit the curve of the following form:

y=β0+β1x1+β2x21+β3x31+....+βnxn1

In this way, instead of merely fitting a straight line to a single input-feature data set, you can fit a more complex curve to the training data.

How does fitting a more complex curve affect the accuracy on the test set? As you know, this can result in overfitting, which can lead to a low test accuracy.

Recall that you populated the following matrix with the outputs obtained from the linear regression models of various polynomial degrees as shown below.

The matrix given above was then used to plot the graphs for the test and train data as shown below.

The blue points represent the train and test data points in these graphs on the left and the right, respectively. The predictions for various polynomial degrees are shown in different colours. In these plots, you can observe that the curves start to overfit the data as the degree of the polynomial is increased beyond a certain degree. This is confirmed by the value of R-squared for both test and train data as shown in the results given below.

As you can observe, the training score is increasing while the test score is decreasing as the degree of the polynomial is increasing. This is a clear sign of overfitting.

# Cross-Validation: Motivation

In this segment, you will learn about cross-validation. You will use this technique to select the number of features for a linear regression model.

As you already know, RFE is one such technique. Now, you will learn how you can use cross-validation to tune this hyperparameter.


In this segment, you will learn about cross-validation. You will use this technique to select the number of features for a linear regression model.

As you already know, RFE is one such technique. Now, you will learn how you can use cross-validation to tune this hyperparameter.


The number of input variables in a linear regression model is a hyperparameter. RFE can be used to select this number. The process of selecting an optimal number is a tough task. What is the reason for this? If the number of features is extremely large (for example, 150), it becomes impossible to do it manually.

In such a case, you have an option to automate it using cross-validation. In the next video, you will learn how this can be done.


In summary, the problems associated with manual hyperparameter tuning are as follows:

Split into train and test sets: Tuning a hyperparameter makes the model 'see' the test data. Also, the results are dependent on the specific train-test split.
Split into train, validation and test sets: The validation data would eat into the training set.
However, in cross-validation, you split the data into train and test sets and train multiple models by sampling the train set. Finally, you only use the test set to test the hyperparameter once.

In the next segment, you will learn how to perform k-fold cross-validation in Python.

# Cross-Validation: Python Demonstration

In the previous segment, you understood the need for using cross-validation for hyperparameter tuning. Now, let's implement it in Python.

Specifically, you will perform k-fold cross-validation, wherein you divide the training data into k-folds.

Note: At timestamp [3:07], in updated version of sklearn it is 'neg_mean_squared_error' instead of 'mean_squared_error'. The same has been updated in the notebook.

Note: The latest version of scikit learn has updated the metrics to neg_mean_square_error.
Use scores = cross_val_score(lm, X_train, y_train, scoring='neg_mean_squared_error', cv=5) to reproduce same results in video.

Refer to the image given below.


In K-fold CV, you divide the training data into K-groups of samples. If K=4 (say), you use K-1 folds to build the model and test the model on the Kth fold. 
In the next segment, you will learn how cross-validation can be used for hyperparameter tuning.

# Cross-Validation: Hyperparameter Tuning

In the next video, you will learn how hyperparameter tuning is done in Python.

You use GridsearchCV to tune the hyperparameters in Python. The grid is a matrix that is populated on each iteration. Please refer to the image given below.

Grid Search
---
You can train the model using a different value of the hyperparameter each time. The estimated score is then populated in the grid.

The following three key steps are to be taken while tuning the hyperparameters in Python:

Create a cross-validation scheme: For example, the number of splits that you want to set
Specify the range of hyperparameters to tune
Perform a grid search on the set range

The results for grid search can be viewed using the following code:

 

pd.DataFrame(model_cv.cv_results_)

You can use the plot of mean test and train scores to choose the optimal number for the hyperparameter.

In the example given above, you had to select only 13 features.
What happens if you want to deal with a large number of features?
In the next lecture, you will learn how to do this using the grid search cv method.


The cross-validation scheme used for this demonstration was K-fold, but this is not the only one that is used. 
Multiple other schemes can be used. In the next video, let's take a look at some of them.


--
The various types of cross-validation are as follows:

K-fold cross-validation
Leave one out (LOO) cross-validation
Leave P-out (LPO) cross-validation
Stratified K-Fold cross-validation
For more information on the above-mentioned methods, please go through the documentation

Link: https://scikit-learn.org/stable/modules/cross_validation.html


---

Summary
The following points regarding model evaluation are worth reiterating:

 

Validation data 

Since hyperparameters need some unseen data to tune the model, the validation set is used.
It prevents the learning algorithm to 'peek' at the test data while tuning the hyperparameters.
A severe and practically frequent limitation of this approach is that data is often not abundant.
 

Cross-validation

It is a statistical technique that enables you to make extremely efficient use of the available data.
It divides the data into several pieces or 'folds' and uses each piece as test data one at a time.



This session covered the following:

1. The validation set is used because hyperparameters need some unseen data to tune the model.

2. Cross-validation is a statistical technique that enables you to make extremely efficient use of available data.



Q1) Training
Why should we have disjoint training and test data sets? (This means that a model should not be tested with data on which it is trained.)

Suggested Answer
Any model needs to be tested on how well it would work in the proverbial ‘real’ world because once a model has seen the data, it can attempt to ‘memorise’ it, and once that is done, testing it on the same data set will not help in determining its performance on unseen data. In an ideal scenario wherein we have plenty of data, we should divide the data into three sets. The first one would be the training data on which we shall train the model. The second one would be the validation data on which we shall test the model and tune the hyperparameters. The third one would be the test data that we will use for assessing our model.

Q2) Variance
Which of the following is more likely to have a low variance?

Weak Learner

✓ Correct
Feedback:
Weak learners create simpler models that have a lower variance. They are not able to model complex relationships and, hence, create a more generic model.


Q3) Bias-Variance
Suppose data is generated via a polynomial equation of degree 4 (i.e., the said polynomial equation will perfectly fit the given data). Which of the following statements is true in this case?


Linear regression will have a high bias and a low variance.

✓ Correct
You missed this!
Feedback:
Linear regression would create a degree-1 polynomial that would be less complex than the degree-4 polynomial and, hence, would have a higher bias. Since the model is less complex and will not overfit, it would have a low variance.




A polynomial equation of degree 4 will have a low bias and a low variance.

✓ Correct
You missed this!
Feedback:
Since the equation fits the data perfectly, both bias and variance will be low.


Q4) Model Variance
How do you measure the variance of a model?

By measuring how much does the estimates of the model change on the test data on changing the training data

✓ Correct
Feedback:
Variance measures the extent of change in a model with respect to the training data.


Q5) Regularization
What is regularization?


It is a technique that is used to strike a balance between model complexity and model accuracy on training data.

✓ Correct
Feedback:
Regularization does not improve accuracy; it improves the balance between accuracy and complexity.


Q6) Simple Models
Which of the following is incorrect with respect to creating simpler models? Assume that you have enough training data available.