Module Overview
Welcome to the module on ‘Advanced Regression’. In the previous modules, you learnt about the principles of model selection, model simplicity and complexity, overfitting, regularization, etc., for linear data.

 
In this module
You will learn how to extend the linear regression framework to problems that are not strictly ‘linear’ and understand the differences between linear and nonlinear regression problems. We will also deal with the regularization techniques that are used to reduce overfitting in linear regression. In the forthcoming video, Anjali will give you an overview of this module.



Learning Objectives:

- Build linear regression models in the presence of non-linearity in data

- Build linear regression models in Python to handle the non-linearity present in data

- Understand and use Ridge and Lasso regularization to handle overfitting due to the increase in model complexity

- Build a regularized linear regression model in Python using both the Ridge and Lasso methods



Learning Objectives
- Build linear regression models in the presence of non-linearity in data

- Build linear regression models in Python to handle the non-linearity present in data

- Understand and use Ridge and Lasso regularization to handle overfitting due to the increase in model complexity

- Build a regularized linear regression model in Python using both the Ridge and Lasso methods

In this session:

- We will recall the basics covered in the Linear Regression module. 

- Then we will try to find the model coefficients in linear regression with the help of normal equations and matrix representations. 

- At the end, we will also discuss the assumptions for linear regression and ways to assess them using residual plots


# Linear Regression - Review

In the earlier module on linear regression, you learnt how to build simple models to solve regression problems. Now, before you build upon that learning and understand how to build regression models when there exists a nonlinear relationship between the independent and the target variable, in the forthcoming video, we will quickly review linear regression and learn about a couple of different methods to solve regression problems.

In the above video, Anjali discussed the following equations:

Simple linear regression equation

Suppose we have ‘n’ observations. Simple linear regression assumes that there is a linear relationship between the input values and the output values. Mathematically, we can express this relationship as:

                                                                        
yi=β0+β1xi+ϵi

where 
xi is the predictor value (variables that help predict the output), 
yi is the response value, 
β0 and β1  are the parameter values or the coefficients, and 
ϵi is an error or the residual. Here, the parameters are the true parameter values for the data belonging to the population with ‘n’ observations. We want to estimate these parameter values using linear regression.

 Predicted values

                                                                              
^yi=bo+b1xi

In this equation, 
bo and 
b1 are the estimated parameter values, which we obtain by fitting a linear regression line, and ^yi
 is the predicted output value after estimating the model parameters. These estimated values are not exactly equal to the true values, but are very close to them if we get a good fit.

 Residuals
                                                                                 
εi=yi−^yi
The error value or residual value for each point is the difference between the actual output (yi) and the predicted output (^yi).


Residual sum of squares (RSS) or Cost

                                      
∑ni=1ε2i=∑ni=1(yi−^yi)2=∑ni=1(yi−bo−b1xi)2

The sum of the squares of errors is considered the loss/cost function in linear regression, which has to be minimised. The entire linear regression framework is built upon the idea of getting those coefficient estimates that minimise the cost, i.e., RSS. The smaller the value of RSS, the closer is the model fit to the data.

Root mean squared error

RMSE=√∑ni=1(yi−^yi)2n

Root mean square error (RMSE) is the square root of mean squared error. Mean squared error is the variance of the residuals. RMSE tells us how close the actual data points are to predictions made by the model
 

 So, we will now jump straight into some action and build a simple linear regression model in Python. Let’s take a look at it in the next video.

 In this video, we have used scikit-learn library of Python for fitting the linear regression line. In the next segment, you will see if there are any methods for getting  those coefficient estimates which minimise the cost function.

 # Estimating Coefficients in SLR

 As we have discussed earlier, we need to minimise the residual sum of squares (RSS) to obtain the best linear regression model. For this, we need to find the optimal b0 and b1 model coefficients so that our model has the least RSS value. Let’s go ahead and watch the forthcoming video and see how we can do this.

 So, in the video, we have discussed two methods to obtain our model coefficients by minimising RSS:

Using an optimisation algorithm, such as gradient descent

Gradient descent is an iterative optimisation algorithm to find the minimum of a cost function; this means we apply a certain update rule over and over again, and following that, our model coefficients or betas would gradually improve according to our objective function.

 

To perform gradient descent, we initialise the weights to some value (e.g., all zeros) and repeatedly adjust them in the direction that decreases the cost function. We repeat this procedure until the betas converge, or stop changing much. Ultimately, the final betas would be close to the optimum. Note that in the above video, we have tried to provide an intuitive understanding of the gradient descent method. To gain a better mathematical understanding, please revise the content on gradient descent.

https://learn.upgrad.com/course/5802/segment/54830/326887/989931/4947755


Using normal equations to solve for model coefficients

Solving normal equations requires a sound knowledge of derivatives. Therefore, refer to this link to revise the basics of derivatives. In the following video, we will look at the same in detail.


In the above video, you learnt how derivatives help with calculating the value of x at which the function is at its minimum. Similarly, in normal equations, we calculate the model coefficients b0 and b1 at which our cost function, i.e., RSS, is minimum by using derivatives. In order to do this:

Take the derivative of the cost function w.r.t. b0 and b1,

Set each equation to 0 and

Solve the two equations to get the best values for the parameters b0 and b1.

Using calculus, we have calculated the model coefficients using the following formulae:

bo=¯y−b1¯x and b1=∑ni=1(x−¯x)(y−¯y) / ∑ni=1(x−¯x)2 here 
¯y and ¯x are the sample means.

Please note that we have not derived the equations here. If you wish to know how to expand the cost function and get the coefficients using partial derivatives, please go through this link.

The results computed using these normal equations and the gradient descent approach are generally the same; just the methods are different. 

Now, it's time to find out whether normal equations in Python provide us with the same answer. Let’s watch the next video and find it out with Anjali.


In the video, we saw that, the coefficients we get after applying normal equations in Python are same as we obtained from building model using scikit-learn. In next segment, we will see how we can represent the simple linear regression equation in matrix form.


# Matrix Representation for SLR

Why matrices?
You might be wondering whether there are any other representations for linear regression that can be used to further simplify the solution. In the next video, Anjali will introduce you to the matrix representation of linear regression and explain how it can be used to compute the model coefficients for linear regression models.

Note: At 02:30, the dimensions are incorrectly written as (n,1) for the model coefficient vector. It should be (2,1).

So, in the video, you saw how the complex form of simple linear regression equations is converted to its matrix equivalent. Each observation can be represented with the following set of equations for ‘n’ observations:

 

y1=β0+β1x1+ϵ1
y2=β0+β1x2+ϵ2
.
.
.
yn=β0+β1xn+ϵn


The equations above have been converted to their matrix/vector equivalent as shown below:

⎡
⎢
⎢
⎢
⎢
⎣
y1
y2
.
.
.
yn
⎤
⎥
⎥
⎥
⎥
⎦
=
⎡
⎢
⎢
⎢
⎣
1x11
x
2
.
.
.
.
.
.
1
x
n
⎤
⎥
⎥
⎥
⎦
[
β
0
β
1
]
+
⎡
⎢
⎢
⎢
⎣
ϵ
1
ϵ
2
.
.
.
ϵ
n
⎤
⎥
⎥
⎥
⎦

                                

The X matrix, i.e., the matrix with the predictors, is also known as the design matrix. Here, the first column in the design matrix is a column of 1’s for the intercept term 
β
0
 and the second column contains the predictor values. There are n rows in the matrix for ‘n’ observations. The error vector consists of residuals for each observation, which is added to the product of the design matrix and the parameter vector to obtain the response vector, Y.

 

You may want to refresh your memory of matrices by visiting the following link.

 

This matrix can be written in a very concise notation as:

Y
=
X
β
+
ϵ

 

Before delving further into the matrix representation, let's try and understand some of the benefits of using matrices:

Formulae become simpler, and more compact and readable.

Code using matrices runs much faster than explicit ‘for’ loops. 

Python libraries, such as NumPy, help us build n-dimensional arrays, which occupy less memory than Python lists and computation is also faster.

Best parameter values through normal equations using matrices
In simple linear regression, we obtained the values of 
b
0
 and 
b
1
 by solving the normal equations using basic algebra. Let us see how can we use matrices for deriving the solution for 
β
 coefficients.


Replay

Mute
Current Time 
2:55
/
Duration 
2:55
 
1x
Playback Rate

Quality Levels
Picture-in-Picture

Fullscreen
3219582
As we saw in the video, to get RSS, we multiply the error matrix by its transpose, as shown below:

Figure1:RSS
Figure1:RSS
Then, we differentiate RSS w.r.t. β and equate it to 0, as shown below:

 

Figure2:RSS
Figure2:RSS
Please note that we have skipped the differentiation step in the above derivation. It is not required to understand that here. The main objective is to understand that with simple matrix operations you can find the value of the coefficients.

 

So, this is how we get our beta coefficients for the least RSS. The same expression can be used irrespective of the number of predictors or variables that are considered in the model. For example, we can use this solution to find the coefficients for simple linear regression as:

 

Figure3:RSS
Figure3:RSS
The same equation can be used to find multiple coefficients present in Multiple Linear Regression. Now, in the forthcoming video, we will use this formula in our Python code and check whether or not we get the same solution.


Replay

Mute
Current Time 
2:31
/
Duration 
2:31
 
1x
Playback Rate

Quality Levels
Picture-in-Picture

Fullscreen
3219582
So, in the video, Anjali built a simple linear regression model on the marketing data set and verified the results obtained from the normal equations and from matrix calculations. So far, you have built and verified a simple linear regression model. Now, as you are already aware, the next step is to build multiple linear regression models. In the next segment, you will learn about multiple linear regression model.

 # Estimating Coefficients in MLR
Simple linear regression is a useful approach for predicting a response on the basis of a single predictor variable. However, in practice, we often have more than one predictor. For more predictors, the multiple linear regression model takes the form: 

                                              
yi=β0+β1xi,1+β2xi,2 +...βkxi,k + ϵi 

where k is the number of predictors in the model and i = 1 to n where n is the total number of observations. In the upcoming video, you will learn how the multiple linear regression model can be represented in matrix form.



So, in the video, Anjali explained how equations of ‘n’ observations can be converted into its matrix equivalent.

                                
⎡
⎢
⎢
⎢
⎢
⎣
y1y2...yn
⎤
⎥
⎥
⎥
⎥
⎦
=
⎡
⎢
⎢
⎢
⎢
⎣
1x1,1x1,2..
.
x1,k1x2,1x2,2...x2,k
.
.
.
.
.
.
.
.
.
.
.
.
.
.
.
1xn
,
1xn
,
2
.
.
.
xn
,
k
⎤
⎥
⎥
⎥
⎥
⎦
⎡
⎢
⎢
⎢
⎢
⎢
⎢
⎣
β0β1β2
.
.
.
βk
⎤
⎥
⎥
⎥
⎥
⎥
⎥
⎦
+
⎡
⎢
⎢
⎢
⎣
ϵ1ϵ2
.
.
.
ϵn
⎤
⎥
⎥
⎥
⎦

This matrix can be written in a very concise notation as:
                                                                             
Y=Xβ+ϵ


Here, each row in the
X matrix belongs to each of the ‘
n’ observations and each column corresponds to each predictor along with the first column of 
1’s. Since there are 
k predictors, we have 
k + 1  elements in the matrix. Finally, we add the product of the design matrix 
X and the coefficient vector to the error vector to get the 
Y vector.

In the next segment, you will learn about the assumptions of linear regression.






# Assumptions of Linear Regression

When using linear regression to model the relationship between a response variable and a predictor, we make a few assumptions. These assumptions are the essential conditions that should be fulfilled before we can draw any inferences about the model estimates or before we can use the model to make any predictions. In the next video, Anjali explains the key assumptions of linear regression.

The linear regression framework comprises certain key assumptions. Let's try and understand the importance of each of these assumptions one by one.

There is a linear relationship between X and Y

X and Y should display a linear relationship of some form; otherwise, there is no use of fitting a linear model between them.



2. Error terms are distributed normally with mean equal to 0 (not X, Y)

There is no problem if the error terms are not distributed normally if you wish to just fit a line and not make any further interpretations.

However, if you wish to draw some inferences on the model that you have built, then you need to have a notion of the distribution of the error terms. One particular repercussion if the error terms are not distributed normally is that the p-values obtained during the hypothesis test to determine the significance of the coefficients become unreliable. 

The assumption of normality is made, as it has been observed that the error terms generally follow a normal distribution with mean equal to 0 in most cases but it is necessary that the mean is 0. The only necessary condition is that the residuals are normally distributed. 


3. Error terms are independent of each other

The error terms should not be dependent upon one another (like in time-series data, where the next value is dependent upon the previous one).

4. Error terms have constant variance (homoscedasticity)

Variance should not increase (or decrease) with a change in error values.

Also, variance should not follow any pattern with a change in error terms.



You can also go through the content at this link to see what happens when the assumptions above are violated. But you will anyway get more clarity as we keep moving ahead.

We basically use the following plots, which help us assess the above assumptions qualitatively:

Residual versus prediction plot: This plot helps us detect nonlinearity, unequal error variances and outliers.

Histogram of error terms: This plot helps detect non-normality of the error values.

We worked upon the Marketing dataset which we used earlier for simple linear regression in Python. 
Let us check if the assumptions are holding true in the forthcoming video.


NOTE: @3:11 Instructor mentions that the predictions are on y-axis and residuals on the x-axis. But in the plot, it is reversed and we have predictions on the x-axis and residuals on the y axis.


In the next segment, Anjali will implement Multiple Linear Regression in Python and also do residual analysis for the same. Residual analysis will further help in checking if the assumptions of linear regression are holding true.


# Multiple Linear Regression in Python
In the forthcoming video, we implement multiple linear regression in Python on the same Marketing data but now considering all the three predictors - Radio, TV and Newspaper.

Note: At 03:54, the second coefficient is mentioned for Radio. It should be for newspaper.

Now, let us solve the same regression problem using normal equations formula with matrix representation and compare the results.


So, in the above video, Anjali built a multiple linear regression model on the marketing data set and verified the results obtained from the normal equations through matrix representation. We also did some residual analysis and verified if the assumptions of linear regression are holding true or not.


Session Summary
In the below video, we will look at the summary of the learnings from this session.



In this session, you learnt how the best-fit line can be obtained given a linear relationship between the dependent/response and the independent/predictor variable(s). Now, what if the relationship between the response and predictor variables was nonlinear? Can we still work within the linear regression framework? We will find the answer to this question in the next session.