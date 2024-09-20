# Introduction: Univariate Logistic Regression

Welcome to the session on 'Univariate Logistic Regression'.

In this session, you will learn a few basic concepts related to logistic regression. Broadly speaking, the topics that will be covered in this session are:

- Binary classification
- Sigmoid function
- Likelihood function
- Building a logistic regression model in Python

Odds and log odds

You will learn about all these concepts through a univariate logistic regression example. Also, if these terms sound a little alien to you right now, you don’t need to worry. By the time you are done with this module, you will be well-versed in the terms of odds and log odds!


unlike Linear regration, Logistic regration helps to classify in diffrent category.

# Binary Classification
The most common use of logistic regression models is in binary classification problems. 
So, let’s hear from Prof. Dinesh what a binary classification problem is.

Model output is 2 possible output in example loan default or not, email is spam or ham 

By looking into dataset there is a chance that we are doing wrong classification if we solely treat this problem based on cutoff.

Because some of the reading like 195 is very close to cutoff value 210 can cause detection of false positive diabetic for normal person with high blood suger.


# Sigmoid Curve

In the last section, you saw what a binary classification problem is, and then you saw an example of a binary classification problem, where a model is trying to predict whether a person has diabetes or not based on his/her blood sugar level. You saw how using a simple boundary decision method would not work in this case.

Now, let’s hear from Prof. Dinesh on how the primitive binary classification model you saw earlier can be modified to make it more useful.


So, to recap, since the sigmoid curve has all the properties you would want — extremely low values in the start, extremely high values in the end, and intermediate values in the middle — it’s a good choice for modelling the value of the probability of diabetes.

 
y= P(Diabetes)= 1 / 1 + e ^ −(β0+β1x) Here, let’s say you take β0 = -15 and β1 = 0.065. Now, what will be the probability of diabetes for a patient with sugar level 220?

= 0.332

So now we have verified, with actual values, that the sigmoid curve actually has the properties we discussed earlier, i.e. extremely low values in the start, extremely high values in the end, and intermediate values in the middle.

However, you may be wondering — why can’t you just fit a straight line here? This would also have the same properties — low values in the start, high ones towards the end, and intermediate ones in the middle.

The main problem with a straight line is that it is not steep enough. In the sigmoid curve, as you can see, you have low values for a lot of points, then the values rise all of a sudden, after which you have a lot of high values. In a straight line though, the values rise from low to high very uniformly, and hence, the “boundary” region, the one where the probabilities transition from high to low is not present.


# Finding the Best Fit Sigmoid Curve - I

So, in the previous lecture, you saw what a sigmoid function is and why it is a good choice for modelling the probability of a class. Now, in this section, you will learn how you can find the best fit sigmoid curve. In other words, you will learn how to find the combination of β0 and β1 which fits the data best.

So, by varying the values of β0 and β1, you get different sigmoid curves. Now, based on some function that you have to minimise or maximise, you will get the best fit sigmoid curve.

Before you move on to that, here’s the interactive app used by Prof. Dinesh in the video. You can use it and see for yourself how the curve changes when the values of 
β0 and β1 are changed.

 
 So, the best fitting combination of 
β0 and β1 will be the one which maximises the product:

(1−P1)(1−P2)(1−P3)(1−P4)(1−P6)(P5)(P7)(P8)(P9)(P10)

This product is called the likelihood function. It is the product of:


[(1−Pi)(1−Pi)------ for all non-diabetics --------] * [(Pi)(Pi) -------- for all diabetics -------]

So, say that for the ten points in our example, the labels are a little different, somewhat like this:

Point no.	1	2	3	4	5	6	7	8	9	10
Diabetes	no	no	no	yes	no	yes	no	yes	yes	yes


In this case, the likelihood would be equal to 
(1−P1)(1−P2)(1−P3)(1−P5)(1−P7)(P4)(P6)(P8)(P9)(P10)

Q1) 
Likelihood
Now, let’s say that for the ten points in our example, the labels are as follows:

Point no.	1	2	3	4	5	6	7	8	9	10
Diabetes	no	no	no	yes	no	yes	yes	yes	yes	yes
In this case, the likelihood would be equal to:

(1−P1)(1−P2)(1−P3)(1−P5)(P4)(P6)(P7)(P8)(P9)(P10)

Feedback:
Recall that likelihood is the product of 
(1−Pi) for all non-diabetic patients and 
(Pi) for all diabetic patients. Hence, the likelihood is given by 
(1−P1)(1−P2)(1−P3)(1−P5), (all non-diabetic patients) multiplied by (P4)(P6)(P7)(P8)(P9)(P10) (all diabetic patients).


# Finding the Best Fit Sigmoid Curve - II

In the previous lecture, you understood what a likelihood function is. To recap, the likelihood function for our data is 
(1−P1)(1−P2)(1−P3)(1−P4)(1−P6)(P5)(P7)(P8)(P9)(P10) . The best fitting sigmoid curve would be the one which maximises the value of this product.

So, let’s hear from Prof. Dinesh on how this best fitting sigmoid curve can be found.
If you had to find 
β0 and β1  for the best fitting sigmoid curve, you would have to try a lot of combinations, unless you arrive at the one which maximises the likelihood. This is similar to linear regression, where you vary  
β0 and β1 until you find the combination that minimises the cost function. 
Note : At 1:21, the final answer of Likelihood should be 0.00002122 instead of 1.75*10^(-5).

In the interactive app given below, you can try a few combinations yourself and see how the likelihood varies with betas.

So, just by looking at the curve here, you can get a general idea of the curve’s fit. Just look at the yellow bars for each of the 10 points. A curve that has a lot of big yellow bars is a good curve. For example, this curve is not a good fit:

Clearly, this curve is a better fit. It has many big yellow bars, and even the small ones are reasonably large. Just by looking at this curve, you can tell that it will have a high likelihood value.


# Odds and Log Odds
In the previous segment, you saw that by trying different values of 
β0 and β1, you can manipulate the shape of the sigmoid curve. At some combination of 
β0 and β1, the 'likelihood' (length of yellow bars) will be maximised.


Logistic Regression - Optimisation Methods (Optional)
The question is - how do you find the optimal values of β0 and  β1
 such that the likelihood function is maximized? The optimisation methods used to do that are an optional part of the course (maximum likelihood estimation, or MLE). You can study the optimisation techniques in detail in a separate optional session.


- Introduction to maximum likelihood estimation (MLE)
- MLE for continuous (normal) and discrete probability distributions  (Bernoulli distribution and logistic regression)
- Optimising MLE cost functions using gradient descent 
- Alternate optimisation methods: Newton-Raphson method 

You may study the optional session either along with this module or sometime later; this will not interrupt your flow of study for this module (there is no deadline for the optional session). There are no prerequisites for the optional session apart from the previous module.

# Logistic Regression in Python
Let's now look at how logistic regression is implemented in python.

In python, logistic regression can be implemented using libraries such as SKLearn and statsmodels, though looking at the coefficients and the model summary is easier using statsmodels. 


You can find the optimum values of 
β0 and β1
 using the python code given below. Please download and run the code and observe the values of the coefficients (you may also want to visualise them on the interactive app on the previous page, though note that β0 can only take integer values in the app, so you can use -13 or -14 approximately).

Please note that you will study a detailed Python code for logistic regression in the next module. This Python code has been run so as to find the optimum values of 
β0 and β1 so that we can first proceed with the very important concept of Odds and Log Odds.

Please find the Finding Optimum Betas using python file here.

The summary of the model is given below:

In the summary shown above, 'const' corresponds to 
β0 and Blood Sugar Level, i.e. 'x1' corresponds to 
β1. So,β0 = -13.5 and β1 = 0.06.


# Odds and Log Odds
So far, you’ve seen this equation for logistic regression:
 

P= 1/ 1+e^−(β0+β1x)
 

Recall that this equation gives the relationship between P, the probability of diabetes and x, the patient’s blood sugar level.


While the equation is correct, it is not very intuitive. In other words, the relationship between P and x is so complex that it is difficult to understand what kind of trend exists between the two. If you increase x by regular intervals of, say, 11.5, how will that affect the probability? Will it also increase by some regular interval? If not, what will happen?

So, clearly, the relationship between P and x is too complex to see any apparent trends. However, if you convert the equation to a slightly different form, you can achieve a much more intuitive relationship. In the next video, let’s hear from Prof. Dinesh on how that can be done.

 [Note: By default, for this course, if the base of the logarithm is not specified, take it as e. So,  
log(x)=loge(x)

 
 So, now, instead of probability, you have odds and log odds. Clearly, the relationship between them and x is much more intuitive and easy to understand.

For example, if you increase x by regular intervals of, say, 11.5, how will that affect the log odds?


Log Odds
So, let’s say that the equation for the log odds is:

ln(P1−P)=−13.5+0.06x

For x = 220, the log odds are equal to -13.5+(0.06*220) = -0.3. For x = 231.5, log odds are equal to: 0.4



Please note that, in the video above, at 3:05, instead of 2.94, it should have been 2.96

 

So, the relationship between x and probability is not intuitive, while that between x and odds/log odds is. This has important implications. Suppose you are discussing sugar levels and the probability they correspond to. While talking about 4 patients with sugar levels of 180, 200, 220 and 240, you will not be able to intuitively understand the relationship between their probabilities (10%, 28%, 58%, 83%). However, if you are talking about the log odds of these 4 patients, you know that their log odds are in a linearly increasing pattern (-2.18, -0.92, 0.34, 1.60) and that the odds are in a multiplicatively increasing pattern (0.11, 0.40, 1.40, 4.95, increasing by a factor of 3.55).

 

Hence, many times, it makes more sense to present a logistic regression model’s results in terms of log odds or odds than to talk in terms of probability. This happens especially a lot in industries like finance, banking, etc.

That's the end of this session on univariate logistic regression. You studied logistic regression, specifically, the sigmoid function, which has this equation:

P=11+e−(β0+β1x) 

However, this is not the only form of equation for logistic regression. If you wish to learn about what the other forms are, you can go through them here. For this course, you do not need to know about the other forms, as we will not be discussing them anywhere.

 

 

# Summary
You first learnt what a binary classification is. Basically, it is a classification problem in which the target variable has only 2 possible values.

You then went through the diabetes example in detail, wherein you tried to predict whether a person has diabetes or not based on that person’s blood sugar level.

You saw why a simple boundary decision approach does not work very well for this example. It would be too risky to decide the class blatantly on the basis of the cutoff because, especially in the middle, the patients could belong to any class — diabetic or non-diabetic.

Hence, you learnt that it is better to talk in terms of probability. One such curve which can model the probability of diabetes very well is the sigmoid curve.

Its equation is given by the following expression:

 

P(Diabetes)=11+e−(β0+β1x)
 

Then, you learnt that in order to find the best-fit sigmoid curve, you need to vary 
β0 and β1 until you get the combination of beta values that maximises the likelihood. For the diabetes example, the likelihood is given by the expression:

Likelihood=(1−P1)(1−P2)(1−P3)(1−P4)(P5)(1−P6)(P7)(P8)(P9)(P10) 

It is the product of:
 
[(1−Pi)(1−Pi) ------ for all non-diabetics --------] * [(Pi)(Pi) -------- for all diabetics -------]

This process, where you vary the betas until you find the best fit curve for the probability of diabetes, is called logistic regression. 

After this, you saw a simpler way of interpreting the equation for logistic regression. You saw that the following linearised equation is much easier to interpret:

 
ln(P1−P)=β0+β1x

The left-hand side of this equation is what is called log odds. Basically, the odds of having diabetes (P/1-P), indicate how much likelier a person is to have diabetes than to not have it. For example, a person for whom the odds of having diabetes are equal to 3, is 3 times more likely to have diabetes than to not have it. In other words, P(Diabetes) = 3 * P(No diabetes).

You also saw how odds vary with variation in x. Basically, with every linear increase in x, the increase in odds is multiplicative. For example, in the diabetes case, after every increase of 11.5 in the value of x, the odds are approximately doubled, i.e. they increase by a multiplicative factor of about 2.