# Introduction
In the previous sessions, you learnt about the basic concepts of hypothesis testing and learnt how to statistically test the inferences made from inferential statistics or the insights generated during EDA. You learnt how to formulate the hypotheses and then make a decision through either the critical value method or the p-value method.

In this session
You will learn how hypothesis testing is used in the industry and how the basic concepts learnt in the previous session form an important foundation of useful industry concepts such as A/B testing.

 

We will cover the following topics in this session:

- T distribution

- Two-sample mean test

- Two-sample proportion test

- A/B testing

- Industry relevance

# T Distribution
As an analyst in the industry, when you would use hypothesis testing, the standard deviation of the population would be unknown most of the times. So how would you proceed in such a scenario? Let us find out.


A t-distribution is also referred to as Student’s T distribution. A t-distribution is similar to the normal distribution in many cases; for example, it is symmetrical about its central tendency. However, it is shorter than the normal distribution and has a flatter tail, which would eventually mean that it has a larger standard deviation.


df = degree of freedom | if sample size increase degree of freedom also increases after  t(df = 30) which makes it like standard normal distribution or z distribution.

- The most important use of the t-distribution is that you can approximate the value of the standard deviation of the population (σ) from the sample standard deviation (s). 
- However, as the sample size increases more than 30, the t-value tends to be equal to the z-value.
Thus, if you want to summarise the decision-making in a flowchart, this is what you would get.

Look at the flowchart above and answer the following questions.

Type of tests
If the sample size is 10 and the standard deviation of the population is known,
which distribution should be used to calculate the critical values and make the decision during hypothesis testing?

Q1)
Standard normal distribution (z-distribution)
✓ Correct
Feedback:
Whenever the standard deviation of the population is known, you have to use z-distribution, irrespective of the value of the sample size (N).

Q2)

Type of tests
If the sample size is 10 and the standard deviation of the population is unknown, which distribution should be used to calculate the critical values and make the decision during hypothesis testing?

T distribution
Feedback:
T distribution is used whenever the standard deviation of the population is unknown and the sample size is less than 30.


Let’s look at how the method of making a decision changes if you are using the sample’s standard deviation instead of the population’s. If you recall the critical value method, the first step is as follows:

Calculate the value of Zc from the given value of α (significance level). Take it as 5% if not specified in the problem.

So, to find Zc, you would use the t-table instead of the z-table. The t-table contains values of Zc for a given degree of freedom and value of α (significance level). Zc, in this case, can also be called as t-statistic (critical).

Download the t-table given below and attempt the following questions to understand how to use the t-table to find Zc.



**Degree of freedom**
degree of freedom = sample size  -1

Q1)
t-test
You are given the standard deviation of a sample of size 25 for a two-tailed hypothesis test of a significance level of 5%.

Use the t-table given above to find the value of Zc.

Ans: 
For sample size = 25, your degrees of freedom would become 25 - 1 = 24. 
So, if you look for the value in the t-table corresponding to d.f. = 24 and α = 0.05 for a two-tailed test, you would get the t-value as 2.064.

Q2) 
t-test
You are given the standard deviation of a sample of size 32 for a two-tailed hypothesis test of a significance level of 5%.

Use the t-table given above to find the value of Zc.

Ans: 

For sample size = 32, your degrees of freedom would become 32 - 1 = 31. So, if you look for the value in the t-table corresponding to d.f. > 29 and α = 0.05 for a two-tailed test, you would get a value of 1.96.



In the second question, you used the t-table to find the value of Zc for sample size = 32 
and a significance level of 5%. If you use the z-table for the same, you would get the same value of Zc, 
since, for sample size ≥ 30, the t-distribution is the same as the z-distribution.

Practically you would not need to refer to the z-table or t-table when doing hypothesis testing in the industry.
Going forward when you need to do hypothesis testing in demonstrations of Excel or R, you would use the term t-test 
since that is mostly performed in the industry. All calculations and results of a t-test are same as the z-test whenever the sample size ≥ 30.

# Two-Sample Mean Test

Now, let’s see how the different concepts that you learnt in the previous session are applied in real-world industry scenarios.

Deepak will walk you through a demonstration of hypothesis testing on Excel, 
so download the Excel file given below and perform all the steps along with Deepak for a deeper understanding. 
You will also be introduced to a new concept called two-sample mean test.


Hypotheses in a Two-Sample Mean Test
In this two-sample mean test, suppose the null hypothesis is stated as follows: H₀: μ₁ - μ₂ = 0

What would be the alternate hypothesis in this case?

H₁: μ₁ - μ₂ ≠ 0

Feedback:
The alternate hypothesis is the claim which opposes the null hypothesis. 
If the null hypothesis states that the difference between both the means is zero, 
then the alternate hypothesis would be that the difference between both the means is not zero, i.e. μ₁ - μ₂ ≠ 0.


**Two-sample mean test** - paired is used when your sample observations are from the same individual or object.
 During this test, you are testing the same subject twice. For example, if you are testing a new drug, you would need to compare the sample before and after the drug is taken to see if the results are different.

 Q1) Two-Sample Mean Test - Paired
There is a hypothesis that Virat Kohli performs better or as good in the second innings of a test match as the first innings. This would be a two-sample mean test, where sample 1 would contain his score from the first innings and sample 2 would contain his score from the second innings. This would be a paired test since each row in the data would correspond to the same match.

What would be the null hypothesis in this case?

H₀: μ₂ - μ₁ ≥ 0

Feedback:
Here, the assumption is that Virat Kohli performs better or as good as in the second innings, 
which means his average in the second innings is assumed to be greater than or equal to his average in the first innings. 
So, the null hypothesis would be: μ₂ ≥ μ₁ or μ₂ - μ₁ ≥ 0



Let’s now move on to the other type of two-sample mean test, which is unpaired.



Two-sample mean test - unpaired is used when your sample observations are independent.
During this test, you are not testing the same subject twice. For example, if you are testing a new drug, you would compare its effectiveness to that of the standard available drug. 
So, you would take a sample of patients who consumed the new drug and compare it with another sample who consumed the standard drug.

In the Excel file, go to the third tab ‘2-sample mean test - Unpaired’ and perform the required test. 
Answer the questions below after performing this test, taking a significance level of 5%.



Q1)
Two-Sample Mean Test - Unpaired
What would be the p-value for this test if you consider it as a two-tailed test?

Feedback:
If you perform the steps shown in the demonstration above and look at the second-last row of the output table, you would see that the p-value of a two-tailed test is 0.022.


Q2)

Two-Sample Mean Test - Unpaired
What can you conclude from this test about the two unpaired samples if you take a significance level of 5%?

There is some significant difference between the means of the two samples

Feedback:
The null hypothesis in this test is that the means of the two samples are the same, and there is no significant difference between them. As the p-value (0.022) is less than 0.05 (value of α), you can reject the null hypothesis and conclude that there is some significant difference between the means of the two samples.





# Two-Sample Proportion Test

So, you now know how to compare the mean of a sample to a particular value using the one-sample mean test, and the means of two different samples using the two-sample mean test.

One thing you should observe in these tests is that the data from the sample is always numeric in nature.
But what would you do if the data is categorical in nature, i.e. 1 or 0; Yes or No, etc.? Let’s take a look.


# A/B Testing Demonstration
Let’s now learn from Ankit Jain about a process that is widely used in digital and online companies — A/B testing.
A/B testing is a direct industry application of the two-sample proportion test sample you have just studied. 


1. 1 Sample Mean test
2. 2 Sample mean test
 a. Paired test
 b. unpaired test
3. 2 sample proportion test

# Hypothesis testing in Python

You can easily do hypothesis testing in Python by using stats from Scipy library.


a)1-sample t-test: testing the value of a population mean

To test, if the population mean of data is likely to be equal to a given value

scipy.stats.ttest_1samp()

stats.ttest_1samp(data['column'], x)
#where x is the mean value you want to test

b)
2-sample t-test: testing for difference across populations
scipy.stats.ttest_ind()

stats.ttest_ind(column_1,column_2) 

c)
Paired tests: repeated measurements on the same individuals
stats.ttest_rel()  

stats.ttest_rel(column_1,column_2)  


# Industry Relevance
Different industry experts have different views on the applications and usability of hypothesis testing because of different reasons.


Let us first hear from Madhukar about the applications of hypothesis testing in the real world and get some insights into how this will be relevant in the next courses of Machine Learning when you reach the model building stage of the Crisp-DM framework.



Industry Relevance
For this example of Domino’s campaign for Peppy Paneer Pizza, test population is considered as it is purchasing that particular pizza because of the campaign and control population is the one which buys that pizza normally.

What would be the null hypothesis in this case?

The difference in response rate of control and test population is statistically insignificant

Feedback:
This is a 2-sample proportion test. The null hypothesis would contain the equality parameter.
So you would assume that difference between response rates of both groups is equal to zero, or you can say that the difference is statistically insignificant.


Anand has a very different take on hypothesis testing, as he believes that, nowadays, all the data is available digitally for most industries. 
This makes the usability of hypothesis testing a little limited in lot of scenarios.

small p value tend to be missleading there is no such thing as right cutoff for p value if variable has significace consider or reject.

p value is small or if diffrance between mean compared to what they are is huge.

need to find if satistical variable has influence you need to find 2 things :

1) does it make a diffrence 
2) if it makes a diffrence what action you can take on that 

satistical test is to rule out some variable if satistical test says this is so close to randomness knock it off 
use it as negetive test or test to rule out things not as test to demonstrate there is actually cause.


To summarise, hypothesis testing still holds importance in the following two types of industries, even if all the data is available digitally:

1) Manufacturing processes in the food, pharmaceuticals, chemicals industries, where it is not practically possible to gather information on the entire population.
2) E-commerce, advertising and digital marketing companies, where the amount of data collected from various samples is so huge that analysing all data becomes very difficult without having big data systems in place.



Summary
So what did you learn in this session?

 

T-distribution:
A T-distribution is used whenever the standard deviation of the population is unknown
The degrees of freedom of a T-distribution is equal to sample size n - 1
For sample size ≥ 30, the T-distribution becomes the same as the normal distribution
The output values and results of both t-test and z-test are same for sample size ≥ 30
 
Two-sample mean test - paired:
It is used when your sample observations are from the same individual or object
During this test, you are testing the same subject twice
 
Two-sample mean test - unpaired:
During this test, you are not testing the same subject twice
It is used when your sample observations are independent
 

Two-sample proportion test:

It is used when your sample observations are categorical, with two categories

It could be True/False, 1/0, Yes/No, Male/Female, Success/Failure, etc. 
 

A/B Testing:

A/B testing is a direct industry application of the two-sample proportion test

It is a widely used process in digital companies in the ecommerce, manufacturing and advertising domains

It provides a way to test two different versions of the same element and see which one performs better

You can download the lecture notes for the module from below. The lecture notes include a summary of the entire module.

Note : The number of stores (page number 6 or page which contains Figure 5) should be 36 instead of 25.

















