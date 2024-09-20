# Introduction
Welcome to the session on ‘Multiple Linear Regression in Python’. In the last session, you learnt about the various theoretical aspects of multiple linear regression. Now, let’s move on to building a multiple linear regression model in Python.

 

In this session
You will learn the generic steps that are required to build a multiple linear regression model. You will build this model for a housing dataset and predict the price of a house using the various potential predictor variables provided. You will first read and visualise your dataset and then prepare your data for building a linear model. This will include dealing with categorical variables, adding dummy variables, and scaling. You will then start building the model with a bottom-up approach, i.e., you will start with one variable and keep on adding more. Once all the variables have been added, you will perform a manual feature elimination and move on to the residual analysis and predictions, as usual. In the end, you will solve the same problem using RFE.

 

Guidelines for in-module questions
The in-video and in-content questions for this module are not graded. The graded questions are given in a separate segment at the end of the module. These questions will adhere to the following guidelines:

# Reading and Understanding the Data
Linear regression is used in various fields such as real estate, telecom, e-commerce, etc. to build predictive models. Let's look at one such example from the real estate industry. Here, you will predict the price of a house on the basis of some predictor variables, such as floor area, number of bedrooms, parking space, etc.

 

Problem Statement:

Consider that a real estate company has the data of real estate prices in Delhi. 
The company wants to optimise the selling price of the properties, based on important factors such as area, bedrooms, parking, etc.

 

Essentially, the company wants:

To identify the variables affecting house prices, e.g., area, number of rooms, bathrooms, etc.
To create a linear model that quantitatively relates house prices with variables, such as the number of rooms, area, number of bathrooms, etc.
To know the accuracy of the model, i.e. how well do these variables predict the house prices
Please find the Housing dataset here and the Multiple Linear Regression notebook here.


Now that you’ve read and inspected the data, let’s move on to visualising it. This will help in interpreting the data well and identifying the variables that can turn out to be useful in building the model.

That was all about visualising the numerical variables. You might have noticed that there are a few categorical variables present in the dataset as well. Let’s visualise them too, using boxplots.

Note : At 1:47, For second box plot, top horizontal line is representing max values while bottom horizontal line is representing min values.

Note : At 3:53, 20 is the width and 12 is the height.

 

Coming up
In the next segment, you will do the data preparation, which is an important step before model building.


** We need to Map all all categorical variable with 2 values to to 1 and  0 

# List of variables to map

varlist =  ['mainroad', 'guestroom', 'basement', 'hotwaterheating', 'airconditioning', 'prefarea']

# Defining the map function
def binary_map(x):
    return x.map({'yes': 1, "no": 0})

# Applying the function to the housing list
housing[varlist] = housing[varlist].apply(binary_map)


You have successfully handled the categorical variables with two levels. 


But one of the columns – 'furnishingstatus' – has three levels. Here, you need to perform dummy encoding.

# Let's drop the first column from status df using 'drop_first = True'

status = pd.get_dummies(housing['furnishingstatus'], drop_first = True)

***
Mapping Variables
After you performed binary encoding of the variable ‘MaritalStatus’ with, ‘Married’ corresponding to 1 and ‘Unmarried’ corresponding to 0, you found out that the mean of the variable ‘MaritalStatus’ was 0.6. What does this statement indicate?

60% of the people on the list are married.

✓ Correct
Feedback:
Notice that when you perform a binary encoding, the only values present in the variable are 0 and 1. So if you calculate the mean, it is only the 1s which will contribute towards it. Since the value '1' corresponds to 'Married', a mean of 0.6 indicates that 60% of the people in the list are married

**Initial Steps**
Before model building, you first need to perform the test-train split and scale the features.

 
Scaling of variables is an important step because, as you may have noticed, the variable ‘area’ is on a different scale with respect to all other numerical variables, which take very small values. 
Also, the categorical variables that you encoded earlier take either 0 or 1 as their values. 
Hence, it is important to have everything on the same scale for the model to be easily interpretable.

In the next video, you will learn the rescaling and splitting the dataset.


---
**Scaling:**
You have seen the two popular rescaling methods- 
1. Min-Max scaling 
2. and Standardisation (mean=0 and sigma=1).
The advantage of Standardisation over the other is that it doesn't compress the data between a particular range as in Min-Max scaling. 
This is useful, especially if there are extreme data point (outlier). Now, let's rescale and fit the data.


Now that you have prepared the data and are done with the test-train split, 
let’s prepare a heat map and take a look at the correlations between the variables.

---
plt.figure(figsize = (16, 10))
sns.heatmap(df_train.corr(), annot = True, cmap="YlGnBu")
plt.show()


---
**Building the Model - I(Forward Selection)**
Now that everything is in place, let's build the model. You will follow a bottom-up approach for this, i.e., you will start by building the model with just one variable. Hence, the choice of this variable becomes very crucial. Let’s see which variable turns out to be ‘The Chosen One’.

import statsmodels.api as sm

# Add a constant
X_train_lm = sm.add_constant(X_train[['area']])

# Create a first fitted model
lr = sm.OLS(y_train, X_train_lm).fit()


Even though ‘area’ is the most correlated variable, it could explain only 28% of the variance. After that, we added 'bathroom' as it had the second highest correlation with the target variable. Then the model was able to explain 50% of the variance. 
# Build a linear model

import statsmodels.api as sm
X_train_lm = sm.add_constant(X_train_lm)

lr = sm.OLS(y_train, X_train_lm).fit()

lr.params

Coming up
Adding two more variables has improved the model. From an adjusted R-squared value of 28%, it has moved to 50%. In the next segment, you will proceed with improving the model further.

**Building the Model - II ( bottom-up approach)**

The bottom-up approach was just to give you an idea of how the parameters change when the number of variables is increased.
More generally, you first build a model using all  and then try to improve the model by dropping some of them.

Let’s now build a model with all the available variables in the next video.


Elimination based on VIF
Suppose the VIFs obtained for five different variables are as follows:

X1	7.12
X2	5.53
X3	5.01
X4	3.45
X5	2.68

Assuming that you’re dropping variables only on the basis of VIF and a VIF > 5 is not acceptable, which of these variables will you definitely drop?

Ans:
X1
Feedback:
Correct. It is always advisable that you drop variables one by one. Now, this variable definitely has a high VIF and needs to be dropped. The other two variables X2 and X3 also have a VIF > 5, but it might happen that after you drop X1, their VIF values will drop. So never drop more than one variable at a time.


Coming up
Now that we seem to have a fair model, in the next segment, let's perform the final steps - analyse the residual terms and predict the price.



**Residual Analysis and Predictions**
$$/$$
Before making the predictions, you need to be certain that the model is reliable. To that end, you need to first perform a residual analysis of the error terms and then move on to making the predictions on the test set; and finally, evaluate the model based on the predictions.

 

In the next video, you will learn about the residual analysis.

Now that the model building is done, let’s go ahead and make inferences on the model.



NOTE : There is a inappropriate change in the code output @07:04. We are working to fix this issue, In the meantime we request you to learn the process of performing the analysis and implement it yourself for better understanding.

 

Let's summarize what you have learned in this session. 

 

Note : The correct equation for price (constant term is missing in Jupyter Notebook)

𝑝𝑟𝑖𝑐𝑒=0.236×𝑎𝑟𝑒𝑎+0.202×𝑏𝑎𝑡ℎ𝑟𝑜𝑜𝑚𝑠+0.11×𝑠𝑡𝑜𝑟𝑖𝑒𝑠+0.05×𝑚𝑎𝑖𝑛𝑟𝑜𝑎𝑑+0.04×𝑔𝑢𝑒𝑠𝑡𝑟𝑜𝑜𝑚+0.0876×ℎ𝑜𝑡𝑤𝑎𝑡𝑒𝑟ℎ𝑒𝑎𝑡𝑖𝑛𝑔+0.0682×𝑎𝑖𝑟𝑐𝑜𝑛𝑑𝑖𝑡𝑖𝑜𝑛𝑖𝑛𝑔+0.0629×𝑝𝑎𝑟𝑘𝑖𝑛𝑔+0.0637×𝑝𝑟𝑒𝑓𝑎𝑟𝑒𝑎−0.0337×𝑢𝑛𝑓𝑢𝑟𝑛𝑖𝑠ℎ𝑒𝑑+0.0428


Derived Variables
List four derived variables from the housing dataset that you think can be created in order to get a better model. (Note that this is subjective and adding a derived feature does not necessarily improve the model.)

1. bathrooms/bedrooms
2. area/stories
3. parking/bedrooms
4. area/bedrooms

Coming up
In the next segment, you will build a model using recursive feature elimination (RFE), which is an automated technique.


# Variable Selection using RFE

Even though the housing dataset doesn’t have many variables and you can easily select the relevant features manually, it is important to learn to use certain automated techniques as well.

Let’s see Rahim rebuild another model for the housing dataset using RFE.

Please find the Housing dataset here and the Multiple Linear Regression Using RFE notebook here.


In order to use RFE, you need to use SKLearn instead of statsmodels. Let’s go ahead and create a linear model using SKLearn to perform RFE.

1st we need to use sklearn RFE to get column with high significance in automated fasion then we need to apply stats model on top of it.


Q1) Residuals
In regression analysis, which of the statements is true?

Now that the features have been selected and the model is built, let's do the residual analysis and make the final predictions.

1. he mean of residuals is always equal to zero.
 

✓ Correct
Feedback:
When a model gives you a “best fit” line, by design it is made such that the mean of all residuals is always zero. 
2. The sum of residuals is always equal to zero.
 

✓ Correct
Feedback:
When a model gives you a “best fit” line, by design it is made such that the sum of all residuals is always zero. 


Q2) Linear regression
Which of the following is incorrect about linear regression?

Linear regression assumes that the data points are not independent (i.e. One observation might be affected by another).

✓ Correct
Feedback:
Linear regression assumes that the data points are independent.
 

 Q3) Overfitting
State True or False:

Overfitting leads to a very high value of R-squared, which is misleading since the model is not actually a good predictor.

Ans:

True

✓ Correct
Feedback:
Overfitting causes the model to almost memorize the data. This reduces the distance between predicted and actual values in the training set. However, this could make the model less accurate on new data, i.e., the model memorises the data instead of recognizing the pattern that the data is following.


Q4) R-squared
Which of the following will help you in effectively comparing models (built on the same dataset) with different numbers of features?

R-squared-adjusted

✓ Correct
Feedback:
This will take number of features into account and give you a fair idea of how many features the model should have.

Q5) Overfitting
Assume that a model has zero training error. i.e. it has completely memorised the training data(a case of overfitting). Which of the following statements is definitely true in this case:


None of the above

✓ Correct
Feedback:
Due to overfitting, it is highly likely that you will have high prediction error on the test set. This would be the case more often than not. But there can be exceptions hence such a statement cannot be made for sure. 
 

 Q6) Imputing categorical variables
Consider the following dataset:

   sepal-length  sepal-width  petal-length  petal-width        class
0           5.1          3.5           1.4          0.2  Iris-setosa
1           4.9          3.0           1.4          0.2  Iris-setosa
2           4.7          3.2           1.3          0.2  Iris-setosa
3           4.6          3.1           1.5          0.2  Iris-setosa
4           5.0          3.6           1.4          0.2  Iris-setosa
Consider that the categorical column/variable has missing values, which metric would you impute the missing values with?

ANS:

Feedback:
 The category column has categorical values. Try to remember how categorical values are imputed. Here, the numbers (1,2,3,4,5) represent categories. A median value might not be the best representation of the general population. It would just represent the mid-value of the dataset and you cannot impute all missing values with a median.


Mode

✓ Correct
Feedback:
Categorical values are generally imputed with the mode as it represents the value that is the most common for the given column.


---
Graded:

Q1)

Elimination based on p-values
Suppose you're trying to predict the gross collection of a movie based on the following five factors: 'Budget', 'Average Critic Score', 'Facebook Likes', 'Number of Tweets', and 'Number of Screens'.

You obtained the following p-values for the five variables after fitting a regression line. Assuming you're only using p-value as a criteria to drop the variables and a p-value > 0.05 is not acceptable, which of these variables do you think is not significant in the prediction of gross collections and should be definitely dropped? Only one option is correct.

Budget	0.03
Average Critic Review	0.21
Facebook Likes	0.11
Number of Tweets	0.32
Number of Screens	0.01
 

Number of Tweets

✓ Correct
Feedback:
Yes! As you can see, the p-value of 'Number of Tweets' is very high and thus, this variable is insignificant. Now, there are other variables in the list which also have a high p-value but we don't drop these simultaneously as it might happen that dropping 'Number of Tweets' might reduce the p-value of the other variables and make them significant.

Q2)

Scaling Variables
Which of the following is/are true regarding the scaling of variables? More than one option(s) may be correct.

Ans:

Scaling should be done after the test-train split.

✓ Correct
Feedback:
Correct! Scaling should always be done after the test-train split since you don't want the test dataset to learn anything from the train data. So if you're performing the test-train split earlier, the test data will then have information regarding the data like the minimum and maximum values, etc.


Standardised scaling will affect the values of dummy variables but MinMax scaling will not.

✓ Correct
Feedback:
MinMax scaling scales in such a way that all the values lie between 0 and 1 using the formula:

x−min(x)/max(x)−min(x)

So if you have dummy variables, which can only take the values 0 and 1, you can notice that for the case of zero, the variable remains zero and for the case of 1, the variable remains 1.

On the other hand, the standard scaler scales in such a way that the mean of the dataset becomes zero and standard deviation becomes one. So this will clearly distort the values of the dummy variables since some of the variables will become negative.

Q3)
Multiple Linear Regression
Consider you are performing multiple linear regression where X1 and X2 are independent variables and Y is the dependent variable. What can you say about the coefficient of X1 and value of y in the regression equation? 

y=β0+β1∗X1+β2∗X2

Ans:


The predicted value of Y increases by 
β1 for a unit increase in X1, given X2 does not change.

✓ Correct
Feedback:
Consider the value of X1 changes from 0 to 1 and the value of X2 stays as 0 or a constant. Then, the value of Y would have changed by 
β1 units given beta2 and X2 are constants.

Q4) Rsq-Adjusted
In the R-squared Adjusted metric, R-squared is “adjusted” or modified according to:

Ans:

Number of predictors

✓ Correct
Feedback:
In the R-squared Adjusted formula, you can see the term ‘k’ in the denominator, where ‘k’ refers to the number of predictors or features in the model.


Sample size

✓ Correct
Feedback:
In the R-squared Adjusted formula, you can see the term ‘n’ in both numerator and denominator, where ‘n’ refers to sample size.