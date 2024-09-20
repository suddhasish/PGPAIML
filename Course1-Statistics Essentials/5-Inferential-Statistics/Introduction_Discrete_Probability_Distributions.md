# Introduction: Discrete Probability Distributions
Welcome to the session on ‘Discrete Probability Distributions’. In the last session, you learnt some basic concepts of probability, such as random variables, probability distributions, and expected value. Let’s now learn some slightly more advanced concepts.

 

In this session
In this session, you will learn about some probability distributions that are commonly used for discrete random variables, such as the binomial probability distribution and the uniform probability distribution. Also, you will learn the concept of cumulative probability which will be very useful in our next session on continuous probability distributions.

 

Prerequisites
It has been assumed in this session that you have knowledge of some basic rules of probability, i.e. multiplication rule and addition rule. Also, it is assumed that you have read upon combinatorics and know what the expression 
nCr
 represents.

 

You can brush up on these topics using the links given below -

Prerequisites for Session 2
You can also solve the practice questions provided in the Resources section.

Optional Questions for Session 2
Make sure you go through these concepts if you don’t remember them, otherwise you will find the session hard to follow.

 

Guidelines for in-module questions
Note that graded questions are given on a separate page labeled 'Graded Questions' at the end of this session. The questions in this session will adhere to the following guidelines:

experiment: A single 6-sided die is rolled. What is the probability of rolling a 2 or a 5?



Addition Rule: https://mathgoodies.com/lessons/addition_rules/

Mutiplication Rule: https://mathgoodies.com/lessons/independent_events/

**Probability Without Experiment - I:**

In the last session, we found the probability for certain events by conducting experiments.

Specifically, we asked 75 people to play the UpGrad red ball game. Based on the data of these people, we created a histogram or, in other words, a frequency distribution. Then, using this histogram, we created the probability distribution.

However, this is a lengthy process. Is there a shorter process for finding the probabilities, perhaps one that doesn’t need repeated experiments? Let’s see.

If there is 3 red ball 3 2 blue ball

P(1 Red ball in 1 trial) = Number of red ball / Number of total ball = 3/5 = 0.6 
P(Event1 and Event2) = P(Event1) * P(Event2)  # if both events are independent.
so P(2 red balls in 2 trial) = P( red ball in 1st trial) *  P( red ball in 2nd trial) = 0.6*0.6 = 0.36

* We are replacing the red ball after drawing it 


**Probability Without Experiment**
What is the probability that you would get this combination of balls after 4 trials? 
(One trial = taking out a ball, noting its colour, and putting it back in the bag.)
Note that the bag contains 2 blue and 3 red balls.

i.e., the combination Blue-Red-Red-Red.

P(1 Red ball in 1 trial) = Number of red ball / Number of total ball = 3/5 = 0.6 
P(1 blue ball in 1 trial) = Number of red ball / Number of total ball = 2/5 = 0.4 
so P(1 blue 3 red balls in 4 trial) = 0.4*0.6*0.6*0.6

**Prob of 3 red ball**

P(BRRR) = 0.4*0.6*0.6*0.6 = 0.0864
P(RBRR) = 0.6*0.4*0.6*0.6 = 0.0864
P(RRBR) = 0.6*0.6*0.4*0.6 = 0.0864
P(RRRB)= 0.6*0.6*0.6*0.4 = 0.0864

P(3 red ball) = P(X=3) = number of Combination * (prob of red)^3 * (prob of blue)^1   = 4 * 0.6 ^3 * 0.4 ^1 = 4*0.0864 = 0.3456


Addition Rule of prob = P(Event1 or Event2) = P(Event1) + P(Event2) 


Note : Addition rule is given for Mutually Exclusive events (not for independent events)

Hence, we have gone through the exercise of finding the probability without conducting any experiment. You saw that these theoretical (calculated) values of probability are actually quite close to the experimental values that we got. The small differences that you can notice exist because of the low number of experiments done.

**Probability Without Experiment - II**

Recall that we claimed that if we had done the UpGrad experiment many more times, then the resulting experimental probability distribution would have been even closer to the theoretical one.
As you can see, after playing the game a lot of times (~500 times), the experimental probability distribution starts to look similar to the theoretical one.
Similarly, you can simulate a coin flip and compare the theoretical distribution with the experimental one.

Now that you know how to find the probability without an experiment, you can calculate the probability for various combinations without much effort. For example, what if the bag for our game had, say, 4 red balls and only 1 blue ball? You don’t need to do the experiment 100 times or 500 times to find the answer. You can find it using a small calculator, the concepts of probability and, of course, your brain!

**Binomial Distribution**
Previously, we found the theoretical probability for our game and compared it with the experimental one. Finding the probability without conducting an experiment means that we can find the probability using just pen and paper and with minimal effort.

 

Now, let’s try to generalise it — let’s say that the probability of getting one red ball in one trial is equal to p. In that case, what would be the probability of all 4 balls being red? Let’s see that in the following video.

We are crring ot experiment 4 times or drawing ball 4 times .

P(X=4) = p*p*p*p
P(X=3) = 4*(p)*(p)*(p)*(1-p)

So, now we have this probability distribution for X (the number of red balls drawn after 4 trials), if the probability of getting a red ball in 1 trial is p:


X P(X=x)
0 (1-p)^4
1 4p(1-p)^3
2 6p^2(1-p)^2
3 4p^3(1-p)
4 p^4

Let’s now watch the following video to see how Prof. Tricha generalises it even further.

The number of combinations in which you could get r red balls and n-r blue balls is equal to ​
nCr​. So, the final probability will be

 n = Total trial
 each trial has 2 possible outcome 
 p = prob of success is same in all trials 
 nCr = n! / (r! * (n-r)!)

 P(X=r) = P(Getting r Success in n trial ) =  nCr(p)^r(1−p)^n−r​.

However, as Prof. Tricha said, there are some conditions that need to be followed in order for us to be able to apply the formula.

Total number of trials is fixed at n

Each trial is binary, i.e., has only two possible outcomes - success or failure

Probability of success is same in all trials, denoted by p

**Binomial Distribution (Examples):**
In the previous section, we listed down some conditions that are to be fulfilled for the binomial distribution to be applicable. Let’s take a few examples to understand these conditions in detail.


Binomial Distribution Applicable	Binomial Distribution Not Applicable
Tossing a coin 20 times to see how many tails occur	Tossing a coin until a heads occurs
Asking 200 randomly selected people if they are older than 21 or not	Asking 200 randomly selected people how old they are
Drawing 4 red balls from a bag, putting each ball back after drawing it	Drawing 4 red balls from a bag, not putting each ball back after drawing it

If you toss a coin 20 times to see how many tails occur, you are following all the conditions required for a binomial distribution. The total number of trials is fixed (20), and you can only have two outcomes, i.e. a tails or a heads. The probability of getting a tails is equal to 0.5 each time you toss the coin.

 

In a way, this is similar to drawing 20 balls out of a bag - 10 blue and 10 red, replacing each ball after drawing it, and seeing how many of the balls are red. Here, the probability of getting a red ball in one trial is 0.5.

 

When you toss a coin until a heads occurs, the total number of trials is not fixed. This is similar to taking out balls from the bag repeatedly until you draw a red ball. You can still find the probability of getting a heads in 1 trial, in 2 trials, in 3 trials etc. and so on, but you cannot use binomial distribution to find that probability.

 

In the second example, where binomial distribution is not applicable, the experiment does not have only two outcomes, but many. It is similar to taking out balls from a bag that contains red, blue, black, orange, and other colours of balls. The probability distribution for this experiment cannot be made using binomial distribution.

In the final example, the probability of the trials is not equal to each other. For example, the probability of drawing a red ball in the first trial is 
35
. Now, in the second trial, the probability of drawing a red ball would be equal to 
24 not35
, as the red ball taken out in the first trial was not put back. Hence, the probability of getting the combination Red-Red-Red-Blue, for example, would be 
35*24*13*22, which is not the value we got while deriving binomial distribution (35*35*35*25). Again, you cannot use binomial distribution to find the probability in this case.

In other words, binomial distribution is applicable in situations where there are a fixed number of yes or no questions, with the probability of a yes or a no remaining the same in all the questions.

Uniform Distribution:

All possible values has equal chance of happening.

So, you now understand that the binomial distribution is a very powerful distribution. To get an idea of what this probability distribution looks like, you can use the interactive app given below. This app shows you the probability distribution for a binomial distribution with n = 5 and p = 0.5. However, you can play around with the value of n and p to see how that changes the probability distribution. Don’t forget to zoom out or in as needed.


**Cumulative Probability**
In the previous example, we only discussed the probability of getting an exact value. For example, we know the probability of X = 4 (4 red balls). But what if the house wants to know the probability of getting < 3 red balls, as the house knows that for < 3 red balls, the players will lose and they will make money?

 

Sometimes, talking in less than is more useful, for example — how many employees can get to work in less than 40 minutes? Let’s explore how you can find the probability for such cases.


Clarification - The cumulative probability distribution table, shown in the above video (02:22 to 03:11) should be - 

x	F(x) = P(X<x)
0	0.0256
1	0.1792
2	0.5248
3	0.8704
4	1.0000
 

So, the cumulative probability of X, denoted by F(x), is defined as the probability of the variable being less than or equal to x.

 

In mathematical terms, you would write cumulative probability F(x) = P(X<x). For example, F(4) = P(X<4), F(3) = P(X<3).


Cumulative Probability
Let’s define X as the number of wickets Ishant Sharma would take in the next T20 match he plays. Also, the following is an incomplete table for cumulative probability based on previous experience:

x(Number of wickets taken by Ishant Sharma in a T20 Match)	  F(x)  
0	0.35
1	0.55
2	0.75

Feedback:
You know that F(2) i.e. P(X<=2) is 0.75.
Now, you have to find the probability of X being higher than 2, i.e. P(X>2). 

Notice that the sum of P(X<=2) and P(X>2) would be equal to 1, 

because their sum will cover all possible outcomes. Hence, P(X<=2) + P(X>2) = 1, which gives 0.75 + P(X>2) = 1. Hence, P(X>2) = 0.25.

The binomial distribution describes the result of n
 independent trials with probability p
. It is frequently used to model the number of successes in a specific number of identical binary experiments, such as the number of heads in five coin tosses.

PMF	Mean
(nx)px(1−p)n−x
np


Summary: Discrete Probability Distributions
We started with learning how to find probability without experiment, using basic concepts such as the addition and the multiplication rule of probability.

 

As a demonstration, we calculated the probability of getting 0, 1, 2, 3 and 4 red balls for our UpGrad red ball game. Then, we compared the values we got by theoretical calculations with the ones we got after the experiments in the first session. Recall that the values were quite similar.

Note : the heading name of below diagram should be Observed Probability Distribution vs Theoretical Probability Distribution.

Figure 2 - Observed vs Theoretical Probability Distribution
Figure 2 - Observed vs Theoretical Probability Distribution
However, they were not exactly the same, due to the low number of experiments we conducted (75). If we had done more experiments, the values would have been exactly the same (the values are exactly the same if the number of experiments approaches infinity).

 

Next, we generalised this probability. Specifically, we talked out the probability of getting r red balls after drawing n balls from a bag. Here, the probability of drawing a red ball in 1 trial was equal to p.

 

The probability distribution for this case is given by the following table (X = number of red balls drawn after playing the game once).

Figure 3 - Binomial Distribution
Figure 3 - Binomial Distribution
In general,


P(X=r)= nCr(p)r(1−p)n−r
 

This distribution is called the binomial distribution. It can be used to find the probability of any kind of event, if that event is a series of yes or no questions, with the probability of yes being the same for all questions.

 
Phrasing the conditions more formally, the binomial distribution can be used if, for an experiment:

The total number of trials is fixed

Each trial is binary, i.e. has only two possible outcomes, success and failure

The probability of success is the same for all the trials
 

Next, we discussed the cumulative probability of x, denoted by F(x), which is the probability that the random variable X takes a value less than or equal to x.

 

For example, we found F(2), the probability of getting 2 or fewer red balls in our UpGrad game. It was calculated as:

 
F(2) = P(X <= 2) = P(X = 0) + P(X = 1) + P(X = 2) = 0.0256 + 0.1536 + 0.3456 = 0.5248

Cumulative probability is a concept that we will use extensively in our next session on continuous random variables.



**Practice Questions:**
These questions are NOT graded.

 
Let’s say you get a job as a senior analyst at a food regulatory body such as the FSSAI. One of your tasks is to check if the amount of lead content in certain food products is within the permissible limit.

 

Recently, the company Kwick Foods filed a complaint against Sunshine, its competitor, that Sunshine’s ready-to-cook pasta contains excess quantities of lead.




Q&A
Practice Questions
These questions are NOT graded.

 

Let’s say you get a job as a senior analyst at a food regulatory body such as the FSSAI. One of your tasks is to check if the amount of lead content in certain food products is within the permissible limit.

 

Recently, the company Kwick Foods filed a complaint against Sunshine, its competitor, that Sunshine’s ready-to-cook pasta contains excess quantities of lead.


Suppose you take 10 random pasta packets from the market and get it tested for the amount of lead. It just so happens that you have picked out packets from a very defective batch, and there is a 5% probability that any pasta packet you select is going to be defective.

Let’s define X as the number of packets found to be defective after the 10 packets have been tested. What will be the expected value of X?

**Feedback:**
If X is defined as the number of pasta packets found to be defective after testing 10 packets, then X would follow a binomial distribution with n = 10 and p = 0.05. Now, you want to find the expected value, which would be equal to EV(X) = 0*P(X=0) + 1*P(X=1) + 2*P(X=2) + 3*P(X=3) + 4*P(X=4) + 5*P(X=5) + 6*P(X=6) + 7*P(X=7) + 8*P(X=8) + 9*P(X=9) + 10*P(X=10). Using a spreadsheet to calculate the individual probabilities, you can find that the expected value EV(X) = 0.5



Probablity = ∑(r*P(X=r))


Suppose a new cancer treatment has been discovered, claiming to increase the one year survival rate for pancreatic cancer to 40%. In other words, the probability that a patient suffering from pancreatic cancer would survive for at least one year after receiving this treatment is 40%.


Suppose a  hospital is planning to use this treatment for its pancreatic cancer patients.

Pancreatic Cancer Hospital
What is the probability that the number of patients that survive the first year after receiving the treatment would not be more than 2?

p(0)+p(1)+P(2) = 10C0*0.4^0*0.6^10 + 10C1*0.4^1*0.6^9 + 10C2*0.4^2*0.6^8 = 0.0060+0.0403+0.120     here its 3 mutually exclusive event 


Canculate NCR = https://www.calculatorsoup.com/calculators/discretemathematics/combinations.php

