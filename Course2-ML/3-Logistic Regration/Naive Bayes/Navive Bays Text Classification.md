In this session
You will learn about the Naive Bayes for text classification and understand how the classifier works in the background. 
Also, you will learn the python implementation of Naive Bayes for text classification problem.


Naive Bayes is commonly used for text classification in applications such as predicting spam emails, classifying text (e.g. news) into categories such as politics, sports, lifestyle etc.
In general, Naive Bayes has proven to perform well in text classification applications.

# Document Classifier - Pre Processing Steps

In this session, you will learn how to build a Naive Bayes document classifier, i.e. a model for classifying text into categories.  

Let’s first understand the problem statement and some necessary data preprocessing steps before building the actual classifier.

To summarise - you understood the data you are going to be working with and to convert the documents given into dictionary/vocabulary by removing ‘stop words’ which are not helpful for helping in document classification.

 

Before we begin the next video, try solving the following questions:


Great, you will now look  at how to use the vocabulary/dictionary to represent the given test documents by counting the occurences of various words. This is the way we represent the documents in Multinomial Naive Bayes.


Why this called bag of word:

It is because the sentences are broken down into words and the ordering doesn't matter anymore as if it were put in a bag and shuffled.

Let us now see the final video of this segment where the prof talks about few notations and document representation in an array format.


# Document Classifier - Worked out Example

You will now learn how to classify new documents into classes ‘cinema’  and ‘education’. Using a worked out example, you will understand how the Naive Bayes classifier assigns class labels to documents.

 Note : At 0:01, the spelling of word 'SEPERATING' should be 'SEPARATING'.

 

Note : At 4:28,It should be P(cinema|w1,w2,.......,wn) = P(w1,w2,......,wn|cinema) P(cinema)/ P(w1,w2,..........,wn) instead of P(cinema|w1,w2,.......,wn) = P(w1,w2,......,wn|class) P(class)/ P(w1,w2,..........,wn)

So now that we have formulated the problem in terms of prior, posterior and likelihood, let us see how this can be tabulated to make our calculations easier.


Now, let's understand the actual process of classification using Multinomial Naive Bayes Classifier.

NOTE: @4.45 min. P(Cinema|"great great story") is wrongly calculated as 0.007 instead of 0.0007

Bet you didn't see that issue coming, did you? We will see how to counter the zero probability issue in the next segment.



Feature Vector:
Suppose you have the following dictionary based on some training document narrating stories about love or action.
W1 W2 W3 W4 W5 W6 W7  W8 
bike couple fast furious tears love shoot songs

What will be feature vector of the document “A fast moving bike entered into the complex and shoot the couple.


1,1,1,0,0,0,1,0

✓ Correct
Feedback:
W4,W5,W6,W8 are not present , hence 0 for them and 1 for others is correct choice.


Q2)  Naive Bayes Classifier
Assume the following likelihoods i.e P(word|class) for each word being part of a positive or negative review of a hotel. 

 	Pos	Neg
i	0.09	0.16
loved	0.30	0.06
the	0.06	0.05
food	0.04	0.35
and	0.08	0.07
cleanliness	0.40	0.03
What class will Naive Bayes assign to the sentence “I loved the food and cleanliness.” if the priors of the classes are considered equal ( it is equivalent to not considering the prior )

Pos

✓ Correct
Feedback:
= + is Pos and - is Neg

P(I | +)P(loved|+)P(the|+)P(food|+)P(and|+)P(cleanliness |+) >

           P(I | -)P(loved|-)P(the|-)P(food|-)P(and|-)P(cleanliness |-)

Q3) Assume the following likelihoods i.e P(word|class) for each word being part of a positive or negative review of a hotel. 

Pos	Neg
i	0.09	0.16
loved	0.30	0.06
the	0.06	0.05
food	0.04	0.35
and	0.08	0.07
cleanliness	0.40	0.03
What class will Naive Bayes assign to the sentence “I loved the food and cleanliness.” if the prior probabilities for positive and negative  classes are considered 0.1 and 0.9 respectively


Neg

✓ Correct
Feedback:
 

+ is Pos and - is Neg

P(I | +)P(loved|+)P(the|+)P(food|+)P(and|+)P(cleanliness |+)P(+) <
P(I | -)P(loved|-)P(the|-)P(food|-)P(and|-)P(cleanliness |-)P(-)

# Laplace Smoothing

In the previous lectures, you came across the ‘zero probability problem’ - the probability of a word which has never appeared in a class (though it may have appeared in the dataset in another class) is 0.
You will now understand how a technique called ‘Laplace smoothing’ helps solve this problem.


Wasn’t that interesting? Did you notice how we could not assign any class label for our test document and got inconclusive results? That is where Laplace smoothing helps. How exactly does it help? The next video will help you understand that.

Note:     In the below video, the Expert mentions 'Educational' in the table whereas the word is 'education'.

You saw how Laplace smoothing helped solve the zero probability problem.

 

Please note that - If there are words occurring in a test sentence which are not a part of the dictionary, then they will not be considered as part of the feature vector since it only considers the words that are part of the dictionary. These new words will be completely ignored.

In the next segment, you will study a variant of the Naive Bayes model we were discussing so far - Bernoulli Naive Bayes.

# Quick Introduction to Bernoulli Naive Bayes

You saw that the most fundamental difference in Bernoulli Naive Bayes Classifier is the way we build the bag of words representation, which in this case is just 0 or 1. Simply put, Bernoulli Naive Bayes is concerned only with whether the word is present or not in a document, whereas Multinomial Naive Bayes counts the no. of occurrences of the words as well.


The whole worked out example is out of the scope of this course. But as optional reading, you can find it below:

# Python Lab - Education Or Cinema ?
In this segment, you will learn how to implement both Multinomial and Bernoulli Naive Bayes classifiers in python.
 

In the last lecture, we used Countvectorizer() which converted the documents into a set of unique words alphabetically sorted and indexed.
Now in the next lecture, we will be proceeding with the pre-processing steps required to fit a Naive Bayes model on it. 
 

Stop Words:
We can see a few trivial words such as 'and','is','of', etc. These words don't make any difference in classifying a document. These are called stop words. So we would like to get rid of them. We can remove them by passing a parameter stop_words='english' while instantiating Countvectorizer().


To Summarise, If we have a vast vocabulary of let's say 2000 or 3000 words, using a Sparse Matrix for Naive Bayes classifier will not be efficient. This is because a Sparse Matric has so many zeros and storing so many zeros in the memory is a waste of memory. Refer to the image below.

Sparse Matrix
Sparse Matrix
Now the way to get rid of these is know as a Compressed Sparse Row format. 

Compressed Sparse Matrix
Compressed Sparse Matrix
This representation can be understood as follows:

 

Consider first 4 rows of the output: (0,2), (0,5), (0,7) and (0,11). It says that the first document (index 0) has 7th , 2nd , 5th and 11th 'word' present in the document, and that they appear only once in the document- indicated by the right hand column entry.

Similarly, consider the entry (4,4) (third from bottom). It says that the fifth document has the fifth word present twice. Indeed, the 5th word('good') appears twice in the 5th document.

In the next lecture, we will finally build a Naive Bayes Classifier using the pre-processed data.

Note : At 1:19, Instructor mistakely told X_test is Compressed Sparse matric instead of X_test is not compressed sparse matric.


In the next segment, you will implement both Multinomial and Bernoulli Naive Bayes classifiers on a real dataset to classify SMSes as spam or ham.

# Python Lab - SMS Spam Ham Classifier : Multinomial

We had mentioned earlier that Naive Bayes finds applications in spam detection. Let’s now see a full-fledged implementation of the Naive Bayes classifier in python on the ‘SMS dataset’.
We’ll build an SMS spam classifier and compare the results of Multinomial NB and Bernoulli NB. For detailed information about the dataset used you can refer to the link. Please find the Spam Ham dataset here and the code file here.


In the last lecture, we pre-processed our real SMS: Spam/Ham classifier data. Now in the next lecture, we will be building and evaluating the model based on Specificity, Sensitivity and ROC curve.
Let's understand them in detail.

---

Sensitivity implies that out of all the actual Spam's, how many of them were correctly predicted by the model as Spam. 

Specificity implies that out of all the genuine SMS's, how many of them were correctly predicted as legitimate by the model.

If we look back to the problem statement, We are fine if some of the Spams are classified as Hams, but it will not be good if an important Ham is classified as Spam by our model. So our motive is to maximise Specificity.

ROC Curves are used to see how well your classifier can separate positive and negative examples and to identify the best threshold for separating them.

 The area under the ROC Curve shows how far the curve from the base line. For the baseline, it's 0.5, and for the perfect classifier, it's 1. In our case the AUC obtained was 99% which is very good. 

# Python Lab - SMS Spam Ham Classifier : Bernoulli

In the last section, we looked at the Naive Bayes Multinomial Classifier to classify the SMS Spam/Ham data. In this session, we will be using the same dataset but will be fitting a Bernoulli Naive Bayes Classifier.

Please find the code file here.

So, you have almost reached the end of the module now and must be already feeling like a Naive Bayes expert. Aren't you?

Did you note how business objectives govern our model evaluation and selection? In this case, you wanted the False positives i.e the ham being classified as spam as low as possible which you could achieve by using Bernoulli Naive Bayes classifier even though the overall accuracy and sensitivity was less than Multinomial Naive Bayes classifier.


Consider a naive Bayes model based on the above training documents with the classes Hot and Cold and the following conditional probability table of the words given a class:

Word

P(word | Hot)

P(word | Cold)

Coffee

6/16

1/6

cold

0

2/6

espresso

1/16

0

hot

P

0

pepsi

0

Q

soup

3/16

0

sprite

R

1/6

tea

4/16

1/6

Q1)  Bayes Theorem
A bag A contains 3 Red and 4 Green balls and another bag B contains 4 Red and 6 Green balls. One bag is selected at random and a ball is drawn from it. If the ball drawn is found Green , find the probability that the bag chosen was A.

20/41

Step 1:

Let E1, E2 denote the events of selecting bag A and B respectively. 

Then P(E1) = P(E2) = 1/2.

 Let G denote the event that the ball chosen from the selected bag is Green.

Then we have to find P(E1/G).

Step 2:

By hypothesis P(G/E1) = 4/7 and  P(G/E2) = 6/10

By Bayes theorem P(E1/G) = (P(G/E1)*P(E1))/P(G)

 Now what is P(G) ?  P(G) = P(G,E1) + P(G,E2)

    = P(G/E1)P(E1) + P(G/E2)P(E2)

Therefore  P(E1/G) =  (P(G/E1)*P(E1))/P(G)

                    =P(G/E1)*P(E1)/P(E1)P(G/E1) + P(E2)P(G/E2)

=(4/7)x(1/2) / (1/2)x(4/7)+(1/2)x(6/10)=(4/14) / (4/14 + 6/20)=20/41



Q2) The bag A  contain 6 Green, 4 Blue ; B contains 4 Green, 6 Blue and C contains 5 Green, 5 Blue balls respectively. A bag is randomly selected  and a ball is drawn from it. If the ball drawn is Green, find the probability that it is drawn from bag A. 

P(G) = = P(G,E1) + P(G,E2) + P(G,E3) 

    = P(G/E1)P(E1) + P(G/E2)P(E2) + P(G/E3)P(E3) = 6/10*1/3 +  4/10*1/3+ 5/10*1/3  

    P(E1/G) =  (P(G/E1)*P(E1))/P(G) =  6/10 * 1/3 / 6/10*1/3 +  4/10*1/3+ 5/10*1/3 = 6/15 = 0.4 




    Q3) 
    Bayes Theorem
Courses

Data Science

(DS)

Machine Learning

(ML)

Deep

Learning

(DL)

Big

Data

(BD)

Artificial

Intelligence

(AI)

Total

Male

80

60

40

50

30

260

Female

70

40

50

70

10

240

Total

150

100

90

 

120

40

500

Given this contingency table, Determine if being Male and having joined Big Data course are INDEPENDENT?



Ans:

To prove that two variables (say A and B) are independent, we must show that

P( A AND B) = P(A | B) * P(B) = P(A) * P(B)

First, from the Contingency Table:

 

P(A AND B) is P( Male AND BD Student) = 50/500

 

P(A) = P(Male) = 260/500

P(B) = P(BD Student) = 120/500

P(A | B) = P(Male GIVEN BD Student) = 50/120



OK- now we have everything we need to check for independence:

P( A AND B) = P(A | B) * P(B) = P(A) * P(B)

P(A | B) * P(B)= P(Male | BD Student) * P(BD Student)

                     = 50/120 * 120/500 = 50/500

P(A) * P(B) = P(Male) * P(BD Student) = 260/500 * 120/500

As we can see P(Male | BD Student) * P(BD Student) not equal to P(Male) * P(BD Student)

So NO these are NOT independent.


   Q3) 

Let us first calculate the probability of a student being a Female student and a DL Student. We essentially want to calculate P(F and DL) . From the table we can see that there are 50 students who are both a Female and a DL students out of total 500 students hence P(F and DL) = 50/500=5/50.

Now the second probability is “probability of a Female student being a DL student” or P(DL |F). We are interested in the probability of a DL student given that the student is a Female. There are 240 Females out of which DL students are 50. Therefore P(DL|F) = 50/240=5/24

The statement is false.



