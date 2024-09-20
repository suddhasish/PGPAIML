Q&A
Introduction
In the previous session, you learnt how to formulate the hypotheses for any situation and then make a decision through the critical value method. 
In that method, you learnt to find the critical values and then compare the sample mean with the critical values to make your decision or rejecting or failing to reject the null hypothesis.

 
In this session
There are various methods similar to the critical value method to statistically make your decision about the hypothesis. 
In this session, you will study one such method, which is called the p-value method.
This is an important method and is used more frequently in the industry.

The broad agenda for this session is as follows:

The p-value method of hypothesis testing
Types of errors in hypothesis testing

This session also covers some additional concepts of Hypothesis Testing from the theory perspective, since that 
is very important while performing Hypothesis Testing in industry using tools like Python, 
Excel etc. The demonstration of Hypothesis Testing on Excel has been done in the last session of this module. 

**p-value Method**
Let’s get started with the p-value method of making a decision.

defined the p-value as the probability of the null hypothesis being accepted (or more aptly, not being rejected). This statement is not technically correct (or formal) definition of p-value, but it is used for better understanding of the p-value.


Higher the p-value, higher is the probability of failing to reject a null hypothesis. On the other hand, lower the p-value, higher is the probability of the null hypothesis being rejected.

After formulating the null and alternate hypotheses, the steps to follow in order to make a decision using the p-value method are as follows:

Calculate the value of z-score for the sample mean point on the distribution
Calculate the p-value from the cumulative probability for the given z-score using the z-table

Make a decision on the basis of the p-value (multiply it by 2 for a two-tailed test) with respect to the given value of α (significance value).

To find the correct p-value from the z-score, first find the cumulative probability by simply looking at the z-table, which gives you the area under the curve till that point.

Situation 1: The sample mean is on the right side of the distribution mean (the z-score is positive)

Example: z-score for sample point = + 3.02

Cumulative probability of sample point = 0.9987

For one-tailed test  →    p = 1 - 0.9987 = 0.0013

For two-tailed test  →    p = 2 (1 - 0.9987) = 2 * 0.0013 = 0.0026

Situation 2: The sample mean is on the left side of the distribution mean (the z-score is negative)
Example: z-score for sample point = -3.02           

Cumulative probability of sample point = 0.0013

 
For one-tailed test  →    p = 0.0013

For two-tailed test  →    p = 2 * 0.0013 = 0.0026

You can download the z-table from the attachment below. It will be useful in the subsequent questions.

Q1)

Questions.

Let’s solve the following problem stepwise to consolidate your learning on how to make a decision about any hypothesis using the p-value method.

You are working as a data analyst at an auditing firm. A manufacturer claims that the average life of its product is 36 months. An auditor selects a sample of 49 units of the product, and calculates the average life to be 34.5 months. The population standard deviation is 4 months. Test the manufacturer’s claim at 3% significance level using the p-value method.

First, formulate the hypotheses for this two-tailed test, which would be:

H₀: μ = 36 months and H₁: μ ≠ 36 months

Now, you need to follow the three steps to find the p-value and make a decision.

Try out the three-step process by answering the following questions.
1)

p-value Method
Step 1: Calculate the value of z-score for the sample mean point on the distribution. Calculate z-score for sample mean (¯x) = 34.5 months.

SAMPLE STANDARD DEVIATION = 4/✓49 = 0.5714

Z score = (Xbar - mu xbar) / sigma Xbar = (34.5 - 36 )/0.5714 = -2.62

Feedback:
You can calculate the z-score for sample mean 34.5 months using the formula: (​​¯x​ - μ) / (σ/​√n) . This gives you (34.5 - 36) / (4/√49) = (-1.5) * 7/4 = -2.62. 
Notice that, since the sample mean lies on the left side of the hypothesised mean of 36 months, the z-score comes out to be negative

2) 
p-value Method
Step 2: Calculate the p-value from the cumulative probability for the given z-score using the z-table.

Find out the p-value for the z-score of -2.62 (corresponding to the sample mean of 34.5 months). 

Hint: The sample mean is on the left side of the distribution and it is a two-tailed test

Situation 2: The sample mean is on the left side of the distribution mean (the z-score is negative)
Example: z-score for sample point = -2.62     

From Z table Z value of p(Z) = P(-2.62)= .0044 

p value = 0.0044 = .0044  *2(Two tailed test) = 0.0088

The value in the z-table corresponding to -2.6 on the vertical axis and 0.02 on the horizontal axis is 0.0044. 
Since the sample mean is on the left side of the distribution and this is a two-tailed test, the p-value would be 2 * 0.0044 = 0.0088


3) p-value Method
Step 3: Make the decision on the basis of the p-value with respect to the given value of α (significance value).

What would be the result of this hypothesis test?


Here, the p-value comes out to be 2 * 0.0044 = 0.0088. Since the p-value is less than the significance level (0.0088 < 0.03), you reject the null hypothesis that the average lifespan of the manufacturer's product is 36 months.


**p-value Method - Examples**

Let’s revisit an example we looked at earlier.

Let’s say you work at a pharmaceutical company that manufactures an antipyretic drug in tablet form, with paracetamol as the active ingredient. An antipyretic drug reduces fever. The amount of paracetamol deemed safe by the drug regulatory authorities is 500 mg. If the value of paracetamol is too low, it will make the drug ineffective and become a quality issue for your company. On the other hand, a value that is too high would become a serious regulatory issue.

There are 10 identical manufacturing lines in the pharma plant, each of which produces approximately 10,000 tablets per hour.

Your task is to take a few samples, measure the amount of paracetamol in them, and test the hypothesis that the manufacturing process is running successfully, i.e. the paracetamol content is within regulation. You have the time and resources to take about 900 sample tablets and measure the paracetamol content in each.

Upon sampling 900 tablets, you get an average content of 510 mg with a standard deviation of 110. What does the test suggest, if you set the significance level at 5%? Should you be happy with the manufacturing process or should you ask the production team to alter the process? Is it a regulatory alarm or a quality issue?

Solve the following questions in order to find out the answers to the questions stated above.

One thing you can notice here is that the standard deviation of the sample of 900 is given as 110, instead of the population’s standard deviation. In such a case, you can use the sample standard deviation (110 in this case) to calculate an approximate population standard deviation.

its  a Two taied test 

Q1) p-value Method
Calculate the z-score for sample mean (¯x) = 510 mg.
Sample Standard deviation = sigma/root (n) = 110 / root (900) = 3.66

Z = (¯x - x)/ sigma = (510-500)/3.66 =  10/3.66 =  2.73

You can calculate the z-score for the sample mean 510 mg using the formula: (​¯x​ - μ) / (σ /​√N​). This gives you (510 - 500) / (110 /√900) = (10) / (110 / 30) = 2.73. 
Notice that, since the sample mean lies on the right side of the hypothesised mean of 500 mg, the z-score comes out to be positive.

Q2) p-value Method
Find out the p-value for the z-score of 2.73 (corresponding to the sample mean of 510 mg).

P(Z) = P(2.73) = .9968

p value = (1 - .9968)*2 = 0.0032*2 = 0.0064

Feedback:
The value in the z-table corresponding to 2.7 on the vertical axis and 0.03 on the horizontal axis is 0.9968. Since the sample mean is on the right side of the distribution and this is a two-tailed test (because we want to test if the value of the paracetamol is too low or too high), the p-value would be 2 * (1 - 0.9968) = 2 * 0.0032 = 0.0064.

Q3) p-value Method
What decision would you make about the manufacturing process from this hypothesis test?

as it is 2 tailed test hence 5% significance level spread to 2 area, 5/100 =0.05/2 = 0.025

P value (0.0064) < Significance level (0.025)


The manufacturing process is not fine and changes need to be made
Feedback:
Here, the p-value comes out to be 0.0064. Since the p-value is less than the significance level (0.0064 < 0.05) and smaller p-value gives you greater evidence against the null hypothesis. 
So you reject the null hypothesis that the average amount of paracetamol in medicines is 500 mg. 
So, this is a regulatory alarm for the company and the manufacturing process needs to change.


Before we move on to the last topic of this session, let us hear from Kalpana on how hypothesis testing can be very useful in making business decisions in the industry.

**Types of Errors**
While doing hypothesis testing, there is always the possibility of making the wrong decision about your hypothesis. 
These instances of a wrong decision being made are referred to as errors. Let’s learn about the different types of errors during hypothesis testing.


There are two types of errors that can result during the hypothesis testing process — type-I error and type-II error.
A type I-error represented by α occurs when you reject a true null hypothesis.
A type-II error represented by β occurs when you fail to reject a false null hypothesis.

The power of any hypothesis test is defined by 1 - β. Power of the test or calculation of β is beyond the scope of this course. You can study more about power of a test from this link.
https://stattrek.com/hypothesis-test/power-of-test.aspx


If go back to the analogy of the criminal trial example, you would find that the probability of making a type-I error would be more if the jury convicts the accused even on less substantial evidence. The probability of a type-I error can be reduced if the jury adopts more stringent criteria to convict an accused party.

However, reducing the probability of a type-I error may increase the probability of making a type-II error. If the jury becomes very liberal in acquitting the people on trial, there would be a higher probability that an actual criminal is able to walk free.

Q1)
Errors in Hypothesis Testing
Mark all the correct options.

Type-I error occurs when the null hypothesis is rejected when it is in fact correct
Type-I error occurs when the null hypothesis is true (i.e. the sample mean lies in the acceptance region) but you incorrectly reject it.


Type II error occurs when the null hypothesis is not rejected when it is in fact incorrect
Feedback:
Type-II error occurs when the null hypothesis is not true (i.e. the sample mean lies in the critical region) but you incorrectly fail to reject the null hypothesis.


Q2)
Suppose the null hypothesis is that a particular new process is as good as or better than the old one. A type-I error is to conclude that:

The old process is better than the new one, when it is not

Type-I error means incorrectly rejecting a true null hypothesis. 
So, type-1 error means that the null hypothesis is true, i.e. the new process is as good as or better than the old one,
but you reject it, i.e. you conclude that the old process is better




----------------
Summary
So what did you learn in this session?

 

Making a decision - p-value method:
Calculate the value of Z-score for the sample mean point on the distribution

Calculate the p-value from the cumulative probability for the given z-score using the z-table

Make the decision on the basis of the p-value with respect to the given value of α (signIficance level)

 

Types of errors:
Type-I error    - Occurs when you reject a null hypothesis even when it is true
                          - Its probability is represented by α

Type-II error   - Occurs when you fail to reject the null hypotheses even though it is false

                                   - Its probability is represented by β

 

Let’s look at the crisp summary of the first two sessions in this video.



1) Type of Hypothesis
2) Type of test
3) Critical value method
4) P-Value method
5) Type of error 
 a) Type 1 error 
 b) Type 2 error 

-------------------

p-value Method
Suppose you conduct a hypothesis test and observe that the values of the sample mean and sample standard deviation when n = 25 do not lead to the rejection of the null hypothesis. You calculate the p-value as 0.0667. What would happen to the p-value if you observe the same sample mean and sample standard deviation for a larger sample size, say greater than 50?

 Graded:


 Decrease
✓ Correct
Feedback:
With an increase in the sample size, the denominator of the z-score decreases, and thus the absolute value of Z-score increases, which means that the sample mean would move away from the central tendency towards the tails. This means that the p-value would actually decrease. Conceptually, Increasing the sample size will make the distribution of sample means narrower, and chance of sample mean falling in the critical region decreases. So p-value will decrease. 


Q1) 

Types of errors
Consider the null hypothesis that a process produces no more than the maximum permissible rate of defective items. In this situation, a type-II error would be:

To conclude that the process does not produce more than the maximum permissible rate of defective items, when it actually does
✓ Correct
Feedback:
Type-II error means not rejecting the incorrect null hypothesis. So, a type-II error would signify that the null hypothesis is actually incorrect, i.e. the process actually produces more than the maximum permissible rate of defective items, but you fail to reject it, i.e. you think it does not produce more than the maximum permissible rate of defective items.


Q2) 
Types of errors
A test to screen for a serious but curable disease is similar to hypothesis testing. In this instance, the null hypothesis would be that the person does not have the disease, and the alternate hypothesis would be that the person has the disease. If the null hypothesis is rejected, it means that the disease is detected and treatment will be provided to the particular patient. Otherwise, it will not. Assuming the treatment does not have serious side effects, in this scenario, it is better to increase the probability of:


Making a type-I error, i.e. providing treatment when it is not needed
✓ Correct
Feedback:
Here, type-I error would be providing treatment upon detecting the disease, when the person does not actually have the disease. And type-II error would be not providing treatment upon failing to detect the disease, when the person actually has the disease. Since the treatment has no serious side effects, type-I error poses a lower health risk than type-II error, as not providing treatment to a person who actually has the disease would increase his/her health risk.