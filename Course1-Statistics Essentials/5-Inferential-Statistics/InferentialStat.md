# Introduction: Inferential Statistics
Welcome to the module on ‘Inferential Statistics’. 


In this module
Many a time, you may require a very large amount of data for your analysis which may need too much time and resources to acquire. In such situations, you are forced to work with a smaller sample of the data, instead of having the entire data to work with.

 

Situations like these arise all the time at big companies like Amazon. For example, say the Amazon QC department wants to know what proportion of the products in its warehouses are defective. Instead of going through all of its products (which would be a lot!), the Amazon QC team can just check a small sample of 1,000 products and then find, for this sample, the defect rate (i.e. the proportion of defective products). Then, based on this sample's defect rate, the team can "infer" what the defect rate is for all the products in the warehouses.

 

This process of “inferring” insights from sample data is called “Inferential Statistics”.


**Introduction: Basics of Probability**
Welcome to the session on ‘Basics of Probability’.

In this session, you will learn a few basic concepts of probability through a specific example. The broad agenda for this session is as follows:

- Random variables

- Probability distributions

- Expected value


**Random Variables**

Gane:  Where we have have 5 ball 3 red 2 blue in a bag and we have to pick 4 red balls which will be win and rest other option loss.

Recall the original question: In the long run (i.e. if it is played a lot of times), is this game profitable for the players or for the house? Or will everybody break even in the long run?


Recall that we established a three-step process for answering this question:

- Find all the possible combinations

- Find the probability of each combination

- Use the probabilities to estimate the profit/loss per player

 
We have completed step 1, i.e. finding all the possible combinations. 

- where we have 16 possible outcome or combination.

- BBBB
- RBBB
- BRBB
- BBRB
- BBBR
- RRBB
- RBRB
- RBBR
- BRRB
- BRBR
- BBRR
- RRRB
- RRBR
- RBRR
- BRRR
- RRRR

Now, let’s proceed to step 2, i.e. finding the probability of each combination.
What are the steps involved in finding the probability? 
Let’s hear more from Professor Tricha on this:

Outcome we got need to be quantified to variable X
X = Number of Redballs

- BRRR  | X = 3
- RRRR  | X = 4

X is here reffered as Random variable.

Associatio outcome of an experiment and natural number.


So, the random variable X basically converts outcomes of experiments to something measurable.

For example, let’s say as a data analyst at a bank, you are trying to find out which of the customers will default on their loan, 
i.e. stop paying their loans. Based on some data, you have been able to make the following predictions:


- Customer No.	Yearly Income (in rupees)	Amount of Loan Due (in rupees)	Number of Dependents	Default Prediction (Yes/No)
- 1	₹10 lakh	₹75 lakh	3	Yes
- 2	₹15 lakh	₹50 lakh	2	No
- 3	₹20 lakh	₹40 lakh	1	No
 

Now, instead of processing the yes/no response, it will be much easier if you define a random variable X, indicating whether the customer is predicted to default or not. The values will be assigned according to this rule:

X = 1, if the customer defaults

X = 0, if the customer does not default
Now, the data changes to the following:


- Customer No.	Yearly Income (in rupees)	Amount of Loan Due (in rupees)	Number of Dependents	X (random variable)
- 1	₹10 lakh	₹75 lakh	3	1
- 2	₹15 lakh	₹50 lakh	2	0
- 3	₹20 lakh	₹40 lakh	1	0
 

Now, in this form, the table is entirely quantified, i.e. converted to numbers. 
Now that the data is entirely in quantitative terms, it becomes possible to perform a number of different kinds of statistical analyses on it.

**Probability Distributions - I**

Recall that, in our UpGrad game example, we need to find out if the game would be profitable for the players or for us (i.e. the house) in the long run. The three-step process for this is:

- Find all the possible combinations

- Find the probability of each combination

- Use the probabilities to estimate the profit/loss per player

 

So far, we have completed step 1, and are on step 2, i.e. finding the probability of each combination. 
For this purpose, we defined a random variable X which helped us convert the outcomes of our experiment to something measurable. 
Now, let’s actually find the probability of each of these combinations.


Possible value of X
X=0
X=1
X=2
X=3
X=4

Considering 75 people going to play this game.
2 people drawn 0 red ball.
12 people drawn 1 red ball.
26 people drawn 2 red ball.
25 people drawn 3 red ball.
10 people drawn 4 red ball.

Probability = Feavorable outcome / Total Outcome
Probabiity of (X =2) = Frequency of 2 / Total Frequency (75)
Probabiity of (X =2) =  26/75 = 0.35 or 35 % of people 

Probability Distribution: Probability of all possible value of X

x p(x)

0 0.027
1 0.16
2 0.347
3 0.333
4 0.133

**Probability Distributions - II**
So basically, a probability distribution is ANY form of representation that tells us the probability for all possible values of X. It could be any of the following:

- A table
- Chart
- An equation

P(x) = x/21

(for x = 1, 2, 3, 4, 5 and 6)


Hence, in a valid, complete probability distribution, there are no negative values, and the total of all probability values adds up to 1. These two conclusions follow from the basic definition of probability.

Also, if you recall, we discussed that the probability distribution and frequency distribution would be exactly similar in shape, just with different scales. You can try it out in this interactive app. The graph on the left shows the frequency distribution and the one on the right shows the probability distribution.


Now, let’s say that a company’s management is pondering over investing in a certain project. Before doing this, it wants to use probability to find whether it can safely expect to make a profit. Whether the company makes a profit or not will actually depend on which economic cycle is going on, i.e. recession, boom, and so on.

 

Based on the opinions of some experts, the following table is created:


Summary: Basics of Probability
- Economic Cycle	Probability
- Recession	0.1
- Normal	0.7
- Boom	0.2

Suppose, as an analyst in the investment division, you have been asked to find the answer to the question: “Can the company expect to make a profit or not? Should it invest in this project?”

However, in this form, the table is of no help at all. Hence, let’s quantify it using a random variable. 
Since you are interested in whether the company will profit or not, let’s define X as X = Net revenue of the project.


Now, through some calculations, a fellow analyst of the company has found what the net revenue would be for each of these scenarios.
She creates a probability distribution with this data:


- X (Net Revenue of Project, in ₹ crores)	    P(x)    
- -305	0.1
- +15	0.7
- +95	0.2


Now, you finally have a probability distribution for X, the net revenue of the project. 
Using this probability distribution, you can find the answer to our original question - “Can the company expect a profit from this project? Or should it expect a loss?” However, to answer it, you will have to learn the concept of expected value, which is what we will cover next.

**Expected Value - I**
Again, let’s go back to the three-step process we followed to find whether the UpGrad red ball game was profitable for the players or for the house:
Find all the possible combinations

Find the probability of each combination

Use the probabilities to estimate the profit/loss per player

Now that we have completed steps 1 and 2, let’s move on to step 3 where we will use the probabilities we calculated to estimate the profit/loss per player.

Number of player with 1 red balls(s) = 160
Number of player with 1 red balls(s) = 347
Number of player with 1 red balls(s) = 27
Number of player with 1 red balls(s) = 333
Number of player with 1 red balls(s) = 133

Total number of red balls  = 0*27 + 1*160 + 2*347 + 3*333 + 4*133 = 2385

Average number of red balls for 1 game = 2385/1000 = 2.385

So, the expected value for a variable X is the value of X we would “expect” to get after performing the experiment once. It is also called the expectation, average, and mean value. Mathematically speaking, for a random variable X that can take values : x1,x2,x3,...........,xn
given by: EV(X)=x1∗P(X=x1)+x2∗P(X=x2)+x3∗P(X=x3)+...........+xn∗P(X=xn)

As you may recall, for our red ball game, the expected value came out to be 2.385. What does that mean? How does that even help us with our original question, which was how much money, on average, are the players expected to make?

Let’s explore that in the following video.

As you may recall, for our red ball game, the expected value came out to be 2.385. What does that mean? How does that even help us with our original question, which was how much money, on average, are the players expected to make?


SO EV = 0*(0.027)+ 1*(0.160)+2*(0.347)+3*(0.333)+4*(0.133)

Changing random variable as it is not helping to answer who will win more in long run.

X = Money won after playing the game once.

Expected value of money won AFTER 1 GAME 

X can take two values: +150  and -10
P(X = +150) = P(4 red balls) = 0.333
P(X = -10) = P(0,1,2 or 3   red balls) = 0.027 + 0.160 + 0.347  + 0.333 = 0.867

So, EV = (150 * 0.133) + (-10*0.867) = +11.28

We figured out there is chance of average player to win the game and earn 11.28 on average which is disaster for house.
Decrease price money / increase the penalty 
If we can set EV as -10 or -20 that makes game profitable.
--------------------

As you may recall, for our red ball game, the expected value came out to be 2.385. 
What does that mean? How does that even help us with our original question, which was how much money, on average, are the players expected to make?
Let’s explore that in the following video.

So, you can clearly see that, after a large number of simulations, the average value does, in fact, converge towards the expected value, which is 2.385.

**Expected Value - II**

Let’s try it for a different activity. Let’s say that you’re throwing a dice. You’ve defined X as the number obtained upon throwing it once. By calculations, you would find that the expected value for this is 3.5. Let’s see what our simulations show:


Expectation
The expected value of an experiment is the probability-weighted average of all possible values. 
It is defined mathematically as the following:

$$E[X] = \sum_{x \in X}xP(x)$$
The law of large numbers states that the average result from a series of trials will converge to the expected value. 
Roll the die to see convergence to its expected value.

Change the theoretical probability of the die to see how that changes the average and expected value.

Now, you may recall that the expected value of a player’s winnings after playing our game once was ₹11.28.
 We said that reducing the prize money and/or increasing the penalty for our game might make the expected value negative. Let’s see how much we need to reduce or increase the prize money.


Recall the problem you saw earlier, where we were asked by a company to suggest whether it should invest in a given project or not.
 We had made this probability distribution for X, the net revenue of the project.

 X (Net Revenue of Project, in ₹ crores)	    P(x)    
-305	0.1
+15	0.7
+95	0.2
 

Now, we are in a position to find the expected value for X, the return of the project. This is called the expected return. If it comes out to be negative, we can say that the project is not worth investing in.

The expected value of X, which is also called the **expected return**, is equal to

 

(-305)*P(X=-305) + (+15)*P(X=+15) + (+95)*P(X=+95) = (-305)*0.1 + (+15)*0.7 + (+95)*0.2 = -1 crore rupees.

 

So, the expected return of the project is -1 crore rupees. Hence, we can conclude that the project is not worth investing in.



-------------

**Summary: Basics of Probability**
In the first section, you learnt how to quantify the outcomes of events by using random variables.

 

For example, recall that we quantified the colours of the balls we would get after playing our game by assigning a value of X to each outcome. We did so by defining X as the number of red balls we would get after playing the game once.

Figure 4 - Quantifying Using Random Variables
Figure 4 - Quantifying Using Random Variables
Next, we found the probability distribution, which was a distribution giving us the probability for all possible values of X.

 

We created this distribution in a tabular form:

Figure 5 - Tabular Form of Probability Distribution
Figure 5 - Tabular Form of Probability Distribution
We also created it in a Frequency Distribution chart:

Figure 6 - Bar Chart Form of Probability Distribution
Figure 6 - Bar Chart Form of Probability Distribution
You saw that, in the bar chart form, we were able to visualise the probability in a much better way., Thus, this form is used more widely as it helps you see trends easily.

 

Then, we went on to find the expected value for X, the money won by a player after playing the game once. The expected value (EV) for X was calculated using the formula:

 



 

Another way of writing this is



 

Calculating the answer this way, we found the expected value to be +11.28.


In other words, if we conduct the experiment (play the game) infinite times, the average money won by a player would be ₹11.28.
Hence, we decided that we should either decrease the prize money or increase the penalty to make the expected value of X negative. 
A negative expected value would imply that, on average, a player would be expected to lose money and the house would profit.

 
**Practice Questions**
These questions are not graded.

 

Let's say that Rajya Laxmi Bank has given student loans to 10,000 people. 
However, the government wants to ensure that the bank is not giving away very risky loans and, hence, wants to know the “Expected Loss” of the bank’s student loan portfolio.

The expected loss is basically the expected value of the money lost by the bank due to people defaulting on their loans, i.e. not paying their EMIs.

The data that the bank uses to calculate the expected loss, looks like this -


- Customer No.	Exposure at Default (in ₹ lakh)	Recovery (%)	Probability of Default
- 00001	11.50	20%	0.007

Here,

**Exposure at default (EAD)** is the total money owed by the customer in case of default

**Recovery (R)** is the percentage of the exposed money that the bank would be able to recover.

For example, in the above example, the bank would recover 20% of the exposed money, i.e. 20%*11.5 = ₹2.3 lakh.

**Probability of default (PD)** is the probability that the customer will default. This is calculated for each customer using a number of factors such as family income, university attended, etc.

Expected Loss
Now, to find the expected loss, the bank has created the following table. As you already know, the probability of customer 1 being a defaulter is 0.007 and that of the customer not being a defaulter is 0.993. Now, in the case of default, what would be the value of X, i.e. the money lost by the bank?

Defaulter/Non-defaulter	   Probability   	X (Money Lost by Bank)
Defaulter	0.007	-
Non-defaulter	0.993	0

Ans:
₹9.2 lakh
Feedback:
The amount recovered would be equal to 20% of 11.5 lakh, i.e. ₹2.3 lakh. However, X is defined as the money lost by the bank. So, the amount lost would be equal to the total money exposed, i.e. ₹11.5 lakh, minus the money recovered, i.e. ₹2.3 lakh. That would mean that the money lost = 11.5 - 2.3 = ₹9.2 lakh.


Now, the bank has the following data -

Defaulter/Non-defaulter	   Probability   	X (Money Lost by Bank)
Defaulter	0.007	₹9.2 lakh
Non-defaulter	0.993	0
What would be the expected loss (expected value of the money lost by the bank)?


₹6440
Feedback:
The random variable X has two possible values, 9.2 lakh for when the customer defaults, and 0 for when the customer doesn’t. So, the Expected value = 9.2 lakh*P(X = 9.2 lakh) + 0*P(X=0) = 9,20,000*(0.007) + 0*(0.993) = 6,440


Expected Loss
So, in general, what would be the expected loss?


PD*EAD*(1-R)
Feedback:
X can take two values. When the customer defaults, X = EAD - (EAD*R) = EAD*(1-R). When she/he doesn’t, X = 0. So, the Expected value = EAD(1-R)*P(X = EAD(1-R)) + 0*P(X=0) = EAD*(1-R)*PD + 0





