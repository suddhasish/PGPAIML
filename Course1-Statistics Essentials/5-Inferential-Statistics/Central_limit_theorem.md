# Introduction: Central Limit Theorem
Welcome to the session on 'Central Limit Theorem'. In the last session, you learnt about probability density functions, specifically the normal and standard normal distributions.

In this session
In this session, you will learn what a sample is and why it is so error-prone. You will then learn how to quantify this error made in sampling, using a very popular theorem in statistics, called the central limit theorem.

**Samples**
So far, you have conducted analysis for data on 75 people, 3,000 people, and so on. But what if you need to analyse a very large amount of data, e.g. data on 300,000 people? Or what if you need to do this for, say, the entire Indian population?


Let’s say that, for a business application, you want to find out the average number of times people in urban India visited malls last year. That’s 400 million (40 crore) people! You can't possibly go and ask every single person how many times they visited the mall. That’s a costly and time-consuming process. How can you reduce the time and money spent on finding this number?


For an upcoming government project, you want to find the average height of the students in Class VIII of a given school. Instead of asking each student, suppose you took a few students as your sample and wrote the data down:

 

Roll Number	Height
8012	121.92 cm
8045	133.21 cm
8053	141.34 cm
8099	126.23 cm
8125	175.74 cm

School Kids Sample
What will be the sample's standard deviation (S)?

Feedback:
We found in the previous question that the sample mean (¯X)=139.69. Now, we can find ∑(Xi−¯X)2, which turns out to be 1841.26. 

Let's apply this to the data you provided for clarity:

Sample Mean ((\bar{X})) = 139.69 cm
Heights ((X_i)) = [121.92, 133.21, 141.34, 126.23, 175.74]
Calculating squared deviations for each:

( (121.92 - 139.69)^2 = (17.77)^2 = 315.6529 )
( (133.21 - 139.69)^2 = (6.48)^2 = 41.9904 )
( (141.34 - 139.69)^2 = (1.65)^2 = 2.7225 )
( (126.23 - 139.69)^2 = (13.46)^2 = 181.1716 )
( (175.74 - 139.69)^2 = (36.05)^2 = 1299.6025 )
Sum of squared deviations: [ 315.6529 + 41.9904 + 2.7225 + 181.1716 + 1299.6025 = 1841.14 ]

Dividing this by n-1, i.e, 4, we get the value of S^2 as 460.315.
The value of S, thus, will be equal to √(460.315) = 21.45



Let's go through another example of sampling.

In order to counter fake news, let’s say Facebook is planning to include a new feature in its timeline. Below each post, a fact-checking warning will be provided, like this:

Figure 2 - Facebook Fact Checking Tool Demo
Figure 2 - Facebook Fact Checking Tool Demo
In case you want to read more about this feature, you can do so by going through this link.

Before changing the timelines of all Facebook users to include this feature, Facebook first wants to evaluate how its users would react to this new feature.
So, it lets a small sample (~10,000 users) try out the new timeline. Then, it asks the 10,000 users whether they prefer the new timeline (Feature B) or the old timeline (Feature A).

Let’s say that one such survey shows that 50.5% of the people prefer feature B over feature A. Based on this, Facebook can say that feature B is preferred by more people than feature A, and hence should replace it.
Hence, by sampling, Facebook found that feature B is preferred by more people than feature A. By conducting the exercise on a sample and not the population, it saved time, money and avoided risks that would come if it would have rolled out an untested feature.

But hold on! How can you be sure that the insights inferred for the sample hold true for the population as well? In other words, just because 50.5% of the people in the sample preferred feature B, is it fair to infer that 50.5% of the people in the population (1.86 billion Facebook users) will also prefer feature B over A?
You cannot answer this question with the information you have right now. However, after the next few lectures, which will cover sampling distributions, central limit theorem and confidence intervals, you will be in a situation to answer this question.

**Sampling Distributions**
Now, let's move on to sampling distributions, whose properties, as we said earlier, will help you estimate the population mean from the sample mean.

* This is average or mean of sample value if we take multiple sample mean then we can avoid deviation error.

So, the sampling distribution, specifically the sampling distribution of the sample means, is a probability density function for the sample mea*ns of a population.

 This distribution has some very interesting properties, which will later help you estimate the sampling error. Let's take a look at these properties.


The sampling distribution’s mean is denoted by 
μ¯X, as it is the mean of the sampling means. Let’s see what it is for this sampling distribution.

Sampling Distribution
What is μ¯X for our sampling distribution? (The data for the 100 sample means is given in the CSV file upgrad_samples.csv).

The sampling distribution’s mean would be equal to the sum of all the sample means, divided by 100. This comes out to be 2.348.

Sampling Distribution
What is the standard deviation of our sampling distribution? (The data for the 100 sample means is given in the CSV file upgrad_samples.csv).



Feedback:
Using the mean from the previous question, you can find the standard deviation using the formula - 
(StandardDeviation)2=∑(Xi−¯X)2n.
 Note that you would divide by n and not n-1 as you have the data for all 100 entries of the distribution and you don't need to sample the distribution. Now, using the formula, you get that the value of the standard deviation of the distribution is 0.4248.


 **Properties of Sampling Distributions**

 We’ve been saying that the sampling distribution has some interesting properties that will later help you estimate the error in your samples. 
 Let’s finally see what these properties are.

So, there are two important properties for a sampling distribution of the mean:

Sampling distribution’s mean (μ¯X) = Population mean (μ)

Sampling distribution’s standard deviation (Standard error) = σ√n, where σ is the population’s standard deviation and n is the sample size


Recall that, in the last video, we created a sampling distribution and found the value of its mean and standard deviation, which turned out to be 2.348 and 0.4248, respectively. These values were very close to the values suggested by the formula, i.e. 2.385 and 0.44.

**Central Limit Theorem**
Now, you understand the third property for sampling distributions, which talks about their shape. 
Basically, it says that for n > 30, the sampling distributions become normally distributed. Let's recall all the three properties you have learnt so far for sampling distributions.

So, the central limit theorem says that, for any kind of data, provided a high number of samples has been taken, the following properties hold true:

Sampling distribution’s mean (μ¯X) = Population mean (μ)

Sampling distribution’s standard deviation (Standard error) = σ√n    | where σ is the population’s standard deviation and n is the sample size

For n > 30, the sampling distribution becomes a normal distribution

We made two sampling distributions (UpGrad game and Banking data set) and saw that they follow these three properties.

Now, let’s listen to Prof. Tricha as she verifies the central limit theorem for some more population distributions.



Prof. Tricha verified CLT by performing simulations on different kinds of data. In case you want to try out these simulations yourself, you can go to this link and try them out. Press the "Begin" button in the top-left corner to get started.

 

Recall that, in the first lecture on samples, we found the mean commute time of 30,000 employees of an office by taking a small sample of 100 employees and finding their mean commute time. 
This sample’s mean was  = 36.6 minutes and its standard deviation was S = 10 minutes.


We then said that this sample mean cannot be taken as the population mean, as there might be some errors in the sampling process. 
However, we can say that the population mean, i.e. daily commute time of all 30,000 employees  = 36.6 (sample mean) + some margin of error.


Now, you may be thinking that you can use the standard error for the margin of error. 
But, although the standard error provides a good estimate of this margin of error, you cannot use it in place of the margin of error. 
To understand why, and how you would find the margin of error in that case, let's move on to the next lecture, where we will use CLT (central limit theorem) to find the aforementioned margin of error

----------------

upGrad and IIITB Machine Learning & AI Program - May 2024
Learn
Live
Discussions
suddhasish kar

Navigate

Q&A
Summary: Central Limit Theorem - Part I
This is a really intense session! Let’s summarise everything that's been taught so far and then you can move on the rest of the session.

 

First, you saw how, instead of finding the mean and standard deviation for the entire population, it is sometimes beneficial to find the mean and standard deviation for only a small representative sample. You may have to do this because of time and/or money constraints.

 

For example, for an office of 30,000 employees, we wanted to find the average commute time. So, instead of asking all employees, we asked only 100 of them and collected the data. The mean = 36.6 minutes and the standard deviation = 10 minutes.

 

However, it would not be fair to infer that the population mean is exactly equal to the sample mean. This is because the flaws of the sampling process must have led to some error. Hence, the sample mean’s value has to be reported with some margin of error.

 

For example, the mean commute time for the office of 30,000 employees would be equal to 36.6 + 3 minutes, 36.6 + 1 minutes, or 36.6 + 10 minutes, i.e. 36.6  minutes + some margin of error.

 

However, at this point in time, you do not exactly know how to find what this margin of error is.

 

Then, we moved on to sampling distributions, which have some properties that would help you find this margin of error.

Figure 4 - Creation of Sampling Distribution
Figure 4 - Creation of Sampling Distribution
We created a sampling distribution, which was a probability density function for 100 sample means with sample size 5.

 

The sampling distribution, which is basically the distribution of sample means of samples, has some interesting properties which are collectively called the central limit theorem, which states that no matter how the original population is distributed, the sampling distribution will follow these three properties:

Sampling distribution’s mean () = Population mean ()

Sampling distribution’s standard deviation (Standard error) = , where   is the population’s standard deviation and n is the sample size
For n > 30, the sampling distribution becomes a normal distribution

 To verify these properties, we performed sampling using the data collected for our UpGrad game from the first session on inferential statistics. The values for the sampling distribution thus created ( = 2.348, S.E. = 0.4248) were pretty close to the values predicted by theory ( = 2.385, S.E. = 0.44).

 To summarise, the notations and formulae for populations, samples and sampling distributions are as follows:

Figure 5 - Commonly Used Notations and Formulae
Figure 5 - Commonly Used Notations and Formulae

Practice Questions - Part I
Let’s say that you work for a news agency, which is conducting an exit poll for the MCD (Municipal Corporation of Delhi) elections. You have been tasked with predicting the winner for ward 75N (Ashok Vihar). You asked 100 randomly selected voters from this ward to name the party they had voted for.
 

The data thus collected is as given in the following table.
 

Contesting Party	Number of Voters
BJP	58
INC	42

From this sample, you have to estimate the percentage of voters that might have voted for BJP.
So, you define X as the proportion of people that voted for BJP. Then, the frequency distribution for X would be:

X  	Frequency
1	58
0	42
Now, you have to find the mean for X, which is equal to (0+0+0+...... 42 times) + (1+1+1+......... 58 times), divided by the total frequency, i.e. 100. So, the mean =  = 0.58 or 58%.

Also, you would have to find the standard deviation for this sample of 100 voters. Since the mean is 0.58, the sample’s variance =  = 0.2461. So, the standard deviation is equal to its square root, i.e. 0.496 or 49.6%.
------------------------------------
Question 1/3
Mandatory
Voter Sample
Now, let’s say you define Y as the proportion of people that voted for the INC party. 
Clearly, the mean of Y will be 0.42. What would be the standard deviation of Y?


49.6%
Feedback:
There would be 42 people for whom Y would be equal to 1, and 58 people for whom Y would be equal to 0. Hence, the sample’s variance = 
(1−0.42)2∗42+(0−0.42)2∗58/100−1=0.2461
. So, the standard deviation is equal to its square root, i.e. 0.496 or 49.6%


Voter Sample
Let’s say you actually took some more samples, each of size 100, and made a sampling distribution for X, the proportion of people that voted for BJP.
------------------------
2)The mean of this sampling distribution is 
μ¯X = 0.50 and the standard error = 0.052.
So, for the whole survey population, i.e. all the voters in ward 75N, the proportion of people that voted for BJP is approximately equal to:

Feedback:
You have to find the mean for all the people or, in other words, the population mean. Using CLT, you can say that the mean of the sampling distribution = the population mean. As the question says that the sampling distribution’s mean = 0.5, the population mean also = 0.5 or 50%

---
3)  Similarly, let’s say you made a sampling distribution for Y, the proportion of people that voted for INC.

The mean of this sampling distribution is 
μ¯X = 0.50 and the standard error is equal to 0.048.

Now, for the whole survey population, i.e. all the voters in ward 75N, the standard deviation of Y is equal to:


----

4) Voter Sample
Similarly, let’s say you made a sampling distribution for Y, the proportion of people that voted for INC.

The mean of this sampling distribution is μ¯X = 0.50 and the standard error is equal to 0.048.

Now, for the whole survey population, i.e. all the voters in ward 75N, the standard deviation of Y is equal to:

You have to find the standard deviation for all people or, in other words, the population standard deviation σ. Using CLT, 
you can say that (σ/√n) = SE. Hence, (σ/√100) = 0.048, which gives σ = .48 or 48%


Standard Error = sigma/root (n)
Population varience  (sigma) = Standard Error * root(n) = 0.048 * root(100) = 0.048*10 = 0.48

-----------------------------
**Estimating Mean Using CLT**

Now that you have gone through the mid-session summary, let’s get back to rest of the session. Earlier, we tried to estimate the mean commute time of 30,000 employees of an office by taking a small sample of 100 employees and finding their mean commute time. This sample’s mean was  = 36.6 minutes and its standard deviation was S = 10 minutes.

Recall that we also said that the population mean, i.e. daily commute time of all 30,000 employees μ= 36.6 (sample mean) + some margin of error.

If you remember, you did not learn exactly how to find this margin of error.
 But now, you can find it by using CLT (central limit theorem). Now that you know CLT, let’s see exactly how you can do this.

Note : At 3:22, The professor told, sample mean lies within 2 standard deviation instead of population mean lies within 2 standard deviation.


**
Sampling distribution mean mu x bar= Population mean mu {unknown}
Sample distribution standard deviation = S.E = (σ/√n) = (S/√n) = 10/√100 = 1
The sampling distribution is normal distribution P(μ-2 < 36.6 < μ+2) = 95.4%
P(36.6-2 < μ < 36.6 + 2) =  P(μ-2 < 36.6 < μ+2) = 95.4%
probability associated with the claim is called (Confidence level)  (here it is 95.4%)
Maximum error made in sample mean is called (margin of error ) (here it is 2 minute)

Final interval of value you present that you are confident about is called confidence interval  (Here it is the Range - (34.6,38.6))

Generalized the approach:
Sample Mean (Xbar) 
Sample standard deviation (S)
Sample size(n)

So, to summarise, let’s say you have a sample with sample size n, mean  and standard deviation S. Now, the y% confidence interval (i.e. the confidence interval corresponding to y% confidence level) for  would be given by the range:
Confidence interval (y% confidence level ) = (Xbar - Z*S/√n,Xbar + Z*S/√n)

where, Z* is the Z-score associated with a y% confidence level. In other words, the population mean and sample mean differ by a margin of error given by
Z*S//√n
Some commonly used Z* values are given below:

****

- At this point, it is important to address a very common misconception. Sampling distributions are just a theoretical exercise and you’re not actually expected to make one in real life. If you want to estimate the population mean, you will just take a sample. You will not create an entire sampling distribution.

You must be wondering — if this is the case, then why did you study sampling distributions? To understand the reason for this, let's go through the actual process of sampling. Recall that you are doing sampling because you want to find the population mean, albeit in the form of an interval. The three steps to follow are as follows:

First, take a sample of size n

Then, find the mean and standard deviation S of this sample

Now, you can say that for y% confidence level, the confidence interval for the population mean , is given by (y% confidence level ) = (Xbar - Z*S/√n , Xbar + Z*S/√n)

 However, as you may have seen in the video above, you cannot finish step 3 without CLT. 
 CLT lets you assume that the sample mean would be normally distributed, with mean  μ and standard deviation σ/√n (approx. S/√n). Using this assumption, it
 becomes possible to find many things such as margin of error, confidence interval, etc.
 Hence, you learnt sampling distributions so that you could learn more about CLT and hence be able to make all the assumptions as stated above.


 **Confidence Interval - Example**
Let’s listen to Prof. Tricha walk you through a real-life example of how confidence intervals can be used to make decisions.

Proportion of lead in maggi noodles 
Population mean = mu +- error ?
n = 100 
Sample Mean (Xbar) = 2.3 ppm
Sample Standard Deviation (S) = 0.3 ppm
Confidence level  = 99%
Confidence interval = mu +- Z*S//√n = 2.3 +- (2.576*0.3)/√100 = (2.223,2.377) {Population Mean (mu) 99% Confidence}


Let’s see another example of how you can use confidence intervals to make a decision. Recall the Facebook example discussed in the last session? Let’s find the 90% confidence interval (confidence interval for 90% confidence level) for that case.

 

Recall that 50.5% of the 10,000 people surveyed preferred feature B over feature A. So, if X = the proportion of people that prefer feature B over feature A, then, for this sample,  = 0.505 (50.5%) and n = 10,000. In addition to this, you now know the sample’s standard deviation S = 0.2(20%) {this is just random value taken for S to show demo}.s

Now, you know that the actual population mean  lies between  + margin of error. However, now, it's vital for us to find this margin of error.

 

---------------------

**Practice Questions - Part II**
Let’s say you work as a data analyst at a pharma company which manufactures an antipyretic drug (tablet form) with paracetamol as the active ingredient. The amount of paracetamol specified by the drug regulatory authorities is 500 mg with an allowed error of 10%. Anything below 450 mg would be a quality issue for your company since the drug would become ineffective, while anything above 550 mg would be a serious regulatory issue.


There are 10 identical manufacturing lines in the plant, each of which produces approximately 10,000 tablets per hour.

You want to take some samples, measure the amount of paracetamol, and test if the manufacturing process is running successfully. You have the resources and time to take a sample of 100 tablets and measure the paracetamol content in each.

For the 100 tablets sampled by you, you find that the mean paracetamol content is 530 mg and the standard deviation is 100 mg.

Now, you want to know what the average content is for all the tablets in the plant. You are thinking of reporting the average as a confidence interval, for which you are 95% confident.

With this information, answer the questions given below

If this margin of error is, say, 1%, then that would mean that the population mean , 
which is the proportion of people that prefer feature B over feature A, lies between the range (50.5-1)% to (50.5+1)%, 
i.e.  49.5 % to 51.5%. It would mean that you cannot say with certainty that  would be more than 50%. So, even though the proportion of people that prefer feature B over feature A is more than 50% in our sample, you would not be able to say with certainty that this proportion would be more than 50% for the entire population.


On the other hand, if the margin of error is, say, 0.3%, then you would be able to say that the population mean lies within (50.5-0.3)% and (50.5+0.3)%, i.e. 50.2% to 50.8%. So, you would be able to say with certainty that the proportion of people that prefer feature B over feature A is more than 50% in our sample and for the entire population too.

 

Now, the margin of error corresponding to 90% confidence level would be given by  = Z*S/√n = 0.0033 (0.33%), and the population mean lies between 50.17% and 50.83%.


Hence, you can say that feature B should replace feature A with 90% confidence.

Q1:
Mean Estimation Using CLT
For the above case, the 95% confidence interval is:

(50.11%, 50.89%)
✓ Correct
Feedback:
From the above, you have X= 50.5%, S = 20% and n = 10,000. The confidence interval is given by 
(¯X−Z∗S√n,¯X+Z∗S√n), where Z* is the Z score associated with 95% confidence level = 1.96. Hence, the 95% confidence interval would be 
(50.5 = (50.11% to 50.89%).

Q2:

* Mean Estimation Using CLT
For the above case, the 99% confidence interval is:
(49.98%,51.02%)
✓ Correct
Feedback:
From the above, you have X= 50.5%, S = 20% and n = 10,000. The confidence interval is given by 
(¯X−Z∗S√n,¯X+Z∗S√n), where Z* is the Z score associated with 99% confidence level = 2.58. Hence, the 99% confidence interval would be 
(50.5 = (49.98% to 51.02%).

Q3
Mean Estimation Using CLT
Now, you want to make the claim that more than 50% people prefer feature B over feature A. Which of the following statement/s about this claim is/are true?

You can make this claim with 90% confidence

You can make this claim with 95% confidence

You can make this claim with 99% confidence

Feedback:
90% confidence interval for μ is (50.17%, 50.83%). Hence, with 90% confidence, you can say that more than 50% people prefer B over A. Similarly, since 95% confidence interval is (50.11%, 50.89%), you can say with 95% confidence that more than 50% people prefer B over A. However, the 99% confidence interval is (49.98%, 51.02%). Hence, at 99% confidence level, you cannot say for sure that more than 50% people prefer B over A.

Summary: Central Limit Theorem - Part II
First, you learnt how, using your knowledge of CLT, you can infer the population mean from the sample mean.

 

We estimated the mean commute time of 30,000 employees of an office, by taking a sample of 100 employees, finding their mean commute time, and estimating based on that value. Specifically, you were given a sample with sample mean 
¯
X
 = 36.6 minutes, and sample standard deviation S = 10 minutes.

 

Using CLT, you concluded that the sampling distribution for mean commute time would have:

Mean = μ {unknown}
Standard error = 
σ√n≈S√n=10√100=1
Since n(100) > 30, the sampling distribution is a normal distribution

Using these properties, you were able to claim that the probability that the population mean μ lies between 34.6 (36.6-2) and 38.6 (36.6+2), is 95.4%.

Then, you learnt some terminology related to the claim:

The probability associated with the claim is called confidence level (here, it is 95.4%)
The maximum error made in sample mean is called margin of error (here, it is 2 minutes)
Final interval of values is called confidence interval [here, it is the range (34.6, 38.6)]

Then, you generalised the whole process. Let’s say you have a sample with sample size n, mean  and standard deviation S. You learnt that the y% confidence interval (i.e. confidence interval corresponding to y% confidence level) for  will be given by the range:

Confidence interval = Where, Z* is the Z-score associated with a y% confidence level

-------------------------------

**Practice Questions - Part II**
Let’s say you work as a data analyst at a pharma company which manufactures an antipyretic drug (tablet form) with paracetamol as the active ingredient. The amount of paracetamol specified by the drug regulatory authorities is 500 mg with an allowed error of 10%. Anything below 450 mg would be a quality issue for your company since the drug would become ineffective, while anything above 550 mg would be a serious regulatory issue.

There are 10 identical manufacturing lines in the plant, each of which produces approximately 10,000 tablets per hour.

You want to take some samples, measure the amount of paracetamol, and test if the manufacturing process is running successfully. You have the resources and time to take a sample of 100 tablets and measure the paracetamol content in each.

For the 100 tablets sampled by you, you find that the mean paracetamol content is 530 mg and the standard deviation is 100 mg.

Now, you want to know what the average content is for all the tablets in the plant. You are thinking of reporting the average as a confidence interval, for which you are 95% confident.

With this information, answer the questions given below.

Paracetamol Content:
Q1)
What is the MOE (margin of error) for 95% confidence level?


Feedback:
If X is the defined as the paracetamol content, then for this sample of X, sample mean 
¯X = 530 mg, sample standard deviation S = 100 mg and sample size n = 100. Also, for 95% confidence interval, Z* is 1.96. Now, you know that the margin of error = 
Z∗S√n=1.96∗100√100 = 19.6

Q2)
What is the confidence interval for 95% confidence level?

Feedback:
As you know, sample mean 
¯X = 530 and Z∗S√n = 19.6. Now, you know the confidence interval is 
(¯X−Z∗S√n,¯X+Z∗S√n)
. Putting in the values, you can calculate the confidence interval as (510.4, 549.6)

Paracetamol Content
What is the confidence interval for 90% confidence level?


513.5 to 546.5

Feedback:
As you know, sample mean 
¯X = 530, S = 100 and n = 100. Also, for 90% confidence interval, Z* is 1.65. Now, you know the confidence interval is 
(¯X−Z∗S√n,¯X+Z∗S√n)
. Putting in the values, you can calculate the confidence interval as (513.5, 546.5).


-------------------------------

Graded
-----------------------

Graded Questions
Question 1

An exit poll was conducted by a news agency for the MCD (Municipal Corporation of Delhi) elections. 
You had been tasked with predicting the winner for ward 75N (Ashok Vihar). 
For that purpose, you asked 100 randomly selected voters from your ward to name the party they had voted for.
 

The data that was thus collected is given in the following table:

 

Contesting Party  	 Mean (Percentage of Voters) 	 Standard Deviation (Percentage of Voters)
BJP                 	58%	                            49.6%
INC	                    42%	                            49.6%

Now, instead of taking more samples and forming a sampling distribution, 
which would be a tedious and expensive task, let's say you decide to use your knowledge of CLT to find the winner.


First, you would have to form a 95% confidence interval for the percentage of voters that voted for BJP.
 Then, you would form another such confidence interval for INC, after which you would be able to compare the two to predict the winner.

 Q1)
Exit Poll Confidence Interval
So, you define X as the proportion of people that voted for BJP. 
Now, for a 95% confidence interval, what would be the value of the MOE (margin of error)?


Feedback:
The margin of error = Z∗S√n.
 From the data given above, you know that S = 49.6% or 0.496 and n = 100. The value of Z* corresponding to 95% confidence is 1.96. So, the margin of error = 
1.96∗0.496√100 = 0.0972, or 9.72%

Q2)
Exit Poll Confidence Interval
What would the 95% confidence interval be for X, the proportion of people that voted for BJP?

(48.28%, 67.72%)
Feedback:
Recall that the margin of error = 9.72% and the sample mean 
¯X = 58%. So, the confidence interval is (58%-9.72%, 58%+9.72%)

Q3) 
Exit Poll Confidence Interval
What would the 95% confidence interval be for Y, the proportion of people that voted for INC?

(32.28%, 51.72%)
✓ Correct
Feedback:
For the variable Y, the sample mean ¯X = 42%. S, the sample’s standard deviation = 49.6% and the sample size n = 100. So, the 95% confidence interval = 
(¯X−Z∗S√n,¯X+Z∗S√n). Putting in the values, you get that the confidence interval is (32.28%, 51.72%).

Q4)

Exit Poll Confidence Interval
Thus, with 95% confidence, you can:

Not make any claims regarding the election results for ward 75N
✓ Correct
Feedback:
The percentage of voters that voted for BJP, falls within the interval (48.28%, 67.72%). The interval for the percentage of voters that voted for INC is (32.28%, 51.72%). Hence, anything is possible. It is possible that BJP gets 67.72% of the votes and wins the election, but it is also possible that INC could get 51.72% of the votes and win the election for ward 75N. Hence, you cannot decide the winner based on this information.

-------

So, in this way, news agencies poll people and use the data to decide the possible winner/winners for each ward. Then, they aggregate the results for all the wards and show them to us as their poll results.
The MCD elections are usually a multi-party affair but the maths in the multi-party scenario would have been very difficult to understand at present. Hence. we’ve only taken ward 75N in this example, which was contested for by only two political parties.

If you want to read more on how exit poll maths works and how the polls are set up to ensure accuracy, you can go through the following links:

https://www.math.arizona.edu/~jwatkins/505d/Lesson_12.pdf
https://www.math.arizona.edu/~jwatkins/505d/Lesson_12.pdf



----------------- Graded Question 2 -----------

**Question 2**

A home renting startup, Ghar ki Baat, is planning to offer 2 BHK fully furnished flats for rent in Powai, Mumbai. In order to ensure that it charges the correct rent, it wants to find the average rent charged by homeowners in Powai.

In order to ensure that it charges the correct rent, it wants to find the average rent charged by homeowners in Powai.

For that purpose, it has acquired the following data, which has a list of 200 fully furnished 2 BHK flats in Powai, along with the monthly rent charged for them in the year 2016.

As a data analyst working for Ghar ki Baat, you are tasked with finding the average rent for all 2 BHK fully furnished flats in Powai, Mumbai, using this data.

Q1)
2 BHK Flat Rent in Powai
What is the 90% confidence interval for the monthly rent in rupees?

(₹44,701, ₹46,441)
✓ Correct
Feedback:
The confidence interval, as you remember, is given by 
(¯X−Z∗S√n,¯X+Z∗S√n). Using Excel or R, you can calculate that the mean, 
¯X = ₹45,571 and the standard deviation S = 7457. Also, since the sample csv file has 200 entries, sample size, n = 200. Z* value for 90% confidence level is 1.65. Putting in all the values, you get the confidence interval (₹44,701, ₹46,441).

Q2)


2 BHK Flat Rent in Powai
What is the 99% confidence interval for the monthly rent in rupees?
(₹44,210, ₹46,932)
✓ Correct
Feedback:
The confidence interval, as you remember, is given by 
(¯X−Z∗S√n,¯X+Z∗S√n). In the last question, you found that the value of the mean, 
¯X = ₹45,571 and the standard deviation, S = 7457. Also, you know that sample size, n = 200 and Z* value for 99% confidence level is 2.58. Putting in all the values, you will get the confidence interval (₹44,210, ₹46,932).

Q3)
2 BHK Flat Rent in Powai
Your boss decides to fix the monthly rent at ₹46,500 and she asks you if this is close enough to the average. She asks you to decide based on a 95% confidence level.

Does the rent fixed by your boss (₹46,500) lie inside the 95% confidence interval for monthly rent?


Yes
✓ Correct
Feedback:
The confidence interval, is given by 
(¯X−Z∗S√n,¯X+Z∗S√n). Also, because of previous questions, you know that the value of the mean 
¯X = ₹45,571, standard deviation S = 7457 and sample size n = 200. Now, using Z* value for 95% confidence level, which is 1.96, you will get the confidence interval (₹44,537, ₹46,605). Clearly, ₹46,500 lies inside the interval.
