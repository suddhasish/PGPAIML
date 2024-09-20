**Introduction**
Welcome to the session on Simple Linear Regression in Python. So far, we have discussed the theory part of simple linear regression. Now, let’s move on to building a simple linear regression model in Python.

In this session
You will learn about the generic steps that are required to build a simple linear regression model. You will first read and visualise the dataset. Next, you will split the dataset into train and test sets. After that, you will build the model on the training data and draw inferences. We have used the dataset and example from the ISLR book. You will use the advertising dataset given in ISLR and analyse the relationship between 'TV advertising' and 'sales' using a simple linear regression model. You will learn to make a linear model using two different libraries: statsmodels and SKLearn.

But before you move on to the Python code, let's do a quick recap of what you have learnt so far.


**Assumptions of Simple Linear Regression**

Before moving on to the Python code, we need to address an important aspect of linear regression: the assumptions of linear regression.
While building a linear model, you assume that the target variable and the input variables are linearly dependent. But do you need any assumptions other than this?
Let’s hear what Rahim has to say.

You are making inferences on the 'population' using a 'sample'. The assumption that variables are linearly dependent is not enough to generalise the results you obtain on a sample to the population, which is much larger in size than the sample. Thus, you need to have certain assumptions in place in order to make inferences.

 

Let's understand the importance of each assumption one by one:

 

There is a linear relationship between X and Y:

X and Y should display some sort of a linear relationship; otherwise, there is no use of fitting a linear model between them.
 



Error terms are normally distributed with mean zero(not X, Y):

There is no problem if the error terms are not normally distributed if you just wish to fit a line and not make any further interpretations.
But if you are willing to make some inferences on the model that you have built (you will see this in the coming segments), you need to have a notion of the distribution of the error terms. One particular repercussion of the error terms not being normally distributed is that the p-values obtained during the hypothesis test to determine the significance of the coefficients become unreliable. (You'll see this in a later segment)
The assumption of normality is made, as it has been observed that the error terms generally follow a normal distribution with mean equal to zero in most cases.
 


Image sources:https://reliawiki.org/index.php/Simple_Linear_Regression_Analysis

Assumptions of Simple Linear Regression
You can also learn more about the simple linear regression in the above link.
Error terms are independent of each other:
The error terms should not be dependent on one another (like in a time-series data wherein the next value is dependent on the previous one).
 



 

Image sources: https://www.jmp.com/en_in/statistics-knowledge-portal/what-is-regression.html

Assumptions of Simple Linear Regression
Error terms have constant variance (homoscedasticity):
The variance should not increase (or decrease) as the error values change.
Also, the variance should not follow any pattern as the error terms change.
 



Image sources: https://www.jmp.com/en_in/statistics-knowledge-portal/what-is-regression.html

Assumptions of Simple Linear Regression
You will look at each of these assumptions in more detail later and validate these while building the model.
You can also go through the following link to see what happens when the assumptions are violated. But things will anyway get clearer once we keep moving ahead.




Q1)
Assumptions of Simple Linear Regression
What will be the effect of the error terms not being homoscedastic in nature?

The inferences made on the model would be unreliable.
Feedback:
Yes! Even if you fit a line through the data, you cannot make inferences about the model. The parameters used to make inferences (which you will study in later segments) will become highly unreliable.

Q2) Assumptions of Simple Linear Regression
Which of the assumptions of linear regression is the following image shown to be violating?


Error terms having constant variance

✓ Correct
Feedback:
Correct! As is evident from the graph, the error terms seem to be reducing with an increase in the value of X. This is clearly a violation of the assumption that the error terms have constant variance.


In the next segment you will learn how to read data and understand data which is a core part of machine learning.

Q3)

Assumptions of Simple Linear Regression
You saw the following image in the lecture. What all assumptions on the error terms is this image referring to?


The error terms are normally distributed.

✓ Correct
Feedback:
Yes. From the image, it is evident that the error terms are normally distributed. But is something missing?



The mean in the distribution of the error terms is zero.

✓ Correct
You missed this!
Feedback:
Yes. If you look at the image carefully, you will see that the two bell curves shown have a mean of zero. 

If it is still not clear, think of it like this: The means of each of these normal distributions are shown to be lying on the line. Now, if the error term lies on the line itself, that would mean that the error term is actually zero.


The error terms have constant variance.

✓ Correct
Feedback:
Yes. If you look at the image, in both the distributions, the standard deviation is shown to be sigma, which refers to the assumption that the error terms have a constant variance.

But are you missing something?


**Reading and Understanding the Data**


From advertising.csv and Simple+Linear+Regression+in+Python.ipynb.

You read the data and visualised it using 'seaborn'. You also looked at the correlations between the target variable ‘Sales’ and the different predictor variables and saw that ‘TV’ has the strongest correlation with ‘Sales’. Sales and TV are linearly correlated. 

Coming up
Now that you have interpreted the data, let's start building a simple linear regression model on top of it, in the next segment.


**Hypothesis Testing in Linear Regression**

Before you move on to the model-building part, there is still one theoretical aspect left to be addressed: the significance of the derived beta coefficient. When you fit a straight line through the data, you'll obviously get the two parameters of the straight line, i.e. the intercept (
β0) and the slope (β1). Now, while β0
 is not of much importance right now, but there are a few aspects surrounding 
β1 which need to be checked and verified.

The first question we ask is, "Is the beta coefficient significant?" What does this mean?

Suppose you have a dataset for which the scatter plot looks like the following:

Now, if you run a linear regression on this dataset in Python, it will fit a line on the data which, say, looks like the following:

 

Now, you can clearly see that the data is randomly scattered and doesn't seem to follow a linear trend or any trend, in general. But Python will anyway fit a line through the data using the least squared method. But you can see that the fitted line is of no use in this case. 
 

Hence, every time you perform a linear regression, you need to test whether the fitted line is a significant one or not or to simply put it, you need to test whether 
β1
 is significant or not. And in comes the idea of Hypothesis Testing on 
β1
. Please note that the following text will assume the knowledge of hypothesis testing, which was covered in one of the earlier modules. Please revisit the module on hypothesis testing in case you need to brush up.

 
You start by saying that 
β1 is not significant, i.e. there is no relationship between X and y.

So in order to perform the hypothesis test, we first propose the null hypothesis that 
β1 is 0. And the alternative hypothesis thus becomes 
β1 is not zero.

Null Hypothesis (H0):β1=0
Alternate Hypothesis (HA):β1≠0 

Let's first discuss the implications of this hypothesis test. If you fail to reject the null hypothesis that would mean that 
β1 is zero which would simply mean that 
β1 is insignificant and of no use in the model. Similarly, if you reject the null hypothesis, it would mean that 
β1 is not zero and the line fitted is a significant one.

Now, how do you perform the hypothesis test? Recall from your hypothesis testing module that you first used to compute the t-score (which is very similar to the Z-score) which is given by 
X−μs/√n where μ is the population mean and 
s is the sample standard deviation which when divided by 
√n is also known as standard error.

Using this, the t-score for 
^β1 comes out to be (since the null hypothesis is that 
β1 is equal to zero):

 ^β1−0SE(^β1)
 

Now, in order to perform the hypothesis test, you need to derive the p-value for the given beta. If you're hazy on what p-value is and how it is calculated, it is recommended that you revisit the segment on p-value. Please note that the formula of 
SE(β1) provided in the t-score above is out of scope of this course.

Let's do a quick recap of how do you calculate p-value anyway:

Calculate the value of t-score for the mean point (in this case, zero, according to the Null hypothesis that we have stated) on the distribution
Calculate the p-value from the cumulative probability for the given t-score using the t-table
Make the decision on the basis of the p-value with respect to the given value of 
β  (significance level)
 

Now, if the p-value turns out to be less than 0.05, you can reject the null hypothesis and state that 
β1 is indeed significant.


Please note that all of the above steps will be performed automatically by the libraries we use Python which you'll learn in the very next segment.


Q1)
Hypothesis Test
What does it mean if you fail to reject the Null hypothesis in the case of simple linear regression?

β1 and thus, the independent variable it is associated with is insignificant in the prediction of the dependent variable. 

✓ Correct
Feedback:
Correct! The Null Hypothesis in simple linear regression is:

β1=0
Thus, if we fail to reject the Null hypothesis, it means that 
β1 is indeed zero, and thus insignificant for the prediction of the independent variable.

Q2)

Which of the following is used to calculate the p-value for a particular beta coefficient?
The t-statistic of the beta coefficient

✓ Correct
Feedback:
The t-statistic along with the t-distribution table is used to determine the p-value of the coefficient.
Q3)
Distribution of the Error Terms
If the sample size is small, i.e. less than 30, which of the following distribution is used to describe the error terms?

T-distribution

✓ Correct
Feedback:
Correct! In case of a small sample size, we use a t-distribution which is very similar to a normal distribution.


Q4)

T-score
Suppose that for a linear model, you got 
β1 as 0.5. Also, the standard error of 
β1 was found out to be 0.02. What will be the value of t-score for β1?

Ans:

25

Feedback:
Recall that the t-score for 
β1 is given as 
β1/SE(β1).
Hence, you have:

t-score =0.5/0.02 =25

Q5)
Significance of Beta
From the t-score you got in the previous question, what can you say about the significance of 
β1 ?


Given the t-score of 25, let's analyze its significance:

High t-score: A t-score of 25 is extremely high, indicating a very low probability that (\beta_1) is zero.
Critical t-value: For most practical purposes, critical t-values for common significance levels (e.g., 0.05, 0.01) and typical degrees of freedom (e.g., df > 30) are much lower than 25 (usually around 2 to 3).

Conclusion: Given the t-score of 25, it is highly likely that (\beta_1) is statistically significant at any conventional significance level (e.g., 0.05, 0.01, 0.001). This means that the predictor variable associated with (\beta_1) has a significant effect on the dependent variable in your linear model.


Correct! Recall that a t-distribution is very similar to a normal distribution. And a value as big as 25 means a practically zero p-value which in turn means that the variable is significant. You can have a look at the t-table here anyway. And you'll anyway see this in the Python demo in the next segment.




Coming up
Now that you know how to determine whether your beta is significant or not, you'll start building the model in the next segment

 

Additional Reading

Why does the test statistic for 
β
1
 follow a t-distribution instead of a normal distribution? (here)




 **Building a Linear Model**
Since 'TV' is very strongly correlated to 'Sales', let's first build a simple linear regression model with ‘TV’ as the predictor variable.

The first important step before building a model is to perform the test-train split. To split the model, you use the train_test_split function.

from sklearn.model_selection import train_test_split
X_train_lm, X_test_lm, y_train_lm, y_test_lm = train_test_split(X, y, train_size = 0.7, test_size = 0.3, random_state = 100)

From now on, you will always use the SKLearn library to perform a test-train split before fitting a model on any data.

After you import the statsmodel.api, you can create a simple linear regression model in just few steps.

import statsmodels.api as sm
X_train_sm = sm.add_constant(X_train)
lr = sm.OLS(y_train, X_train_sm)
lr_model=lr.fit()

Here, OLS stands for Ordinary Least Squares, which is the method that 'statsmodels' use to fit the line. You use the command 'add_constant' so that statsmodels also fits an intercept. If you don't use this command, it will fit a line passing through the origin by default.
Let's build the summary statistic in the next video.

Now, let's take a look again at the summary statistics that was outputted by the model.

Summary Statistics:
Now, let's take a look at the summary statistics that was outputted by the model again.

Summary Statistic
Summary Statistic
F-statistic

You were introduced to a new term named F-statistic and Prob(F-statistic). Now, recall that in the last segment, you did a hypothesis test for beta to determine whether or not the coefficient 
β1 outputted by the model was significant or not. Now, F-statistic is similar in the sense that now instead of testing the significance of each of the betas, it tells you whether the overall model fit is significant or not. This parameter is examined because many a time it happens that even though all of your betas are significant, but your overall model fit might happen just by chance.

 The heuristic is similar to what you learnt in the normal p-value calculation as well. If the 'Prob (F-statistic)' is less than 0.05, you can conclude that the overall model fit is significant. If it is greater than 0.05, you might need to review your model as the fit might be by chance, i.e. the line may have just luckily fit the data. In the image above, you can see that the p-value of the F-statistic is 1.52e-52  which is practically a zero value. This means that the model for which this was calculated is definitely significant since it is less than 0.05.

This will be more appreciable when you study multiple linear regression since there you have a lot of betas for the different predictor variables and thus it is very helpful in determining if all the predictor variables together as a whole are significant or not or simply put, it tells you whether the model fit as a whole is significant or not. 

R-squared

Like you studied earlier as well, R-squared value tells you exactly how much variance in the data has been explained by the model. In our case, the R-squared is about 0.816 which means that the model is able to explain 81.6% of the variance which is pretty good.

Coefficients and p-values:

The p-values of the coefficients (in this case just one coefficient for TV) tell you whether the coefficient is significant or not. In this case, the coefficient of TV came out to be 0.0545 with a standard error of about 0.002. Thus, you got a t-value of 24.722 which lead to a practically zero p-value. Hence, you can say that your coefficient is indeed significant. 

Apart from this, the summary statistics outputs a few more metrics which are not of any use as of now. But you'll learn about some more of them in multiple linear regression.
Let's see how the model actually looks by plotting it.


You visualised the predicted regression line on the scatter plot of the training data which is one of the things you should do as a part of model evaluation.

Q1)
Viewing the coefficients
Which of the following commands can be used to view 
β0 and β1 once you have fitted the line using statsmodels? The name of your linear regression object is lr. (More than one option(s) may be correct.)

lr.params
Feedback:
Yes! You can view both the parameters using this simple command.

lr .summary()
Feedback:
The summary() function also outputs the values of coefficients and hence, can be used to view these values as well.


Q2)
Summary Statistics
Suppose you built a linear regression model in which the target variable is 'Scaled Pressure' which is being predicted with the help of the feature variable 'Frequency', and you got the following summary statistics of the model that you built.


Looking at the summary statistic, what can be said about the significance of the overall model fit?

The overall model fit is significant

Feedback:
Correct! If you look at the summary statistics, you can see that the F-statistic has a value of 270.2 which is a very high value and this, the Prob(F-statistic) is 5.93e-56 (as shown in the table) which is a practically zero value. Hence, the value of less than 0.05 which means that the overall model fit is significant.

Q3)

Summary Statistics
Let's take a look at the summary statistics you saw in the last question again.

What can you say about the significance of the coefficient the variable 'Frequency'?

 Ans:
 Correct! If you look at the table, you can see that the p-value for the coefficient of the variable 'Frequency' is 0 which is a low value and hence, the coefficient is significant.

 Q4)

 Summary Statistics
Finally, looking at the following summary statistics, what can you say about the extent of fit, i.e. the variance explanatory power of the model?

Correct! Look at the summary statistics closely. The value of R-squared is 0.153. Recall that R-squared varies from 0 to 1 wherein a value of 0 implies that none of the variance in the data is explained and a value of 1 implies that all of the variance in the data is explained. Can you answer the question now? Hence, a value of 0.153 is a low value of R-squared which in turn implies that the model doesn't explain much variance present in the data.


**Residual Analysis and Predictions**
Now that you have built the linear model, you can move ahead with the next steps. Now, building the model on the train set has two parts: fitting a line and validating the assumptions of regression.

 

Recall that one of the assumptions that you studied was that the error terms should be normally distributed with mean equal to 0. So once you have built the model, you'd need to verify if your model is not violating this assumption. And doing this is fairly simple: you just plot a histogram of the error terms to check whether they are normally distributed. And another assumption was that the error terms should be independent of each other. Again for this, you need to plot the error terms, this time with either of X or y to check for any patterns. Let's see all of this in action in the following video.

The residuals are normally distributed, and there are no visible patterns in the error terms (except for the fact that the variance seems to be increasing a little for the higher values). So, this model fit looks good. Let's go ahead and make predictions on the test set.

You will use the 'predict()' function present in 'statsmodels.api' for the same.

Note : At 8:41, the value of R-squared should be between 0 to 1.

Q1)

Residual Analysis
Plotting a histogram of the residuals helps you determine: (More than one option may be correct.).


Correct! A histogram of the error terms is plotted to check if the error terms are normally distributed.
Correct! While the histogram tells you whether the error terms are normally distributed or not, it also helps you check if they are centred around zero which is quite crucial.

Q2)


Model Comparison using RMSE
You fit two linear regression models for the same data, where the first one gives an RMSE value of 3.78, and the second returns a value of 6.33. Which of these is a better model?


Yes! Recall that RMSE (Root Mean Squared Error) is a metric that tells you the deviation of the predicted values by a model from the actual observed values. So, since it is a sort of error term, it is better to have a low RMSE.

Notice that the RMSE for the first model is lesser than the second model. So naturally, this model would be better than the other.


Q3)
Model Comparison using R-squared
For the two linear regression models mentioned in the last question, the R-squared values in the train and test sets are as follows:

Model	R-squared (on train set)	R-squared (on test set)
First Model	0.85	0.61
Second Model	0.74	0.72


Ans:


The second model

✓ Correct
Feedback:
The second model seems to be a better one because even though the R-squared for the first model is quite good on the train set, but it drops tremendously in the test set. This simply means that the first model is not generalising well whereas in the case of the second model we have decent and close values of R-squared for both the train and test sets.



Coming up
So, overall, your model fit seems to be doing a good job. These were the steps for fitting a line using 'statsmodels'. In the next segment, you will look at another library called 'SKLearn', which can be used to perform linear regression as well.


**Linear Regression using SKLearn**

So far, you have worked with the 'statsmodels' package. This is a great package if you want to fit a line and draw inferences as well. 
But many times, you may not be interested in the statistics part of linear regression. You might just want to fit a line through the data and make predictions. 
In such cases, you can use 'SKLearn', which involves lesser hassle than 'statsmodels'. Also, the industry standard as to what package should be used varies widely. Some companies prefer statsmodels whereas some others prefer SKLearn, so it is better for you if you know about both of these packages.


SKLearn is a ‘lighter’ version of the linear regression packages. The two simple steps to fit a line using SKLearn are as follows:

 

from sklearn.linear_model import LinearRegression

lm = LinearRegression()   # Create a linear regression object
lm.fit(X_train, y_train)



Q1) Parameters in SKLearn
Which of these commands will give you the value of  slope for the fitted model?

Correct! lm.coeff_ gives you the value of β1 which is the slope of the fitted line.




Summary
In this session, you built a simple linear regression model in Python using the advertising dataset. You also saw some more theoretical aspects in between. Here's a brief of what you learnt in this session.

A quick recap of simple linear regression
Assumptions of simple linear regression
Linear relationship between X and y.
Normal distribution of error terms.
Independence of error terms.
Constant variance of error terms.
Hypothesis testing in linear regression
To determine the significance of beta coefficients.
H0:β1=0;
HA:β1≠0. 
T-test on the beta coefficient.
t score=^βiSE(^βi).
Building a linear model
OLS (Ordinary Least Squares) method in statsmodels to fit a line.
Summary statistics
F-statistic, R-squared, coefficients and their p-values.
Residual Analysis
Histogram of the error terms to check normality.
Plot of the error terms with X or y to check independence.
Predictions
Making predictions on the test set using the 'predict()' function.
Linear Regression using SKLearn
A second package apart from statsmodels for linear regression.
A more hassle-free package to just fit a line without any inferences.


Rahim has also answered some common doubts surrounding linear regression in the following additional segment. You can go through the segment here. This part has also been included in the notebook provided to you at the beginning of the session.

 

Coming Up
In the next session, you will move from simple linear regression to multiple linear regression wherein you will use multiple independent variables to explain a single dependent variable.


---
Practice:
Q1)
Best fit line
Which method is used to find the best fit line for linear regression?

Feedback:
Correct! The least square error which gives the sum of the square of differences between the actual values and the predicted values (using the regression line fitted) is used to determine the best fit line. The key to getting the best fit line is minimising these errors.

Q2) Hypothesis Test
In order to reject the Null Hypothesis used in linear regression, the p-value of βi should be?

Feedback:
The Null hypothesis in the case of linear regression is:

βi=0

So if your p-value is less than 0.05, you can reject the Null Hypothesis and conclude that the coefficient is significant.

Also, note that 0.05 is just a conventional cutoff. Based on your requirement, you can set the cutoff to anything; it might be a higher value like 0.1 or a lower value like 0.02.

Q3) Residual Analysis
Which of the following is true regarding residual in linear regression?

Correct! Recall that one of the assumptions of linear regression was, the residuals are normally distributed around zero, i.e. their mean is equal to zero. Hence, the sum of residuals should also be zero.

Q4) Significance of Fit
Which of the following parameters is used to determine the overall significance of a model fit?

F-statistic

Feedback:
Correct! In order to determine the overall model fit, the F-statistic is used. 

The basic idea behind the F-test is that it is a relative comparison between the model that you've built and the model without any of the coefficients except for 
β0 . If the value of the F-statistic is high, it would mean that the Prob(F) would be low and hence, you can conclude that the model is significant. On the other hand, if the value of F-statistic is low, it might lead to the value of Prob(F) being higher than the significance level (taken 0.05, usually) which in turn would conclude that the overall model fit is insignificant and the intercept-only model can provide a better fit.

Q5) Heteroscedasticity
What does it imply if your linear regression model is said to be heteroscedastic?


Correct! Recall that one of the major assumptions of simple linear regression was that the error terms should be constant, i.e. homoscedastic. Heteroscedastic is just the opposite of that.


Q6) t-value
Which if the following expression gives the correct relationship between a beta coefficient and its t-value?

t=βiSE(βi)

✓ Correct
Feedback:
Correct! The t-value for a particular coefficient is given by the coefficient divided by its standard error.


Q7) Linear Regression in Python
Which of the following built-in packages are widely or popularly used to build a linear regression model in Python? Multiple options can be correct.


statsmodels.api

✓ Correct
Feedback:
Correct! statsmodels.api can be used to build a linear regression model in Python.

SKLearn

✓ Correct
Feedback:
Correct! SKLearn can be used to build a linear regression model in Python.


SciPy

✓ Correct
You missed this!
Feedback:
Reference :

https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.linregress.html 


Q8) Generic steps in building a linear regression model
Which of the following step(s) are required to fit a straight line through a set of data points using statsmodels.api? Multiple options can be correct.


sm.add_constant(X)

✓ Correct
Feedback:
Correct! The two simple steps involved to fit a line are:

sm.add_constant(X)

sm.OLS(y, X).fit()

sm.OLS(y, X).fit()

✓ Correct
Feedback:
Correct! The two simple steps involved to fit a line are:

sm.add_constant(X)

sm.OLS(y, X).fit()



Graded:
---
Q1)
Strength of Relationship
Which of the following is indicative of a strong relationship between X and y?


The correlation coefficient between X and y is 0.95
Feedback:
The correlation coefficient specifies how strong is the relationship between two variables. And in this case, the value is 0.95 which is quite high indicating a strong relationship between X and y.

Q2) Hypothesis Testing for Betas
In order to determine whether the coefficient in a simple linear regression model is significant or not, which Null Hypothesis do we propose?


β1=0

✓ Correct
Feedback:
Correct! The Null Hypothesis in the case of simple linear regression is indeed:

β1=0

This is kept so because in case that the Null hypothesis is rejected, you can conclude that 
β1 is not zero and the coefficient is significant, but if we fail to reject the Null Hypothesis, the coefficient is deemed insignificant.

Q3) 

Overall Model Fit
Which metric is used to determine the significance of the overall model fit?



F-statistic

✓ Correct
Feedback:
Correct! The F-statistic tells whether the overall model fit is significant or not.

Q4)

Fitting a line using statsmodels
Why do you add a constant to the train set using the sm.add_constant() command, when you’re fitting a line using statsmodels?

statsmodels fits a line passing through the origin by default.

✓ Correct
Feedback:
Correct! By default, statsmodels fits a line passing through the origin, i.e. it doesn't fit an intercept. Hence, you need to use the command 'add_constant' so that it also fits an intercept.

Q5)

Correlation
The correlation coefficient between the age of a person and their IQ test score is found to be -1.0087.
What can you conclude from this?

None of the above

✓ Correct
Feedback:
The correlation coefficient should be in the range [1,-1]. A value beyond this range indicates an error in measurement.