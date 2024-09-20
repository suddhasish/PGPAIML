# Introduction to Model Selection

In the previous course, you may have come across situations wherein a model performs well on training data but not on the test data. You would have also faced confusion regarding the model to be used for a given problem. For example, by now, you have learnt about many classification models. Given a problem that requires classification, how would you decide which model is the best?

 
Questions such as these frequently arise irrespective of the choice of the model, data or the problem itself. The aim of this session is to answer such questions.

As Professor Raghavan mentioned, in these sessions, you will learn about some thumb rules and some general pointers regarding the selection of appropriate models. This session is only a discussion on such thumb rules. In subsequent sessions, these rules will be applied in the context of various problems and algorithms. 


The central issue in all of machine learning is how do we extrapolate learnings from a finite amount of available data to all possible inputs ‘of the same kind’? Training data is always finite, and yet, the model is supposed to learn all about the task at hand from it and perform well on unseen data. 



Consider the car pricing data set in linear regression, for example, which was trained using a few thousand observations. How do you ensure, and be confident, that the model is as good as it seems on the training data and deploy it to make predictions on real, unseen data?

Often, it is mistaken that if a model performs well on training data, it will produce good results on test data as well, and quite often, that is not the case.


Occam's razor is perhaps the most important thumb rule in machine learning and is incredibly 'simple' at the same time. When in dilemma, choose the simpler model. The question then is 'how do we define simplicity?'. In the next segment, you will learn about some objective ways to measure model simplicity and understand why simplicity is preferred over sophistication and complexity using various examples.



Ocams Razor: 
What does Occam's razor, a fundamental principle, suggest?

Occam’s razor does not suggest that a model should be unjustly simplified until no further simplification is possible. It suggests that when faced with a trade-off between a complex and a simple model, with all other things being roughly equal, you are better off choosing the simpler one. The reason for this will be explained shortly.

--
The central issue in machine learning can be said to be the study of How to extrapolate learnings from a finite amount of data to explain or predict all possible inputs of the same type


# Model and Learning Algorithm:

Before you dive into the concept of a simple model and learn about its benefits, we will take a short detour to reiterate some terminologies and the machine learning framework. You will now learn about the process of using training data, learning from it and then building a model to describe a system that performs a task at hand, such as classification or regression. The key objectives to be understood are as follows:

Meaning of a model, learning algorithm, system and hypothesis class
Difference between a learning algorithm and a model (often misunderstood)
Meaning of ‘class of models’ 

You revised the basic machine learning framework. You will now learn about a basic property of a learning algorithm, which is that it can only produce models of a certain type within its boundaries. This means that an algorithm designed to produce a linear class of models, such as linear / logistic regression, will never be able to produce a decision tree or a neural network. The class of the model becomes critical because a wrong class will yield a sub-optimal model. Let's understand this point in more detail.


Note: The linearity of SVMs will be discussed in detail in a later module. For now, remember that all SVMs (with any kernel or type of problem) are fundamentally linear problems.


Having understood the terminology and differences among algorithms, models and classes of models, you are now ready to learn about model simplicity, complexity and common issues such as overfitting.


#  Simplicity, Complexity and Overfitting
We will now discuss the notion of model simplicity and complexity in detail
and use some examples and analogies to gain an understanding of the pros and cons of simple and complex models. 

Now, you will gain an understanding of the type of learning model to be chosen. Suppose we choose regression, what type of regression will we use?

From your school or college, you can probably recall those few fellows who seemed to study less but understood much more than others. They never seemed to care about memorising or mechanically practising the concepts taught but were able to explain complex problems in physics or mathematics with simplicity and elegance. 


Assuming that people learn using ‘mental models’, do these students have remarkably different mental models than those who solve a bunch of books and focus on memorisation? How can they learn so much from a finite amount of information provided and apply the same to solve unseen, complex problems? 


In this segment, Prof. Raghavan will explain the meaning of model simplicity and complexity along with the pros and cons associated with them. As a by-product, you will also understand that the best way to ‘learn’ is ‘to keep your mental models simple’. 

Simpler models make a higher number of errors in training. In the next video, you will learn how to handle these.

