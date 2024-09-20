Introduction
Welcome to the module on 
# ‘Hypothesis Testing’.

 In the previous module, you learnt about inferential statistics.

In this session
The statistical analyses learnt in Inferential Statistics enable you try to make inferences about the population mean from the sample data when you have no idea of the population mean. However, sometimes you have some starting assumption about the population mean and you want to confirm those assumptions using the sample data. It is here that hypothesis testing comes into the picture. We will cover the basic concepts of hypothesis testing in this session, which are as follows:

Types of hypotheses:

- Types of tests

- Decision criteria

- Critical value method of hypothesis testing

This session covers the concepts of Hypothesis Testing from the theory perspective, 
since that is very important while performing Hypothesis Testing in industry using tools like R, Excel,Python etc. 
The demonstration of Hypothesis Testing on Excel and Python has been done in the last session of this module. 

# Understanding Hypothesis Testing
In the last module, you learned about the following topics:

Inferential statistics: Making inferences about the population using the sample data

Now, these methods help you formulate a basic idea or conclusion about the population. 
Such assumptions are called “hypotheses”. But how do you really confirm these conclusions or hypotheses? Let’s see.

Let’s understand the basic difference between inferential statistics and hypothesis testing.
--------------------------------------------------------------------------


Inferential statistics is used to find some population parameter (mostly population mean) when you have no initial number to start with. So, you start with the sampling activity and find out the sample mean. Then, you estimate the population mean from the sample mean using the confidence interval.

Hypothesis testing is used to confirm your conclusion (or hypothesis) about the population parameter (which you know from EDA or your intuition). Through hypothesis testing, you can determine whether there is enough evidence to conclude if the hypothesis about the population parameter is true or not.

Both these modules have a few similar concepts, so don’t confuse terminology used in hypothesis testing with inferential statistics.
Let’s get started by understanding the basics of hypothesis testing.

CONFLICTING HYPOTHESIS IN CRIMINAL TRIAL EXAMPLE 

Hypothesis Testing starts with the formulation of these two hypotheses:

Null hypothesis (H₀): The status quo (Defendent is innocent or nothing changes)

Alternate hypothesis (H₁): The challenge to the status quo (Defendent is not innocent)

Outcome: Rejection of Null hypothesis or Guilty
Fail Reject null hypothesis due to lack of evidence - Not Guilty.

Null and Alternate Hypotheses
In the Maggi Noodles example, if you fail to reject the null hypothesis, what can you conclude from this statement?

--> Maggi Noodles do not contain excess lead

The null hypothesis is that the average lead content is less than or equal to 2.5 ppm. 
Since you fail to reject the null hypothesis, you can conclude that Maggi Noodles do not contain excess lead. 
Please note than you can only fail to reject the null hypothesis, you can never accept the null hypothesis.

- Types of Hypotheses
The null and alternative hypotheses divide all possibilities into:

--> 2 non-overlapping sets
Feedback:
Both the null and alternate hypotheses can’t be true at the same time. Only one of them will be true.

**Null and Alternate Hypotheses**

The first step of hypothesis testing is the formulation of the null and alternate hypothesis for a given situation. 
Let’s learn how to do this through different examples.



Distribution of AC Unit per store in summer mean mu = 350 


Null hypothesis (H₀): The status quo ( Mean AC sales per store is 350 unit)

Alternate hypothesis (H₁): The challenge to the status quo (Mean AC sales per store is not equals  350 unit)

If we are unable to reject  Null hypothesis (H₀) that dosent mean we are accepting it so only we can say lack of evidence to reject null hypothesis.
which means we may or maynit be able to prove alternate hypothesis which desent mean we can reject null hypothesis.

- Flipkart claimed that its total valuation in December 2016 was $14 billion. What would be the alternate hypothesis for the given situation?
H₁: Total valuation ≠ $14 billion


You have seen examples where you can write the null hypothesis (or status quo) easily from the claim statement, 
like in the last question - Flipkart claimed that its total valuation in December 2016 was $14 billion.

But in some instances, if your claim statement has words like “at least”, “at most”, “less than”, or “greater than”, you cannot formulate the null hypothesis just from the claim statement (because it’s not necessary that the claim is always about the status quo).

You can use the following rule to formulate the null and alternate hypothesis:
The null hypothesis always has the following signs:  =  OR   ≤   OR    ≥
The alternate hypothesis always has the following signs:  ≠   OR  >   OR    <

For example:  

Situation 1:  Flipkart claimed that its total valuation in December 2016 was at least $14 billion. 
Here, the claim contains ≥ sign (i.e. the at least sign), so the null hypothesis is the original claim.

The hypothesis in this case can be formulated as:


Total Valuation >=$14 Billion --> Null Hypothesis 
Total Valuation < $14 Billion --> Alternate Hypothesis 

Situation 2:  Flipkart claimed that its total valuation in December 2016 was greater than $14 billion. 
Here, the claim contains > sign (i.e. the ‘more than’ sign), so the null hypothesis is the complement of the original claim. The hypothesis in this case can be formulated as:

The hypothesis in this case can be formulated as:

Total Valuation > $14 Billion -->  Alternate Hypothesis    
Total Valuation <=  $14 Billion -->  Null Hypothesis  

Now, answer the following questions to consolidate your learning about the formulation of null and alternate hypothesis.


Q1)

Null and Alternate Hypothesis
The average commute time for an UpGrad employee to and from office is at least 35 minutes.

What will be the null and alternate hypothesis in this case if the average time is represented by μ?

H₀: μ ≥ 35 minutes and H₁: μ < 35 minutes

Feedback:
The null hypothesis is always formulated by either = or ≤ or ≥ whereas the alternate hypothesis is formulated by ≠ or > or <. In this case, the average time taken was greater than or equal to 35 minutes. So, that becomes the null hypothesis. Less than 35 minutes becomes the alternate hypothesis.

To summarize this, you cannot decide the status quo or formulate the null hypothesis from the claim statement, you need to take care of signs in writing the null hypothesis. 
Null Hypothesis never contains ≠ or > or < signs. It always has to be formulated using = or ≤ or ≥ signs.
Before you go ahead and look at some more examples of formulating null and alternate hypothesis, let us hear from Ankit Jain about how he used hypothesis testing during his time at Facebook.

# Making a Decision
Once you have formulated the null and alternate hypotheses, let’s turn our attention to the most important step of hypothesis testing 
— making the decision to either reject or fail to reject the null hypothesis — through an interesting example of a friend playing archery.


- Upper Critical point: point above which implies to  reject null hypothesis. (example average score of something > 70)
- Lower critical point: point below which implies to  reject null hypothesis.

- Critical point statistical significanse to reject null hypothesis 
- If your sample mean lies in the acceptance region, then: You fail to reject the null hypothesis because it is not beyond the critical point 
  and you can consider that sample mean is equal to the population mean statistically.

  So, you learnt about what critical values are and how your decision to reject or fail to reject the null hypothesis 
  is based on the critical values and the position of the sample mean on the distribution.
  Let’s learn more about the critical region and understand how the position of the critical region changes 
  with the different types of null and alternate hypotheses.


The formulation of the null and alternate hypotheses determines the type of the test and the position of the critical regions in the normal distribution.


You can tell the type of the test and the position of the critical region on the basis of the ‘sign’ in the alternate hypothesis.

      

-       ≠ in H₁    →   Two-tailed test      →     Rejection region on both sides of distribution (Example: someones score mean is = 70 
                                                    so alternated hypothesis is  ≠ 70 where critical region lies in both side of mean )

-      < in H₁    →   Lower-tailed test     →    Rejection region on left side of distribution (Example: Average score  >= 35 then pass so alternate hypothesis become average score < 35 
                                                 where critical region lies lower end before mean)

-      > in H₁    →   Upper-tailed test     →   Rejection region on right side of distribution (Example: maggi noodles should have led content <= 2.5 ppm so alternate hypothesis become led content > 2.5 ppm)


Q1) 
Null and Alternate Hypotheses
The average commute time for an UpGrad employee to and from office is at least 35 minutes.
If this hypothesis has to be tested, select the type of the test and the location of the critical region.

Feedback:
For this situation, the hypotheses would be formulated as 
H₀: μ ≥ 35 minutes and 
H₁: μ < 35 minutes. 
As < sign is used in alternate hypothesis, it would be a lower-tailed test and the rejection region would be on the left side of the distribution.

**Critical Value Method**

Now, let’s learn how to find the critical values for the critical region in the distribution and make the final decision of rejecting or failing to reject the null hypothesis.
Note: At 1:07, professor mistakenly told 370.16 instead of 370.6. It should be 370.6

Standard deviation
What will be the standard deviation of the distribution of sample means if the population has a mean of 350 and a standard deviation of 90,
 a sample mean of 370.16, and a sample size of 36?

 Feedback:
Recall your learnings from inferential statistics — how can you calculate the standard deviation of the sample means from the population standard deviation?

Feedback:
The standard deviation of a distribution of sample means is obtained by dividing the population standard deviation by the square root of the sample size. 
So, 90/ ​√36​ = 90/6 = 15.


Before you proceed with finding the Zc and finally the critical values, let’s revise the steps performed in this method till now.

First, you define a new quantity called α, which is also known as the significance level for the test. It refers to the proportion of the sample mean lying in the critical region. For this test, α is taken as 0.05 (or 5%).

LCV = 0.025
UCV = 0.025

Then, you calculate the cumulative probability of UCV from the value of α, which is further used to find the z-critical value (Zc) for UCV.

Attempt the following questions before you go ahead and learn the remaining steps in this method.

UCV = 1 - 0.025 = 0.975

Q1)
Area of rejection region
What will be the area of the critical region on the right-hand side of the distribution if the significance level (α) for a two-tailed test is 3%?

Feedback:
Here, value of α is 0.03 (of 3%), so the area of the rejection region would be 0.03 and the area of the acceptance region would be 0.97. In addition, since this is a two-tailed test, the area of the critical region on the right-hand side would be half of 0.03, i.e. 0.015.


q2)

Area of rejection region
What would be the area of the critical region on the right-hand side of the distribution if the significance level (α) for an upper-tailed test is 3%?
Feedback:
Here, the value of α is 0.03 (of 3%), so the area of the critical region would be 0.03 and the area of the acceptance region would be 0.97. Since this is an upper-tailed test, the critical region is only on the right-hand side of the distribution, and the area of the critical region would be 0.03.

Q3)

Area of rejection region
What would be the value of the cumulative probability of UCV if the significance level (α) for an upper-tailed test is 3%?

0.97

Feedback:
The area of the critical region in this case would be 0.03 (as calculated in the last question), which would be the area beyond the UCV point in the distribution. So, the area till the UCV point would be 1 - 0.03, i.e. 0.97. This would be the cumulative probability of that point, going by the definition of cumulative probability.


After formulating the hypothesis, the steps you have to follow to make a decision using the critical value method are as follows:

Calculate the value of Zċ from the given value of α (significance level). Take it a 5% if not specified in the problem.

Calculate the critical values (UCV and LCV) from the value of Zċ.

Make the decision on the basis of the value of the sample mean x with respect to the critical values (UCV AND LCV).

You can download the z-table from the attachment below. It will be useful in the subsequent questions.




**Example 2:** 

Let’s solve the following problem stepwise to consolidate your learning on how to make a decision about any hypothesis.

A manufacturer claims that the average life of its product is 36 months. An auditor selects a sample of 49 units of the product, and calculates the average life to be 34.5 months. 
The population standard deviation is 4 months. Test the manufacturer’s claim at 3% significance level using the critical value method.


First, you need to formulate the hypotheses for this two-tailed test, which would be:

H₀:μ = 36 months and H₁: μ ≠ 36 months

Now, you need to follow the three steps to find the critical values and make a decision.

Try out the three-step process by answering the following questions.


Q1) Critical Value Method
1st step: Calculate the value of Zc from the given value of α (significance level).

Calculate the z-critical score for the two-tailed test at 3% significance level.

Feedback:
For 3% significance level, you would have two critical regions on both sides with a total area of 0.03. So, the area of the critical region on the right side would be 0.015, which means that the area till UCV (cumulative probability of that point) would be 1 - 0.015 = 0.985. So, you need to find the z-value of 0.985. The z-score for 0.9850 in the z-table is 2.17 (2.1 on the horizontal axis and 0.07 on the vertical axis)

Q2) Critical Value Method
2nd step: Calculate the critical values (UCV and LCV) from the value of Zc.

Find out the UCV and LCV values for Zc = 2.17.

μ = 36 months        σ = 4 months       N (Sample size) = 49



3% significance level and 2 tailed test hence 
UPPER critical region = 0.015
Lower critical region = 0.015
UCV point = 0.985
Zċ = 2.17  form Z table 
Standard deviation of sample mean = sigma Xbar = sigma (population varience) /root (n) = 4 /7 = 0.5714

CV = Mu + (Zc * sigma Xbar) = 34.5 + 2.17*0.5714
Feedback:
The critical values can be calculated from μ ± Zc x (σ/​√N​) as 36 ± 2.17(4/√49​) = 36 ± 1.24 which comes out to be 37.24 and 34.76.

Q3)
Critical Value Method
3rd step: Make the decision on the basis of the value of the sample mean ​
¯x  with respect to the critical values (UCV AND LCV).

What would be the result of this hypothesis test?

UCV = 37.24 months                 LCV = 34.76 months              Sample mean (​¯x) = 34.5 months

Reject the null hypothesis as below LCV



**Critical Value Method - Examples**
You have learnt how to perform the three steps of the critical value method with the help of the AC sales problem as well as the above product lifecycle comprehension problem, which was a two-tailed test. But what would happen if it were a one-tailed test? Let’s watch the video below to understand.


Attempt the following questions to complete this one-tailed test.

**Example1**
Q1)
Critical Value Method
Consider this problem — H₀: μ ≤ 350 and H₁: μ > 350

In case of a two-tailed test, you find the z-score of 0.975 in the z-table, since 0.975 was cumulative probability of UCV in that case. 
In this problem, what would be the cumulative probability of critical point in this example for the same significance level of 5%?
Feedback:
In this problem, the area of the critical region beyond the only critical point, which is on the right side, is 0.05 (in the last problem, it was 0.025). So, the cumulative probability of the critical point (the total area till that point) would be 0.950.

Q2) 

Critical Value Method
Consider this problem — H₀: μ ≤ 350 and H₁: μ > 350

The next step would be to find the Zc, which would basically be the z-score for the value of 0.950. Look at the z-table and find the value of Zc.

1.645

Feedback:
0.950 is not there in the z-table. So, look for the numbers nearest to 0.950. You can see that the z-score for 0.9495 is 1.64 (1.6 on the horizontal bar and 0.04 on the vertical bar), and the z-score for 0.9505 is 1.65. So, taking the average of these two, the z-score for 0.9500 is 1.645.


Q3)

Critical Value Method
Consider this problem, H₀: μ ≤ 350 and H₁: μ > 350

So, the Zc comes out to be 1.645. Now, find the critical value for the given Zc and make the decision to accept or reject the null hypothesis.

μ = 350     σ = 90       N (Sample size) = 36    
¯x= 370.16

The standard deviation of a distribution of sample means is obtained by dividing the population standard deviation by the square root of the sample size. 
So, 90/ ​√36​ = 90/6 = 15.

CV = Mu + (Zc * sigma Xbar) = 350 + 1.645 *  15  = 350 + 24.67 = 374.675 

Feedback:
The critical value can be calculated from μ + Zc x (σ/√N). 350 + 1.645(90/√36) = 374.67. Since 370.16 (¯x) is less than 374.67,¯x lies in the acceptance region and you fail to reject the null hypothesis.
Fail to reject null hypothesis.





**Example2**
Government regulatory bodies have specified that the maximum permissible amount of lead in any food product is 2.5 parts per million or 2.5 ppm. Let’s say you are an analyst working at the food regulatory body of India FSSAI. Suppose you take 100 random samples of Sunshine from the market and have them tested for the amount of lead. The mean lead content turns out to be 2.6 ppm with a standard deviation of 0.6.
One thing you can notice here is that the standard deviation of the sample is given as 0.6, instead of the population’s standard deviation. In such a case, you can approximate the population’s standard deviation to the sample’s standard deviation, which is 0.6 in this case.

Answer the following questions in order to find out if a regulatory alarm should be raised against Sunshine or not, at 3% significance level.



Critical Value Method
Select the correct null and alternate hypotheses in this case.


H₀: Average lead content ≤ 2.5 ppm and H₁: Average lead content > 2.5 ppm
✓ Correct
Feedback:
The null hypothesis is your assumption about the population — it is based on the status quo. It always makes an argument about the population using the equality sign. The null hypothesis in this case would be that the average lead content in the food material is less than or equal to 2.5 ppm. And the alternate hypothesis is that the average lead content is greater than 2.5 ppm.


Critical Value Method
Calculate the z-critical score for this test at 3% significance level


probability of the critical point (the total area till that point) would be = 1 - 0.03 = 0.97


Z critical value = 

This is a one-tailed test. So, for 3% significance level, you would have only one critical region on the right side with a total area of 0.03. This means that the area till the critical point (the cumulative probability of that point) would be 1 - 0.030 = 0.970. So, you need to find the z-value of 0.970. The z-score for 0.9699 (~0.970) in the z-table is 1.88.


Critical Value Method
Now, you need to find out the critical values and make a decision on whether to raise a regulatory alarm against Sunshine or not. Select the correct option.

CV = μ + Zc x (σ/​√N​), as 2.5 + 1.88(0.6 /√100​) = 2.61 ppm



Critical value = 2.61 ppm and Decision: Don’t raise a regulatory alarm
✓ Correct
Feedback:
The critical value can be calculated from μ + Zc x (σ/​√N​), as 2.5 + 1.88(0.6 /√100​) = 2.61 ppm . You need to use the + sign since the critical value is on the right-hand side (upper-tailed test). Since the sample mean 2.6 ppm is less than the critical value (2.61 ppm), you fail to reject the null hypothesis and don’t raise a regulatory alarm against Sunshine.


Critical Value Method
The critical value for this test at 3% significance level comes out to be 2.61 ppm. If you take more than 100 samples 
(with the same sample mean and standard deviation), how would the z-score and critical value change?



The z-score would remain the same but the critical value would decrease
✓ Correct
Feedback:
Since Zc is calculated from the given value of α (3%), it remains the same. 
Critical value is calculated using the formula: μ + Zc x (σ/​√N​), since it is an upper-tailed test. 
If you increase the value of N, the critical value would decrease according to the formula.


------------------

Summary
So what did you learn in this session?

 

Hypothesis — a claim or an assumption that you make about one or more population parameters
Types of hypothesis:

Null hypothesis (H₀) - Makes an assumption about the status quo
- Always contains the symbols ‘=’, ‘≤’ or ‘≥’

Alternate hypothesis (H₁) - Challenges and complements the null hypothesis

- Always contains the symbols ‘≠’, ‘<’ or ‘>’

Types of tests:
Two-tailed test - The critical region lies on both sides of the distribution
                             - The alternate hypothesis contains the ≠ sign
Lower-tailed test - The critical region lies on the left side of the distribution
                                - The alternate hypothesis contains the < sign
Upper-tailed test - The critical region lies on the right side of the distribution
                                                 - The alternate hypothesis contains the > sign

Making a decision - Critical value method:

Calculate the value of Zc from the given value of α (significance level)

Calculate the critical values (UCV and LCV) from the value of Zc

Make the decision on the basis of the value of the sample mean 
¯x with respect to the critical values (UCV AND LCV)
----------------

Graded Questions
-----------------

Types of hypotheses
The null and alternative hypotheses are statements about:

Population parameters
✓ Correct
Feedback:
The hypothesis is always made about the population parameters. The sample parameters are only used as evidence to test the hypothesis.

Null and Alternate Hypotheses
A house owner claims that the current market value of his house is at least Rs.40,00,000.  60 real estate agents are asked independently to estimate the house's value. The hypothesis test that is conducted ends with the decision of "reject H₀".  Which of the following statements accurately states the conclusion?

The house owner is wrong, the house is worth less than Rs. 40,00,000
Feedback:
Rejection of the null hypothesis means rejection of the status quo or the earlier assumption of the house owner that his house is worth at least Rs. 40,00,000. As the null hypothesis is H₀: House market value ≥ 40,00,000, the alternate hypothesis would be opposite of that.


Null and Alternate Hypotheses
Which of the following options hold true for null hypothesis?

More than one option may be correct.


The claim with the “less than or equal to” sign
✓ Correct
Feedback:
The null hypothesis is always written with the “equal to” or “less than or equal to” or “more than or equal to” sign.

The claim with the “equal to” sign
✓ Correct
Feedback:
The null hypothesis is always written with the “equal to” or “less than or equal to” or “more than or equal to” sign.

Q1)

Cadbury states that the average weight of one of its chocolate products ‘Dairy Milk Silk’ is 60 g. 
As an analyst on the internal Quality Assurance team, you would like to test whether, at the 2% significance level, 
the average weight is 60 g or not. A sample of 100 chocolates is collected and the sample mean size is calculated to be 62.6 g. 
The standard deviation, as calculated from the sample, is 10.7 g.

 

Answer the following questions in order to draw a conclusion from the test.


Critical Value Method
What would be the Zc for the critical point/s in this case?

2.33

Feedback:
For a 2% significance level, you would have two critical regions on both sides with a total area of 0.02 (because you want to test if the average weight of the chocolate is greater than or less than 60 g). So, the area of the critical region on the right side would be 0.01, which means that the area till UCV (cumulative probability of that point) would be 1 - 0.01 = 0.99. So, you need to find the z-value of 0.99. The z-score for 0.9901 in the z-table is 2.33 (2.3 on the horizontal axis and 0.03 on the vertical axis). So, you can take the z-score for either 0.9901 for 0.99.

Q2)
Critical Value Method
Find out the critical values for this test and conclude whether the QA team can safely pass this test or not.

60 + 2.33 * 10.7/✓ 100 = 62.49

sample mean size is calculated to be 62.6 g so test failed

Feedback:
The critical values can be calculated from μ ± Zc x (σ/​√N​) as 60g ± 2.33(10.7 /√100) = 60g ± 2.49g which comes out to be 62.49 g and 57.51 g. Since 62.6 g is greater than the UVC of 62.49, which means the sample mean lies outside the range of the critical values, you reject the null hypothesis that the average weight of the chocolate is 60 g. So, the QA would not pass this test.



