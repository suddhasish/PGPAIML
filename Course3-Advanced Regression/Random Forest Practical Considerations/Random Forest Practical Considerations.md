# Ensembles

In this session, you will learn about random forests, one of the most popular algorithms in machine learning. Random forests use a technique known as bagging, which is an ensemble method. So, before you learn about random forests, let's first understand ensembles.


An ensemble refers to a group of things viewed as a whole rather than individually. In an ensemble, a collection of models is used to make predictions, rather than individual models. Arguably, the most popular in the family of ensemble models is the random forest, which is an ensemble made by the combination of a large number of decision trees.

 

In principle, ensembles can be made by combining all types of models. An ensemble can have a logistic regression, a neural network, and a few decision trees working in unison.

 

Now, before you understand how ensembles work, the following questions may arise:

- How does a collection of models work better than individual models?
- How do you choose individual models to form an ensemble such that it is better than any of the individual models?
In the following lectures, you will be able to find answers to these questions.



# Diversity and Acceptability

Ensembles of models are somewhat analogous to teams of individual players. If you were to choose a football team, you would take the following two steps:

- Choose people with different skill sets, such as defenders, attackers and a goalkeeper, to ensure diversity
- Choose good players, i.e., ensure that all players are acceptable from the point of view of their skill sets (and at least better than a regular person)

Diversity ensures that the models serve complementary purposes, which means that the individual models make predictions independent of each other.

For example, a random forest is an ensemble with a large number of trees as individual models. Diversity ensures that even if some trees overfit, the other trees in the ensemble will neutralise the effect. The independence among the trees results in a lower variance of the ensemble compared to a single tree. Ensembles are more robust to the choice of the training data which makes them more stable and less prone to high variance and overfitting. We will soon discuss how the learning algorithm is designed to achieve independence and how it is beneficial.

**Acceptability** implies that each model is at least better than a random model. This is a pretty lenient criterion for each model to be accepted into the ensemble, i.e., it has to be at least better than a random guesser.

Now, let’s watch the following video and hear Rahim explain the different ways in which you can bring in diversity.


There are a number of ways in which you can bring diversity among your models you plan to include in your ensemble.

- 1) Use different subsets of training data
- 2) Use different training hyperparameters
- 3) Use different types of classifiers
- 4) Use different features


Now you have understood the different ways to bring in diversity. But what makes an ensemble better than an individual model? Let’s understand this in the next segment. But first, let's answer some questions based on your learnings so far.

Q1)  Random Model
A binary classification model under consideration is better than a random model when it:

Makes correct predictions with a probability that is statistically better than that of a random model, i.e., 0.5.

✓ Correct
Feedback:
Acceptability means that a model is not making any random guesses, the probability of success of which, i.e., P(success), is 0.50. Thus, we want models for which the probability of success is > 50%

Q2) Diversity
What happens if the models in your ensemble are not diverse enough?

Ans:


Since the models are not diverse, they might give somewhat similar results and hence the ensemble performance might not be much better than the individual models.

✓ Correct
Feedback:
More the diversity, more diverse will be the results in the ensemble and hence, the ensemble will be equipped to handle and make predictions for a more diverse range of attributes. If the diversity is reduced, the models will give similar results and hence the ensemble performance might not be much better than the individual models.

# Comprehension - Ensembles

How can you guarantee that if the two conditions of diversity and acceptability are fulfilled to make an ensemble, it will be better than any individual model? Let's hear about this in the next video from Prof. Raghavan.


# Idependence : 


