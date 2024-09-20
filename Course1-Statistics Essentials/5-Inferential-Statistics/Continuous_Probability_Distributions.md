**Introduction: Continuous Probability Distributions**
Welcome to the session on ‘Continuous Probability Distributions’. In the last session, you learnt about the binomial distribution and the uniform distribution. Also, you learnt the concept of cumulative probability.


In this session
In this session, you will learn about cumulative probability in a little more depth. You will see how the probability of a continuous variable is expressed and how it is different from the way the probability of a discrete variable is expressed. You will then learn about the normal distribution, which is a commonly used probability distribution among continuous random variables.

**Probability Density Functions - I**

In the last section, you saw how to find the probability of certain events using multiplication and addition rules of probability. Also, for some specific cases, you saw that probability distributions like the binomial distribution and the uniform distribution can be used to find the probability.


However, so far we have only been talking about discrete random variables, e.g. number of balls, number of patients, cars, wickets, pasta packets, etc. What happens when we talk about the probability of continuous random variables, such as time, weight etc.? Is there any difference? Let’s see.

Note : At 4:23, the headline of slide should be PDFs vs CDFs insdead of CDFs vs PDFs.

So, now you know what a CDF is and what a PDF is. Since these two functions talk about probabilities in terms of intervals rather than exact values, it is advisable to use them when talking about continuous random variables, and not the bar chart distribution that we used for discrete variables.


Just to recall, a CDF, or a cumulative distribution function, is a distribution which plots the cumulative probability of X against X.

A PDF, or Probability Density Function, however, is a function in which the area under the curve, gives you the cumulative probability.

For example, the area under the curve, between 20, the smallest possible value of X and 28, gives the cumulative probability for X = 28.



The main difference between the cumulative probability distribution of a continuous random variable and a discrete one, is the way you plot them. While the continuous variables’ cumulative distribution is a curve, the distribution for discrete variables looks more like a bar chart:


The reason for showing both of these so differently is that, for discrete variables, the cumulative probability does not change very frequently. In the discrete example, we only care about what the probability is for 0, 1, 2, 3 and 4. This is because the cumulative probability will not change between, say, 3 and 3.999999. For all values between these two, the cumulative probability is equal to 0.8704.

However, for the continuous variable, i.e. the daily commute time, you have a different cumulative probability value for every value of X. For example, the value of cumulative probability at 21 will be different from its value at 21.1, which will again be different from the one at 21.2 and so on. Hence, you would show its cumulative probability as a continuous curve, not a bar chart.

**Probability Density Functions - II**


A commonly observed type of distribution among continuous variables is the uniform distribution. For a continuous random variable following a uniform distribution, the value of probability density is equal for all possible values. Let’s explore this distribution a little more.



Uniform Distribution
In a uniform PDF, all the possible values have the same probability density. The figure below shows such a uniform PDF, where the possible values are 0 to 10.

* For this graph, what is the value of the probability density from X = 0 to X = 10?



Since all possible values are between 0 and 10, the area under the curve between 0 and 10 is equal to 1.
Clearly, this area is the area of a rectangle with length 10 and unknown height h. Hence, you can say that 10*h = 1, which gives us h = 0.1. So, the value of the PDF for all values between 0 and 10 is 0.1.

Uniform Distribution
For the uniform PDF from the previous question, find the cumulative probability for X = 0.5.

*Uniform Distribution
For the uniform PDF from the previous question, find the cumulative probability for X = 0.5.

The cumulative probability for X = 0.5 is equal to the area under the curve between X = 0, the lowest possible value, and X = 0.5.

This area = 0.1*0.5 = 0.05.

 
Now, I’m sure you are wondering, when to use PDFs and when to use CDFs? They are both good for continuous variables, but which one is used more in real life analysis?

Well, PDFs are more commonly used in real life. The reason is that it is much easier to see patterns in PDFs as compared to CDFs. For example, here are the PDF and the CDF of a uniformly distributed continuous random variable:


Again, it is clear that the symmetrical nature of the variable is much more apparent in the PDF than in the CDF.
Hence, generally, PDFs are used more commonly than CDFs.


Cumulative Probability of Continuous Variables
Suppose you work at a sports analysis company and you want to analyse the effect a bowler’s height has on his/her performance. So, you create a list of all 5 wicket hauls in the last decade. Based on this data, they created a cumulative probability distribution for X, where X = height of the bowler who took the 5 wicket haul.

Now, based on the data, you conclude that the cumulative probability, F(175.3 cm) = 0.3. In this case, which of the following statements is correct?

P(X<175.3 cm) = 0.3

P(X<175.3 cm) = 0.3

(Remember that height is a continuous variable.)


Both statements 1 and 2 are correct
Feedback:
You can say that P(X ≤ 175.3 cm) = P(X < 175.3 cm) + P(X = 175.3 cm). Now, since X is a continuous variable, you know that the probability of getting an exact value is zero. Hence, P(X=175.3 cm) = 0, which means that P(X ≤ 175.3 cm = P(X < 175.3 cm) + 0.


**Normal Distribution**
You’ve seen how the probability distributions of continuous random variables differ from those of discrete random variables.

But can you think of some examples of continuous distributions? 
Which is the most commonly used continuous probability distribution? 
Which distribution occurs most commonly in nature? Let’s hear from Prof. Tricha on this.


Most commonly used continous random variable Probablity density function or Normal Distribution .
Distribution is symetric on mean median and mode 

mean u (mu)
Standard deviation (Sigma)
Probability lying mu + sigma and mu-sigma is 68%
Probability lying mu + 2sigma and mu-2sigma is 95%
Probability lying mu + 3sigma and mu-3sigma is 99.7%

*This is called 1-2-3 rule


Finding Probablity of Normal variable X
mean = 35
mu = 5
P(25 < X < 45) = P(mu -2sigma < X < mu + 2sigma) = 95%

P(25 < X < 50) = P(mu - 2 sigma < X < mu +3 sigma) = 49.85% + 47.5% = 97.35%

P(<40>) = P(X < mu + sigma) = 50% + 34% = 84%


All data that is normally distributed follows the 1-2-3 rule. This rule states that there is a -

68% probability of the variable lying within 1 standard deviation of the mean

95% probability of the variable lying within 2 standard deviations of the mean

99.7% probability of the variable lying within 3 standard deviations of the mean



This is actually like saying that, if you buy a loaf of bread everyday and measure it, then - (mean weight = 100 g, standard deviation = 1 g)

For 5 days every week, the weight of the loaf you bought that day will be within 99 g (100-1) and 101 g (100+1).

For 20 days every 3 weeks, the weight of the loaf you bought that day will be within 98 g (100-2) and 102 g (100+2).

For 364 days every year, the weight of the loaf you bought that day will be within 97 g (100-3) and 103 g (100+3).

A lot of naturally occurring variables are normally distributed. For example, the heights of a group of adult men would be normally distributed. To try this out, we asked 50 male employees at the UpGrad office for their height and then plotted the probability density function using that data.

As you can see, the data is roughly normal.

 

You can visualise the PDF and CDF for different normal distributions by using the interactive app given below. From the various options in the drop-down menu, select “Normal”. You will then get to see the probability distribution for a normal distribution with µ = 0 and σ = 1. In fact, you can play around with the value of µ and σ to see how that changes the distribution. Using the green slider below the distribution, you can visualise the distribution’s cumulative probability.

In fact, you can select “Uniform” in the drop-down menu and visualise the CDF and PDF for the uniform distribution too. Be sure to play around with a and b, which give the lowest and highest possible values, respectively, for the random variable.

*Probability of Normal Random Variables
Let’s say that you need to find the cumulative probability for a random variable X which is normally distributed. You do not know what the value of X is or, for that matter, what the value of µ and σ is. You only know that X = µ + σ. Can you find the cumulative probability, i.e. the probability of the variable being less than µ + σ?

Feedback:
You can still find the cumulative probability. If the variable is normally distributed, then it doesn’t matter what the value of µ and σ is, there is a 34% probability that X lies between µ and µ + σ, i.e. P(µ < X < µ + σ = 34%). Similarly, there is a 50% probability that X is less than µ, i.e. P(X < µ = 50%). Again, this would happen regardless of what the value of µ and σ is. Hence, you can say that P(X < µ + σ) = 84% for every normal variable, no matter what the value of µ and σ is.




**Standard Normal Distribution**
As you learnt in the previous question, it doesn’t matter what the value of µ and σ is. 
All you need to know, if you want to find the probability, is how far the value of X is from µ — specifically, what multiple of σ is the difference between X and µ.


Let’s see how you can find this.


Let consider Mean (mu) = 35 
Standard deviation (Sigma) = 5
X = 43.25

Diffrence = X-mu = 8.25 = mu +1.65*sigma

this value of 1.56 is called Z score of random variable 

Z = X-mu/Sigma


Z = standerdized normal variable

P(-2  Z < 2) = P(mu - 2sigma < X  < mu + 2sigma) = 95%  # known from 1-2-3 rule
P(-2  Z < 3) = P(mu - 2sigma < X  < mu + 3sigma) = 97.35%
P(Z <1) = P(X < mu + sigma) = 84%

* Dstribution of Z called standard normal distribution
* Mathmetitian prepared Z table 

* How to calculate if a employee have average commute time 43.25 min 

mu = 35
sigma = 5

P(X < 43.25) = 
Z = (43.25 - 35) / 5 = 1.65 

P(X < 43.25) = P(Z<1.65) =0.95(95%)

between 25.2 AND 44.8

P(25.2 < X <44.8) = P(-1.96 < Z < +1.96) = P(Z=+1.96) - P(Z=-1.96) = 0.975 - 0.025 = .95 = 95%

As you just learnt, the standardised random variable is an important parameter. It is given by:

Z=(X−μσ) /σ

Basically, it tells you how many standard deviations away from the mean your random variable is.
As you just saw, you can find the cumulative probability corresponding to a given value of Z, using the Z table:


Alternatively, you can use the following equation to find the cumulative probability:

 F(Z)=1√2π∫Z−∞e−t22dt 

However, I’ve a feeling that you will prefer the table! :-)

Not only that, you can also use Excel or Python to find the cumulative probability for Z. For example, let’s say you want to find the cumulative probability for Z = 1.5. In Excel, you would type:

 
= NORM.S.DIST(1.5, TRUE)

Basically, the syntax is:

= NORM.S.DIST(z, TRUE)

 Here, z is the value of the Z score for which you want to find the cumulative probability. TRUE = find cumulative probability, FALSE = find probability density.

 
Also, you can find the probability without standardising. Let’s say that X is normally distributed, with mean (μ) = 35 and standard deviation (σ) = 5. Now, if you want to find the cumulative probability for X = 30, you would type:

= NORM.DIST(30, 35, 5, TRUE)

Basically, the syntax is:

= NORM.DIST(x, mean, standard_dev, TRUE)

The Z-table mentioned below might be broken. Please use this link instead, for solving the problem.



As you can see, the value of σ is an indicator of how wide the graph is. This will be true for any graph, not just the normal distribution. A low value of σ means that the graph is narrow, while a high value implies that the graph is wider. This will happen because the wider graph will clearly have more values away from the mean, resulting in a high standard deviation.

 

Again, there are some more probability distributions that are commonly seen among continuous random variables. They are not covered in this course, but if you want to go through some of them, you can use the links below -

https://online.stat.psu.edu/stat414/lesson/15/15.1
https://online.stat.psu.edu/stat414/lesson/15/15.4
https://online.stat.psu.edu/stat414/lesson/15/15.8






These questions are NOT graded.
 
------------
Let’s say you work as an analyst at a pharma company which manufactures an antipyretic drug (tablet form) with paracetamol as the active ingredient. The amount of paracetamol specified by the drug regulatory authorities is 500 mg with a permissible error of 10%. Anything below 450 mg would be a quality issue for your company since the drug will be ineffective, while above 550 mg would be a serious regulatory issue.

Now, the company’s QC (Quality Control) department comes and selects a tablet at random from Batch Z2. It is interested in finding if the paracetamol level is above 450 mg or not.

What is the probability that the tablet selected by QC has a paracetamol level above 450 mg?

* Let’s define X as the amount of paracetamol in the selected tablet. Now, X is a normally distributed random variable, with mean μ = 510 mg and standard deviation σ = 20 mg. Now, you have to find the probability of X being more than 450, i.e. P(X>450). Converting this to Z, you get P(X>450) = P(Z>{450-510}/20) = P(Z>-3) = 1 - P(Z<-3) = 0.9987, or 99.87%.
-------------------
Now, let’s say that QC decides to sample one more tablet. This time, it selects a tablet from Batch Y4. Based on previous knowledge, you know that Batch Y4 has a mean paracetamol level of 505 mg, and its standard deviation is 25 mg. This time, QC wants to check both the upper limit and the lower limit for the paracetamol level.

What is the probability that the tablet selected by QC has a paracetamol level between 450 mg and 550 mg?

X = 450,550
μ = 505
σ = 25

Z=(X−μ) /σ


P(450 < X < 550) = P(-2.2 < Z < 1.8) = P(Z=+2.2) - P(Z=-1.8) = .98610 - .03593 = .95017 = 95.017

Let’s define X as the amount of paracetamol in the selected tablet. Now, X is a normally distributed random variable, with mean μ = 505 mg and standard deviation σ = 25 mg. Now, you have to find the probability of X being more than 450 and less than 550, i.e. P(450 < X < 550). Converting this to Z, you get P(450 < X < 550) = P({450-505}/25 < Z < {550-505}/25) = P(-2.2 < Z < 1.8) = P(Z < 1.8) - P(Z < -2.2) = 0.9641 - 0.0139 = 0.9502, or 95%.

----------


The graph you see above represents the PDF of a uniformly distributed random variable X. As you can see, the probability density is equal for all the possible values of X (-5 to +5).

Uniform Distribution
What is the probability of the random variable X lying between -1.5 and +2.5, i.e. P(-1.5<X<2.5)?

The graph you see above represents the PDF of a uniformly distributed random variable X. As you can see, the probability density is equal for all the possible values of X (-5 to +5).


The probability of the variable lying between -1.5 and 2.5 would be equal to the area under the PDF, between X = -1.5 and X = 2.5. This would be equal to the area of a rectangle, with breadth 0.1 and length 2.5 - (-1.5) = 4. Multiplying the two, you get the area of the rectangle, which is equal to 0.1*4 = 0.4.



[Important Note: The Z-value in the following link may not work correctly sometimes. Please use this link instead]

 
-----------------------------
The normal distribution, aka the Gaussian distribution, was discovered by Carl Friedrich Gauss in 1809. Gauss was trying to create a probability distribution for astronomical errors. Astronomical errors are the errors that were made by astronomers while observing phenomena such as distances in space.


For example, Gauss found that an astronomer trying to estimate the distance between Earth and Uranus always makes an error. This error is normally distributed, with µ = 0 km and σ = 1,000 km.

Astronomical Error
Based on the information above, what is the probability of the astronomer overestimating the distance by 2,330 km or more?

(X+2330)/1000=Z  


or Z = 2.330  = .99010


To find the probability that the astronomer overestimates the distance by 2,330 km or more, we can use the properties of the normal distribution. Given that the errors are normally distributed with a mean (µ) of 0 km and a standard deviation (σ) of 1,000 km, we need to calculate the probability that the error is at least 2,330 km.

Step-by-Step Calculation
Standardize the Error Value: To find this probability, we first convert the error value into a standard normal variable (Z-score). The Z-score is calculated by: [ Z = \frac{X - \mu}{\sigma} ] where (X) is the value of interest (2,330 km), (\mu) is the mean (0 km), and (\sigma) is the standard deviation (1,000 km).

Plugging in the values: [ Z = \frac{2330 - 0}{1000} = 2.33 ]

Find the Probability: The Z-score of 2.33 corresponds to the astronomer's error being 2,330 km away from the mean. We need to find the probability that the error is greater than this Z-score. This is the upper tail of the normal distribution.

Using the Z-table or a calculator for the standard normal distribution, we find the probability that (Z > 2.33). This value is typically looked up in standard normal distribution tables or calculated using a function in a statistics software or calculator.

Using the Z-table: The Z-table provides the cumulative probability from the left up to Z. For (Z = 2.33), the cumulative probability is approximately 0.9901. Since we are interested in the probability of exceeding this Z-score, we calculate (1 - 0.9901 = 0.0099).

et’s define X as the astronomical error, which is normally distributed with mean 0 km and standard deviation 1,000 km. 
Now, you have to find the probability that X > 2330, i.e. P(X>2330). 
Converting this to Z, 
it becomes P(Z>2.33). Since P(Z<=2.33) + P(Z>2.33) = 1,
 P(Z>2.33) = 1 - P(Z<2.33) = 1 - 0.9901 = 0.0099 or 0.99%, which is approximately 1%

Conclusion
The probability that the astronomer overestimates the distance by 2,330 km or more is approximately 0.0099, or 0.99%.
 This indicates a very low likelihood of such a large error occurring under the given normal distribution of errors.
-------------------------------
Astronomical Error
Hence, what is the probability that the astronomer under- or over-estimates the distance by less than 500 km?

  P(-500 < X < 500)=P(-0.5 < Z < 0.5) = P(Z < 0.5) - P(Z < -0.5)  = .69146-.30854


 Feedback:
Let’s define X as the astronomical error, which is normally distributed with mean 0 km and standard deviation 1,000 km.
 Now, you have to find the probability that -500 < X < 500, 
 i.e. P(-500 < X < 500). Converting this to Z, 
 it becomes P(-0.5 < Z < 0.5) = P(Z < 0.5) - P(Z < -0.5) = 0.6915 - 0.3085 = 0.3830, or 38.30%.





