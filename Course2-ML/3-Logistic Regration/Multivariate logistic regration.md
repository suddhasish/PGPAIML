Introduction
Welcome to the session on 'Multivariate Logistic Regression (Model Building)'.

Just like when you’re building a model using linear regression, one independent variable might not be enough to capture all the uncertainties of the target variable in logistic regression as well. So in order to make good and accurate predictions, you need multiple variables and that is what we’ll study in this session.

Before starting with multivariate logistic regression, the first question that arises is, “Do you need any extensions while moving from univariate to multivariate logistic regression?” Recall the equation used in the case of univariate logistic regression was:


P = 1 / 1 + e^−(β0+β1X)
The above equation has only one feature variable 
X, for which the coefficient is 
β1. Now, if you have multiple features, say n, you can simply extend this equation with ‘n’ feature variables and ‘n’ corresponding coefficients such that the equation now becomes:

P = 1/ 1+e^−(β0+β1X1+β2X2+β3X3+...+βnXn)

Recall this extension is similar to what you did while moving from simple to multiple linear regression.

# In this session
In this session, you will learn how to:

- Build a multivariate logistic regression model in Python
- Conduct feature selection for logistic regression using:
    * Automated methods: RFE -Recursive Feature Elimination
    * Manual methods: VIF and p-value check
We will use the ‘Telecom Churn’ dataset in this session to build a model using multivariate logistic regression. This will involve all the familiar steps such as:

Data cleaning and preparation
    * Preprocessing steps
    * Test-train split
    * Feature scaling
    * Model Building using RFE, p-values and VIFs
Apart from the familiar old steps, you’ll also be introduced to something known as a confusion matrix and you’ll also learn how the accuracy is measured for a logistic regression model.

# Multivariate Logistic Regression - Telecom Churn Example

Let's now look at the process of building a logistic regression model in Python.

You will be looking at the telecom churn prediction example. You will use 21 variables related to customer behaviour (such as the monthly bill, internet usage etc.) to predict whether a particular customer will switch to another telecom provider or not (i.e. churn or not).


Problem Statment
You have a telecom firm which has collected data of all its customers. The main types of attributes are:

Demographics (age, gender etc.)
Services availed (internet packs purchased, special offers taken etc.)
Expenses (amount of recharge done per month etc.)
 

Based on all this past information, you want to build a model which will predict whether a particular customer will churn or not, i.e. whether they will switch to a different service provider or not. So the variable of interest, i.e. the target variable here is ‘Churn’ which will tell us whether or not a particular customer has churned. It is a binary variable - 1 means that the customer has churned and 0 means the customer has not churned.

 
Please find the churn dataset here.

Please find the internet_data dataset here.

Please find the customer_data dataset here.

Please find the data dictionary here 

Please find the Logistic Regression code file here

So, here’s what the data frame churn_data looks like:

Data Frame 1:  churn_data
Data Frame 1: churn_data
Also, here’s the data frame customer_data:

Data Frame 2: customer_data
Data Frame 2: customer_data
Lastly, here’s the data frame internet_data:

Data Frame 3: internet_data
Data Frame 3: internet_data
Now, as you can clearly see, the first 5 customer IDs are exactly the same for each of these data frames. Hence, using the column customer ID, you can collate or merge the data into a single data frame. We'll start with that in the next segment.

# Data Cleaning and Preparation - I


Before you jump into the actual model building, you first need to clean and prepare your data. 
As you might have seen in the last segment, all the useful information is present in three dataframes with ‘Customer ID’ being the common column. 
So as the first step, you need to merge these three data files so that you have all the useful data combined into a single master dataframe. 


Now that you have the master dataframe in place, and you have also performed a binary mapping for few of the categorical variables, the next step would be to create dummy variables for features with multiple levels. The dummy variable creation process is similar to what you did in linear regression as well. 

 

Note : At 3:32, the correct should be telecom['TotalCharges'] = pd.to_numeric(telecom['TotalCharges'],errors='coerce') at cell number 19.


So the process of dummy variable creation was quite familiar, except this time, you manually dropped one of the columns for many dummy variables. For example, for the column ‘MultipleLines’, you dropped the level ‘MultipleLines_No phone service’ manually instead of simply using ‘drop_first = True’ which would’ve dropped the first level present in the ‘MultipleLines’ column. The reason we did this is that if you check the variables ‘MultipleLines’ using the following command, you can see that it has the following three levels:
 

So the process of dummy variable creation was quite familiar, except this time, you manually dropped one of the columns for many dummy variables. For example, for the column ‘MultipleLines’, you dropped the level ‘MultipleLines_No phone service’ manually instead of simply using ‘drop_first = True’ which would’ve dropped the first level present in the ‘MultipleLines’ column. The reason we did this is that if you check the variables ‘MultipleLines’ using the following command, you can see that it has the following three levels:
 

Now, out of these levels, it is best that you drop ‘No phone service’ since it isn’t of any use because it is anyway being indicated by the variable ‘PhoneService’ already present in the dataframe.

To simply put it, the variable ‘PhoneService’ already tells you whether the phone services are availed or not by a particular customer. In fact, if you check the value counts of the variable 'PhoneService', following is the output that you get:



You can see that the level 'No' appears 682 times which is exactly equal to the count of the level 'No phone service' in 'MultipleLines'.
You can see that the dummy variable for this level, i.e. 'MultipleLines_No phone service' is clearly redundant since it doesn't contain any extra information and hence, to drop it is the best option at this point. You can verify it similarly for all the other categorical variables for which one of the levels was manually dropped.


Q1)

This happens because the level ‘No internet service’ just tells you whether a user has internet service or not. Now because the number of users not having an internet service is the same, the count of this level in all of these variables will be the same. You can also check the value counts of the variable ‘InternetService’ and you’ll see that the output you’ll get is:

Fiber Optic    3096
DSL                   2421
No                      1526

Coincidence? No! 
This information is already contained in the variable ‘InternetService’ and hence, the count will be the same in all the variables with the level ‘No internet service’. This is actually also the reason we chose to drop this particular level.



# Data Cleaning and Preparation - II
You’ve merged your dataframes and handled the categorical variables present in them. But you still need to check the data for any outliers or missing values and treat them accordingly. Let's get this done as well.

you saw that one of the columns, i.e. 'TotalCharges' had 11 missing values. Since this isn't a big number compared to the number of rows present in a dataset, we decided to drop them since we won't lose much data.

Now that you have completely prepared your data, you can start with the preprocessing steps. As you might remember from the previous module, you first need to split the data into train and test sets and then rescale the features. So let’s start with that.


This is part of feature scaling , learn mean and standard deviation from train set and transform on test set as we dont want to learn anything new from test set just want to apply learning from test set.

The 'fit_transform'  command first fits the data to have a mean of 0 and a standard deviation of 1, i.e. it scales all the variables using:

Xscaled=(X−μ)/σ

Now, once this is done, all the variables are transformed using this formula. Now, when you go ahead to the test set, you want the variables to not learn anything new. You want to use the old centralisation that you had when you used fit on the train dataset. And this is why you don't apply 'fit' on the test data, just the 'transform'.

# Building your First Model

Let’s now proceed to model building. Recall that the first step in model building is to check the correlations between features to get an idea about how the different independent variables are correlated. In general, the process of feature selection is almost exactly analogous to linear regression.

NOTE: Pearson coefficient isn't preferred for binary variables. For binary variables, there are other criteria that work best.An in-depth discussion on this is beyond the scope of this course.

 

Looking at the correlations certainly did help, as you identified a lot of features beforehand which wouldn’t have been useful for model building. Recall that Rahim dropped the following features after looking at the correlations from the heatmap:

MultipleLines_No
OnlineSecurity_No
OnlineBackup_No
DeviceProtection_No
TechSupport_No
StreamingTV_No
StreamingMovies_No
 

If you look at the correlations between these dummy variables with their complimentary dummy variables, i.e. ‘MultipleLines_No’ with ‘MultipleLines_Yes’ or ‘OnlineSecurity_No’ with ‘OnlineSecurity_Yes’, you’ll find out they’re highly correlated. Have a look at the heat map below:

If you check the highlighted portion, you’ll see that there are high correlations among the pairs of dummy variables which were created for the same column. For example, ‘StreamingTV_No’ has a correlation of -0.64 with ‘StreamingTV_Yes’. So it is better than we drop one of these variables from each pair as they won’t add much value to the model. The choice of which of these pair of variables you desire to drop is completely up to you; we’ve chosen to drop all the 'Nos' because the 'Yeses' are generally more interpretable and easy-to-work-with variables.

Now that you have completed all the pre-processing steps, inspected the correlation values and have eliminated a few variables, it’s time to build our first model. 


So you finally built your first multivariate logistic regression model using all the features present in the dataset. This is the summary output for different variables that you got:

In this table, our key focus area is just the different coefficients and their respective p-values. As you can see, there are many variables whose p-values are high, implying that that variable is statistically insignificant. So we need to eliminate some of the variables in order to build a better model.

 

We'll first eliminate a few features using Recursive Feature Elimination (RFE), and once we have reached a small set of variables to work with, we can then use manual feature elimination (i.e. manually eliminating features based on observing the p-values and VIFs).


Feature Elimination using RFE
You built your first model in the previous segment. Based on the summary statistics, you inferred that many of the variables might be insignificant and hence, you need to do some feature elimination. Since the number of features is huge, let's first start off with an automated feature selection technique (RFE) and then move to manual feature elimination (using p-values and VIFs) - this is exactly the same process that you did in linear regression.

 

So let's start off with the automatic feature selection technique - RFE.

 

Note : At 0:51, the comment should be " running RFE with 15 variables as output " instead of " running RFE with 13 variables as output ".


Let's summarise the steps you just performed one by one. First, you imported the logistic regression library from sklearn and created a logistic regression object using:

from sklearn.linear_model import LogisticRegression
logreg = LogisticRegression()

Then you run an RFE on the dataset using the same command as you did in linear regression. In this case, we choose to select 15 features first (15 is, of course, an arbitrary number).


from sklearn.feature_selection import RFE
rfe = RFE(logreg, 15)             # running RFE with 15 variables as output
rfe = rfe.fit(X_train, y_train)

RFE selected 15 features for you and following is the output you got:

[('tenure', True, 1),
 ('PhoneService', True, 1),
 ('PaperlessBilling', True, 1),
 ('MonthlyCharges', False, 6),
 ('TotalCharges', True, 1),
 ('SeniorCitizen', True, 1),
 ('Partner', False, 8),
 ('Dependents', False, 4),
 ('Contract_One year', True, 1),
 ('Contract_Two year', True, 1),
 ('PaymentMethod_Credit card (automatic)', True, 1),
 ('PaymentMethod_Electronic check', False, 3),
 ('PaymentMethod_Mailed check', True, 1),
 ('gender_Male', False, 9),
 ('InternetService_Fiber optic', True, 1),
 ('InternetService_No', True, 1),
 ('MultipleLines_Yes', True, 1),
 ('OnlineSecurity_Yes', True, 1),
 ('OnlineBackup_Yes', False, 2),
 ('DeviceProtection_Yes', False, 7),
 ('TechSupport_Yes', True, 1),
 ('StreamingTV_Yes', True, 1),
 ('StreamingMovies_Yes', False, 5)]


 You can see that RFE has eliminated certain features such as 'MonthlyCharges', 'Partner', 'Dependents', etc.

 

We decided to go ahead with this model but since we are also interested in the statistics, we take the columns selected by RFE and use them to build a model using statsmodels using:

 

X_train_sm = sm.add_constant(X_train[col])
logm2 = sm.GLM(y_train,X_train_sm, family = sm.families.Binomial())
res = logm2.fit()


Here, you use the GLM (Generalized Linear Models) method of the library statsmodels. 'Binomial()' in the 'family' argument tells statsmodels that it needs to fit a logit curve to a binomial data (i.e. in which the target will have just two classes, here 'Churn' and 'Non-Churn').

 

Now, recall that the logistic regression curve gives you the probabilities of churning and not churning. You can get these probabilities by simply using the 'predict' function as shown in the notebook.

 

Since the logistic curve gives you just the probabilities and not the actual classification of 'Churn' and 'Non-Churn', you need to find a threshold probability to classify customers as 'churn' and 'non-churn'. Here, we choose 0.5 as an arbitrary cutoff wherein if the probability of a particular customer churning is less than 0.5, you'd classify it as 'Non-Churn' and if it's greater than 0.5, you'd classify it as 'Churn'. The choice of 0.5 is completely arbitrary at this stage and you'll learn how to find the optimal cutoff in 'Model Evaluation', but for now, we'll move forward with 0.5 as the cutoff.

 # Confusion Matrix and Accuracy
You chose a cutoff of 0.5 in order to classify the customers into 'Churn' and 'Non-Churn'. Now, since you're classifying the customers into two classes, you'll obviously have some errors. The classes of errors that would be there are:

'Churn' customers being (incorrectly) classified as 'Non-Churn'
'Non-Churn' customers being (incorrectly) classified as 'Churn'
 

To capture these errors, and to evaluate how well the model is, you'll use something known as the 'Confusion Matrix'. A typical confusion matrix would look like the following:

Confusion Matrix
Confusion Matrix
This table shows a comparison of the predicted and actual labels. The actual labels are along the vertical axis, while the predicted labels are along the horizontal axis. Thus, the second row and first column (263) is the number of customers who have actually ‘churned’ but the model has predicted them as non-churn.

 

Similarly, the cell at second row, the second column (298) is the number of customers who are actually ‘churn’ and also predicted as ‘churn’.

Note that this is an example table and not what you'll get in Python for the model you've built so far. It is just used an example to illustrate the concept.

 Now, the simplest model evaluation metric for classification models is accuracy - it is the percentage of correctly predicted labels. So what would the correctly predicted labels be? They would be:

'Churn' customers being actually identified as churn
'Non-churn' customers being actually identified as non-churn.
As you can see from the table above, the correctly predicted labels are contained in the first row and first column, and the last row and last column as can be seen highlighted in the table below:

Correctly Predicted Labels
Correctly Predicted Labels
Now, accuracy is defined as:

 
Accuracy=Correctly Predicted LabelsTotal Number of Labels

Hence, using the table, we can say that the accuracy for this table would be:
 

Accuracy=1406+2981406+143+263+298≈80.75

Now that you know about confusion matrix and accuracy, let's see how good is your model built so far based on the accuracy. But first, answer a couple of questions.

So using the confusion matrix, you got an accuracy of about 80.8% which seems to be a good number to begin with. The steps you need to calculate accuracy are:

Create the confusion matrix
Calculate the accuracy by applying the 'accuracy_score' function to the above matrix
The code used to do this was:

 

# Create confusion matrix
confusion = metrics.confusion_matrix(y_train_pred_final.Churn, y_train_pred_final.predicted)

# Calculate accuracy
print(metrics.accuracy_score(y_train_pred_final.Churn, y_train_pred_final.predicted))


To summarise, you basically performed an iterative manual feature elimination using the VIFs and p-values repeatedly. You also kept on checking the value of accuracy to make sure that dropping a particular feature doesn't affect the accuracy much. 

This was the set of 15 features that RFE had selected which we began with:

And this is the final set of features which you arrived at after eliminating features manually:

Final Set of Features after Manual Feature Elimination
Final Set of Features after Manual Feature Elimination
As you can see, we had dropped the features 'PhoneService' and 'TotalCharges' as a part of manual feature elimination.

 

Interpreting the Model
Refer to the above image, i.e. the final summary statistics after completing manual feature elimination. Now suppose you are a data analyst working for the telecom company, and you want to compare two  customers, customer A and customer B. For both of them, the value of the variables tenure, PhoneService, Contract_One year, etc. are all the same, except for the variable PaperlessBilling, which is equal to 1 for customer A and 0 for customer B.

In other words, customer A and customer B have the exact same behaviour as far as these variables are concerned, except that customer A opts for paperless billing, and customer B does not. Now use this information to answer the following questions.



Multivariate Logistic Regression (Variable Selection)
Based on the above information, what can you say about the log odds of these two customers? 

PS: Recall the log odds for univariate logistic regression was given as:

l
n
(
P
1
−
P
)
=
β
0
+
β
1
X

Hence, for multivariate logistic regression, it would simply become:

l
n
(
P
1
−
P
)
=
β
0
+
β
1
X
1
+
β
2
X
2
+
β
3
X
3
+
.
.
.
+
β
n
X
n



log odds (customer A) > log odds (customer B)

✓ Correct
Feedback:
Recall the log odds are just the linear term present in the logistic regression equation. Hence, here we have 13 variables, so the log odds will be given by:

l
n
(
P
1
−
P
)
=
β
0
+
β
1
X
1
+
β
2
X
2
+
β
3
X
3
+
.
.
.
+
β
13
X
13

Now, for the two customers, all beta and all x values are the same, except for 
X
2
 (the variable for paperless billing), which is equal to 1 for customer A and 0 for customer B. 

Hence, the value will exceed by the coefficient of 'PaperlessBilling' which is 0.3367.

Basically, for customer A, this term would be = 0.3367 * 1

And for customer B, this term would be = 0.3367 * 0


Q2) 

Multivariate Logistic Regression (Variable Selection)
Now, what can you say about the odds of churn for these two customers?


For customer A, the odds of churning are higher than for customer B

✓ Correct
Feedback:
Recall that in the last question, you were told that log odds for customer A are higher than those for customer B. So, the odds of churning for customer A are also higher than the odds of churning for customer B. This is because, as the number increases, its log increases and vice versa.

Q3) Multivariate Logistic Regression - Log Odds
Now, suppose two customers, customer C and customer D, are such that their behaviour is exactly the same, except for the fact that customer C has OnlineSecurity, while customer D does not. What can you say about the odds of churn for these two customers?


For customer C, the odds of churning are lower than for customer D

✓ Correct
Feedback:
Recall that the log odds for customer C will differ from those for customer D, by a margin of 
β
O
n
l
i
n
e
S
e
c
u
r
i
t
y
. Now since in this case, this coefficient is negative (-0.3739), this means that the log odds of customer C will be 0.3739 less than that of customer D. Since the log odds of customer C are lower, naturally, the actual odds for C would also be lower.


Now that we have a final model, we can begin with model evaluation and making predictions. We'll start doing that in the next session.

---
Summary
In this session, you learnt how to build a multivariate logistic regression model in Python. The equation for multivariate logistic regression is basically just an extension of the univariate equation:

 

P=11+e−(β0+β1X1+β2X2+β3X3+...+βnXn)
 
The example used for building the multivariate model in Python was the telecom churn example. Basically, you learnt how Python can be used to decide the probability of a customer churning based on the value of 21 predictor variables such as monthly charges, paperless billing, etc.

First, the data was imported, which was present in 3 separate csv files. After creating a merged master data set, one that contains all 21 variables, data preparation was done, which involved the following steps:
Missing value imputation
Outlier treatment
Dummy variable creation for categorical variables
Test-train split of the data
Standardisation of the scales of continuous variables

After all of this was done, a logistic regression model was built in Python using the function GLM() under statsmodel library. This model contained all the variables, some of which had insignificant coefficients. Hence, some of these variables were removed first based on an automated approach, i.e. RFE and then a manual approach based on VIF and p-value.

Apart from this, you also learnt about confusion matrix and accuracy and saw how accuracy was calculated for a logistic regression model.

Confusion Matrix
Given the following confusion matrix, calculate the accuracy of the model.

Actual/Predicted	Nos	Yeses
Nos	1000	50
Yeses	250	1200


---
Feedback:
Correct! 

Recall that the formula for accuracy is given as - 

Accuracy=Correctly
Predicted LabelsTotal Number of Labels

Here, the number of correctly predicted labels is = 1000 + 1200 = 2200.

And the total number of labels is = 1000 + 250 + 50 + 1200 = 2500

Hence, you have - 

Accuracy=2200/2500=0.88=88%

--------------

To find the person who is most likely to like the show, you can use log odds. Recall the log odds is given by:

ln(P1−P)=β0+β1X1+β2X2+β3X3+...+βnXn

Here, there are five variables for which the coefficients are given. Hence, the log odds become:

ln(P1−P)=0.47X1−0.45X2+0.39X3−0.23X4+0.55X5

As you can see, we have ignored the 
β0 since it will be the same for all the three consumers. Now, using the values of the 5 variables given, you get - 

(Log Odds)Reetesh=(0.47×1)−(0.45×0)+(0.39×0)−(0.23×0)+(0.55×1)=1.02

(Log Odds)Kshitij=(0.47×1)−(0.45×1)+(0.39×1)−(0.23×0)+(0.55×1)=0.96

(Log Odds)Shruti=(0.47×0)−(0.45×1)+(0.39×0)−(0.23×1)+(0.55×1)=−0.13

As you can clearly see, the log odds of Reetesh is the highest, hence, the odds of Reetesh liking the show is the highest and hence, he is most likely to like the new show, Sacred Games.




