

Introduction
In this session, you will learn about the high-level API Keras and how to implement a neural network using Keras. You will also explore some best practices for training neural networks, dropouts and batch normalisation.

 

In this Session
We will cover the following topics:

Keras: High-level API using TensorFlow

Implementation of neural networks using Keras

Epoch, batch, overfitting and underfitting

Dropouts and batch normalisation



# Introduction to Keras

In this segment, you will learn how to build neural networks using Keras, a deep learning library that you will primarily be using throughout this course. 

Introduction to Keras
In this segment, you will learn how to build neural networks using Keras, a deep learning library that you will primarily be using throughout this course. 

 

Keras is a high-level library designed to work on top of Theano or TensorFlow. The main advantage of using Keras is that it is an easy-to-use, minimalistic API that can be used to build and deploy deep learning models quickly. Due to its simplicity, Keras's syntax and model building pipeline is easy to learn for beginners (although it does not compromise on flexibility, you can do almost everything with Keras that you do with pure TensorFlow or Theano).

 

You will be surprised to see how only a few lines of Python code in Keras can build and train complex, deep neural networks. In this segment, you will learn about the typical model-building process in Keras.


Building neural networks in Keras
Download the notebook file attached below. It contains the code that will be used in this segment.


Download the data set provided below.

Keras Installation
To install Keras, open your Jupyter Notebook and implement the following command:

 

!pip install keras
To check the version of Keras on your system, execute the following command (Note: Do not forget to import Keras.)

print(keras.__version__)
Note that you need to have either Theano or TensorFlow on your system in order to use Keras. So, you should install either of the two before importing Keras; otherwise, it might throw an error. So, you first need to install TensorFlow if not already done. For this, you can execute the following command:

!pip install tensorflow
Keras by default uses TensorFlow as the backend. If you wish to use Keras with Theano as the backend, you need to find the 'keras.json' file and change "backend": "tensorflow" to "backend":"theano" in the .json file.

 

Now that you know how to install Keras and TensorFlow, let's take a look at the steps implemented by Keras for building a model.


There are six main steps involved in building a model using Keras:

 

1. Load the data:

We load the data available using the following function as defined in the notebook:

load_data()
Note that the shape of the matrices changes in the Keras implementation with respect to the Numpy implementation. The following lines of code take the transpose of each of the matrices read by load_data() function and assign the matrices to the corresponding variables:

train_set_x = train_set_x.T
train_set_y = train_set_y.T
test_set_x = test_set_x.T
test_set_y = test_set_y.T

2. Define the model:

Typically, models in Keras are defined as a sequence of layers. So, we first need to create a model, 'nn_model', as follows: 

nn_model = Sequential()

This model has no layers as of now. We can add as many layers as we want to it. Let's add the first hidden layer. As we add a layer, we also need to specify the number of neurons in the layer and the activation function they will use. You will observe that we use the function 'Dense', which specifies that the layers are fully connected, i.e., every neuron in one layer will be connected to every other neuron in the next layer. The line of code added within the model is as follows:

nn_model.add(Dense(35, input_dim=784, activation='relu'))
Here, as an example, ‘35’ denotes the number of neurons in the hidden layer and ‘784’ denotes the input size.

You can find more types of layers here.

3. Compile the model:

After we have defined the model, we need to compile the model. During this step, Keras uses the backend libraries to efficiently represent the above-described model for training and prediction. We need to specify the loss function, the metrics as well as the optimiser in this step. In a classification problem, the loss function is the cross-entropy loss, which is 'categorical_crossentropy' in Keras. The metrics and the optimiser we use are 'accuracy' and 'adam' (consider this as an optimiser similar to gradient descent, which helps you to find optimum values of your model’s parameters). The line of code added in the model for compilation is as follows:      

nn_model.compile(loss='categorical_crossentropy', optimizer='adam', metrics=['accuracy'])



4. Fit the model:

The next step is to fit the model on the data set available. You need to pass the training data present in the variables 'train_set_x' and 'train_set_y' that you created earlier. You also need to pass the number of epochs you want for the training to happen. Essentially, 1 epoch is 1 pass through the entire data set in mini-batches (we will discuss this in the subsequent segments). So, you also need to specify the mini-batch size (the number of data points to be sent through the neural network in one go).

nn_model.fit(train_set_x, train_set_y, epochs=10, batch_size=32)
Note that unless we call the 'model.fit()' function, the training does not begin. 

 


 5. Evaluate the model:

In this step, we can see the accuracy scores that we finally achieved using the following command:

scores_train = nn_model.evaluate(train_set_x, train_set_y)

print("\n%s: %.2f%%" % (nn_model.metrics_names[1], scores_train[1]*100))
To get the score on the test data, we can write the following code:

scores_test = nn_model.evaluate(test_set_x, test_set_y)

print("\n%s: %.2f%%" % (nn_model.metrics_names[1], scores_test[1]*100))
Note that we only changed the data set from train to test.


6. Make predictions:

Predictions can be performed using the '.predict()' function in the following manner:

predictions = nn_model.predict(test_set_x)


These are the steps involved in building a model in Keras. You must have observed that we need not write any code for feedforward or backpropagation as we did when we implemented the neural network using TensorFlow. Using Keras eliminates all those efforts. Keras is used almost everywhere because it is quite flexible. You may want to refer to the complete documentation of Keras here.


Let’s proceed to the housing price prediction example for a demonstration on how to build and train a model. We will first perform data preprocessing of the housing data set before proceeding to model building using Keras.


Now that we have performed feature transformation on the data set, let’s watch the next video to learn how to create a model and train it using Keras.


In the videos above, we saw how the implementation of a training model we built earlier in TensorFlow required just a few lines of code using Keras. Quite interestingly, in the Keras model, we were passing 32 rows of input data as a batch for a training step, unlike what you have seen before. We do this instead of passing the whole data set through the training step because loading the whole data set while training the model will occupy a lot of memory and will slow down your training speed. Therefore, we split it into ‘mini-batches’ (usual size is 32) and pass each batch one by one through the training step. This is memory- and speed-efficient.

 

If the batch size is set to 1, then it becomes the stochastic gradient descent (which is shown in the TensorFlow code). If the batch size is set to the size of the data set, then it is called batch gradient descent (where we pass the whole data set through training in one go). If the batch size is a fraction of the whole data set, like 32 or 64, then it is mini-batch gradient descent.


The whole process can be summarised as follows:
1. Define a simple sequential model to set the hidden layer(s) and the output layer. The following code allows us to define the simple sequential model:

model = keras.Sequential(
 [ keras.layers.Dense(2, activation="sigmoid", input_shape=(X.shape[-1],)),
    keras.layers.Dense(1, activation="linear")
 ] )
2. Display the properties and dimensions of each layer of the neural network.

model.summary()
3. Define the type of optimiser to update the weights and biases.

model.compile(optimizer=keras.optimizers.SGD(), loss="mean_squared_error")
4. Fit all the components defined above into one line of code to train the neural network.

model.fit(X,Y.values,epochs=10,batch_size=32)
5. Obtain predictions on different input data.

model.predict(X)[:,0]


Now, let's see how we can use Keras for a problem on unstructured data, i.e., MNIST. We will use Keras to train an image classifier on it. 

NOTE: The code can be run on Google Colab, jupyter notebook, or other compatible platforms. However, Google Colab is preferable as it requires a minimal initial setup.

Google Colab is a free cloud service and provides free GPU access. You can learn how to get started with Google Colab here. 

 

The datasets can be downloaded below. (You can upload the zip file directly to Google Colab as the inbuilt codes are written in a notebook to extract the datasets.)


Now that we have explored the MNIST data set, let’s build a model, train it and finally get predictions on the input data set using the trained model.


A visualisation of the model architecture used for training the neural network for the MNIST data set is given below.

Now, you know how to use Keras to build and train neural networks. You may want to change the values of different hyperparameters in the model and analyse how it affects model performance. 


Question 1
Out of the following functions, which function starts training of a Keras model?

==>
fit()

✓ Correct
Feedback:
This function initiates and executes the training process.

Question 2
If the training dataset size is 65000 and the batch size defined during the training process is 26, how many iterations will one epoch have?

==>


2500

✓ Correct
Feedback:
One epoch will go through the whole training dataset batch-wise and each iteration is for a single batch. So, there will be 65000/26 = 2500 iterations for the network to go through the whole dataset.

Question 3
Which of the following is(are) not an activation function?

==>
SGD

✓ Correct
Feedback:
SGD is not an activation function. It is a type of optimiser used for training.

Adam

✓ Correct
Feedback:
Adam is not an activation function. It is a type of optimiser used for training.


Question 4
Which of the following is not a model function used for building, training or evaluating a neural network in Keras?

==>

augment()

✓ Correct
Feedback:
This function is not one of the steps used for building, training or evaluating a neural network.


Question 5
Which function is used to define the cost function when building a neural network with Keras?

==>

compile()

✓ Correct
Feedback:
This defines the optimiser, metrics, loss function and different important hyperparameters to set up the training process.

model.compile(

    optimizer=keras.optimizers.SGD(), loss="mean_squared_error"

         )



Question 6
What will be the Keras code snippet to define the architecture given below? (Please refer to the bottom of the image to know the number of nodes in each layer).

The output layer has linear activation and the rest of the layers have ReLU activation function.


==>

model = keras.Sequential(
    [
        keras.layers.Dense(
            10, activation="relu",input_shape=(X_train.shape[-1],)
        ),
        keras.layers.Dense(
            10, activation="relu"
        ),
        keras.layers.Dense(
            5, activation="relu"
        ),
        keras.layers.Dense(1, activation="linear")
    ]
)
✓ Correct
Feedback:
This Keras model code meets all the requirements.



In the next segment, we will discuss different modifications that can be done to build better neural networks


# MNIST: Epoch, Batch, Overfitting and Underfitting


In the previous segment, you learnt how to write the code snippets for building and training a neural network using Keras. You saw its implementations on two different examples and understood the meaning behind each line of code while building the model. In this segment, we will discuss different attributes such as batch and epoch in depth. We will also discuss the different aspects of the output summary obtained from the network. 

 

Let’s concentrate on what we had done while building the ANN for MNIST. We built a full-fledged classification architecture. Let’s now start analysing the main elements of the architecture other than the parameters of the architecture. These elements are called hyperparameters. 

 

Let’s start with the term ‘epochs’. In the following line of code, a model is being trained using the function fit(). A number of arguments are passed to this function which we have seen earlier. We will concentrate on the ‘epochs’ argument first: 

model.fit(X_train, y_train, batch_size=64, epochs=5, validation_data=(X_val, y_val))
 

The number of epochs mentioned in the code snippet defines the number of times the learning algorithm will work through the entire data set. One epoch indicates that each training example has had an opportunity to update the internal model parameters, i.e., the weights and biases.

 

Now, lets consider the batch size hyperparameter represented by the argument ‘batch_size’ in the following line of code:

model.fit(X_train, y_train, batch_size=64, epochs=5, validation_data=(X_val, y_val))
 

Batch size refers to the number of training examples utilised in one iteration. The model decides the number of examples to work with in each iteration before updating the internal model parameters.

A model summary states the details of the parameters used and displays the layers of the architecture. A simple summary() function is required for this:

 

model.summary()
 

This can be used after we compile the model (refer to the previous segment for more details on this). For the MNIST architecture, we have the summary given below.

Model: "sequential"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
dense (Dense)                (None, 128)               100480    
_________________________________________________________________
dense_1 (Dense)              (None, 128)               16512     
_________________________________________________________________
dense_2 (Dense)              (None, 128)               16512     
_________________________________________________________________
dense_3 (Dense)              (None, 10)                1290      
=================================================================
Total params: 134,794
Trainable params: 134,794
Non-trainable params: 0



Some important points regarding this model summary are as follows:

The model is given as ‘sequential’, which means that the layers are set up one after the other in a singular sequence.

We know the input data’s size is 784, which means that 784 neurons are present in the input layer.

The first hidden layer is a dense layer, which means that all of its neurons are fully connected with the neurons of the previous layer, which is the input layer. The output shape is defined as 128, which means that the hidden layer has 128 neurons.

The number of parameters is as follows:
If the input layer has 784 neurons and the first hidden layer has 128 neurons and is fully connected (dense), then the weight matrix will be of size 784 x 128, and there will be 128 elements in the bias vector, one for each neuron in the hidden layer.

Total elements in the weight matrix = 784 x 128 = 100352

Total elements in the bias vector = 128

Total number of parameters  = 100352 + 128 = 100480 (as is given)

The second hidden layer is a dense layer and has 128 neurons.

The number of parameters is as follows:
If the first hidden layer has 128 neurons and the second hidden layer has 128 neurons, then the weight matrix is of size 128 x 128 and the bias vector is of size 128.

Total elements in the weight matrix = 128 x 128 = 16384

Total elements in the bias vector = 128

Total number of parameters = 16384 + 128 = 16512 (as is given)

Similarly, the third hidden layer is dense and has 128 neurons. Since the second hidden layer has 128 neurons too, the total number of parameters will be 16512 (just as described in the previous point).

The last dense layer is the output layer with 10 neurons (classes). 

The number of parameters is as follows:
The third hidden layer has 128 neurons, and the output layer has 10 neurons. The weight matrix is of size 128 x 10 and the bias vector is of size 10. 

Total elements in the weight matrix = 128 x 10 = 1280

Total number of parameters = 1280 + 10 = 1290 (as is given)

In the end, the summary shows the total of trainable and non-trainable parameters. Trainable parameters are the ones going through the learning process, i.e., the weights and biases. Non-trainable parameters are the ones that do not go through the training process. For example in the following code, ‘0.3’ defines the number of randomly selected weights set to zero, and this is not going to change throughout the training process.

keras.layers.Dropout(0.3)
Hence, it is a non-trainable parameter. (Note: You will learn about Dropouts shortly.)

 

So far, only weights and biases and no other types of parameters are included in this model; hence, all the parameters are trainable parameters. This gives us the sum of all the parameters in all the layers as 134794.

 

While training the model after using model.fit() function, you must have seen something like this:


The text above can be analysed as follows: 

The text 591/591 indicates the number of batches the training step is running through. Since the batch size is 64 and the training data set is of size 37800 (90% of the total  dataset which is 42000) while the rest 10% is validation dataset, it will be separated into 591 batches (37800/64).

You can also see the amount of time it is taking for training a single batch, for example, 7ms/step.

The text snippets loss and val_loss show the sparse categorical cross-entropy loss (mentioned while compiling the model; refer to the previous segment for this).

The text snippets accuracy and val_accuracy show the proportion of matches between the predicted class and the actual class. This proportion is calculated on the whole training and validation data sets.

And, after 5 epochs (5 run-throughs of training the whole data set), we can see the validation accuracy reached is approximately 93%.

Note: The calculation speed, loss, and accuracy may differ slightly in each runtime as it depends on computational power.


There are two points to keep in mind regarding training a model on a data set. Firstly, the model should be able to determine generalised trends in a proper manner for smarter predictions. Secondly, it should be able to apply these observations and trends to future data (the data that the model has never seen) and make predictions accurately. To measure how it is performing on these two bases, we assess whether the model may be overfitting or underfitting. If the model overfits, it will perform well on the training data set, but not on the testing data set. If the model underfits, it will find it difficult to identify even the major patterns present in the data.

 

If the model is not able to understand the underlying trend of the given data set, then the model is said to be underfitting. And, the accuracy of the model is low even on the training data set. This usually happens when the amount of data to train on is less or the model defined has linear elements with few non-linear relationships for it to be able to understand complex trends and patterns. When this happens, the model becomes more free and flexible, which results in incorrect predictions even on the training data. The opposite is true when the model overfits, that is, the model learns the exact patterns of the training data and is unable to generalise on unseen data. Both underfitting and overfitting are issues that needs to be addressed.





Question 2
When building a neural network, which of the following hyperparameters most affects the trade off between underfitting and overfitting?


==>

Number of hidden layers and the number of nodes per hidden layer

✓ Correct
Feedback:
 The architecture of the neural network most affects the way the model will train on a given dataset. Thus, it is the most important factor to decide the model’s regularization (overfitting and underfitting).


 Question 3
__________ refers to a model that has a good training accuracy but is not able to predict well on new data not seen before.

==>

Overfitting

Question 1
Validation accuracy can be greater than training accuracy.
==>

True

✓ Correct
Feedback:
Although typically training accuracy is higher than validation accuracy, it may happen that validation accuracy is higher than training accuracy. This may happen as an artifact of how the data split has been performed or other reasons like data leakage, regularization, and so on.



Question 4
________ refers to a model that can’t train and perform well on a given training dataset and also can't predict accurately on new data.


==>

Underfitting


Question 5
Which one of the following is not a reason why overfitting happens?

==>

Early stopping during the training phase

✓ Correct
Feedback:
 An early stopping in the training iteration algorithm will either underfit the model or result in a good fit. Overfitting will occur if it is continuously learning on the same dataset a lot of times.



 Question 7
Select the way(s) to avoid overfitting.(More than one option may be correct)


==>


Increase the training dataset

✓ Correct
Feedback:
More data can help in making the model understand generalised trends across the dataset.


Reduce the number of epochs used

✓ Correct
Feedback:
 This can be done so that the training doesn’t become rigidly specific to only the training dataset.


 Use regularization techniques

✓ Correct
Feedback:
 Regularization techniques are useful for addressing the problem of overfitting.



 To summarise, you have understood what different aspects of the model output mean when training the model after we have defined the model architecture and hyperparameters.

The training process requires your careful attention to ensure that the model is learning well, not too much or not too less, and is able to observe underlying trends and patterns for making more accurate predictions on future data.

In the next segment, we will discuss the concept of dropouts, which is one way to regularise a neural network and handle overfitting.


# Dropouts

The previous segment, you explored different parts of the training process and got some insights on how to judge whether the trained model is performing well (overfitting or underfitting). Neural networks that are usually large, complex models with tens of thousands of parameters have a tendency to overfit the training data. As with many other ML models, regularisation is a common technique used in neural networks to address this problem. Let's now take a look at a popular regularisation technique used for neural networks called dropouts. 

 

The main purpose of using dropouts is to reduce overfitting. Sometimes, a model trains on the training data set and its weights and biases converge to very specific values, values that are ideal for only the training data set. Adding a dropout layer to the neural network helps to break that specific combination of weights and biases. This enables the neural network to search for a broader and more general pattern and makes predictions more robust. In the next video, you will be introduced to the mathematics behind the dropout layer.



To summarise, the dropout operation is performed by multiplying the weight matrix 
W
l
 with an 
α
 mask vector as shown below.

W
l
.
α

 

For e.g. let's consider a weight matrix of the first layer 
W
1
=
⎡
⎢
⎢
⎢
⎢
⎢
⎣
w
1
11
w
1
12
w
1
13
w
1
21
w
1
22
w
1
23
w
1
31
w
1
32
w
1
33
w
1
41
w
1
42
w
1
43
⎤
⎥



Then, the shape of the vector 
α
 will be (3,1). Now if the value of 
q
 (the probability of 1) is 0.66, the 
α
 vector will have two 1s and one 0. Hence, the 
α
 vector can be any of the following three:

 

⎡
⎢
⎣
1
1
0
⎤
⎥
⎦
   or 
⎡
⎢
⎣
1
0
1
⎤
⎥
⎦
or 
⎡
⎢
⎣
0
1
1
⎤
⎥
⎦
 

 

One of these vectors is then chosen randomly in each mini-batch. Let's say that, in some mini batch, the mask 
α
 = 
⎡
⎢
⎣
1
1
0
⎤
⎥
⎦
is chosen. Hence, the new (regularised) weight matrix will be:

                                                    
⎡
⎢
⎢
⎢
⎢
⎢
⎣
w
1
11
w
1
12
w
1
13
w
1
21
w
1
22
w
1
23
w
1
31
w
1
32
w
1
33
w
1
41
w
1
42
w
1
43
⎤
⎥
⎥
⎥
⎥
⎥
⎦
.
⎡
⎢
⎣
1
1
0
⎤
⎥
⎦
 = 
⎡
⎢
⎢
⎢
⎢
⎢
⎣
w
1
11
w
1
12
0
w
1
21
w
1
22
0
w
1
31
w
1
32
0
w
1
41
w
1
42
0
⎤
⎥
⎥

As you can see, all the elements in the last column become zero. 
You can see the differences between the ANN without dropout and the ANN with dropout below. 
Adding a dropout layer essentially removes the links from the third neuron in the first layer to all the neurons in the next layer. 
The cross on the interconnections indicates that the interconnection has been removed.



Some important points to note regarding dropouts are:

Dropouts can be applied only to some layers of the network (in fact, that is a common practice - you choose some layer arbitrarily to apply dropouts to)
The mask 
α is generated independently for each layer during feedforward, and the same mask is used in backpropagation
The mask changes with each minibatch/iteration and is randomly generated in each iteration (sampled from a Bernoulli with some 
p(1)=q)

Why the dropout strategy works well is explained through the notion of a manifold. Manifold captures the observation that is in high dimensional spaces, the data points often actually lie in a lower-dimensional manifold. This is observed experimentally and can be understood intuitively as well. 

 

For example, in a 50-dimensional space 
R
50
, it is likely that the data points actually lie in a much lower-dimensional subspace (manifold). The dropout strategy uses this fact to find a lower-dimensional solution to the problem.

 

Apart from reducing the complexity of the model, dropouts help us in another way.

Let's watch the next video to find out.


As you learnt in the video above, dropouts help in symmetry breaking. There is an extremely high likelihood that communities will be created within neurons, which can restrict the neurons from learning independently. Hence, by setting a random set of the weights to zero in every iteration, this community/symmetry can be broken. Note that a different mini-batch is processed in every iteration in an epoch, and dropouts are applied to each mini-batch.

 

Reinforce your concepts of dropouts with the following set of questions:



Question 1/2
Mandatory
Alpha vector dimension
Suppose you want to add dropout to a particular weight matrix with dimensions (4, 7). What is going to be the dimension of the mask vector 
α
?

==>


7

✓ Correct
Feedback:
For the image above, the weight matrix will have the dimensions (4,7), i.e., 4 rows and 7 columns. 
The shape of α will be (Number of columns, 1) or the dimension of α = (number of neurons in the previous layer 'l-1', 1).

Dropouts
You want to add dropout to a particular weight matrix 
W
3
 with dimension (4, 7). Suppose the value of 'q', which is the probability of 1 is 0.25. How many elements in 
W
3
 will be set to 0?

 ==>

 21

✓ Correct
Feedback:
There are 28 weight elements. The probability of 1 is 0.25. Hence, 75% of the weight elements will be set to 0 that is 21.

Notice that after applying the mask 
α
, one of the columns of the weight matrix is set to zero. If the 
j
t
h
 column is set to zero, it is equivalent to the contribution of the 
j
t
h
 neuron in the previous layer is zero. In other words, you cut off one neuron from the previous layer. 

 

There are other ways to create the mask. One is to create a matrix which has 'q' percentage of the elements set to 1 and the rest 0. You can then multiply this matrix with the weight matrix element-wise to get the final weight matrix. Hence, for a weight matrix 
⎡
⎢
⎢
⎢
⎢
⎢
⎣
w
1
11
w
1
12
w
1
13
w
1
21
w
1
22
w
1
23
w
1
31
w
1
32
w
1
33
w
1
41
w
1
42
w
1
43
⎤
⎥
⎥
⎥
⎥
⎥
⎦
, the mask matrix for 'q'  = 0.66 can be 
⎡
⎢
⎢
⎢
⎣
1
0
1
1
1
0
0
1
1
1
1
0
⎤
⎥
⎥
⎥
⎦
.

Multiplying the above matrices element-wise, we get 
⎡
⎢
⎢
⎢
⎢
⎢
⎣
w
1
11
0
w
1
13
w
1
21
w
1
22
0
0
w
1
32
w
1
33
w
1
41
w
1
42
0
⎤
⎥


Visually, the matrix above can be shown as:



 

Well again, you need not worry about how to implement dropouts since you just need to write one simple line of code to add dropout in Keras.

 

You can write the following line of code:

# dropping out 20% neurons in a layer in Keras 
model.add(Dropout(0.2))


Some important points to note while implementing dropouts are as follows:

 Here, '0.2' is the probability of zeros and not ones.

This is one of the hyperparameters to be experimented with when building a neural network.

You do not apply dropout to the output layer.

The mask used here is a matrix.

Dropout is applied only during training, not while testing.

 Let’s now take a look at a demonstration of how dropout can be used as a good regularisation technique to help reduce overfitting in a model. For this, we will revisit the house price prediction example and build a neural network using Keras.

 

Here are some of the data points from the housing data set after feature transformation, as seen in the sessions on Feedforward Propagation.



Let’s now take a look at a demonstration of how dropout can be used as a good regularisation technique to help reduce overfitting in a model. For this, we will revisit the house price prediction example and build a neural network using Keras.

 

Here are some of the data points from the housing data set after feature transformation, as seen in the sessions on Feedforward Propagation.


In the upcoming video, you will see how the training and validation performance changes with the use of the Dropout layer.


As you can see, the model used in the video above to improve the training and validation performance is as shown in the code snippet below,

model = keras.Sequential(
    [
        keras.layers.Input(shape=(X_train.shape[-1],)),
        keras.layers.Dense(
            10, activation="relu"
        ),
        keras.layers.Dropout(0.2),
        keras.layers.Dense(
            10, activation="relu"
        ),
        keras.layers.Dense(
            5, activation="relu"
        ),
        keras.layers.Dense(1, activation="linear")
    ]
)
 

The results obtained are given below.



Thus, we can conclude that adding the Dropout layer has regularised the model and helped in reducing the overfitting issue.

 

The important points to note are folows:

1. We have to experiment with optimal placement of dropout as well as optimal value of the dropout ratio to get the best result of the model.

2. We can add dropout at different hidden layers in the model simultaneously. For example, we can add dropout at the second layer and third layer together.


Question 1
Dropout layer can be added after the input layer.

==>



True

✓ Correct
Feedback:
The only specification of where dropout layers cannot be added is after the output layer. It is allowed after the input layer and hidden layers.


Question 2
Which of the following is(are) not one of the benefits of using dropout?(More than one option may be correct)

==>


Speed of training

✓ Correct
Feedback:
The addition of a dropout layer does not impact the speed with which a model trains.

Training accuracy

✓ Correct
You missed this!
Feedback:
Dropout is a regularisation technique that will increase the training accuracy, not “better” it. 
When using dropouts, training accuracy may also go down.

Question 3
In dropouts, α is a trainable parameter and not a hyperparameter.

==>

False

✓ Correct
Feedback:
α does not change during the training process, hence it is a hyperparameter.


In the next segment, 
we will explore a widely used technique called batch normalisation, 
which helps in improving the performance of neural networks.

Question 4
What will be the value of the Dropout hyperparameter ‘q’ for the connections between 2 layers given below?

==>

0.33

✓ Correct
Feedback:
We can see that there are 4 connections dropped out from 12 connections in total. 
Since, the dropout hyperparameter ‘q’ is the probability of zeros, then q=4/12=0.333 approximately.


✓ Correct
Feedback:
The connections that are set to zero are as follows,

First layer first neuron to second layer second neuron

First layer second neuron to second layer third neuron

First layer third neuron to second layer first neuron

First layer fourth neuron to second layer third neuron

Their corresponding elements are set to zero in the matrix.


Question 6
Dropout layer is also used during test time.

=>
False

✓ Correct
Feedback:
It is only used during training. These layers are deactivated during test time.



In the next segment, 
we will explore a widely used technique called batch normalisation, 
which helps in improving the performance of neural networks.

 
## Batch Normalisation
So far, you have understood how dropouts help regularise the neural network. 
Let's now take a look at one of the widely used techniques in training a neural network called batch normalisation.

 

It is generally a good idea to have your data on a common scale while training a neural network.
 Sometimes, when training a neural network, large activations might be produced. 
 Different sizes of activations can result in unstable training behaviour. 
 This is where ‘normalisation’ can be helpful. Normalisation is seen as an aid to the optimisation process.
  Commonly seen benefits are that fewer epochs are required to complete the network’s training process and sometimes,
   it avoids the neural network to get stuck during the training process. 
Let’s dive deeper into the batch normalisation layer.



Before moving ahead, let's first clearly understand the problem batch normalisation is trying to solve. The feed forward equations for a single data point are given below:

h
1
=
σ
(
W
1
.
x
+
b
1
)

h
2
=
σ
(
W
2
.
h
1
+
b
2
)
 = 
σ
(
W
2
.
(
σ
(
W
1
.
x
+
b
1
)
)
+
b
2
)

h
3
=
σ
(
W
3
.
h
2
+
b
3
)
 = 
σ
(
W
3
.
(
σ
(
W
2
.
(
σ
(
W
1
.
x
+
b
1
)
)
+
b
2
)
)
+
b
3
)

h
4
=
σ
(
W
4
.
h
3
+
b
4
)
=
σ
(
W
4
.
(
σ
(
W
3
.
(
σ
(
W
2
.
(
σ
(
W
1
.
x
+
b
1
)
)
+
b
2
)
)
+
b
3
)
)
+
b
4
)


Batch normalisation is performed on the output of the layers of each batch, 
H
l
. It is essentially normalising the matrix 
H
l
 across all data points in the batch. Each vector in 
H
l
 is normalised by the mean vector 
μ
 and the standard deviation vector 
^
σ
 computed across a batch.

 

The image shows the batch normalisation process for a layer 
l
. Each column in the matrix 
H
l
 represents the output vector of layer 
l
, 
h
l
, for each of the 
m
 data points in the batch. We compute the 
μ
 and the 
^
σ
 vectors which represent the mean output from layer 
l
 across all points in the batch'. We then normalise each column of the matrix 
H
l
 using 
μ
 and 
^
σ
.



Hence, if a particular layer 
l
  has 5 neurons, we will have 
H
l
 of the shape (5, m) where 'm' is the batch size and 
μ
 & 
^
σ
 vectors of shape (5,1). The first element of 
μ
 (
μ
1
) is the mean of the outputs of the first neuron for all the 'm' data points, the second element 
μ
2
 is the mean of the outputs of the second neuron for all the 'm ' data points and so on. Similarly, we get a vector 
^
σ
 as the standard deviation of the outputs of the five neurons across the m points. The normalisation step is then:

 

H
l
=
H
l
−
μ
^
σ

 

This step is performed by broadcasting 
μ
 and 
^
σ
. The final 
H
l
 after batch normalisation is shown on the left side of the image above.

 

Let’s try this out for the simple model built for the housing data set. The architecture is given below to refresh your memory



Hence, if a particular layer 
l
  has 5 neurons, we will have 
H
l
 of the shape (5, m) where 'm' is the batch size and 
μ
 & 
^
σ
 vectors of shape (5,1). The first element of 
μ
 (
μ
1
) is the mean of the outputs of the first neuron for all the 'm' data points, the second element 
μ
2
 is the mean of the outputs of the second neuron for all the 'm ' data points and so on. Similarly, we get a vector 
^
σ
 as the standard deviation of the outputs of the five neurons across the m points. The normalisation step is then:

 

H
l
=
H
l
−
μ
^
σ

 

This step is performed by broadcasting 
μ
 and 
^
σ
. The final 
H
l
 after batch normalisation is shown on the left side of the image above.

 

Let’s try this out for the simple model built for the housing data set. The architecture is given below to refresh your memory




Suppose there is a batch normalization layer after the first hidden layer. The model in Keras would look like this:

 
model = keras.Sequential(
    [
        keras.layers.Input(shape=(X_train.shape[-1],)),
        keras.layers.Dense(
            2, activation="sigmoid"
        ),
        keras.layers.BatchNormalization(),
        keras.layers.Dense(1, activation="linear")
    ]
)


We will now see how batch normalization is performed on the output of the hidden layer before it is given as the input to the next (in this case, output) layer. Let’s focus on the first neuron of the hidden layer. We know that the output value, i.e., the activation it obtains from the input is as follows: 
h
1
1
=
σ
(
w
1
11
x
1
+
w
1
12
x
2
+
b
1
1
)
 where, 
σ
 is the sigmoid activation function (please refer to the image of the model given above for the values of weights and biases).


 The 
μ
(mean) and 
σ
(standard deviation) are calculated from the six values of the output of the first neuron in the hidden layer, i.e., 
h
l
1
, and then, we performed 
h
l
=
h
l
−
μ
^
σ
to obtain the new output values to be fed to the next layer as the input. The same operation can be performed separately on the second neuron of the hidden layer. Remember that we have defined the batch size as 6. These values will change as per the batch size considered.

 

This is how batch normalisation is performed on the output of each node in a layer. This normalised output is then fed as the input to the next layer. Batch normalisation is generally performed on all the layers except the output layer.

 

However, there is one small problem: How do we perform batch normalisation during test time? Test data points are fed forward one at a time, and there are no 'batches' during test

time. Thus, we do not have any 
μ
 and 
σ
 to normalise each test data point with. So, we take some sort of an average, i.e., the average of the 

μ
's  and 
σ
's of the different batches of the training set.



To get an intuition behind how batch normalisation solves the problem of decoupling the weight interactions and improves the training procedure, let's reiterate why the normalisation of the input data works in the first place. The answer is that the loss function contours change after normalisation, as shown in the figure below, and it is easier to find the minimum of the contours in the image on the right than that of the contours in the image on the left. 


Note that the batch normalization process can also be applied to the cumulative input vector into the layer, 
Z
l
, instead of  
H
l
. These are different heuristics, so you need not worry about them. This is because deep learning frameworks such as Keras use empirically proven techniques; you just need to write a simple line of code.

Libraries such as Keras use a slightly different form of batch normalization. We transform the equations given above as:



where, the constant 
ϵ
 ensures that the denominator does not become zero (when the variance is 0). The constants 
γ
 and 
β
 are hyperparameters. In Keras, batch normalisation is implemented as follows:




#Parameters used in batch normalisation.
#In case not mentioned, these values will take the default value.
model.add(BatchNormalization(axis=-1, epsilon=0.001, 
beta_initializer='zeros', 
gamma_initializer='ones'))
The ‘axis=-1’ specifies that the normalisation should happen across the rows.

 

An example of how you can add the layer in the Keras architecture is given below.

model = keras.Sequential([
    keras.layers.Input(shape=(784,)),
    keras.layers.Flatten(),
    keras.layers.Dense(128, activation=tf.nn.relu),
    keras.layers.Dense(128, activation=tf.nn.relu),
    keras.layers.Dense(128, activation=tf.nn.relu),
    keras.layers.BatchNormalization(),
    keras.layers.Dense(10, activation=tf.nn.softmax)
])
You can play around with the model architecture along with the batch normalization layer in the MNIST_keras notebook provided in the earlier segment. And then we can test the model performance. Just add the batch normalization code after the third layer as shown in the above code and run the model. Here, the batch normalization is performed in the third layer and then output is fed to the next layer.

 

In this example, the working principle of batch normalization is as follows:

We can see that the dense hidden layer has 128 neurons. Suppose a batch size of 64 is defined for training the model. This means that 64 input examples are supplied at once to the neural network; hence, there will be 64 outputs of the third dense hidden layer. This means that each of the 128 neurons will have 64 outputs. For each neuron, the mean and standard deviation is computed using its corresponding 64 outputs and then normalized. The updated outputs are then fed as inputs to the next layer.

 

Note: Batch normalization might not be very useful in the neural networks that we have learnt about so far. Batch normalization is usually used in large architectures that train over a variety of data and solve complex problems. You will understand the importance of the batch normalization layer when you are introduced to the concept of Convolutional Neural Networks in another module. 

 


 Question 1
What is(are) the use(s) of batch normalisation?


Finds more generalised trends in the dataset

✓ Correct
You missed this!
Feedback:
Normalized parameters across the model make the model more robust and this leads to finding more generalised trends and patterns of the dataset.


Quicker convergence of the model

✓ Correct
Feedback:
Use of batch normalisation may lead to quicker convergence of the model


Question 2
For a batch normalization layer, the mean 
μ
 is 50 and the standard deviation 
γ
 is 0.08. We know that, 
H
l
=
H
l
−
μ
^
σ
=
γ
H
l
+
β

Assume that 
ϵ
=
0
. Find the value of 
γ
 and 
β
 respectively.


 ==>

 12.5, -625

✓ Correct
Feedback:
From the equation above, we can see that, 
γ
=
1
^
σ
 and 
β
=
−
μ
^
σ
.

Substituting the values 
μ
=
50
 and 
^
σ
=
0.08
, we get 
γ
=
12.5
  and 
β
=
−
625
.


Summary
In this session, you learnt how to implement an artificial neural network using Keras. You also learnt how to modify a neural network to improve a model’s performance. You explored how to regularise a neural network using dropouts. You were also introduced to batch normalisation and understood how it helps in training a model. 

 

This completes the module Introduction to Neural networks. You are encouraged to explore additional content for more understanding of neural networks. In the next module, we will study convolutional neural networks (CNN). Till then, happy learning!

 

The lecture notes summary of this module is attached below.



Graded:


Question 1
A model summary is given below for neural network architecture.

Model: "sequential"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
dense_1 (Dense)              (None, 64)               (blank)    
_________________________________________________________________
dense_2 (Dense)              (None, 32)               2080     
_________________________________________________________________
dense_3 (Dense)              (None, 32)               (blank)     
_________________________________________________________________
dense_4 (Dense)              (None, 5)                (blank)      
=================================================================
Total params: (blank)
Trainable params: (blank)
Non-trainable params: 0
_________________________________________________________________
The input data vector has 1000 features. The dense_4 layer is the output layer.

Notice that there are blanks filled in different places. Let’s answer a few questions to know each of the values.

What is the number of parameters in the third dense hidden layer?



==>

1056

✓ Correct
Feedback:
The number of parameters is the total number of weights and biases. 

The third hidden dense layer has 32 neurons and each neuron will have a bias term. 
Thus, 32 elements are present in the bias vector for the third hidden layer. 
The weight matrix is between the second layer with 32 neurons and the third layer with 32 neurons.
 Hence, the weight matrix will have 32*32=1024 elements. Adding the bias terms, in total, there are 32+1024=1056 parameters.



 Q2)

 Question 2
A model summary is given below for neural network architecture.

Model: "sequential"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
dense_1 (Dense)              (None, 64)               (blank)    
_________________________________________________________________
dense_2 (Dense)              (None, 32)               2080     
_________________________________________________________________
dense_3 (Dense)              (None, 32)               (blank)     
_________________________________________________________________
dense_4 (Dense)              (None, 5)                (blank)      
=================================================================
Total params: (blank)
Trainable params: (blank)
Non-trainable params: 0
_________________________________________________________________
The input data vector has 1000 features. The dense_4 layer is the output layer.

Notice that there are blanks filled in different places. Let’s answer a few questions to know each of the values.

Calculate the number of weights in the weight matrix for the first dense hidden layer.

==>

64000

✓ Correct
Feedback:
As the input has 1000 features and the first dense hidden layer has 64 neurons, the weight matrix will have 64*1000 = 64000 elements in it

Question 3
A model summary is given below for neural network architecture.

Model: "sequential"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
dense_1 (Dense)              (None, 64)               (blank)    
_________________________________________________________________
dense_2 (Dense)              (None, 32)               2080     
_________________________________________________________________
dense_3 (Dense)              (None, 32)               (blank)     
_________________________________________________________________
dense_4 (Dense)              (None, 5)                (blank)      
=================================================================
Total params: (blank)
Trainable params: (blank)
Non-trainable params: 0
_________________________________________________________________
 

The input data vector has 1000 features. The dense_4 layer is the output layer.

Notice that there are blanks filled in different places. Let’s answer a few questions to know each of the values.

Find the number of parameters for the output layer.

==>

165

✓ Correct
Feedback:
The number of parameters is the total number of weights and biases. Since the output layer has 5 neurons, each one will have a bias term, thus, 5 elements are there in the bias vector of the output layer. The weight matrix is between the third layer with 32 neurons and the output layer with 5 neurons. Hence, the weight matrix will have 32*5=160 elements. Adding the bias terms to the weights, in total, there are 5+160=165 parameters.



Question 4
A model summary is given below for neural network architecture.

Model: "sequential"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
dense_1 (Dense)              (None, 64)               (blank)    
_________________________________________________________________
dense_2 (Dense)              (None, 32)               2080     
_________________________________________________________________
dense_3 (Dense)              (None, 32)               (blank)     
_________________________________________________________________
dense_4 (Dense)              (None, 5)                (blank)      
=================================================================
Total params: (blank)
Trainable params: (blank)
Non-trainable params: 0
_________________________________________________________________
The input data vector has 1000 features. The dense_4 layer is the output layer.

Notice that there are blanks filled in different places. Let’s answer a few questions to know each of the values.

Find the total number of trainable parameters.


==>

67365

✓ Correct
Feedback:
 The total number of trainable parameters is the total number of parameters in the model. It’s value is 64064+2080+1056+165 = 67365.

 





