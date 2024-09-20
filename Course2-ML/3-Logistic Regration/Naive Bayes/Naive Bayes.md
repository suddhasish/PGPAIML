# Conditional Probability and Its Intuition
Welcome to the first session of ‘Naive Bayes’!


You heard in the module introduction video that the basis of the Naive Bayes algorithm is Bayes’ theorem, and that is what this session is all about. But before you get into Bayes’ theorem, let's hear from Prof. Dinesh about conditional probability and try to understand its intuition.


So, you now understand the intuition behind conditional probability. In the next lecture, Prof. Dinesh will elaborate the notion of this kind of probability more formally.

Conditional probability is needed to understand relative probabilities, which is more often the case in the real world scenarios instead of looking into the absolute probability of events in isolation.




# Bayes' Theorem

In this section, you will understand Bayes’ Theorem for calculating the conditional probability. The example we will use now is something almost all of us can relate to which is cricket.

While watching cricket matches on TV, you may have seen statistics similar to this: “India wins 70% matches when Tendulkar scores a century.” Sounds like conditional probability? This is a classic example of how conditional probability can be used to estimate the chances of an event taking place, given certain other events that have happened.  

Suppose that India plays 100 matches, out of which it wins 60 and loses 40. Also, Sachin Tendulkar plays these 100 matches, scores a century in 12 of them, and doesn't score a century in the rest 88.

To make things interesting, you also have this additional information: out of the 60 games that India wins, Sachin scores a century in 10, and out of the 40 games that India loses, Sachin scores a century only in two.

Let us look at how the two-way contingency matrix will look like for the above case :

India Win	India Lose	Total
Sachin Scores a Century	10	2	12
Sachin Doesn't Score a Century	50	38	88
Total	60	40	100
 Q1)
Now, can you answer this question: what is the probability that India wins, given that Sachin has scored a century?

Try attempting the question before moving on to the video.

The total sample space will be the total number of matches played by India and Sachin, i.e. 100, and the favourable outcomes will be the number of matches in which both India won and Sachin scored a century, i.e. 10.

Q2) 

What is the probability of India losing the match AND Sachin not scoring a century? ( Answer expected in X.XX format)

The total sample space will be the total number of matches played by India and Sachin, i.e. 100, and the favourable outcomes will be the number of matches in which both India lost and Sachin did not score a century, i.e. 38.

Bays theorm:

P(A∩B) =  P(A|B)  * P(B)
P(A|B) = P(A∩B) / P(B)

P(A∩B) =  P(B|A)  * P(A)

P(A|B) = P(B|A) * P(A) / P(B) 

---

You learnt some important concepts related to Bayes’ theorem, i.e. conditional probability and joint probability.
Let’s revise the concepts you have just learnt using the spam-ham example discussed earlier. Let’s define the events A and B as follows:

A: The email is spam

B: The email contains the word ‘viagra’

Now, based on the above definition, solve the questions given below.




---

Bayes Theorem and Its Building Blocks
What type of probability is ‘the probability that an email which contains the word ‘viagra’ is spam’?
Ans: Conditional probability 

---
Bayes Theorem and Its Building Blocks
What type of probability is ‘the probability that an email contains the word ‘viagra’ and it is spam’?

Joint Probability

---
Bayes Theorem and Its Building Blocks
What is the symbolic notation of conditional probability?

P(A|B)

---
Bayes Theorem and Its Building Blocks
What is the symbolic notation of joint probability?

P(A∩B)



#Summary
In this segment, you have understood the theoretical concepts behind Bayes theorem and its building blocks i.e conditional probability, joint probability, etc.

 

You also understood how Bayes' theorem can be derived using joint and conditional probability using a two-way contingency table example.

 

In the next session, you will understand how Naive Bayes works with categorical data and different terminologies used in Naive Bayes.

 

Additional Content - Soft Skills:
Navigate here to access the soft skills content related to the Problem Solving.



Graded Questions
 

Courses Data Science (DS) Machine Learning(ML) Deep Learning(DL) Big Data(BD) Artificial Intelligence (AI) Total

Male 80 60 40 50 30 260

Female 70 40 50 70 10 240

Total 150 100 90 120 40 500

The contingency table above shows the number of females and males who joined specific programs. For example, it shows that 70 females joined the Data Science program and that 40 males joined the Deep Learning program. Also, notice that the table shows the totals in the last row and column, respectively.

You have a total of 240 females and 260 males in the dataset. This is a total of 500. Finally, the table also shows the totals for specific programs. For example, 150 people joined the Data Science program, 100 joined Machine Learning, and so on.

Q1) Given this contingency table, what is the probability that a randomly selected person joined Data Science?

 Feedback:
The table shows you that 150 people joined Data Science out of the total 500 people who are part of the data.

Therefore, P(Person who joined DS) = 150/500 = .3 (or 30%).

q2) Given this contingency table, what is the probability that a randomly selected female joined DS? In other words, what is the probability of a person joining DS, GIVEN that she is female?

P(A|B) = P(A∩B) / P(B) = (70 / 500 )(prob of be female and select ds)/ 240 / 500 (prob of being female)= 70 /240 


Q3) Consider a set containing all DL students OR all male students. What is the Probability that a randomly selected person will belong to this set?

Hint: Use the formula: (A or B) = p(A) + p(B) – p(A and B)


310
500

✓ Correct
Feedback:
This question deals with a probability concept called the ‘OR’. There is a formula for OR, which is — P(A OR B) = P(A) + P(B) – P(A AND B)

In this example, you’re looking at two things: DL and Male.

So, the question asked is —P(DL OR Male) = P(DL) + P(Male) – P(DL AND Male)

Using the table in the question description, you see that —P(DL) = 90/500

 

P(Male) = 260/500

 

P(DL AND Male) = 40/500

 

Therefore ...

P(DL OR Male) = P(DL) + P( Male) – P(DL AND Male)

= 90/500 + 260/500 – 40/500 = (90 + 260 – 40)/500 = 310/500 = .62 or 62%

 

**Now, why do you subtract the probability of (Male and DL)? The answer is that when you count all the males and then count all the people who joined DL, there is an overlap because some males joined DL. This means you counted them twice, and so you have to subtract the extra count.


Q4) Graded Question
What is the probability of a student being a female AND an AI student?

Hint: Use the formula: 

( P(A and B) ) is the probability of a student being both a female and an AI student.
( P(A | B) ) is the probability of a student being a female given that they are an AI student.
( P(B) ) is the probability of a student being an AI student.


P(A AND B) = P(A | B) * P(B) = 10/40 * 40/500 = 10 / 500

--

Here, the question is asking for P(Female AND AI).

P(A AND B) = P(A | B) * P(B)

This is read as the probability of A GIVEN B times the probability of B. When A and B are INDEPENDENT, P(A AND B) = P(A | B) * P(B) = P(A) * P(B).

Here, P(Female | AI Student) = 10/40. i.e. If you know that 40 students are AI students, then 10 of them are female.

P(AI Student) = 40/500

Therefore, P(Female AND AI Student) = P(Female | AI Student) * P(AI Student) = 10/40 * 40/500 = 10/500 = .02 or 2%.

You can also do this directly from the table, without the formula:

P( Female AND AI Student) = 10/500 = .02 or 2%

The two answers are identical, and there are just two ways to solve the question.


Q5)  What is the probability of a Deep Learning (DL) student being a male?

40/90 * 90/500 = 40 /500

Ans:

40/90

Feedback:
Question is asking to determine P(M|DL). We know from the chain rule that

P(A and B) = P(A|B)*P(B)

Therefore P(A|B) = P(A and B) / P(B)

Now from the given table P(M and DL) = 40/500  and P(DL) = 90/500.

So P(M|DL) = P(M and DL)/P(DL) = (40/500)/(90/500) = 40/90.

In fact we didn't need to do all these.

As soon as we are talking about only DL students, we are talking about only 90 students. Now what is the probability of any student from this 90 students being a male. As there are 40 males in these 90 students, the probability of selecting a male is 40/90.

---
# Naive Bayes - With One Feature

Welcome to the second session of ‘Naive Bayes’. In this session, you will implement Naive Bayes on a mushroom dataset. So, let's have a quick glance at the structure of the dataset.

Please find the Mushroom Dataset here 


You will now implement Naïve Bayes on this mushroom dataset and try to classify a new test point into either of the two classes – edible or poisonous. 
As the name suggests, the Naive Bayes algorithm uses Bayes’ theorem to classify new test points. But, how exactly does it do this? Let’s find out.


Naïve Bayes is a probabilistic classifier that returns the probability of a test point belonging to a class, using Bayes’ theorem. As you learned previously, Bayes’ theorem is defined as —

P(Ci|x)=P(x|Ci)P(Ci)P(x) , where Ci
 denotes the classes, and X denotes the features of the data point.

Probabilities are calculated simply by counting the number of instances/occurrences for categorical data.

The effect of the denominator P(x) is not incorporated while calculating probabilities as it is the same for both the classes and hence, can be ignored without affecting the final outcome.

The class assigned to the new test point is the class for which  
P(Ci|x) is greater


# Comprehension
Comprehension: Naive Bayes With One Feature

Table 1: Mushroom Dataset with One Feature
S.No	Type of mushroom	Cap shape
1.	Poisonous	Convex
2.	Edible	Convex
3.	Poisonous	Convex
4.	Edible	Convex
5.	Edible	Convex
6.	Poisonous	Convex
7.	Edible	Bell
8.	Edible	Bell
9.	Edible	Convex
10.	Poisonous	Convex
11.	Edible	Flat
12.	Edible	Bell
 

Consider the table shown above.  There are two types of mushrooms, edible and poisonous, which is the target (dependent) variable.  They have various kinds of cap-shapes. Out of the total 12 mushrooms, eight are edible and four poisonous.

 
You want to train Naive Bayes using this data so that it can predict whether a given (new) mushroom is edible or poisonous. The task is to classify a mushroom as edible/poisonous.

Say you represent the two class labels as C_{k}, where k = 1 represents edible, and k = 2 represents poisonous. The task is to predict the probability of a mushroom belonging to C1 or C2 using the feature ‘cap-type’. You can represent the class either as C1, C2 or C = edible/poisonous.

 
The feature ‘cap-shape’ is represented by X, i.e. X can take the values CONVEX, FLAT, BELL, etc. In the following questions, you will break down each term of the Bayes Theorem and understand them individually.

 
 Q1) Probability calculation
The probability of a CONVEX mushroom being edible, P(C = edible | X = CONVEX) is given by:
P( X = CONVEX | C = edible) . P(C = edible) / P(X = CONVEX

Q2)  Probability calculation
The value of P(C = edible) is simply the number of edible mushrooms in the dataset divided by the total observations. What is the value of P( C = edible)?

P(edible) is the fraction of edible mushrooms in the data, which is 8/12.


So you noticed that P(C = edible) is 8/12 = 66.66%. This means that approx. 66.66% of all mushrooms are edible. Note that P(C = edible) appears in the numerator of the Bayes expression and this value is directly proportional to the chances of a mushroom being edible. Let’s understand the other two terms in the Bayes expression.


Q1) Probability calculation
Now let’s say you picked a new mushroom whose cap-shape is CONVEX. What are the chances of this happening, i.e. what is the value of P(X = CONVEX)?

P(X = CONVEX) is the fraction of convex mushrooms in the data. There are 8 convex mushrooms, thus it is 8/12.

Q2) Probability calculation
What is the probability of the mushroom being CONVEX given it is edible, i.e. P(X = CONVEX | C = edible)? This is the fraction of CONVEX mushrooms out of all the edible ones.

P(X = CONVEX | C = edible) = P(C = edible | X = CONVEX) . P(X = CONVEX) / P(C = edible) = 4/8 * 8/12) / 8/12 = 4/8

---

Q3) Probability calculation
In the previous questions, you have calculated that P(C = edible) is 8/12, P(X = CONVEX) is 8/12 and  P(X = CONVEX | C = edible) is 4/8.

What is the probability that the CONVEX mushroom is edible, P(C = edible | X = CONVEX)?


P(C = edible | X = CONVEX) = P( X = CONVEX | C = edible) . P(C = edible) / P(X = CONVEX)

= (4/8).(8/12) / (8/12)

= 50%


Q4) Probability calculation
In the previous question, you found the probability of the CONVEX mushroom being edible. What is the probability of the CONVEX mushroom being poisonous, P(C = poisonous | X = CONVEX)?



4/8
✓ Correct
Feedback:
Since a mushroom can either be edible or poisonous, P(C = poisonous | X = CONVEX) is 1 - P(C = edible | X = CONVEX) = 1 - 4/8 = 4/8.

Q5) 

Probability calculation
What are the chances of a random mushroom being poisonous, i.e. P(C = poisonous)?


4/12
✓ Correct
Feedback:
There are 4 poisonous mushrooms out of 12.

Q6) Probability calculation
What are the chances of a mushroom being CONVEX given it is poisonous, i.e. P(X = CONVEX | C = poisonous)?

1
✓ Correct
Feedback:
P(X = CONVEX | C = poisonous) means out of all the poisonous mushrooms, how many are CONVEX. Out of the total 4 poisonous mushrooms, all the 4 are convex. Thus, it is 4/4.

Let’s analyse the results of this problem:

 

The probabilities of a CONVEX mushroom being edible and poisonous are both 50%. The probability of a mushroom being edible, P(C = edible | X = CONVEX) is

 

P( X = CONVEX | C = edible) . P(C = edible) / P(X = CONVEX)

= (4/8).(8/12) / (8/12)

= 50%

 

Similarly, the probability of the mushroom being poisonous, P(C = poisonous| X = CONVEX) is

 

= P( X = CONVEX | C = poisonous) . P(C = poisonous) / P(X = CONVEX)

= (4/4).(4/12) / (8/12)

= 50%

 
----

Note that the denominator is common in both calculations, i.e. P(X = CONVEX) = 8/12, and thus you do not need to calculate it. You can simply compare the numerators and conclude the classes based on that:

 

Edible: P( X = CONVEX | C = edible) . P(C = edible) =  (4/8).(8/12) = 4/12 = 33.33%

Poisonous: P( X = CONVEX | C = poisonous) . P(C = poisonous) =  (4/4).(4/12) = 4/12 = 33.33%

 

Since both numerators are 4/12, you cannot classify the CONVEX mushroom as edible or poisonous (if you consider 50% as the threshold probability for classification). The fundamental concept is that you only need to compare the numerators for the two classes and assign the class based on that.

 

Let’s now break down the Bayes theorem. The 50% probability that the CONVEX mushroom is edible (or poisonous) is a result of three probabilities. P(edible | CONVEX) is:

Proportional to P(edible), which tells us how abundant edible mushrooms are; if P(edible) is high, then P(edible | CONVEX) will be high simply because edible mushrooms are abundant!  
P(edible) is 66.66% and P(poisonous) is 33.33 %
This pushes the favour towards edible since they are in abundance
Proportional to P(CONVEX | edible), which explains how likely you are to find a CONVEX mushroom if you separately consider all the edible ones;
P(CONVEX | edible) is 50% and P(CONVEX | poisonous) is 100%
This pushes the favour towards poisonous since all poisonous mushrooms are CONVEX
Inversely proportional to P(CONVEX); this term cancels out while comparing the two classes
 

Thus, the numerators are equal because of the product of two probabilities balances each other out.

P(edible) = 66.66% \times  50% = 33.33%

P(poisonous) = 33.33% \times 100% = 33.33%

 


# Conditional Independence in Naive Bayes
In the previous segment, you understood the basic idea behind the working of Naive Bayes and how it is implemented on categorical data consisting of one feature and one target variable. In this case, the calculations for solving the classification problem are very simple as the probabilities can simply be calculated by counting. In this segment, you will understand how Naive Bayes would work if there are more than one feature in the data set.

Please find the Mushroom dataset here 


Naïve Bayes follows an assumption that the variables are conditionally 
independent given the class 
i.e. P(X = convex,smooth | C= edible) can be written as P(X=smooth | C=edible) *  P(X=convex | C=edible). 

The terms P(X=smooth | C=edible) and P(X=convex | C=edible)

is simply calculated by counting the data points. 
Hence, the name “Naïve” because in most real-world situations the variables are not conditionally independent given the class label but most of the times the algorithm works nonetheless.

Let us say you are trying to compute 
P(A and B | C). If P(A | C) is the same for all values of B and P(B | C) is the same for all values of A, 
then there is conditional independence between A and B, given C. 

This is when P(A and B | C) = P(A | C) x P(B | C), implying that A is not conditioned on B or vice versa.

Despite this assumption, Naive Bayes has proven to work very well in some cases, such as text classification. You'll study an example of classifying emails into spam/ham in the next session.

Comprehension - Naive Bayes with Multiple Features

Table 2: Mushroom Dataset
S.No	Type of Mushroom	Cap.shape	Cap.surface
1.	Poisonous	Convex	Scaly
2.	Edible	Convex	Scaly
3.	Poisonous	Convex	Smooth
4.	Edible	Convex	Smooth
5.	Edible	Convex	Fibrous
6.	Poisonous	Convex	Scaly
7.	Edible	Bell	Scaly
8.	Edible	Bell	Scaly
9.	Edible	Convex	Scaly
10.	Poisonous	Convex	Scaly
11.	Edible	Flat 	Scaly
12.	Edible	Bell	Smooth
 

 

Refer to the table above for the questions that follow. The first two columns are same as before. The third column is cap.surface - it is the second, newly added feature. The task is to predict the Type.of.mushroom given its two features.

 

In the multivariate case, the feature X is written as X = (cap.shape, cap.surface). Let us say if you take a mushroom having cap.shape = CONVEX and cap.surface =  SCALY, the probability of it being edible is expressed as:

 
1) P(C = edible | X = CONVEX, SCALY) =  P(X = CONVEX, SCALY | C = edible) * P(edible) / P(X = CONVEX, SCALY)

You can similarly write the expression for P(C = poisonous | X = CONVEX, SCALY) and compare that with P(C = edible | X = CONVEX, SCALY) and conclude the result. Recall that you do not need to calculate the denominator because it is same for both the edible and the poisonous class.

Useful numbers:

Number of edible mushrooms = 8

Number of poisonous mushrooms = 4

Ans: P(edible) x P(CONVEX | edible) x P(SMOOTH| edible)

2) 

Calculating conditional probability
What is P(CONVEX | edible)?

4/8

3) Calculating conditional probability
What is P(SMOOTH| edible)?

Feedback:
Out of the 8 edible mushrooms, 2 are smooth.

4) Calculating conditional probability
What is P(CONVEX | poisonous)?

1

5) Calculating conditional probability
What is P(SMOOTH| poisonous)?

Feedback:
Out of 4 poisonous mushrooms, 1 is SMOOTH.

6)
Classifying a mushroom
In the previous questions, you have calculated that:

What is P(CONVEX | edible) = 4/8

P(SMOOTH| edible) = 2/8

P(CONVEX | poisonous) = 1 and

P(SMOOTH| poisonous) = 1/4


If all mushrooms above 50% probability of being edible are classified as edible, is the CONVEX, SMOOTH mushroom edible?


P(C = edible | X = CONVEX, SMOOTH) = 

 P(C = edible | X = CONVEX, SMOOTH) 
 =  P(X = CONVEX, SMOOTH | C = edible) * P(edible) / P(X = CONVEX, SCALY)
 =  P(CONVEX|C=edible)*P(SMOOTH|C=edible) * P(edible)
 = 4/8*2/8*8/12 = 0.0833

---
Cannot be decided, it is a tie

✓ Correct
Feedback:
P(edible | CONVEX, SMOOTH) = P(edible).P(CONVEX | edible).P(SMOOTH| edible)/denominator = (8/12)(4/8)(2/8)/d = 1/12d

P(poisonous | CONVEX, SMOOTH) = P(poisonous).P(CONVEX | poisonous). P(SMOOTH| poisonous)/denominator = (4/12)(1)(1/4)/d = 1/12d.

Since both numerators are equal to 1/12d, this mushroom cannot be classified with a 50% threshold. Although if you would take a higher threshold, like 60% (which is reasonable since you don't want to take responsibility of people eating poisonous mushrooms), then it will be classified as poisonous. Why? Because, when you set the threshold as 60%, you want the probability of edible|CONVEX,SMOOTH to atleast 60%.
---

# Deciphering Naive Bayes
You saw how conditional independence lets you calculate the class probability in cases where you have more than one feature. Now, in this segment, you will deal with the original five variable problem, where the new test point has the following features:  

Cap Shape = Convex
Cap Surface = Smooth
Cap Colour = White
Bruises = Yes
Odour = None
Here the objective is to classify it into edible or poisonous class. Let's see how that can be done

Please find the Mushroom dataset here.


Now that you know how to classify a data point with five features, you can generalise this classification rule for any number of features in the dataset.  In the next lecture, you will understand the importance and meaning of each probability term in the Bayes theorem and how each term affects the classification

Again, Bayes theorem is defined as: 


P(C_{i}) is known as the prior probability. It is the probability of an event occurring before the collection of new data.  Prior plays an important role while classifying, when using Naïve Bayes, as it highly influences the class of the new test point.
P(X/C_{i}) represents the likelihood function. It tells the likelihood of a data point occurring in a category. The conditional independence assumption is leveraged while computing the likelihood probability.
The effect of the denominator P(x) is not incorporated while calculating probabilities as it is the same for both the classes and hence, can be ignored without affecting the final outcome.
P(C_{i}/X) is called the posterior probability, which is finally compared for the classes, and the test point is assigned the class whose Posterior probability is greater.
Prior, Posterior and Likelihood
Let’s understand the terminology of Bayes theorem.

 

You have been using 3 terms: P(Class = edible / poisonous), P(X | Class) and P(Class | X). Bayesian classification is based on the principle that ‘you combine your prior knowledge or beliefs about a population with the case specific information to get the actual (posterior) probability’.

P(Class = edible) or P(Class = poisonous) is called the prior probability
This incorporates our ‘prior beliefs’ before you collect specific information. If 90% of mushrooms are edible, then the prior probability is 0.90. Prior gets multiplied with the likelihood to give the posterior. In many cases, the prior has a tremendous effect on the classification. If the prior is neutral (50% are edible), then the likelihood may largely decide the outcome.

P(X|Class) is the likelihood
After agreeing upon the prior, you collect new, case-specific data (like plucking mushrooms randomly from a farm and observing the cap colours). Likelihood updates our prior beliefs with the new information. If you find a CONVEX mushroom, then you’d want to know how likely you were to find a convex one if you had only plucked edible mushrooms.

 

If  P(CONVEX| edible) is high, say 80%, implying that there was an 80% chance of getting a convex mushroom if you only took from edible mushrooms, this will reflect in increased chances of the mushroom being edible.

 

If the likelihood is neutral (e.g. 50%), then the prior probability may largely decide the outcome. If the prior is way too powerful, then likelihood often barely affects the result.

P(Class = edible | X) is the posterior probability
It is the outcome which combines prior beliefs and case-specific information. It is a balanced outcome of the prior and the likelihood.

 

If Zimbabwe takes 3 Australian wickets in the first over in a world cup, would you predict Australia to lose? Probably not, because the prior odds are way too strong in favour of Australia. They’ve never lost to Zimbabwe in a world cup! The likelihood, though it may be high, gets balanced by the prior odds (Australia’s prior odds may even be 99%!) to give you the correct posterior.

 

Comprehension - Naive Bayes with Multiple Features:

Please use the table data to answer the questions below:

Table 3: Mushroom Dataset
S.No	Type of Mushroom	Cap shape	Cap surface
1.	Poisonous	Convex	Scaly
2.	Edible	Convex	Scaly
3.	Poisonous	Convex	Smooth
4.	Edible	Convex	Smooth
5.	Edible	Convex	Fibrous
6.	Poisonous	Convex	Scaly
7.	Edible	Bell	Scaly
8.	Edible	Bell	Scaly
9.	Edible	Convex	Scaly
10.	Poisonous	Convex	Scaly
11.	Edible	Flat 	Scaly
12.	Edible	Bell	Smooth


q1)

Likelihood calculation
Say you consider a (CONVEX, SCALY) mushroom. The likelihood is higher for it being:


Feedback:
Likelihood is P(X = (CONVEX, SCALY) | Class). Class = edible: P(CONVEX | Edible).P(SCALY | EDIBLE) = (4/8)(5/8) = 20/64 = 31.25 % Class = poisonous: P(CONVEX | poisonous).P(SCALY | poisonous) = (4/4)(3/4) = 75 %

Q2) Likelihood Calculation
The values of P(X|Class). P(Class) where X = (CONVEX, SCALY) for both classes (edible and poisonous) are respectively:

Edible = 20.8 %; Poisonous = 25.0 %
✓ Correct
Feedback:
Edible: P(CONVEX | Edible). P(SCALY | EDIBLE). P(Edible) = (4/8)(5/8)(8/12) = 20.8% , Poisonous: P(CONVEX | poisonous). P(SCALY | poisonous). P(Poisonous) = (4/4)(3/4)(4/12) = 25%


Q3) Choose the correct statement
For the (CONVEX, SCALY) mushroom:

The prior is in favor of edible; posterior in favor of poisonous
✓ Correct
Feedback:
Prior is 8/12 and 4/12 for edible and poisonous respectively; posterior is 20.8% and 25%.


Summary
In the previous segments, you have understood the theoretical concepts behind naive Bayes and have also understood how it classifies using the mushroom dataset. You also got to know about the different terminologies used in Naive Bayes.

 

For a mathematical understanding and the derivation of maximum-likelihood (ML) estimates for the Naive Bayes model, it's highly recommended to check out this session.

In the next session, you will understand how Naive Bayes is used in Text Classification and also learn its implementation in Python.



---

Likelihood Calculation
Consider an email with the vector of features X = (free, data, weekend, click). What is the likelihood, P(X | spam)?


spam|free * spam | data * spam|weekend * spam|click * P(spam) = 2/3 * 1/5 * 2/3 * 7/15 =  

4/ 2401
✓ Correct
Feedback:
P(X | spam) = P(free|spam). P(data|spam). P(weekend | spam). P(click|spam) = (2/7)(1/7)(1/7)(2/7) = 4/2401



Q1) Consider an email with the vector of features X = (free, data, weekend, click). What is the likelihood, P(X | ham)?

1/8 * 3/8 * 1/8 * 1/8 


2/ 4096
✓ Correct
Feedback:
P(X | ham) = P(free|ham). P(data|ham). P(weekend | ham). P(click | ham) = (1/8)(2/8)(1/8)(1/8) = 2/4096.

Q2) Calculating conditional probability
The value of P(X|Class). P(Class) for class = spam for X = (free, data, weekend, click)?



Feedback:
P(class = spam| X) = P(class = spam). P(X | class = spam) = (7/15)(4/2401).

Q3) Posterior Probability
What is the posterior for class = ham (i.e. without division by denominator) for the feature vector  X = (free, data, weekend, click)?

(2/4096)(8/15)
✓ Correct
Feedback:
P(class = ham| X) = P(class = ham). P(X | class = ham) = (8/15)(2/4096).

Q4) 


Question 2
What is the sensitivity of the model?

You have worked on a small data set in the previous questions. Let’s say that you run your predictions on a larger data set with 1000 test points and get the following table of predictions (confusion matrix).

Figure 5 - Confusion Matrix
Figure 5 - Confusion Matrix
The positive class is spam. To evaluate the model, you will need to check the accuracy, sensitivity (rate of true positives) and specificity (rate of true negatives).

TP (True positive)= 440
FN (False Negetive) = 40 
Sensitivity = TP / (TP + FN)

440 / 480

✓ Correct
Feedback:
440 out of 480 spams have been classified correctly.


Q5)

What is the specificity of the model?


TN =  True Negetive =  500
FP = False positive = 20

SPC (Specificity) = TN / (FP + TN) = 500 / 20+500


Feedback:
The fraction of correctly predicted hams = 500 / (500 + 20).


Q6) Question 4
Given that you do not want to misclassify any genuine emails, which metric should be as high as possible?

Specificity
✓ Correct
Feedback:
Fraction of correctly classified hams is measured by specificity (true negative rate).


