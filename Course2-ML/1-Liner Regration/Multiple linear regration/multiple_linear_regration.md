Introduction
Welcome to the session on Multiple Linear Regression. So far, we have discussed the simple linear regression, where the model is built using one independent variable only. But, what if you have multiple independent variables? How do you make a predictive model in such a case? Build a multiple linear regression on top of such a data is one such solution.

 

In this session
You will use the example of sales prediction using the TV marketing budget that you saw in the previous session to build a multiple linear regression model. But now, instead of just one variable, you will have three variables to deal with. The marketing budget will be split into three marketing channels — TV marketing, radio marketing, and newspaper marketing. You will see how adding more variables brings in many new problems and how do you approach them. In the end, you will learn about feature selection and feature elimination to build the most optimal model.

 

This session is almost completely a theoretical session on multiple linear regression and its various aspects. So don't worry much if you don't get everything in the first go as you will also see each of these aspects in action in the next session as well which is a Python demonstration on multiple linear regression where things will become clearer.



**Motivation- When One Variable isn't Enough**


The term ‘multiple' in multiple linear regression gives you a fair idea in itself. It represents the relationship between two or more independent input variables and a response variable. Multiple linear regression is needed when one variable might not be sufficient to create a good model and make accurate predictions.

Let’s hear Rahim talk about it.

R-squared
In the simple linear regression model between TV and sales, the accuracy, or the 'model fit', as measured by R-squared was about 0.81. But, when you brought in the radio and the newspaper variables along with TV, the R-squared increased to 0.91 and 0.83, respectively. Do you think the R-squared value will always increase (or at least remain the same) when you add more variables?

Ans:
The R-squared will always either increase or remain the same when you add more variables. Because you already have the predictive power of the previous variable so the R-squared value can definitely not go down. And a new variable, no matter how insignificant it might be, cannot decrease the value of R-squared.


You saw that multiple linear regression proved to be useful in creating a better model, as there was a significant change in the value of R-squared. Recall that the R-squared for simple linear regression using 'TV' as the input variable was 0.816. When you have two variables as input - 'Newspaper' and 'TV', the R-squared gets increased to 0.836. Using 'Radio' along with 'TV' increased its value to 0.910. So it seems that adding a new variable helps explain the variance in the data better.

It is recommended that you check the R-squared after adding these variables to see how much has the model improved.
Let’s now look at the formulation of multiple linear regression. The multiple linear regression is just an extension of simple linear regression. Hence, the formulation is largely the same.




Most of the concepts in multiple linear regression are quite similar to those in simple linear regression. The formulation for predicting the response variable now becomes:

 

Y=β0+β1X1+β2X2+...+βpXp+ϵ


Apart from the formulation, there are some other aspects that still remain the same:

The model now fits a hyperplane instead of a line
Coefficients are still obtained by minimising the sum of squared errors, the least squares criteria
For inference, the assumptions from simple linear regression still hold - zero-mean, independent and normally distributed error terms with constant variance

Q1)
Assumptions of multiple linear regression
Which of the following assumptions changes for multiple linear regression?

None of the above assumptions changes when moving from simple to multiple linear regression.


**Moving from SLR to MLR: New Considerations**

When moving from a simple linear regression model to a multiple linear regression model, there are a few things that you have to look at.

Let's hear Rahim explain them in the following video.


The new aspects to consider when moving from simple to multiple linear regression are:

1. Overfitting
As you keep adding the variables, the model may become far too complex
It may end up memorising the training data and will fail to generalise
A model is generally said to overfit when the training accuracy is high while the test accuracy is very low
2. Multicollinearity
Associations between predictor variables, which you will study later
3. Feature selection
Selecting the optimal set from a pool of given features, many of which might be redundant becomes an important task



Q1)

Overfitting
Which of these two models would be a better fit to the data?

The first one
Feedback:
Correct! The first model seems to be generalising well on the dataset. So if more such similar data is introduced, the accuracy will not drop. 
But the second model clearly seems to have memorised all the data points in the dataset and hence, is displaying overfitting which might not be good if new data points are introduced.


Image used in the above question are from the following sources:

 

In the link below, you can understand more about the overfitting concept.

https://elitedatascience.com/overfitting-in-machine-learning


Coming up
Rahim has already discussed overfitting in the video above. In the next segment, you will study multicollinearity which is the phenomenon where adding multiple independent variables to the model can sometimes bring about dependency within themselves or cause redundency.


**Multicollinearity**

In the last segment, you learned about the new considerations that are required to be made when moving to multiple linear regression. Rahim has already talked about overfitting. Let’s now look at the next aspect, i.e., multicollinearity.

Note: At 00:41, Rahim accidentally says '9X1 + 9X2'. However, it should be '9X1 + 1X2'.


Multicollinearity refers to the phenomenon of having related predictor variables in the input dataset. In simple terms, in a model which has been built using several independent variables, some of these variables might be interrelated, due to which the presence of that variable in the model is redundant. You drop some of these related independent variables as a way of dealing with multicollinearity.

 

Multicollinearity affects:

1. Interpretation:
    Does “change in Y, when all others are held constant” apply?
2. Inference: 
    Coefficients swing wildly, signs can invert
    p-values are, therefore, not reliable
 

Multicollinearity is, thus, a big issue when you are trying to interpret the model. It is essential to detect and deal with the multicollinearity present in the model. Let's see how you can detect multicollinearity in the model.




You saw two basic ways of dealing with multicollinearity

1. Looking at pairwise correlations
   Looking at the correlation between different pairs of independent variables
2. Checking the Variance Inflation Factor (VIF)
   Sometimes pairwise correlations aren't enough
   Instead of just one variable, the independent variable might depend upon a combination of other variables
   VIF calculates how well one independent variable is explained by all the other independent variables combined
   The VIF is given by:
 
VIFi=1/1−Ri^2

where 'i' refers to the i-th variable which is being represented as a linear combination of rest of the independent variables.
 You'll see VIF in action during the Python demonstration on multiple linear regression.

The common heuristic we follow for the VIF values is:

> 10:  Definitely high VIF value and the variable should be eliminated.

> 5:  Can be okay, but it is worth inspecting.

< 5: Good VIF value. No need to eliminate this variable.

But once you have detected the multicollinearity present in the dataset, how exactly do you deal with it? Rahim answers this question in the following video.




1) Drop highly corelated variable which is not relavent for business to interpeat 
2) create new variable combining all corelated variable.
3) PCA
4) PLS

Q1)
Effects of Multicollinearity
Which of the following is not affected by multicollinearity i.e., if you add more variables that turn out to be dependent on already included variables?

R-squared value
Feedback:
The predictive power given by the R-squared value is not affected because even though you might have redundant variables in your model, they would play no role in affecting the R-squared. Recall the thought experiment that Rahim had conducted in one of the lectures. So suppose you have two variables, X1 and X2 which are exactly the same. So using any of the following, say, 10X1 or (4X1 + 6X2) will give you the same result. In the second case, even though you have increased one variable, the predictive power remains the same.

Q2)

VIF
VIF is a measure of:

How well a predictor variable is correlated with all the other variables, excluding the target variable
Feedback:
VIF measures how well a predictor variable can be predicted using all other predictor variables.

Q3) 
Calculating VIF
When calculating the VIF for one variable using a group of variables, the 
R2 came up to be 0.75. What will the approximate VIF for this variable be?

Ans:

Calculating VIF
When calculating the VIF for one variable using a group of variables, the 
R2  came up to be 0.75. What will the approximate VIF for this variable be?

Q4) Analysing the VIF value
Is the VIF obtained in the previous case a good VIF value?

Yes
Feedback:
The common heuristic for VIF values is that if it is greater than 10, it is definitely high. If the value is greater than 5, 
it is okay but worth inspecting. And anything lesser than 5 is definitely okay.


Some methods that can be used to deal with multicollinearity are:

1. Dropping variables
Drop the variable which is highly correlated with others
    Pick the business interpretable variable
2. Create new variable using the interactions of the older variables
    Add interaction features, i.e. features derived using some of the original features
3. Variable transformations
    Principal Component Analysis (covered in a later module)
Coming up
In the next segment, you will learn to handle the categorical variables present in the dataset.


PLS:
https://support.minitab.com/en-us/minitab/18/help-and-how-to/modeling-statistics/regression/supporting-topics/partial-least-squares-regression/what-is-partial-least-squares-regression/


**Dealing with Categorical Variables**

So far, you have worked with numerical variables. But many times, you will have non-numeric variables in the data sets. 
These variables are also known as categorical variables. Obviously, these variables can't be used directly in the model since they are non-numeric.

So in the following video, let’s see how you can deal with these variables.



When you have a categorical variable with say 'n' levels, the idea of dummy variable creation is to build 'n-1' variables, indicating the levels. 
For a variable say, 'Relationship' with three levels namely, 'Single', 'In a relationship', and 'Married', you would create a dummy table like the following:


Relationship Status	Single	In a relationship	Married
Single	            1	        0	            0
In a relationship	0	        1	            0
Married	            0	        0	            1

But you can clearly see that there is no need of defining three different levels. 
If you drop a level, say 'Single', you would still be able to explain the three levels.
Let's drop the dummy variable 'Single' from the columns and see what the table looks like:


Relationship Status	In a relationship	Married
Single	                  0	            0
In a relationship	      1	            0
Married                 	0	        1

Q1)
Number of Dummy Variables
The creation of dummy variables to convert a categorical variable into a numeric variable is an important step in data preparation. Consider a case where a categorical variable is a factor with 22 levels. How many dummy variables will be required to represent this categorical variable while developing the linear regression model?

21
✓ Correct
Feedback:
N-1 dummy variables can be used to describe a categorical variable with N levels.

---
Before you move on to the next segment, there’s one concept that needs to be addressed, the concept of scaling the variables.
Rahim had addressed scaling when answering a few common doubts surrounding linear regression in this optional segment, but now that you have dummy variables in the picture as well, let’s revisit the different aspects of scaling. 


It is important to note that scaling just affects the coefficients and none of the other parameters like 
t-statistic, 
F-statistic, 
p-values, 
R-squared, 
etc.

There are two major methods to scale the variables, 
i.e.
standardisation and MinMax scaling.

**Standardisation** basically brings all of the data into a 
standard normal distribution with mean zero and standard deviation one.

Standardisation:  
x = x−mean(x)/sd(x)

**MinMax scaling**, on the other hand, brings all of the data in the range of 0 and 1. 
The formulae in the background used for each of these methods are as given below: 

MinMax Scaling: 
x = x−min(x)/max(x)−min(x)


Coming up
In the next segment, you will learn to assess and compare models. 
The concept of comparing models is a very important part as for a data set we can use many models but to use 
a correct mapped model to the problem statement is a core part of machine learning.

Additional Reading

To know more about dummy variables (https://stats.idre.ucla.edu/other/mult-pkg/faq/general/faqwhat-is-dummy-coding/)
Why it's necessary to create dummy variables (https://stats.stackexchange.com/questions/89533/convert-a-categorical-variable-to-a-numerical-variable-prior-to-regression)
When to Normalise data and when to standardise? (https://stackoverflow.com/questions/32108179/linear-regression-normalization-vs-standardization)
Various scaling techniques (https://en.wikipedia.org/wiki/Feature_scaling)

**Model Assessment and Comparison**
Once the model is built, you would want to assess it in terms of its predictive powers. 
For multiple linear regression, you may build more than one model, with different combinations of the independent variables. 
In such a case, you would also need to compare these models with one another to check which one yields optimal results. 


Now, for the assessment, you have a lot of new considerations to make. 
Besides, selecting the best model to obtain decent predictions becomes quite subjective.
You need to maintain a balance between keeping the model simple and explaining the highest variance 
(which means that you would want to keep as many variables as possible). 
This can be done using the key idea that a model can be penalised for keeping a large number of predictor variables. 


 
Adjusted R2=1−(1−R2)(N−1)/N−p−1  // Higher is better.

Akice information criterion:
                                                                  
AIC=n×log(RSS/n)+2p  // lower this score is better 

Hence, there are two new parameters that come into picture:

Here, 
n is the sample size meaning the number of rows you'd have in the dataset and 
p is the number of predictor variables.

Q1)
Calculating Adjusted R-Squared
When a model was built from a dataset with 101 samples and 10 predictor variables, the R-squared value was found to be 0.7. What will the value of the adjusted R-squared be for the same model?

0.67

✓ Correct
Feedback:
The formula for adjusted R-squared is given as:

1−(1−R2)(N−1)N−p−1
So, substituting the given values at the appropriate places gives us:

1−(1−0.7)(101−1)/101−10−1≈0.67

q2)
R-squared vs Adjusted R-squared
Why do you think it is better to use adjusted R-squared in the case of multiple linear regression?

Ans:
The major difference between R-squared and Adjusted R-squared is that R-squared doesn't penalise the model for having more number of variables. Thus, if you keep on adding variables to the model, the R-squared will always increase (or remain the same in the case when the value of correlation between that variable and the dependent variable is zero). Thus, R-squared assumes that any variable added to the model will increase the predictive power.

Adjusted R-squared on the other hand, penalises models based on the number of variables present in it. So if you add a variable and the Adjusted R-squared drops, you can be certain that that variable is insignificant to the model and shouldn't be used. So in the case of multiple linear regression, you should always look at the adjusted R-squared value in order to keep redundant variables out from your regression model.


Coming up
Adjusted 
R2 adjusts the value of 
R2 such that a model with a larger number of variables is penalized. In the next segment, Rahim will talk about feature selection.

Additional Reading :

The following links provide a detail study on AIC and other parameters used in automatic feature selection :

https://en.wikipedia.org/wiki/Akaike_information_criterion
https://en.wikipedia.org/wiki/Akaike_information_criterion
https://en.wikipedia.org/wiki/Akaike_information_criterion

**Feature Selection**

The one crucial aspect of multiple linear regression that remains to be discussed is feature selection. 
When building a multiple linear regression model, you might have quite a few potential predictor variables; 
selecting just the right ones becomes an extremely important exercise.

Let’s see how you can select the optimal features for building a good model.

To get the optimal model, you can always try all the possible combinations of independent variables and see which model fits the best. But this method is obviously, time-consuming and infeasible. Hence, you need some other method to get a decent model. This is where manual feature elimination comes in, where you:

1. Build the model with all the features
2. Drop the features that are least helpful in prediction (high p-value)
3. Drop the features that are redundant (using correlations and VIF)
4. Rebuild model and repeat

Note that, the second and third steps go hand in hand and the choice of which features to eliminate first is very subjective.
You'll see this during the hands-on demonstration of multiple linear regression in Python in the next session.

Q1) Model Assessment
After performing inferences on a linear model built with several variables, you concluded that the variable ‘r’ was insignificant. This meant that the variable ‘r’:

Had a high p-value
Feedback:
A high p-value means that the variable is not significant, and hence, doesn't help much in prediction.

---
Now, manual feature elimination might work when you have a relatively low number of potential predictor variables, say, ten or even twenty. 
But it is not a practical approach once you have a large number of features, say 100. 
In such a case, you automate the feature selection (or elimination) process. Let's see how.


Automated Approach:

Rule criteria being used:

-  Top n feature : RFE (Recurssive Feature Elimination)
-  Forward / Backward /Stepwise selection : based on AIC 
-  Regularization (Lasso)

A combination Approach:  use a combination of automated (coarse tuning) + manual (fine tuning) selection .

Q1)
Recursive Feature Elimination
Read this document and answer the following question. 
Based on your reading, how do you think RFE measures the importance of the variable?

RFE:
class sklearn.feature_selection.RFE(estimator, *, n_features_to_select=None, step=1, verbose=0, importance_getter='auto')[source]
Feature ranking with recursive feature elimination.

Given an external estimator that assigns weights to features (e.g., the coefficients of a linear model), the goal of recursive feature elimination (RFE) is to select features by recursively considering smaller and smaller sets of features. First, the estimator is trained on the initial set of features and the importance of each feature is obtained either through any specific attribute or callable. Then, the least important features are pruned from current set of features. That procedure is recursively repeated on the pruned set until the desired number of features to select is eventually reached.

Recursive feature elimination is based on the idea of repeatedly constructing a model (for example, an SVM or a regression model) and choosing either the best or worst performing feature (for example, based on coefficients), setting the feature aside and then repeating the process with the rest of the features. This process is applied until all the features in the dataset are exhausted. Features are then ranked according to when they were eliminated. As such, it is a greedy optimisation for finding the best performing subset of features.

Q2) Recursive Feature Elimination
Suppose you have to build five multiple linear regression models for five different datasets. You're planning to use about 10 variables for each of these models. The number of potential variables in each of these datasets are 15, 30, 65, 10, and 100. In which of these cases you would definitely need to use RFE?

2nd, 3rd, and 5th cases

Feedback:
Correct! Though you might be thinking that while you would definitely need RFE in the 3rd and 5th cases, feature elimination in the 2nd dataset can be performed manually. But please note that while performing a manual elimination, you need to drop features one by one and bringing down the number from 30 to 10 can be very time-consuming. So it might be a good idea a perform an RFE to bring the number down to, say, 15, and then perform a manual feature elimination.


---

You need to combine the manual and the automated approaches in order to get an optimal model relevant to the business. Hence, you first do an automated elimination (coarse tuning), and when you have a small set of potential variables left to work with, you can use your expertise and subjectivity to eliminate a few other features (fine tuning).

---
Summary
Here’s a brief summary of what you learned in this session:

1. When one variable might not be enough
A lot of variance isn’t explained by just one feature
Inaccurate predictions
2. Formulation of MLR: MLR  helps us to understand how much will the dependent variable change when we change the independent variables.
3. New considerations to be made when moving from SLR to MLR
Overfitting - When the model becomes complex and gives very good results in training data and fails in the testing data.
Multicollinearity - To identify if there is any dependency within the pool of independent variables to remove redundancy.
Feature selection - Out of the pool of many features what features are considered to be most important. We drop the redundant features and those features that are not helpful in prediction. 
4. Dealing with categorical variables
Dummy variables - USed when there are fewer levels. You learnt about it using the marital status example.
5. Feature Scaling
Standardisation - Method used to make sure that data is internally consistent.
MinMax scaling - Method used to make sure that data is internally consistent.
Scaling for categorical variables - Categorical variables cannot used as they are, so they are converted to numeric format.
6. Model Assessment and Comparison
Adjusted R-squared - The adjusted R-squared value increases only if the new term improves the model more than would be expected by chance.
AIC, BIC - Various types of criteria used for automatic feature selection 
7. Feature Selection
Manual feature selection - A very tedious task in order to select the correct set of features.
Automated feature selection - The three step process is involved.
Select top 'n' features
Forward/backward/Stepwise selection based on AIC
Regularization  
Finding a balance between the two - A balance of both manual and automatic feature selection is required to attain the features.


Interview Practice Questions
---
Q1)
R-squared Values
Suppose you built a model with some features. 
Now you go and add another variable to the model. 
Which of the following statements would be true? (More than one option may be correct)


The R-squared value will either increase or remain the same

✓ Correct
Feedback:
Correct! The R-squared value always increases or remains the same with the addition of variables. It can never happen that an additional variable, no matter how insignificant it may be, will decrease the value of R-squared.


The Adjusted R-squared value may increase or decrease

✓ Correct
Feedback:
Correct! The key idea behind Adjusted R-squared is that it penalises models for having more number of variables. Thus, if the value increases on the addition of a variable, we may conclude that that variable is significant and vice-versa.

Q2)Overfitting
Overfitting is more probable when:


Number of data points are less

✓ Correct
Feedback:
Correct! Overfitting is the condition wherein the model is so complex that it ends up memorising almost all the data points on the train set. Hence, this condition is more probable if the number of data points is less since the model passing through almost every point becomes easier.


Q3)

VIF
VIF is a measure of:


How well a predictor variable is correlated with all the other variables, excluding the target variable

✓ Correct
Feedback:
VIF measures how well a predictor variable can be predicted using all other predictor variables


Q4) 
**Calculating VIF**
Suppose you were predicting the sales of a company using two variables 'Social Media Marketing' and 'TV Marketing'. You found out that the correlation between 'Social Media Marketing' and 'TV Marketing' is 0.9. What will be the approximate value of VIF for either of them?

Feedback:
Correct! The formula for VIF is given by:

**VIF=11−Ri2**
Here, the R-squared variable will simply be the correlation coefficient squared since we have only 2 variables. Hence, you have:

**VIF=1/1−0.9^2≈5.26**


Q5) **Dummy Variables**
Suppose you have 'n' categorical variables, each with 'm' levels. How many dummy variables would you need to represent all the levels of all the categorical variables?

Feedback:
Each of the dummy variables has 'm' levels. So to represent one categorical variable, 
you would require (m-1) levels.
Hence, to represent 'n' categorical variables, you would need (m-1)*n dummy variables.

Q6) Automated Feature Selection
Which of the following is/are an example of an automated approach for linear regression?


Recursive Feature Elimination

✓ Correct

Stepwise Selection using AIC

✓ Correct

Regularisation

Q7) Redundant Variables
After performing inferences on a linear model built with several variables, 
you concluded that the variable ‘r’ was almost being described by other feature variables. This meant that the variable ‘r’:

Had a high VIF

✓ Correct
Feedback:
Correct! If the variable is being described well by the rest of the feature variables, 
it means it has a high VIF meaning it is redundant in the presence of the other variables.
---
**Graded Question:**
---
Graded questions
Comprehension:

You are given a multiple linear regression model: 
Y=β0+β1x1+β2x2+β3x3

Recall that the null hypothesis states that the variable is insignificant. Thus, if we fail to reject the null hypothesis, you can say that the predictor is insignificant.
For e.g. if you fail to reject null hypothesis for 
x1, you can say that 
x1 is insignificant. This would also imply that the coefficient for 
x1 i.e., 
β1 = 0.
In other words, the null hypothesis tests if the predictor's coefficient, i.e 
βi = 0. If the null hypothesis is rejected then 
βi≠0.

Q1)
Comprehension Questions
If  β1=β2=0  holds and β3 = 0 fails to hold, then what can you conclude?

Ans:

There is a linear relationship between the outcome variable(Y) and 
x3

✓ Correct
Feedback:
Since, 
β3=0 fails to hold, this means that 
x3 is a significant variable in this linear regression model. Thus, we can say that there is a linear relationship between the outcome variable(Y) and 
x3

Q2) Comprehension Questions
If  β1  =β2 =β3 = 0  holds true, then what can you conclude?

Ans:
There is no linear relationship between y and any of the 3 independent variables

✓ Correct
Feedback:
If all the coefficients are found insignificant, then there cannot be a linear relationship between Y and any of the variables.

Q3) 
If the analyst adds this independent variable to the model, which of the following could happen? More than one choices could be correct.
--
1. 
The model’s R-squared will decrease
2. The model’s adjusted R-squared could decrease
3. The Beta-coefficient for predictor - digital marketing expenses, will remain same
4. The relationship between marketing expenses and sales can become insignificant



When adding an additional predictor variable that is highly correlated with an existing predictor variable (in this case, digital marketing expenses), several outcomes are possible. Here’s an analysis of each option:

The model’s R-squared will decrease:

Unlikely. R-squared measures the proportion of variance in the dependent variable that is predictable from the independent variables. Adding more predictors generally does not decrease R-squared; it either increases or remains the same because it accounts for more variance.
The model’s adjusted R-squared could decrease:

Possible. Adjusted R-squared adjusts for the number of predictors in the model. If the new predictor does not add significant explanatory power relative to its cost in degrees of freedom, the adjusted R-squared could decrease.
The Beta-coefficient for predictor - digital marketing expenses, will remain same:

Unlikely. When adding a predictor that is highly correlated with an existing predictor, multicollinearity can occur. This often causes the beta coefficients to change because the predictors are now sharing some of the same explanatory power.
The relationship between marketing expenses and sales can become insignificant:

Possible. Due to multicollinearity, the standard errors of the coefficients can increase, which might make the relationship between marketing expenses and sales statistically insignificant even if it was significant before.

Q4) Graded Questions
Suppose you need to build a model on a data set which contains 2 categorical variables with 2 and 4 levels respectively. How many dummy variables should you create for model building?

Feedback:
Since n-1 dummy variables can be used to describe a variable with n levels, you will get 1 dummy variable for the variable with two levels, and 3 dummy variables for the variable with 4 levels.

Q5) Redundant Variables
If one of the feature variables say, A is being explained well by some of the other feature variables, this would mean that the variable A has:

A high VIF

✓ Correct
Feedback:
Correct! If the feature variable A is being well explained by the other feature variables, this would mean that A has a high VIF. This is also evident from the formula for VIF: 
1 / 1−R2i.

Now, if A is being explained by some of the other feature variables, this would mean that the R-squared value is pretty high, which would make the denominator which is 
(1−R2i)
 very low, which again, in turn, would make the VIF value high. 

Q6) R-squared
Given different Rsq values of linear regression models on the same training dataset, which model would you choose as the best predictor? 
Assume that all these models are multiple linear regression models 

[Hint: Do you think only Rsq values are sufficient here?]


While R-squared ((R^2)) values provide a measure of how well the independent variables explain the variability of the dependent variable, they are not the only metric to consider when choosing the best predictive model. Here are some reasons why (R^2) values alone are insufficient:

Limitations of R-squared
Overfitting: A higher (R^2) value can sometimes indicate overfitting, especially if the model is too complex. Overfitting occurs when the model captures noise in the training data rather than the underlying pattern, leading to poor generalization on new data.
Adjusted R-squared: Unlike (R^2), adjusted (R^2) adjusts for the number of predictors in the model. It is a better measure when comparing models with different numbers of predictors.
Residual Analysis: Examining the residuals (the differences between observed and predicted values) can provide insights into the model's performance. Patterns in residuals can indicate issues like heteroscedasticity or non-linearity.
Cross-Validation: Cross-validation techniques, such as k-fold cross-validation, provide a more reliable estimate of model performance on unseen data.
Other Metrics: Metrics such as Mean Squared Error (MSE), Root Mean Squared Error (RMSE), Mean Absolute Error (MAE), and Akaike Information Criterion (AIC) can provide additional insights into model performance.
Comprehensive Model Evaluation
To choose the best predictive model, consider the following steps:

Adjusted R-squared: Compare the adjusted (R^2) values to account for the number of predictors.
Cross-Validation: Perform cross-validation to assess how well the model generalizes to new data.
Residual Analysis: Check the residuals for any patterns that suggest model inadequacies.
Other Metrics: Evaluate additional metrics like MSE, RMSE, MAE, and AIC.
Domain Knowledge: Use domain knowledge to ensure the model makes sense theoretically and practically.
Summary
Given the options:

0.86
0.76
0.94
(R^2) values alone are insufficient to answer this question.
The correct choice is:

4. (R^2) values alone are insufficient to answer this question.
You should consider a comprehensive evaluation using multiple metrics and techniques to choose the best predictive model.

Q7)
R-squared
State true or false:

Each time you add a feature to a model, the R-squared increases or remain same, even if it is by chance. It never decreases. 


True

✓ Correct
Feedback:
When you add a variable to your linear regression model, the value of its coefficient is optimized to give the best possible R-squared value.
The coefficient can take a non-zero value, which increases the value of R-squared for the model as compared to the previous model; or the coefficient is zero, which causes the R-squared value to remain the same. 
Hence, adding a feature will either always increase the R-squared value or not affect it at all.