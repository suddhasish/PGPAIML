Introduction
As discussed in the previous session, the linear regression model assumes a linear relationship between the response and predictor variables. But in some cases, the true relationship between the response and the predictors may be nonlinear. In this session, we will present a very simple method to directly extend the linear model to accommodate nonlinear relationships. But before that, we need to identify the nonlinearity present in the data.

In this session

We will try to answer the following questions:

- How to identify non-linearity in data especially in the presence of multiple variables in the model?

- What can we do when the relationship between the dependent and independent variable(s) is nonlinear?



# Identifying Nonlinearity in Data

The linear regression model assumes that there is a linear relationship between the predictors and the response variable. However, if the true relationship is nonlinear, then virtually all of the conclusions that we draw from the fit do not hold much credibility. In addition, the prediction accuracy of the model can be reduced significantly. In the forthcoming video, Anjali explains how we can identify nonlinearity in data


So, in the video, you learnt how to identify nonlinearity in data for simple linear regression and multiple linear regression: 

For Simple Linear Regression 

Plot the independent variable against the dependent variable to check for nonlinear patterns.

For Multiple Linear Regression, since there are multiple predictors, we, instead, plot the residuals versus the predicted values, 
^yi. Ideally, the residual plot will show no observable pattern. In case a pattern is observed, it may indicate a problem with some aspect of the linear model. Apart from that:

Residuals should be randomly scattered around 0.
The spread of the residuals should be constant.
There should be no outliers in the data
If nonlinearity is present, then we may need to plot each predictor against the residuals to identify which predictor is nonlinear.


# How to handle nonlinear data?
Once we have the residual plots showing nonlinearity, we might need to make some changes, either to the model or to the data. In the upcoming video, you will learn how to do that.


In the above video, you learnt that there are three methods to handle nonlinear data:

   1)  Polynomial regression

   2)  Data transformation

   3)  Nonlinear regression

In the next segment, we will deal with the first method to handle non-linearity in data that is Polynomial Regression.


# Polynomial Regression

In the forthcoming video, Anjali will explain how to identify and handle non-linear data in Python. 
This type of data can be efficiently handled by polynomial regression.

The kth-order polynomial model in one variable is given by:

y=β0+β1x+β2x2+β3x3+....++βkxk+ϵ


If 

xj = xj and j = 1, 2, ..., k, then the model is a multiple linear regression model with k predictor variables, 

x1,x2,x3,....,xk. So, the linear regression model 

y=Xβ+ϵ

includes polynomial predictors. Thus, polynomial regression can be considered an extension of multiple linear regression and, hence, we can use the same technique used in multiple linear regression to estimate the model coefficients for polynomial regression. 

In the upcoming video, Anjali will explain how to build a model using Polynomial Regression in Python.


So, in the above example, we took the square of the independent variable and fitted a linear regression model. As a result, it provided us with better results.

In the next segment, we will look at another method to handle the non-linearity present in the data.



Q1) 
Transformations
On inspection of the relationship between one predictor variable (a) and the response variable (y), you identify that the two have a cubic relationship.
In the final model, which of the following predictors would you include?

a,a2,a3

✓ Correct
Feedback:
Since this is a cubic fit, we need to include third degree of the predictor. In polynomial regression, we need to include the lower degree polynomials in the model as well. Hence, we include all three predictors as mentioned in the answer.

Q2) Polynomial Regression
For the previous question, what will be the linear regression equation?


yi=β0+β1ai+β2a2i+β3a3i+ϵi

✓ Correct
Feedback:
In polynomial regression, we need to include the lower degree polynomials in the model as well. Hence, we include all three predictors. Recall that model equation also contains the error term.


# Data Transformation

In the previous segment, you learnt about polynomial regression, which is one of the methods to handle nonlinear data. In this segment, you will learn about the other method that can be used to handle nonlinearity and still satisfy the assumptions of linear regression by transforming the data. Let’s try and understand data transformation through code in the forthcoming video.

Note: In order to explore some of the commonly seen shapes, please refer to the following [link](https://www.mathsisfun.com/sets/functions-common.html).

 

We saw in the code, that the relationship between the predictor and response variable was non-linear. We also saw that using Linear Regression did not give good results since the actual fit should not be a straight line but should instead follow the data points along the non-linear curve which here resembles a logarithmic function.

 

However, linear regression assumes that the relationship between the response and predictor variables is linear. In order to continue using the linear regression framework, we transformed the data so that the relationship does become linear.




If the residual plot indicates the presence of nonlinear relations in the data, then a simple approach is to use nonlinear transformations of the predictors. For instance, for a predictor x, these transformations can be log(x), sqrt(x), exp(x), etc., in the regression model.

 

We need to remember that although log is the most commonly used function for transformations, it is not the only one that we can use. 
There are a few other functions that we can use depending upon the shape of the data.

Let’s take a look at some of these functions. 
                                                                             
ln(y)=β0+β1x


U shape: 

We know that both the response and the predictor variables can be transformed. If the data looks something like above, then you may want to try taking a log transform of the response variable. Here, you can fit the model with ln(y) as the response variable and x as the predictor variable.

                                                                                    
y=β0+β1e−x


Sleeping u shaped:

In this case, when the y values rise quickly for smaller values of x and start flattening out for larger values of x, then we can use an exponential transformation. Fit the model with y as the response variable and 
e−x as the predictor variable. 

Note: The solid blue line is when 
β1 is less than 0 and the dotted line is when 
β1 is greater than 0. 



For more transformations, please refer to the following [link](https://online.stat.psu.edu/stat462/node/155/).


How do we decide when and what to transform?
Essentially, to handle nonlinear data, we may have to try different transformations on the data to determine a model that fits it well. Hence, we may try polynomial models or transformations of the x-variable(s) or the y-variable, or both. These transformations can be square root, logarithmic or reciprocal transformations, although this is not an exhaustive list. Generally, one of these transformations helps. In the forthcoming video, Anjali explains when and how to perform data transformation.



- Transforming y values primaryly helps handelling issue with the error term and may help with non linerarity.
- Transforming X value primaryly corrects the non-linerarity.


# Transform the predictors or the response?
When we transform the response variable, we will change both its errors and variance. 

Hence, we should transform the response variable only if the error terms are not normal or if the residuals exhibit non-constant variance, as seen in the residual plots. Transformations that can be applied on the response variable can include natural log, square root or inverse, i.e., ln(y), √y or 1/y, respectively.

 
However, if nonlinear trends are observed in the residual plots, then we should first try to transform the predictor variable(s). Despite these guidelines, the transformations may not always work. In the next segment, you will learn about Nonlinear regression.


Model Equation
If we want to fit a linear regression model between the previously mentioned predictor and the response variable, what will be the model equation?


^yi=β0+β1eai+ϵi

Feedback:
Since the relationship between a and y is exponential, after the exponential transformation of the predictor, we can use the linear regression framework to estimate the model coefficients.

# Nonlinear Regression

All of the models that we have discussed so far have been linear in terms of the parameters (i.e., linear in terms of the beta's). Nevertheless, for models in which the response variable is related nonlinearly with the parameters or the model coefficients, we use nonlinear regression. Let’s watch the forthcoming video to learn more about nonlinear regression.

So, in the equation shown in the video:

We can see clearly that the relationship between the response variable and the model coefficients is nonlinear. Here, we cannot use the linear regression framework anymore to estimate the model coefficients. Note that this is out of the scope of this module. 

Of the three models that we have discussed, polynomial regression and data transformation allow us to stay within the linear regression framework. After transforming the predictors, when we fit the model, we still check whether the model follows the assumptions so that we can trust the results that we get from the model.

It may so happen that the models built by you and by another person are different, but at the same time, they may be equally correct. What matters is that the model that you build is not very complex, it follows the assumptions of linear regression and then only, you’ll be able to make a correct inference. Please remember that data science is as much an art as it is a science. In the next segment, we will look at some of the pitfalls of linear regression.

Additional Reading:
To know more about the algorithms for nonlinear least-square estimation, you can refer to this [link](https://online.stat.psu.edu/stat462/node/204/).



# Linear Regression Pitfalls
Comprehension
When we fit a linear regression model to a particular data set, many problems may arise. Most common among these are the following:

Non-constant variance

Autocorrelation and time series issue

Multicollinearity

Overfitting

Extrapolation

In this segment, you will learn about each of these problems, and we will also discuss the methods for overcoming some of these pitfalls.

Non-constant variance

Constant variance of error terms is one of the assumptions of linear regression. Unfortunately, many times, we observe non-constant error terms. As discussed earlier, as we move from left to right on the residual plots, the variances of the error terms may show a steady increase or decrease. This is also termed as heteroscedasticity.

 

When faced with this problem, one possible solution is to transform the response Y using a function such as log or the square root of the response value. Such a transformation results in a greater amount of shrinkage of the larger responses, leading to a reduction in heteroscedasticity.

 

Autocorrelation

This happens when data is collected over time and the model fails to detect any time trends. Due to this, errors in the model are correlated positively over time, such that each error point is more similar to the previous error. This is known as autocorrelation, and it can sometimes be detected by plotting the model residuals versus time. Such correlations frequently occur in the context of time series data, which consists of observations for which measurements are obtained at discrete points in time.

 

In order to determine whether this is the case for a given data set, we can plot the residuals from our model as a function of time. If the errors are uncorrelated, then there should be no observable pattern. However, on the other hand, if the consecutive values appear to follow each other closely, then we may want to try an autoregression model. 

 

Multicollinearity

If two or more of the predictors are linearly related to each other when building a model, then these variables are considered multicollinear. A simple method to detect collinearity is to look at the correlation matrix of the predictors. In this correlation matrix, if we have a high absolute value for any two variables, then they can be considered highly correlated. A better method to detect multicollinearity is to calculate the variance inflation factor (VIF), which you studied in the Linear Regression module.

 

When faced with the problem of collinearity, we can try a few different approaches. One is to drop one of the problematic variables from the regression model. The other is to combine the collinear variables together into a single predictor. Regularization (which we will discuss in the next session) helps here as well.

 

Overfitting

When a model is too complex, it may lead to overfitting. It means the model may produce good training results but would fail to perform well on the test data. One possible solution for overfitting is to increase the amount and diversity of the training data. Another solution is regularization, which we will cover in the next session.

 

     5. Extrapolation

Extrapolation occurs when we use a linear regression model to make predictions for predictor values that are not present in the range of data used to build the model. For instance, suppose we have built a model to predict the weight of a child given its height, which ranges from 3 to 5 feet. If we now make predictions for a child with height greater than 5 feet or less than 3 feet, then we may get incorrect predictions. The predictions are valid only within the range of values that are used for building the model. Hence, we should not extrapolate beyond the scope of the model.

 

In the next session, we will learn about overfitting and techniques to reduce model complexity.