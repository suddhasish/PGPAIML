# Introduction
Welcome to the module on ‘Linear Regression’.

 

In this module, you will start off with a quick introduction to three machine learning techniques — regression, classification, and clustering. Then, you will go deeper into one of the most important regression models in machine learning — Linear Regression.

You will learn primarily about the following two types of linear regression models:

Simple linear regression

Multiple linear regression

In this session
You will get a quick introduction to machine learning models. You will also learn about the basics of simple linear regression, how to find the best-fitted line for a model and all the various parameters associated with it.


The broad agenda for this session is as follows:

- Introduction to machine learning

- Supervised and unsupervised learning methods

- The linear regression model

- Residuals

- Residual sum of squares (RSS) and R² (R-squared)

R² value is given by 1 - (RSS / TSS)


# Introduction to Machine Learning


In the previous course, you learnt data preparation, which is the third step of the CRISP-DM framework.
Following the same CRISP-DM framework, now let's move to the fourth and the most interesting stage, called modelling.


Q1) Supervised and Unsupervised Learning
Identify what type of problem this is.

You have the past data of two cricket teams on the performance of the teams based on different parameters and the match results. You have to predict which team will win.
Ans:
You have the data of the past few years to train your model on. Since you know the results of different games based on different performance parameters, it would be a supervised learning problem — more specifically, a classification problem since your output variable (i.e. the name of the team) is categorical.

Q2) Supervised and Unsupervised Learning
Identify what type of problem this is.

You feed a large collection of spam emails to the learning model to identify the different sub-groups of these spam mails. No labels are presents in the data set.
Ans:
This can be addressed using unsupervised learning as there are no labels assigned to your data set and they need to be identified.
q3)
Supervised and Unsupervised Learning
Identify what type of problem this is.

Consider a large data set of the medical profiles of cancer patients. This data contains no labels for the medical profiles of the cancer patients. The model has to learn whether there might be different groups of such patients for which separate treatments might be tailored.

Feedback:
This can be addressed using an unsupervised learning algorithm, in which you group patients into different clusters.

# Regression Line

In the previous segment, you learnt about the different types or classifications of machine learning models. Let’s now talk about one of the classification which is Regression.

In the next video, you will learn about the types of regression and linear equations.


Read this link to revise the physical significance of an equation of a straight line, and also to understand how to find the slope and intercept of a straight line from its graph.

Answer the following questions in the context of the straight-line plot given below.

Since you now know about the equation of a straight line, let’s look at the general equation of a straight line which is fitted during simple linear regression.


**A simple linear regression model attempts to explain the relationship between a dependent and an independent variable using a straight line.**
**The independent variable is also known as the predictor variable. And the dependent variables are also known as the output variables.**


In the next segment you will learn about the best-fit line. There can be many regression lines but we need the optimized line to predict the values.This is done using some mathematical techniques.


**Best- Fit Line:**

In regression, there is a notion of a best-fit line — the line which fits the given scatter-plot in the best way. Let’s look at how you can define the notion of a best-fit line.

Let’s reiterate what you have learnt till now:

You started with a scatter plot to check the relationship between sales and marketing budget.

You found residuals and RSS for any given line passing through the scatter plot.

Then you found the equation of the best-fit line by minimising the RSS and found the optimal value of β₀ and β₁.

Q1)
Least Squares Regression Line
The coefficients of the least squares regression line are determined by the Ordinary Least Squares method — which basically means minimising the sum of the squares of the:
Ans:
y-coordinates of actual data - y-coordinates of predicted data
Feedback:
The Ordinary Least Squares method has the criterion of the minimisation of the sum of squares of residuals. Residuals are defined as the difference between the y-coordinates of actual data and the y-coordinates of predicted data.

Q2)

Best Fit Regression Line
What is the main criterion used to determine the best-fitting regression line?

he line that minimises the sum of squares of distances of points from the regression line


Feedback:
The criterion is given by the Ordinary Least Squares (OLS) method, which states that the sum of squares of residuals should be minimum. This is explained by this option.



Since now you know that the best-fit line is obtained by minimising a quantity called Residual Sum of Squares (RSS), this is the best time to be introduced to what is known as the cost function.



----
Gradient Descent
Gradient Descent is an optimisation algorithm which optimises the objective function (for linear regression it's cost function) to reach to the optimal solution.

 

You can learn about the cost function and ways to optimise the cost function (minimisation or maximisation). The topic is covered in detail as the part of the optional session; you may access the content using this link. Since the session is optional, you may visit this as per your convenience, but we strongly suggest you go through it as Gradient Descent will also be used for Logistic Regression and even Neural Networks.

Let’s now see a demonstration of obtaining a best-fit line and finding out the RSS for the marketing spend vs sales example in Excel.


--
Best- Fit Line
In regression, there is a notion of a best-fit line — the line which fits the given scatter-plot in the best way. Let’s look at how you can define the notion of a best-fit line.

Let’s reiterate what you have learnt till now:

You started with a scatter plot to check the relationship between sales and marketing budget.

You found residuals and RSS for any given line passing through the scatter plot.

Then you found the equation of the best-fit line by minimising the RSS and found the optimal value of β₀ and β₁.

Since now you know that the best-fit line is obtained by minimising a quantity called Residual Sum of Squares (RSS), this is the best time to be introduced to what is known as the cost function.

 

Gradient Descent
Gradient Descent is an optimisation algorithm which optimises the objective function (for linear regression it's cost function) to reach to the optimal solution.

You can learn about the cost function and ways to optimise the cost function (minimisation or maximisation).
The topic is covered in detail as the part of the optional session; you may access the content using this link. 
Since the session is optional, you may visit this as per your convenience, but we strongly suggest you go through it as Gradient Descent will also be used for Logistic Regression and even Neural Networks.
----------

**Strength of Simple Linear Regression**
------
After determining the best fit line, there are a few critical questions you need to answer, such as:

How well does the best-fit line represent the scatter-plot?

How well does the best-fit line predict the new data?

Are the above questions answered well by the RSS? Attempt these two questions on your own before getting the answers from the professor in the following lecture.

Q1)
RSS - Residual Sum of Squares
In the previous example of marketing spend (in lakhs) and sales amount (in crores), let’s assume you get the same data in different units — marketing spend (in lakhs) and sales amount (in dollars). 
Do you think there will be any change in the value of RSS due to change in units in this case (as compared to the value calculated in the Excel demonstration)?

Yes, value of RSS would change because units are changing.

Feedback:
The RSS for any regression line is given by this expression: 
∑(yi−yipred)2.
 RSS is the sum of the squared difference between the actual and the predicted values, and its value will change if the units change since it has units of ​
y2​. For example, (140 rupees - 70 rupees)^2 = 4900, whereas (2 USD - 1 USD)^2 = 1. So value of RSS is different in both the cases because of different units.


You can play with the interactive graphic below and look at how the position of the regression line and the values of RSS and TSS change with a change in the values of β₀ and β₁.

Let’s go back to our Excel demonstration and see how you can find out the TSS and then R² for the same example for which we had performed regression.

You can download the Excel sheet used in the demonstration for your reference.




Comprehension:

The plot below represents a scatter-plot of 2 variables X and Y, with the Y variable being dependent on X. Let’s assume the line with the equation Y = X/2 + 3 plotted in the graph represents the best-fit line. This is the same line whose equation you found earlier.

You can find the value of the residual for each point, e.g. for x = 2, the residual would be 5 - 4 = 1.

Answer the following questions in order to consolidate your learning about RSS and R².
Q1)

Residual Sum of Squares (RSS)
Find the value of RSS for this regression line.

Ams:
6.25
✓ Correct
Feedback:
The residuals for all 5 points are -0.5, 1, 0, -2, 1. The sum of squares of all 5 residuals would be 0.25 + 1 + 0 + 4 + 1 = 6.25

Q2)

Total Sum of Squares (TSS)
Find the value of TSS for this regression line.

Ans:
14
✓ Correct
Feedback:
The average of y-value for all data points (3 + 5 + 5 + 4 + 8)/5 = 25/5 = 5. So 
y−¯y term for each data point would be -2, 0, 0, -1, 3. So, the squared sum of these terms would be 4 + 0 + 0 + 1 + 9 = 14.

Q3)
R²
The RSS for this example comes out to be 6.25 and the TSS comes out to be 14.

What would be the R² for this regression line?

Ans:

1 - (6.25/14)
✓ Correct
Feedback:
R² value is given by 1 - (RSS / TSS). So, in this case, R² value would be 1 - (6.25 / 14).

**RSE**
Apart from R², there is one more quantity named RSE (Residual Square Error) which is linked to RSS. Let’s see what that is.



Summary
Here's a brief summary of what you learned in this session: 

Machine learning models can be classified into following two categories on the basis of learning algorithm:
Supervised learning method: Past data with labels is available to build the model
Regression: The output variable is continuous in nature
Classification: The output variable is categorical in nature
Unsupervised learning method: Past data with labels are not available
Clustering: No pre-defined notion of labels is there
Past data set is divided into two parts during supervised learning method: 
Training data  is used for the model to learn during modelling
Testing data is used by the trained model for prediction and model evaluation
Linear regression models can be classified into two types depending upon the number of independent variables: 
Simple linear regression: When the number of independent variables is 1
Multiple linear regression: When the number of independent variables is more than 1
The equation of the best fit regression line Y = β₀ + β₁X can be found by minimising the cost function (RSS in this case, using the Ordinary Least Squares method) which is done using the following two methods:
Differentiation
Gradient descent method
The strength of a linear regression model is mainly explained by R²,  where R² = 1 - (RSS / TSS)
RSS: Residual Sum of Squares
TSS: Total Sum of Squares




Correlation Coefficient
The value of the correlation coefficient will always be:


Between -1 and 1

✓ Correct
Feedback:
Correct! The value of the correlation coefficient always lies between -1 and 1, where a negative value implies a negative correlation, a positive value shows a positive correlation, and a zero value shows no correlation.


R-squared
The strength of a linear regression line is determined by the value of the R-squared. If this value is found to be 0, what does it imply?


No variance in the data is being explained by the fitted line.

✓ Correct
Feedback:
Correct! The value of R-squared lies between 0 and 1, where 1 implies that the variance in the data is being explained by the model, and 0 implies that none of the variance values is being explained by the model. Obviously, it is very difficult to achieve either of the extreme values.



Correlation
Suppose that you run a linear regression on the data, where you have X as the independent variable and y as the target variable. You find that the correlation between y and X is -0.92. What can you say in this situation?
X and y are strongly related.

✓ Correct
Feedback:
Correct! The absolute value of the correlated coefficient is very high. The negative sign just implies that X and y are negatively correlated. Hence, they have a very strong negative correlation.



Machine Learning Models
A Singapore-based startup Healin launched an app called JustShakeIt, which enables a user to send an emergency alert to emergency contacts and/or caregivers simply by shaking the phone with one hand. The program uses a machine learning algorithm to distinguish between actual emergency shakes and everyday jostling, using data with labels.

What kind of problem is this?



Supervised learning-Classification

✓ Correct
Feedback:
The algorithm has to distinguish between actual emergency shakes and everyday jostling. Here, your output variable has predefined labels (shake/jostle), which are categorical in nature. So, this is a supervised learning-classification problem.



Coefficients of Regression Equation
The independent variable X from a linear regression is measured in miles. If you convert it to kilometres (keeping the unit of the dependent variable Y the same), how will the slope coefficient change? (Note: 1 mile = 1.6 km)

Ans:
It will get divided by 1.6.

✓ Correct
Feedback:
In the linear regression equation, X gets multiplied by 1.6 with no change in Y. So, the slope will be divided by 1.6.

Q3)
Strength of the Regression Model
You want to find the linear relation between the number of X-ray machines purchased at one time and the cost per machine. The following data has been obtained on the same:

X: Number of machines purchased	1	3	6	10	15
Y: Cost per widget (in thousand rupees)	89	85	79	73	64
Suppose the R² between X and Y is 0.87. Which of the following conclusions can you draw from this?


The linear relation between X and Y is strong, and their correlation will be negative.

✓ Correct
Feedback:
A higher value of R² means a strong linear relation. As Y is decreasing with the increasing value of X, you can conclude that their correlation will be negative.