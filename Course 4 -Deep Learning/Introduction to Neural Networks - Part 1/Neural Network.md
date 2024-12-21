# Biological to Artificial Neuron
As the name Artificial Neural Networks (ANNs) suggests, the design of ANNs is inspired by the human brain. Although not as powerful as the brain (yet), artificial neural networks are the most powerful learning models in the field of machine learning.

In the past few years, deep artificial neural networks have proven to perform surprisingly well on complex tasks such as speech recognition (converting speech into text), machine translation, and image and video classification. Such models are also commonly called deep learning models.


Let’s begin our journey into deep learning with an introduction to artificial neural networks.

Artificial neural networks are said to be inspired by the structure of the human brain. Let’s first learn about the basic structure of the brain and the anatomy of a neuron and understand how information travels through neurons.


In simple words, the biological neuron works as follows: it receives signals through its dendrites, which are either amplified or inhibited, as they pass through the axons to the dendrites of other neurons.


Let’s now take a look at how an artificial neural network is similar to the human brain.

To summarise, the main bottleneck in using neural networks is the availability of abundant training data. Neural networks find applications across various domains such as images and videos (computer vision), text and speech. Note that the words ‘deep learning’ and ‘neural networks’ are often used interchangeably.


Also, artificial neural networks are a collection of many simple devices called artificial neurons. The network ‘learns’ to conduct certain tasks, such as recognising a cat, by training the neurons to ‘fire’ in a certain way when given a particular input, such as a cat. In other words, the network learns to inhibit or amplify the input signals to perform a certain task, such as recognising a cat, speaking a word or identifying a tree.  


In the next segment, you will study the basics of a perceptron. The perceptron was one of the earliest proposed models for learning simple classification tasks, which later became the fundamental building block of artificial neural networks.



# Perceptron
In this segment, you will study the basics of a simple device called the perceptron, which was the first step towards creating the large neural networks that we have developed today. Let's take an example to understand how a perceptron works.


Consider a sushi place you plan to visit this Saturday. There are various factors that would affect this decision, such as:

The distance between the sushi place and your home
The cost of the food they serve there
The number of people accompanying you
You make such a decision based on multiple such factors. Also, each decision factor has a different ‘weight’, for example, the distance of the place might be more important than the number of people accompanying you. 

 

Perceptrons work in a similar manner. They take some signals as inputs and perform a set of simple calculations to arrive at a decision. Let’s watch the next video to study the basic perceptron.

A perceptron acts as a tool that enables you to make a decision based on multiple factors. Each decision factor holds a different ‘weight’, for example, your neighbor, Rohit, may consider the amenities around the house to be more important than the other two factors. Similarly, perceptrons take such different factors as input signals, attach a certain weight based on the importance they give to the corresponding factors, and perform basic operations to decide what to do.

 

In other terms, the perceptron takes a weighted sum of multiple inputs (with bias) as the cumulative input and applies an output function on the cumulative input to get the output, which then assists in making a decision. You can observe the cumulative input in the formula given below,
 

CumulativeInput=w1x1+w2x2+w3x3+b
 

Where, 
xi’s represent the inputs, 
wi’s represent the weights associated with inputs and b represents bias.


Soon, you will be talking about everything in terms of vectors and matrices. So, let's start using these terms from now. Let’s say 
w and x are vectors representing weights and inputs as follows (note that, by default, a vector is assumed to be a column vector):



w
=⎡
⎢
⎢
⎢
⎢
⎢
⎢
⎣
w1
w2
.
.
wk
⎤
⎥
⎥
⎥
⎥
⎥
⎥
⎦
,
x
=
⎡
⎢
⎢
⎢
⎢
⎢
⎢
⎣
x1
x2
.
.
xk
⎤
⎥
⎥
⎥
⎥
⎥
⎥
⎦


A neat and concise way to represent the weighted sum of 
w
 and 
x
 is using the dot product of the transpose of the weight vector 
w
T
 and the input vector 
x
. Let’s understand this concept of taking the dot product of the transpose of weight vectors and input vectors.

 

The transpose of w is w
T=[w1w2..wk], a row vector of size 1 x k. Taking the dot product of  
wT with x , we get the following:

wT.x=[w1w2..wk].⎡⎢⎢⎢⎢⎢⎢⎣
                    x1
                    x2
                    ..
                    xk
                    ⎤⎥⎥⎥⎥⎥⎥⎦
                    = w1x1+w2x2+....+wkxk


After adding bias to wT.x, you will get the following equation:

CumulativeInput=wT.x+b=w1x1+w2x2+w3x3+b

We then apply the step function to the cumulative input. According to the step function, if this cumulative sum of inputs is greater than 0, then the output is 1/yes; or else, it is 0/no. So, in Rohit’s case, if upon applying the step function on the cumulative input the output is 1, then he would like to visit the sushi place on the upcoming Saturday.

Cumulative Input
Suppose you have the following vectors: 

w
=
⎡
⎢
⎢
⎢
⎢
⎢
⎢
⎣
3
1
5
7
4
⎤
⎥
⎥
⎥
⎥
⎥
⎥
⎦
,

x
=
⎡
⎢
⎢
⎢
⎢
⎢
⎢
⎣
1
1
0
1
0
⎤
⎥
⎥
⎥
⎥
⎥
⎥
⎦

The bias value is -2. Calculate the cumulative input to the perceptron.


==>

Feedback:
The cumulative input is calculated as follows:
CumulativeInput=wT.x+b=w1x1+w2x2+w3x3+w4x4+w5x5+b

 = 3*1 + 1*1 + 5*0 + 7*1 + 4*0 + (-2) 
 = 3 + 1 + 7 - 2 
 = 9  

 Q2)

 Perceptron
Suppose you have the following vectors: 

w
=
⎡
⎢
⎢
⎢
⎢
⎢
⎢
⎣
3
1
5
7
4
⎤
⎥
⎥
⎥
⎥
⎥
⎥
⎦
,
x
=
⎡
⎢
⎢
⎢
⎢
⎢
⎢
⎣
1
1
0
1
0
⎤
⎥
⎥
⎥
⎥
⎥
⎥
⎦

The bias value is -2. The step function is used as the output function. 
What will be the output of the perceptron? 


-->

1

✓ Correct
Feedback:
We first calculate the cumulative input as follows:

C
u
m
u
l
a
t
i
v
e
I
n
p
u
t
=
w
T
.
x
+
b
=
w
1
x
1
+
w
2
x
2
+
w
3
x
3
+
w
4
x
4
+
w
5
x
5
+
b

=
3
∗
1
+
1
∗
1
+
5
∗
0
+
7
∗
1
+
4
∗
0
+
(
−
2
)

=
3
+
1
+
7
−
2

=
9

Since the cumulative input is 9, which is greater than 0, the output of the perceptron will be 1, i.e., output = f(9) = 1, where f is the step function.


Now, you have a basic understanding of a perceptron. 

Note: For a detailed discussion on perceptrons, please refer to the optional section.

 

Let’s proceed to the next segment to understand what is an artificial neuron.


# Artificial Neuron
Now that you have a basic understanding of perceptrons, let’s study the design of Artificial Neural Networks (ANNs). 

Neural networks are a collection of artificial neurons arranged in a particular structure. In this segment, you will understand how a single artificial neuron works, i.e., how it converts inputs into outputs. You will also understand the topology or structure of large neural networks. Let’s get started by understanding the basic structure of an artificial neuron.


As you learnt in the video above, a neuron is quite similar to a perceptron. However, in perceptrons, the commonly used activation/output is the step function, whereas in the case of ANNs, the activation functions are non-linear functions.

 

Note: You will learn about these activation functions in the upcoming segments.


Take a look at the structure of an artificial neuron in the image given below.

 

Artificial Neuron
Artificial Neuron
 

Here, a's represent the inputs, 
w's represent the weights associated with the inputs, and 
b represents the bias of the neuron.

In the next video, you will understand how large neural networks are designed using multiple individual neurons.

As you learned in the video above, multiple artificial neurons in a neural network are arranged in different layers. The first layer is known as the input layer, and the last layer is called the output layer. The layers in between these two are the hidden layers.

 

The number of neurons in the input layer is equal to the number of attributes in the data set, and the number of neurons in the output layer is determined by the number of classes of the target variable (for a classification problem).

 

For a regression problem, the number of neurons in the output layer would be 1 (a numeric variable). Take a look at the image given below to understand the topology of neural networks in the case of classification and regression problems. 


Note that the number of hidden layers or the number of neurons in each hidden layer or the activation functions used in the neural network changes according to the problem, and these details determine the topology or structure of the neural network. We will discuss this in the subsequent segments.


Let's watch the next video to understand what it means to specify a neural network completely, i.e., what all we need to specify in order to completely describe a neural network.


So far, you have understood the basic structure of artificial neural networks. To summarise, there are six main elements that must be specified for any neural network. They are as follows:

1. Input layer
2. Output layer
3. Hidden layers
4. Network topology or structure 
5. Weights and biases
6. Activation functions

You might have some questions, such as ‘How do we decide the number of neurons in a layer?’ or ‘How are weights and biases determined?’. You will be able to answer these questions in the next few segments, wherein you will learn about each of these specifications in depth.


# Inputs and Outputs of a Neural Network
As you learnt in the previous segment, the number of neurons in the input layer is determined by the input given to the network, and the number of neurons in the output layer is equal to the number of classes (for a classification task) or is one (for a regression task). Now, let’s take a look at some examples to understand the inputs and outputs of ANNs better.

 

Let’s get started by understanding the inputs and outputs of an ANN from Professor Srinivasaraghavan in the upcoming video.



The most important thing to note is that inputs can only be numeric. For different types of input data, you need to use different ways to convert the inputs into a numeric form. The most commonly used inputs for ANNs are as follows:

Structured data: The type of data that we use in standard machine learning algorithms with multiple features and available in two dimensions, such that the data can be represented in a tabular format, can be used as input for training ANNs. Such data can be stored in CSV files, MAT files, Excel files, etc. This is highly convenient because the input to an ANN is usually given as a numeric feature vector. Such structured data eases the process of feeding the input into the ANN. 


The most important thing to note is that inputs can only be numeric. For different types of input data, you need to use different ways to convert the inputs into a numeric form. The most commonly used inputs for ANNs are as follows:

Structured data: The type of data that we use in standard machine learning algorithms with multiple features and available in two dimensions, such that the data can be represented in a tabular format, can be used as input for training ANNs. Such data can be stored in CSV files, MAT files, Excel files, etc. This is highly convenient because the input to an ANN is usually given as a numeric feature vector. Such structured data eases the process of feeding the input into the ANN. 
Text data: For text data, you can use a one-hot vector or word embeddings corresponding to a certain word. For example, in one hot vector encoding, if the vocabulary size is |V|, then you can represent the word wn


 as a one-hot vector of size |V| with '1' at the nth element with all other elements being zero. The problem with one-hot representation is that, usually, the vocabulary size |V| is huge, in tens of thousands at least; hence, it is often better to use word embeddings that are a lower-dimensional representation of each word. The one-hot encoded array of the digits 0–9 will look as shown below.
data = np.array([0,1,2,3,4,5,6,7,8,9])
print(data.shape)
one_hot(data)
(10,)
array([[1.,0.,0.,0.,0.,0.,0.,0.,0.,0.,],
[0.,1.,0.,0.,0.,0.,0.,0.,0.,0.,],
[0.,0.,1.,0.,0.,0.,0.,0.,0.,0.,],
[0.,0.,0.,1.,0.,0.,0.,0.,0.,0.,],
[0.,0.,0.,0.,1.,0.,0.,0.,0.,0.,],
[0.,0.,0.,0.,0.,1.,0.,0.,0.,0.,],
[0.,0.,0.,0.,0.,0.,1.,0.,0.,0.,],
[0.,0.,0.,0.,0.,0.,0.,1.,0.,0.,],
[0.,0.,0.,0.,0.,0.,0.,0.,1.,0.,],
[0.,0.,0.,0.,0.,0.,0.,0.,0.,1.,]])
Images: Images are naturally represented as arrays of numbers and can thus be fed into the network directly. These numbers are the raw pixels of an image. ‘Pixel’ is short for ‘picture element’. In images, pixels are arranged in rows and columns (an array of pixel elements). The figure given below shows the image of a handwritten 'zero' in the MNIST data set (black and white) and its corresponding representation in NumPy as an array of numbers. The pixel values are high where the intensity is high, i.e., the color is bright, while the values are low in the black regions, as shown below.



Images (cont.): In a neural network, each pixel of the input image is a feature. For example, the image provided above is an 18 x 18 array. Hence, it will be fed as a vector of size 324 into the network. Note that the image given above is black and white (also called a grayscale image), and thus, each pixel has only one ‘channel’. If it were a colored image called an RGB (Red, Green and Blue) image, each pixel would have three channels, one each for red, blue, and green, as shown below. Hence, the number of neurons in the input layer would be 18 x 18 x 3 = 972. The three channels of an RGB image are shown below.

Speech: In the case of a speech/voice input, the basic input unit is in the form of phonemes. These are the distinct units of speech in any language. The speech signal is in the form of waves, and to convert these waves into numeric inputs, you need to use Fourier Transforms (you do not need to worry about this as it is covering areas of specialized mathematics that will not be covered in this course). Note that the input after conversion should be numeric, so you are able to feed it into a neural network.

Q1)

Inputs
Fill in the blank.
In a classification problem with 12 attributes and 3 class labels, the number of neurons in the input and output layers will be _______.
 
 ==>

 12,3

✓ Correct
Feedback:
The input layer will have 12 neurons corresponding to the 12 attributes, and the output layer will have 3 neurons corresponding to the probability of the class labels 1, 2 and 3.

Q2)

Inputs
Fill in the blanks:
Neural networks are quite popularly used in image recognition problems. Their task is to classify a given grayscale image (say, a Google image) into categories such as nature, animal, and sports. An image is simply a collection of pixels. 

Let’s take the example of a 720 x 1080 image. There are 720 pixels along the vertical axis of the image and 1080 pixels along the horizontal axis. Each pixel acts as an attribute and contains a ‘value’ that may represent the colour, shade, etc., at that point on the image.

To classify an image into the three categories mentioned above, the number of neurons in the input and output layers are ______ and ______, respectively.
 
 ==>


720 X 1080, 3

✓ Correct
Feedback:
Each of the 720 x 1080 pixels acts as an attribute and is the input sent to the neural network. Also, each of the three output neurons will have the probability of the image being related to the nature, animal or sports category. Therefore, this is the correct answer.

Q3)


Inputs
Considering the 720 x 1080 image mentioned above was coloured (RGB channels) instead of being a grayscale image, what would be the number of neurons in the input layer?

==>

720 x 1080 x 3

✓ Correct
Feedback:
As the input image is coloured and hence has three channels (RGB), the number of attributes sent as an input to the neural network would be 720 x 1080 x 3.
 

 Now that you have learnt how to feed input vectors into neural networks, let’s understand how the output layers are specified.

 #Inputs and Outputs of a Neural Network
As you learnt in the previous segment, the number of neurons in the input layer is determined by the input given to the network, and the number of neurons in the output layer is equal to the number of classes (for a classification task) or is one (for a regression task). Now, let’s take a look at some examples to understand the inputs and outputs of ANNs better.

 

Let’s get started by understanding the inputs and outputs of an ANN from Professor Srinivasaraghavan in the upcoming video.

The most important thing to note is that inputs can only be numeric. For different types of input data, you need to use different ways to convert the inputs into a numeric form. The most commonly used inputs for ANNs are as follows:

Structured data: The type of data that we use in standard machine learning algorithms with multiple features and available in two dimensions, such that the data can be represented in a tabular format, can be used as input for training ANNs. Such data can be stored in CSV files, MAT files, Excel files, etc. This is highly convenient because the input to an ANN is usually given as a numeric feature vector. Such structured data eases the process of feeding the input into the ANN. 
Text data: For text data, you can use a one-hot vector or word embeddings corresponding to a certain word. For example, in one hot vector encoding, if the vocabulary size is |V|, then you can represent the word 
w
n
 as a one-hot vector of size |V| with '1' at the nth element with all other elements being zero. The problem with one-hot representation is that, usually, the vocabulary size |V| is huge, in tens of thousands at least; hence, it is often better to use word embeddings that are a lower-dimensional representation of each word. The one-hot encoded array of the digits 0–9 will look as shown below.
data = np.array([0,1,2,3,4,5,6,7,8,9])
print(data.shape)
one_hot(data)
(10,)
array([[1.,0.,0.,0.,0.,0.,0.,0.,0.,0.,],
[0.,1.,0.,0.,0.,0.,0.,0.,0.,0.,],
[0.,0.,1.,0.,0.,0.,0.,0.,0.,0.,],
[0.,0.,0.,1.,0.,0.,0.,0.,0.,0.,],
[0.,0.,0.,0.,1.,0.,0.,0.,0.,0.,],
[0.,0.,0.,0.,0.,1.,0.,0.,0.,0.,],
[0.,0.,0.,0.,0.,0.,1.,0.,0.,0.,],
[0.,0.,0.,0.,0.,0.,0.,1.,0.,0.,],
[0.,0.,0.,0.,0.,0.,0.,0.,1.,0.,],
[0.,0.,0.,0.,0.,0.,0.,0.,0.,1.,]])

Images: Images are naturally represented as arrays of numbers and can thus be fed into the network directly. These numbers are the raw pixels of an image. ‘Pixel’ is short for ‘picture element’. In images, pixels are arranged in rows and columns (an array of pixel elements). The figure given below shows the image of a handwritten 'zero' in the MNIST data set (black and white) and its corresponding representation in NumPy as an array of numbers. The pixel values are high where the intensity is high, i.e., the color is bright, while the values are low in the black regions, as shown below.

Speech: In the case of a speech/voice input, the basic input unit is in the form of phonemes. These are the distinct units of speech in any language. The speech signal is in the form of waves, and to convert these waves into numeric inputs, you need to use Fourier Transforms (you do not need to worry about this as it is covering areas of specialized mathematics that will not be covered in this course). Note that the input after conversion should be numeric, so you are able to feed it into a neural network.


Now that you have learnt how to feed input vectors into neural networks, let’s understand how the output layers are specified.


Depending on the nature of the given task, the outputs of neural networks can either be in the form of classes (if it is a classification problem) or numeric (if it is a regression problem). 
One of the commonly used output functions is the softmax function for classification. Take a look at the graphical representation of the softmax function shown below.



A softmax output is similar to what we get from a multiclass logistic function commonly used to compute the probability of an output belonging to one of the multiple classes. It is given by the following formula: 

pi=ewix′ / ∑c−1t=oewt.x′

where c is the number of classes or neurons in the output layer, x′ is the input to the network, and 
wi’s are the weights associated with the inputs.


Suppose the output layer of a data set has 3 neurons and all of them have the same input 
x′  (coming from the previous layers in the network). The weights associated with them are represented as 
w0,w1 and w2. In such a case, the probability of the input belonging to each of the classes are expressed as follows:



Suppose the output layer of a data set has 3 neurons and all of them have the same input 
x
′
  (coming from the previous layers in the network). The weights associated with them are represented as 
w0,w1 and w2. In such a case, the probability of the input belonging to each of the classes are expressed as follows:


p0=ew0x′/ew0.x′+ew1x′+ew2x′
p1=ew1x′/ew0.x′+ew1x′+ew2x′
p2=ew2x′/ew0.x′+ew1x′+ew2x′
 

Also, it is evident from these expressions that the sum 
p0+p1+p2=1 and that p0,p1 and p2 ϵ(0,1)


Softmax Output
Suppose the output layer has 4 neurons, and all of them have the same input ‘x’. The weights associated with them are represented as 
w0,w1,w2 and w3, respectively. What will be the expression for p3?

Q2)

Range of Softmax
Suppose we have two classes (0 and 1) in the output, and the probability of getting class 0 as the output is 
p
0
 and the probability of getting class 1 as the output is 
p
1
. In the softmax output layer, if the minimum value of 
p
0
 is 0.5, then what is the range of 
p
1
?


==>

0 to 0.5

✓ Correct
Feedback:
We know that 
p0+p1=1. Hence, the maximum value for 
p1 is
p1=1−p0=1−0.5=0.5
, and the minimum value is 0. Therefore, the range for 
p1 is 0 to 0.5.

 So, we have seen the softmax function as a commonly used output function in multiclass classification. Now, let’s understand how the softmax function translates to the sigmoid function in the special case of binary classification.


In the case of a sigmoid output, there is only one neuron in the output layer because if there are two classes with probabilities 
p
0
 and 
p
1
, we know that 
p
0
+
p
1
=
1
. Hence, we need to compute the value of either 
p
0
 or 
p
1
. In other words, the sigmoid function is just a special case of the softmax function (since binary classification is a special case of multiclass classification).
In fact, we can derive the sigmoid function from the softmax function, as shown below. Let's assume that the softmax function has two neurons with the following outputs:

p
0
=
e
w
0
x
′
e
w
0
.
x
′
+
e
w
1
x
′
,
p
1
=
e
w
1
x
′
e
w
0
.
x
′
+
e
w
1
x
′


 Consider only  
p
1
 and divide both the numerator and the denominator with the numerator. We can now rewrite 
p
1
 as:

p
1
=
1
1
+
e
w
0
.
x
′
e
w
1
.
x
′
=
1
1
+
e
(
w
0
−
w
1
)
.
x
′

And, if we replace 
w
1
−
w
0
 = some 
w
, we get the sigmoid function. Voila!




Q1)

Softmax Calculation
Consider a neural network with three output neurons for classification. The input vector is 
x
′
=
⎡
⎢
⎣
2
1
1
⎤
⎥
⎦
, and the weights are 
w
0
=
⎡
⎢
⎣
1
1
−
1
⎤
⎥
⎦
 ,
w
1
=
⎡
⎢
⎣
2
0
−
1
⎤
⎥
⎦
 and 
w
2
=
⎡
⎢
⎣
1
2
2
⎤
⎥
⎦
. What are the values of 
p
0
, 
p
1
 and 
p
2
 up to three decimal points?


 ==>

 0.017, 0.047, 0.936

✓ Correct
Feedback:
We get 
w
0
.
x
=
2
,
w
1
.
x
=
3
,
w
2
.
x
=
6
 

Hence, we get 
e
w
0
∗
x
′
=
7.3891
,
e
w
1
∗
x
′
=
20.0855
,
e
w
2
∗
x
′
=
403.4287

 

This gives us the following values:

p0=ew0x′ / ew0.x′+ew1x′+ew2x′=7.3891
7.3891+20.0855+403.4287

p1=ew1x′ / ew0.x′+ew1x′+ew2x′
=
20.0855
7.3891
+
20.0855
+
403.4287

p2=ew2x′ / ew0.x′+ew1x′+ew2x′=403.4287
7.3891+20.0855 + 403.4287


Now that you have understood how the output is obtained from the softmax function and how different types of inputs are fed into the ANN, let's learn how to define inputs and outputs for image recognition on the famous MNIST data set for multiclass classification.




There are various problems you will face while trying to recognise handwritten text using an algorithm, including:

Noise in the image
The orientation of the text
Non-uniformity in the spacing of text
Non-uniformity in handwriting 
The MNIST data set takes care of some of these problems, as the digits are written in a box. Now the only problem the network needs to handle is the non-uniformity in handwriting. Since the images in the MNIST data set are 28 X 28 pixels, the input layer has 784 neurons (each neuron takes 1 pixel as an input) and the output layer has 10 neurons (each giving the probability of the input image belonging to any of the 10 classes). The image is classified into the class with the highest probability in the output layer. 

 

To revise what we have learnt in this segment, the softmax function stated above is a general case for multiclass classification. It is a commonly used output layer activation function for classification. You learnt how to feed input data into an ANN and obtain the output from it. In the next segment, we will move on to defining the building blocks of a neural network, which will help you understand the workings of a neuron and how to build its network.


# Workings of a Single Neuron

In this segment, you will learn how to define the input, the processing of this input and the corresponding output from a single neuron.
In the video below, we will be showing you in detail the structure and working of an artificial neuron.





Now that you have seen how inputs are fed into a neuron and how outputs are obtained using activation functions, let’s reiterate the concepts with a short summary.



In the image above, you can see that 
x
1
, 
x
2
 and 
x
3
 are the inputs, and their weighted sum along with bias is fed into the neuron to give the calculated result as the output.

 

To summarise, the weights are applied to the inputs respectively, and along with the bias, the cumulative input is fed into the neuron. An activation function is then applied on the cumulative input to obtain the output of the neuron. We have seen some of the activation functions such as softmax and sigmoid in the previous segment. We will explore other types of activation functions in the next segment. These functions apply non-linearity to the cumulative input to enable the neural network to identify complex non-linear patterns present in the data set.


An in-depth representation of the cumulative input as the output is given below.

In the image above, z is the cumulative input. You can see how the weights affect the inputs depending on their magnitudes. Also, z is the dot product of the weights and inputs plus the bias.

 

In this segment, you saw how a neuron takes an input and performs some operations on it to give the output. The output is obtained through an activation function. In the next segment, we will explore some popular activation functions.




# Different Activation Functions
As mentioned in one of the previous segments, in the case of ANNs, the activation functions are non-linear. In this segment, you will learn about these non-linear activation functions. But before you explore the different activation functions for ANNs, let’s watch the next video as Professor Srinivasaraghavan revises the concept of non-linearity.

The image provided below shows the graphical representation of a linear function and one of the possible representations of a non-linear function.

non-linear function.
non-linear function.
The activation functions introduce non-linearity in the network, thereby enabling the network to solve highly complex problems. Problems that take the help of neural networks require the ANN to recognise complex patterns and trends in the given data set. If we do not introduce non-linearity, the output will be a linear function of the input vector. This will not help us in understanding more complex patterns present in the data set. 

 

For example, as we can see in the image below, we sometimes have data in non-linear shapes such as circular or elliptical. If you want to classify the two circles into two groups, a linear model will not be able to do this, but a neural network with multiple neurons and non-linear activation functions can help you achieve this.


Let’s learn about the various types and properties of common activation functions and understand how to choose the correct activation function.

While choosing activation functions, you need to ensure that they are:

1. Non-linear,
2. Continuous, and
3. Monotonically increasing.

The different commonly used activation functions are represented below.


The features of these activation functions are as follows:

Sigmoid: When this type of function is applied, the output from the activation function is bound between 0 and 1 and is not centred around zero. A sigmoid activation function is usually used when we want to regularise the magnitude of the outputs we get from a neural network and ensure that this magnitude does not blow up.

Tanh (Hyperbolic Tangent): When this type of function is applied, the output is centred around 0 and bound between -1 and 1, unlike a sigmoid function in which case, it is centred around 0.5 and will give only positive outputs. Hence, the output is centred around zero for tanh. 

ReLU (Rectified Linear Unit): The output of this activation function is linear in nature when the input is positive and the output is zero when the input is negative. This activation function allows the network to converge very quickly, and hence, its usage is computationally efficient. However, its use in neural networks does not help the network to learn when the values are negative.

Leaky ReLU (Leaky Rectified Linear Unit): This activation function is similar to ReLU. However, it enables the neural network to learn even when the values are negative. When the input to the function is negative, it dampens the magnitude, i.e., the input is multiplied with an epsilon factor that is usually a number less than one. On the other hand, when the input is positive, the function is linear and gives the input value as the output. We can control the parameter to allow how much ‘learning emphasis’ should be given to the negative value.

In the next video, you will learn how to compute the output of a neuron, given the inputs, weights, biases and the sigmoid activation function.

Now that you have an idea of how to compute the output of a neuron using an activation function, try to answer the questions given below.


Q1)

Cumulative Input
Consider a single neuron with the following weight vector, input vector and bias:

w
=
⎡
⎢
⎣
2
−
6
3
⎤
⎥
⎦
x
=
⎡
⎢
⎣
3
2
1
⎤
⎥
⎦
and bias b = -1
Calculate the cumulative input for this neuron.

==>

Feedback:
You can calculate the cumulative input as follows:

CumulativeInput=wT.x+b=w1x1+w2x2+w3x3+b
      
=
(2∗3)+(−6∗2)+(3∗1)−1
=6−12+3−1
=
−4

Q2)
ReLU
What will be the output of this neuron, given that you use the ReLU activation function (up to three decimal places)?

==>

0

✓ Correct
Feedback:
For ReLU, output: y = x for all x > = 0 and y = 0 for all x < 0. As y = -4, which is less than 0, the output should also be 0.

Q3)

Leaky ReLU
What will be the output of the neuron, given that you use the Leaky ReLU activation function with α=0.2 (up to three decimal places)?

==>

-0.8

✓ Correct
Feedback:
The value of x is -4. For x < 0, Leaky ReLU output = αx = -4*0.2 = -0.8.

Q4)

Sigmoid Function
What will be the output of the neuron, given that you use the sigmoid/logistic activation function (up to three decimal places)?

==>


0.018

✓ Correct
Feedback:
The sigmoid function is given by the following formula: 
f(x)=1/1+e−x. Hence, computing the output of the sigmoid function when x = -4 gives us 0.018.


Having explored the key components in building the architecture of ANNs, let's now understand how neural networks are trained and used to make predictions. In the next segment, you will learn about the hyperparameters and parameters of neural networks.

# Parameters and Hyperparameters of Neural Network

Parameters and Hyperparameters of Neural Network
Neural networks require rigorous training, but what does it mean to train neural networks? What are the parameters that the network learns during training, and what are the hyperparameters that you (as the network is designed) need to specify beforehand?

Recall that models such as linear regression and logistic regression are trained on their coefficients, i.e., the task is to find the optimal values of the coefficients to minimize a cost function.

Neural networks are no different; they are trained on weights and biases.

 
In this segment, you will be introduced to the parameters that are learned during neural network training. You will also develop a broad understanding of how the learning algorithm works. Let’s get started by watching the upcoming video.





During training, the neural network learning algorithm fits various models to the training data and selects the best prediction model. The learning algorithm is trained with a fixed set of hyperparameters associated with the network structure. Some of the important hyperparameters to consider to decide the network structure are given below:

1. Number of layers
2. Number of neurons in the input, hidden and output layers
3. Learning rate (the step size taken each time we update the weights and biases of an ANN)

4. Number of epochs (the number of times the entire training data set passes through the neural network)
The purpose of training the learning algorithm is to obtain optimum weights and biases that form the parameters of the network.

Note: You will learn about hyperparameters such as learning rate and the number of epochs in the subsequent session. In this session, we will focus on the number of layers and the number of neurons in each layer.


The notations that you will come across going forward are as follows:

1.  W represents the weight matrix.
2. b stands for bias.
3. x represents the input.
4. y represents the ground truth label.
5. p represents the probability vector of the predicted output for the classification problem. 
6. hL represents the predicted output for the regression problem (where L represents the number of layers). 
7. h also represents the output of the hidden layers with appropriate superscript. The output of the second neuron in the nth hidden layer is denoted by  hn2.
8. h also represents the output of the hidden layers with appropriate superscript. The output of the second neuron in the nth hidden layer is denoted by  hn2.
9. z represents the accumulated input to a layer. The accumulated input to the third neuron of the nth hidden layer is 
zn3.
10. The bias of the first neuron of the third layer is represented as  
b31.
11. The superscript represents the layer number. The weight matrix connecting the first hidden layer to the second hidden layer is denoted by 
W2
12. The subscript represents the index of the individual neuron in a given layer. The weight connecting the first neuron of the first hidden layer to the third neuron of the second hidden layer is denoted by 
w2 31.
Having understood these notations, let’s reinforce by answering the questions given below.

You might want to look at how the inputs of the first data point 
x1 are represented. This will help you in answering the questions.

You might want to look at how the inputs of the first data point 
x1 are represented. This will help you in answering the questions.

q1)
Notations
How will you represent the element of the weight matrix between layers 1 and 2 represented as “x” in the figure (do not confuse this with the bias)?
==>

Feedback:
The elements are of the weight matrix 
W2. The fifth neuron of the first layer is connected to the second neuron of the second hidden layer, hence the subscript will be 25. Hence, this is the correct answer. 
q2)
Notations
How will you represent the element of the weight matrix represented as “z”?
==>

W433

✓ Correct
Feedback:
The elements are of the weight matrix 
W4, and since the third neuron of the third layer is connected to the third neuron of the fourth layer, the subscript is 33.

Q3)

Notations
How will you represent the bias of the neuron denoted by ‘u’?

==>


b
3
2

✓ Correct
Feedback:
‘u’ is the bias of the third layer for the second neuron. Hence, it will be represented as 
b
3
2
 and this is the correct answer.

 Q4) 

 Notations
How will you represent the output of the neuron denoted by “y”?

==>
h
2
5

✓ Correct
Feedback:
The output for the fifth neuron in the second layer is denoted by 
h
2
5
. This is because the superscript gives the layer number, and the subscript gives the node in that layer. Therefore, this is the correct answer.


So far, you have come across simple neural networks and have computed the outputs for them, but this is not the case with real-world applications. At times, the neural networks can be highly complex and large. Therefore, you will need some assumptions to make them easier to understand. You will learn about these assumptions in the next segment.


# Assumptions for Simplifying Neural Network

Since large neural networks can potentially have extremely complex structures, certain assumptions are made to simplify the way in which information flows in them. In the next video, Professor Srinivasaraghavan will explain some of the most common assumptions.

The image below shows the assumptions explained in the video above.


To summarise, commonly used neural network architectures make the following simplifying assumptions:

1. The neurons in an ANN are arranged in layers, and these layers are arranged sequentially.
2. The neurons within the same layer do not interact with each other.
3. The inputs are fed into the network through the input layer, and the outputs are sent out from the output layer.
4. Neurons in consecutive layers are densely connected, i.e., all neurons in layer l are connected to all neurons in layer l+1.
5. Every neuron in the neural network has a bias value associated with it, and each interconnection has a weight associated with it.
6. All neurons in a particular hidden layer use the same activation function. Different hidden layers can use different activation functions, but in a hidden layer, all neurons use the same activation function.
7. This brings us to the end of this session. In the next segment, we will quickly summarise what you learnt in this session.




Summary
Let’s take a quick look at what you have learnt in this session.

Some important points can be summarised as follows:

 

1. Firstly, you understood the limitations of preliminary machine learning and how deep learning can be used to build complex models.

2. Next, you saw how the architecture of ANNs draws inspiration from the human brain.

3. You also learnt about the basic functioning of a perceptron.

4. Further, you learnt about the basic building block of ANNs: Neurons. The structure of an artificial neuron is shown below.

Here, ‘a’ represents the inputs, ‘w’ represents the weights associated with the inputs, and ‘b’ represents the bias of the neuron.

6. You then learnt about the architecture of ANNs, including the topology, the parameters (weights and biases) on which the neural network is trained and the hyperparameters.

7. ANNs only take numerical inputs. Hence, you need to convert all types of data into a numeric format so that neural networks can process it.

8. Next, you were introduced to the most common activation functions such as sigmoid, ReLU, Leaky ReLU and tanh, which are shown below.


Some simplifying assumptions in the architecture of ANNs are as follows.

The neurons in an ANN are arranged in layers, and these layers are arranged sequentially.

The neurons within the same layer do not interact with each other.

The inputs are fed into the network through the input layer, and the outputs are sent out from the output layer.

Neurons in consecutive layers are densely connected, i.e., all neurons in layer l are connected to all neurons in layer l+1.

Every neuron in the neural network has a bias value associated with it, and each interconnection has a weight associated with it.

All neurons in a particular hidden layer use the same activation function.
 

Finally, you fixed the following notations:

W represents the weight matrix.

b stands for bias.

x represents input.

y represents the ground truth label.

p represents the probability vector of the predicted output for the classification problem.

h represents the output of the hidden layers, and 
h
L
 represents the output prediction for the regression problem.

z represents the cumulative input fed into each neuron of a layer.

The superscript represents the layer number.

The subscript represents the index of each individual neuron in a layer.



Graded:

1.
Basic Hyperparameters of Neural Network
The hyperparameters in a neural network are ________. (Note: More than one option may be correct.)

==>

The number of layers

✓ Correct
Feedback:
Weights and biases are parameters to be found by training the learning algorithm. The number of layers is one of the predefined hyperparameters.


The number of neurons in each layer

✓ Correct
Feedback:
Weights and biases are parameters to be found by training the learning algorithm. The number of neurons is one of the predefined hyperparameters.

he activation function (assuming it is the same for each neuron)

✓ Correct
Feedback:
Weights and biases are parameters to be found by training the learning algorithm. The activation function is one of the predefined hyperparameters.


2.
Inputs
Suppose you want to classify an RGB image with an input of 32 x 32 pixels as ‘dog’, ‘cat’, ‘bird’ or ‘none of the above’. How many neurons will the input layer have?

==>

3072

✓ Correct
Feedback:
A black-and-white 32 x 32 image will have 32 x 32 input neurons. However, since an RGB image has 3 channels, the network will have 32 * 32 * 3 = 3072 input neurons.

3.
Outputs
Suppose you want to classify an RGB image with an input of 32 x 32 pixels as ‘dog’, ‘cat’, ‘bird’ or ‘none of the above’. How many neurons will the output layer have?

==>

Feedback:
Since there are 4 classes,i.e., ‘dog’, ‘cat’, ‘bird’ and ‘none of the above’, we will have 4 output neurons.

5.


Output layer
Suppose you want to classify an RGB image with an input of 32 x 32 pixels as ‘dog’, ‘cat’, ‘bird’ or ‘none of the above’. Would you use a sigmoid/ softmax layer as the output layer?

==>

Feedback:
Since there are 4 classes, we would use a softmax function in the output layer.

6.

Notations
How would you denote the output of the third hidden layer?

==>

Feedback:
The output of a hidden layer is denoted by 
h
. The superscript denotes the layer number. Hence 
h3
 is the correct answer. Note: Since a specific neuron is not mentioned, we do not have a subscript.


 7.

 Notations
How would you denote the weight that connects the sixth neuron of the hidden layer 3 to the eighth neuron of the hidden layer 4?

==>

w
4
86

✓ Correct
Feedback:
Here, the notation 
w
4
 indicates the weights for the fourth hidden layer because the superscript is 4. Also, in the subscript, we have the neuron of the 
l
t
h
 layer, i.e., 8 as the first number and the neuron of the 
(
l
−
1
)
t
h
 layer, i.e., 6 as the second number. Since this is the case, the answer is correct.

 8. 
 Number of Interconnections
We have the hidden layer number 3 with 11 neurons and the hidden layer number 4 with 18 neurons. Also, these hidden layers are densely connected. How many connections will be there between the two hidden layers?

==>


198

✓ Correct
Feedback:
Number of interconnections = Number of neurons in layer 
l
 x Number of neurons in layer 
(
l
−
1
)
                                                                   = 11 * 18 = 198
9. Assumptions of Neural Network
State whether the following statement is true or false.

According to the assumptions of neural networks, the activation function of all the neurons in one particular layer is the same.

==>

True

✓ Correct
Feedback:
All neurons in a particular hidden layer use the same activation function. Hence, this answer is correct.




# Introduction to Feedforward Neural Network


Welcome to the second session on Feedforward Neural Networks. 

 

In the previous session, you understood the architecture of neural networks and how it was inspired by the structure of the human brain. You also learnt about the working of an artificial neuron, the hyperparameters and parameters of neural networks and various simplifying assumptions.

 

In this session, you will learn how information flows in a neural network from the input layer to the output layer to enable the neural network to make a prediction. The information flow in this direction is often called feedforward. You will also learn how to assess the performance of a neural network.
 

In this session
The following topics will be covered:

Information flow from the input layer to the output layer
Regression and classification feedforward methods
Working of neural networks
Loss function


## Flow of Information Between Layers
In the previous session, you learnt about the structure, topology, and hyperparameters of neural networks along with some simplifying assumptions of neural networks. In this segment, you will understand how information flows from one layer to the next one in a neural network.  
In artificial neural networks, the output from one layer is used as input to the next layer. Such networks are called feedforward neural networks. This means that there are no loops in the network, i.e., information is always fed forward, never fed backward. Let’s start by understanding the feedforward mechanism between the two layers. For simplicity, in the next video, the professor will use the input and the first layer to demonstrate how information flows between any two layers.




In the video above, you learnt how information flows from one layer to another. In the next video, let’s consider a subset of a network with two layers and hear from Gunnvant as he explains how feedforward propagation is done.


As seen in the video, an image of a subset of the neural network is shown below:


As you learnt in the previous session, the weight matrix between layer 0 (input layer) and layer 1 (the first hidden layer) is denoted by 
W. The dot product between the matrix 
W and the input vector 
xi along with the bias vector 
b, i.e., 
W.xi+b, acts as the cumulative input 
z to layer 1. The activation function is applied to this cumulative input 
z to compute the output 
h of layer 1. 


Let’s take the above-mentioned example and perform matrix multiplication to get a vectorised method to compute the output of layer 1 from the inputs of layer 0.

 

Here, the following input is given:

x
i
=
⎡
⎢
⎣
x
1
x
2
x
3
⎤
⎥
⎦

The dimensions of the input are (3,1).
There are two neurons in the first hidden layer. Hence, the cumulative input 
z
1
 will be given as:

z
1
=
[
z
1
1
z
1
2
]

Also, the weight matrix will be of dimension 2x3 and is represented as follows:

W
1
=
[
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
]

 

NOTE: The notation of a neuron's weight in a particular layer is represented as:

And, the bias vector can be represented as follows: 

b
1
=
[
b
1
1
b
1
2
]

The matrix representation of obtaining 
z
1
1
 is given below. 


 z
1
1
=
w
11
x
1
+
w
12
x
2
+
w
13
x
3
+
b
1

 

Here, 
z
1
1
 is obtained by taking a dot product of the input vector and the corresponding weights. The same goes for obtaining the value of 
z
1
2
. Hence, we get:

 

z12=w21x1+w22x2+w23x3+b2

The two equations can be written as a matrix multiplication as given below:
 

[
z
1
1
z
1
2
]
=
[
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
]
⎡
⎢
⎣
x
1
x
2
x
3
⎤
⎥
⎦
+
[
b
1
1
b
1
2
]
=
[
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
w
1
13
x
3
+
b
1
1
w
1
21
x
1
+
w
1
22
x
2
+
w
3
23
x
3
+
b
1
2
]

The next step is to apply the activation function to the 
z1 vector to obtain the output 
h1. As mentioned in the video, the activation function is applied to each element of the vector. Thus, the final output 
h1 of layer 1 is:

h
1
=
[
h
1
1
h
1
2
]
=
σ
(
W
1
.
x
1
+
b
1
)
=
[
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
w
1
13
x
3
+
b
1
1
)
σ
(
w
1
21
x
1
+
w
1
22
x
2
+
w
3
23
x
3
+
b
1
2
)
]


As Gunnvant mentioned, 
x
 is a vector function, i.e., it is applied element-wise to a vector.

 

This completes the forward propagation of a single data point through one layer of the network.


To summarise, the steps involved in computing the output of the 
i
t
h
 neuron in layer 
l
 is as follows:

Multiply each row of the weight matrix with the output from the previous layer to obtain the weighted sum of inputs from the previous layer.
Convert the weighted sum into the cumulative input by adding the bias vector.
Apply the activation function 
σ
(
x
)
 to the cumulative input to obtain the output vector 
h
. 

Q1) 


Question 1
Given below is a part of a neural network showing connections between the second layer with two neurons and the third layer with three neurons. What will be the weight matrix representation W between the two layers?

==>

W
3
=
⎡
⎢
⎢
⎣
w
3
11
w
3
12
w
3
21
w
3
22
w
3
31
w
3
32
⎤
⎥
⎥
⎦

✓ Correct
Feedback:
W
3
 will have the weights 
W
3
i
j
 where i is the neuron index of the third layer and j is the neuron index of the second layer. Each row has weights associated with each neuron of the third layer and each column has weights associated with each neuron of the second layer. Since each row represents the weights of each neuron in the third layer, this is the correct answer.


 Q2)

 Question 2
Let’s consider again the part of the neural network mentioned in the previous question. What will be the expression for the cumulative input, 
z
3
2
? (Given that the input values of the 2nd layer are [h1,h2])


==>

z
3
2
=
w
3
21
h
1
+
w
3
22
h
2

✓ Correct
Feedback:
z
2
3
 is the cumulative input of the second neuron in the third layer. Hence, the weights corresponding to 
z
3
2
 are 
w
3
21
 and 
w
3
22
. The cumulative input is the dot product of the weights (
w
3
21
,
w
3
22
) and activations (
h
1
,
h
2
) from the second layer

3.

Question 3
What is the correct representation of the output of the 
i
t
h
 neuron of the 
l
t
h
 layer?

 ==>

 
h
l
i

✓ Correct
Feedback:
We use the letter 
h
 to denote the output from a neuron. The superscript is the layer number 
l
 and the subscript is the index of the neuron 
i
 in that layer. Hence, this is the correct answer.



 With this premise, let’s study feedforward in a small neural network in the next segment.



# Forward Pass - Demonstration

In the previous segment, you saw how the output of the next layer is calculated, given the inputs from the previous layer. In this segment, you will learn about the flow of data through different layers in a step-by-step fashion using an example in which we intend to calculate the price of a house, given its size and the number of rooms in it. You may want to use pen and paper to do the calculations yourself for better understanding.


We saw how the cumulative input is computed for each node and how an activation function is applied to each input to obtain the output for each node in the first layer. Now that we have the output from the first layer, let’s watch the next video to see the flow of this data through the second layer.


To reiterate, the problem statement is to predict the price of houses, given the size of the houses and the number of rooms available. 

Std. Number of Rooms	Std. House Size (sq. ft.)	Price ($)
3	
1,340

313,000

5	3,650	
2,384,000

3	1,930	
342,000

3	2,000	
420,000

4	1,940	
550,000

2	880	490,000
 

In this case, we first scale the input and output for these 6 observations using the formula 
(
o
b
s
−
m
e
a
n
)
s
t
d
.
d
e
v
i
a
t
i
o
n
 . So, we get the table given below.

 

Std. Number of Rooms	Std. House Size (sq. ft.)	Price ($)
-0.32	-0.66	-0.54
1.61	1.80	2.03
-0.32	-0.03	-0.51
-0.32	-0.03	-0.41
0.65	-0.02	-0.25
-1.29	-1.15	-0.32
 

As you saw in the video, we want to build a neural network that will predict the price of a house, given two input attributes: number of rooms and house size. Let’s start with the structure of the neural network that we will consider for this case. We have an input layer with two input nodes, 
x
1
 and 
x
2
, one hidden layer with two nodes, a sigmoid activation function and finally an output layer with a linear activation function (since this is a regression problem), as shown below.


Now, to understand how the data moves forward in the network to enable the neural network to make predictions, we will initialise the weights and biases with random values. We recommend that you keep a pen and paper handy for practising the computations that will be performed further. The intention is that as this network gets trained, the weights and biases will be updated as per the data such that the predicted output will eventually be the same or at least similar to the actual output.

 

Let’s start by initialising the weights and biases to the following values:

L
a
y
e
r
1
:
W
1
=
[
w
1
11
w
1
12
w
1
21
w
1
22
]
=
[
0.2
0.15
0.5
0.6
]
b
1
=
[
b
1
1
b
1
2
]
=
[
0.1
0.25
]
L
a
y
e
r
2
:
W
2
=
[
w
2
21
w
2
22
]
=
[
0.3
0.2
]
b
2
=
[
b
2
1
]
=
[
0.4
]


Remember, the superscript denotes the layer to which it belongs and the subscript denotes the node in that particular layer. 

 

To showcase the step-by-step computation of the output, let’s take the first example as the input vector: 
 

X1=[x
1
x
2
]
=
[
−
0.32
−
0.66
]


Let’s compute the output from the first node in layer 1.

Computing the cumulative input for the first node of the hidden layer:

z
1
1
=
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
=
0.2
∗
(
−
0.32
)
+
0.15
∗
(
−
0.66
)
+
0.1
=
−
0.063

 

Applying the sigmoid activation function to obtain the output from the first node:

h11=σ(
−
0.063
)
=
1
1
+
e
−
z
1
1
=
1
1
+
e
−
(
−
0.063
)
=
0.484

Layer 1: Node 2

Next, let’s compute the output from the second node in layer 1 by following a similar process.

Computing the cumulative input for the second node of the hidden layer:

z
1
2
=
w
1
21
x
1
+
w
1
22
x
2
+
b
1
2
=
0.5
∗
(
−
0.32
)
+
0.6
∗
(
−
0.66
)
+
0.25
=
−
0.306

 

Applying the sigmoid activation function to get the output from the second node, we get:

h
1
1
=
σ
(
−
0.306
)
=
1
1
+
e
−
z
1
2
=
1
1
+
e
−
(
−
0.306
)
=
0.424

 

Each of these individual operations can be done together using matrix multiplication. 
We have the input vector 
X
1
, the weight matrix 
W
1
 and the bias vector 
b
1
 with the following values:

X
1
=
[
x
1
x
2
]
=
[
−
0.32
−
0.66
]

 

W
1
=
[
w
1
11
w
1
12
w
1
21
w
1
22
]
=
[
0.2
0.15
0.5
0.6
]

 

b
1
=
[
b
1
1
b
1
2
]
=
[
0.1
0.25
]

 

We know that:

h
1
=
[
h
1
1
h
1
2
]
=
σ
(
W
1
.
x
i
+
b
)

 

h
1
=
σ
(
[
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
w
1
21
x
1
+
w
1
22
x
2
+
b
1
2
]
)

 

h
1
=
σ
(
[
0.2
∗
(
−
0.32
)
+
0.15
∗
(
−
0.66
)
+
0.1
0.5
∗
(
−
0.32
)
+
0.6
∗
(
−
0.66
)
+
0.25
]
)
=
σ
(
[
−
0.063
−
0.306
]
)

 

h
1
=
[
0.484
0.424
]

 

Now that we have the outputs for the two neurons in the hidden layer, we can calculate the final output.



Moving on to the output layer with the linear activation function, we first compute the cumulative input to the neuron:

z
2
1
=
w
2
11
h
1
1
+
w
2
12
h
1
2
+
b
2
1
=
0.3
∗
0.484
+
0.2
∗
0.424
+
0.4
=
0.63

 

Since this is a regression problem, we have considered the activation function as the linear activation function, i.e., the input is sent as the output without any modification. Hence, the output is the same as the cumulative input:

h
2
1
=
z
2
1
=
0.63

This value of 0.63 is the prediction that the neural network makes in the first forward pass.

 

The matrix multiplication method will give us the same output as shown below:

h
2
=
(
W
2
h
1
+
b
2
)
=
(
[
w
2
11
w
2
12
]
[
h
1
1
h
1
2
]
)
+
b
2

 

h
2
=
(
W
2
h
1
+
b
2
)
=
(
[
0.3
0.2
]
[
0.484
0.424
]
)
+
0.4

 

h
2
=
[
0.63
]

 

Hence, performing the forward pass through the neural network using the input as [-0.32, -0.66] gives us the output as 0.63. The prediction is very different from the actual value of -0.54, but this is to be expected because we initialised the neural network with random weights and biases. As we train the neural network, we will update these parameters and get better predictions through multiple iterations. In the upcoming session, we will cover this process in depth. 

 

This was a demonstration of how information flows forward in a neural network from the input to the output, i.e., the forward pass to make a prediction. 


Question 1
What is the expression for the output 
H
l
 of the 
l
t
h
 layer in terms of the output 
H
l
−
1
 of the previous layer?

 ==>

 H
l
=
σ
(
W
l
H
l
−
1
+
b
l
)

✓ Correct
Feedback:
The output of the 
l
t
h
 layer 
H
l
 is obtained by applying the activation function 
σ
 on the cumulative input 
Z
l
. We know that 
Z
l
=
W
l
H
l
−
1
+
b
l
 where 
W
l
 and 
b
l
 are the weight matrix and bias vector respectively for the layer 
l
. Hence, 
H
l
=
σ
(
W
l
H
l
−
1
+
b
l
)
 is the correct answer.


 Question 2
As you have seen in the feedforward demonstration of the housing price prediction example, the output 
h
2
 obtained is 0.63 using a linear activation function in the output neuron. What will be the value of 
h
2
 if the activation function used was the sigmoid instead?

 ==>
 0.652

✓ Correct
Feedback:
If the output neuron has a linear activation function, then 
h
2
=
z
2
=
0.63
.  However, if 
the output neuron has a sigmoid activation function, then 
h
2
=
σ
(
z
2
)
=
σ
(
0.63
)
=
0.652
. Hence, this is the correct answer.


Question 3
As you have seen in the feedforward demonstration of the housing price prediction problem, the input used was 
x
=
[
−
0.32
−
0.66
]
. Now, let’s say we change the input to 
x
=
[
1.61
1.8
]
. What will be the output of the hidden layer, 
h
1
?

==>

 
z
1
=
[
1.322
1.572
]

✓ Correct
Feedback:
 
z
1
=
W
1
x
+
b
1
=
[
0.2
0.5
0.15
0.6
]
[
1.61
1.8
]
+
[
0.1
0.25
]

h
1
=
[
1.322
1.572
]


Question 4
We have seen in the neural network used for the housing price prediction problem, the hidden layer used the sigmoid activation function and the output layer used the linear activation function. In this case, the output, 
h
2
 in terms of the input vector 
x
 would look like the equation 
h
2
=
W
2
σ
(
W
1
x
+
b
1
)
+
b
2
. Now, if we were to use linear activation function throughout the neural network (instead of the sigmoid activation function), what would be the output 
h
2
 in terms of the input vector 
x
? 

==>

h
2
=
W
2
W
1
x
+
W
2
b
1
+
b
2

✓ Correct
Feedback:
We have the following solution, going from right to left of the network

h
2
=
z
2
 as it is linear activation
z
2
=
W
2
h
1
+
b
2
, the cumulative input sent to the output layer
h
1
=
z
1
 as it is linear activation (if it were sigmoid like in the original example, it would be
h
1
=
σ
(
z
1
)
z
1
=
W
1
x
+
b
1
 the cumulative input of hidden layer
When we combine all the equations, we get 
h
2
=
W
2
W
1
x
+
W
2
b
1
+
b
2

Question 5
As you have seen in the previous question, when we use linear activations throughout the neural network, the output 
h
2
 is linearly dependent on the input 
x
. Why do you think we don’t use linear activation functions in neural networks?

==>

The use of linear activation functions only will not enable the network to identify more general non-linear trends in the data.

✓ Correct
Feedback:
Non-linearity introduces much better ways to understand variations and underlying trends in the input data. You can refer to Session 1 - Segment 6 - “Different activation functions” to revise the concept. 


The use of linear activation functions will not polynomial dependencies to be identified in the input data.

✓ Correct
Feedback:
Sometimes, output depends on the input in a non-linear way like polynomial dependencies, eg.  
h
2
=
(
x
1
)
2
+
(
x
2
)
3
. These trends cannot be identified with linear functions and non-linear activation functions are needed to identify such trends.
 

 In the next segment, we will introduce a concise algorithm that can be used for any feedforward neural network. 


 # Feedforward Algorithm

Having understood how information flows in the network for a regression problem, let’s write the pseudocode for a feedforward pass through the network for a single data point 
x
i
.

The pseudocode for a feedforward pass is given below:

We initialise the variable 
h
0
 as the input: 
h
0
=
x
i
We loop through each of the layers computing the corresponding output for each layer, i.e., 
h
l
. 
For l in [1,2,......,L]: 
hl=σ(Wl.hl−1+bl)
We compute the prediction p by applying an activation function to the output from the previous layer, i.e., we apply a function to 
hL, as shown below.  
p=f(hL)


There are some important things to notice here. In both the regression and classification problems, the same algorithm is used till the last step. In the final step, in the classification problem, p defines the probability vector, which gives the probability of the data point belonging to a particular class among different possible classes or categories. In the regression problem, p represents the predicted output obtained, which we will normally refer to as 
hL

Let’s discuss the classification problem. We use the softmax output, which we had defined in an earlier session, which gives us the probability vector 
pi  of an input belonging to one of the multiple output classes (c):

⎡
⎢
⎣
pi1
.
pic
⎤
⎥
⎦

As per our understanding of the softmax function, we know that 
pij=e^wjhL / ∑ct=1Wth^L

j = [1,2,......,c] and c =  Number of classes.

Note that calculating 
p
i
j
=
e
w
j
h
L
∑
c
t
=
1
W
t
h
L
is often called normalising the vector 
p
i
.

 

Hence, the complete feedforward algorithm for the classification problem becomes:


h0=xi
For  l in [1,2,....,L]: 
hl=σ(Wl.hl−1+bl)
pi=eW0.hLpi=normalise(pi)



The classification feedforward algorithm has been extensively used in industries like finance, healthcare, travel etc. Considering the finance industry, one of the applications of this algorithm is categorising customer applications for credit cards as ‘Good’, ‘Bad’ or ‘Needing further analysis’ by credit card companies. For this, credit card companies consider different factors such as annual salary, any outstanding debts and age. These can be the features in the input vector that is fed into a neural network, which then predicts which category the customer belongs to. 
 

For the regression problem, we can skip the third and fourth steps, i.e., computing the probability and normalising the ‘predicted output vector’ p, because in a regression problem, the output is 
h
L
,i.e., the value we obtain from the single output node, and we usually compare the output obtained from the ANN directly with the ground truth. We do not need to perform any further operations on the predicted output to get probabilities in a regression problem.
 

Note that 
Wo
 (the weights of the output layer) can also be written as 
W^L+1


# Comprehension based Questions

Let’s try to implement the same algorithm for a classification problem and answer a few questions. 
Given below is the representation of an ANN. ​

Question 1
Dimension 
W
O
 (Single Correct) (One attempt only)
What will be the dimensions of 
W
O
, where 
W
O
 is the weight of the output layer?

==> 

(3,2)

✓ Correct
Feedback:
 Dimension = (Number of neurons in layer l, Number of neurons in layer l-1) for the weight matrix 
W
l

Question 2
Weight Matrix Calculation (Single Correct) (One attempt only) 

Consider, 
W
0
=
⎡
⎢
⎣
3
4
1
9
6
2
⎤
⎥
⎦
 ,
h
2
=
[
1
2
]
and bias =0. What will be 
W
0
.
h
2
?
==>

⎡
⎢
⎣
11
19
10
⎤
⎥
⎦

✓ Correct
Feedback:
 It is simple matrix multiplication.

⎡
⎢
⎣
3
4
1
9
6
2
⎤
⎥
⎦
[
1
2
]
+
0
=
⎡
⎢
⎣
3
∗
1
+
4
∗
2
1
∗
1
+
9
∗
2
6
∗
1
+
2
∗
2
⎤
⎥
⎦
=
⎡
⎢
⎣
11
19
10
⎤
⎥
⎦

Question 3
Consider 
W
O
=
⎡
⎢
⎣
3
4
1
9
6
2
⎤
⎥
⎦
  , 
h
2
=
[
1
2
]
and bias = 0. What will be the softmax output vector p, i.e., the output of the third layer? In other words, what will normalised(p) be (upto 5 decimal places)?

==>



⎡
⎢
⎣
0.00034
0.99954
0.00012
⎤
⎥
⎦

✓ Correct
Feedback:
We will use the following formula:

 

p
i
=
e
W
O
.
h
L
=
⎡
⎢
⎣
e
11
e
19
e
10
⎤
⎥
⎦
=
⎡
⎢
⎣
59874.1417
178482301
22026.4658
⎤
⎥
⎦

p
i
=
n
o
r
m
a
l
i
s
e
(
p
i
)
=
⎡
⎢
⎢
⎢
⎢
⎣
59874.1417
178564201.571
178482301
178564201.571
22026.4658
178564201.571
⎤
⎥
⎥
⎥
⎥
⎦
=
⎡
⎢
⎣
0.00034
0.99954
0.00012
⎤
⎥
⎦


Question 4
What is the predicted label in this example?
==>


2

✓ Correct
Feedback:
As the highest probability is for the neuron representing label 2, label 2 is the predicted label


The primary goal in machine learning is to get the predicted output to be the same or as close to the ground truth output as possible. We have seen the feedforward algorithm and learnt how to compute each element in an ANN. Now, we want to train the neural network to get the predicted output as close as possible to the actual output. In order to do this, in the next segment, we will discuss the Loss function, which quantifies the difference between the predicted output and the actual output. 

# Loss Function


Now that we know how to calculate the predicted output from a neural network when given an input, we want to check if the neural network predicted it correctly. We will revisit the calculations we had done in the previous segment on the housing price prediction problem.

Std. Number of Rooms	Std. House Size (sq. ft)	Predicted Price	Actual Price
-0.32	-0.66	0.63	-0.54
As you can see in the table above, the predicted price is not the same or even close to the actual price. So, we want to know how wrong the prediction of the neural network is and want to quantify this error in the prediction. A loss function or cost function will help us quantify such errors.

 

A loss function or cost function is a function that maps an event or values of one or more variables onto a real number intuitively, representing some ‘cost’ associated with the ‘event’, as shown below: 

L
(
y
,
^
y
)
=
f
:
(
y
,
^
y
)
→
R

Neural networks minimise the error in the prediction by optimising the loss function with respect to the parameters in the network. In other words, this optimisation is done by adjusting the weights and biases. We will see how this adjustment is done in subsequent sessions. For now, we will concentrate on how to compute the loss. 

 

In the case of regression, the most commonly used loss function is MSE/RSS.

 

In the case of classification, the most commonly used loss function is Cross Entropy/Log Loss.

 

Let’s consider the regression problem where we predict the house price, given the number of rooms and the size of the house. Here, we will use the RSS method to calculate the loss.





Std. Number of Rooms	Std. House Size (sq. ft.)	Predicted Price	Actual Price
-0.32	-0.66	0.63	-0.54
 

 In this example, we get a prediction 0.63, but the expected output is -0.54. Let’s calculate the loss using RSS: 

Loss(L)=12(actual−predicted)2=12(−0.54−0.63)2=0.68445

As given above, the MSE is the mean square error of all the samples in the given data. This gives us a quantified method of measuring how well the neural network is predicting the output. 

 

Now, let’s take a look at the loss function for the classification problem. In the next video, you will learn how to quantify the loss for a classification problem.


Now that we have learnt about the forward pass and the loss function for regression and classification problems, we know that given any input and its actual output, we can assess the behaviour of the neural network. 



Question 1
Which of the following loss functions can be used for regression analysis?

==>


RSS

✓ Correct
Feedback:
RSS (Residual Sum of Squares) gives the sum of the squares of the differences between the predicted and the actual output in Regression.


MSE

✓ Correct
Feedback:
MSE (Mean Square Error) gives the mean of the squares of the differences between the predicted and the actual output in Regression.


Question 2
For a binary classification problem, let’s say we have two input data points for which we obtained the predicted probability outputs. We also have the actual desired outputs. They are given in the table below,

Sr.No.	Actual Output	Predicted Output
Input 1	1	0.8
Input 2	0	0.2
Calculate the log loss for the above classification problem. You can use the following formula for your computation:

LogLoss=−1N∑Ni=1yi.log(p(yi))+(1−yi).log(1−p(yi))

where, N is the total number of data points, 
yi is the actual output and p(
yi) is the predicted output of the 
ith data point.



==>

0.0969

✓ Correct
Feedback:
Using the formula, 
LogLoss=−1N∑Ni=1yi.log(p(yi))+(1−yi).log(1−p(yi)),

we get, 
LogLoss=−12(log(0.8)+log(0.8))=0.0969

Note: When actual output is similar to the predicted output, the value obtained for log loss will be low.


Question 3
For the same binary classification problem as in the previous question, we have the following table.

Sr. No.	Actual Output	Predicted Output
Input 1	1	0.2
Input 2	0	0.8
Calculate the new log loss for the above classification problem.


==>

0.6989

✓ Correct
Feedback:
 Using the formula, 
L
o
g
L
o
s
s
=
−
1
N
∑
N
i
=
1
y
i
.
l
o
g
(
p
(
y
i
)
)
+
(
1
−
y
i
)
.
l
o
g
(
1
−
p
(
y
i
)
)

 

we get, 
L
o
g
L
o
s
s
=
−
1
2
(
l
o
g
(
0.2
)
+
L
o
g
(
0.2
)
)
=
−
l
o
g
(
0.2
)
=
0.6989

Note: When the actual output is not similar to the predicted output, the value obtained for log loss will be high.


Let’s now attempt a few questions based on this topic and then proceed to the next segment to understand how neural networks are trained in order to minimise the loss. 


Let’s now attempt a few questions based on this topic and then proceed to the next segment to understand how neural networks are trained in order to minimise the loss. 

## What Is Learning in Neural Networks
 

In this segment, you will understand how neural networks are trained. Recall that the training task is to compute the optimal weights and biases by minimising some cost function. Let's start with a quick recap on defining the training task.

The task of training neural networks is similar to that of other ML models such as linear regression and logistic regression. The predicted output (output from the last layer) minus the actual output is the cost (or the loss), and we have to tune the parameters 
w
 and 
b
 such that the total cost is minimised.  


The loss function for a regression model can be given as follows:

L
o
s
s
(
L
)
=
R
S
S
=
∑
(
a
c
t
u
a
l
−
h
L
)
2
L
o
s
s
(
L
)
=
f
(
W
,
b
)

 

To start training a neural network, we randomly initialise the weights at the outset.

An important point to note is that if the data is large (which is often the case), the loss calculation itself can get pretty messy. For example, if you have a million data points, they will be fed into the network (in batches), the output will be calculated using feedforward, and the loss/cost 
Li(forith data point) will be calculated. The total loss is the sum of losses of all the individual data points. Hence: 

Totalloss=L=L1+L2+L3+........+L1000000

The total loss L is a function of 
w
's and 
b
's. Once the total loss is computed, the weights and biases are updated (in the direction of decreasing loss). In other words, L is minimised with respect to the 
w
's and 
b
’s.


One important point to note here is that we minimise the average of the total loss and not the total loss that you will get to see shortly. Minimising the average loss implies that the total loss is getting minimised.


This can be done using any optimisation routine such as gradient descent. 


The parameter being optimised is iterated in the direction of reducing cost according to the following rule

Wnew=Wold−α∂L/∂W

The same can be written for biases. Note that weights and biases are often collectively represented by one matrix called W. Going forward, 
W
 will, by default, refer to the matrix of all weights and biases.


The main challenge is that 
W
 is a huge matrix, and thus, the total loss L as a function of 
W
 is a complex function. Let's watch the next video to understand how to deal with this complexity.


 As you learnt in the video above, the loss function for a very small and simple neural network can be quite complex. The best way to minimise this complex loss function is by using gradient descent.



 Question 1
Consider the minimisation of the univariate function 
L
(
w
)
=
w
2
.

Apply the gradient descent algorithm and show the value of 
w
 obtained in one iteration, assuming that we initialise 
w
0
 = 4 and use learning rate  
α
=
0.1
.
 

 ==>

 
3.2

✓ Correct
Feedback:
Use the following expression to compute the weight:
Wnew=Wold−α∂L∂w

Wnew=Wold−α∂L/∂w=4−0.1(8)=3.2


Question 2
Consider the minimisation of the function 
L
(
w
1
,
w
2
)
=
w
2
1
+
w
2
2
.
Apply the gradient descent algorithm and show the value of 
(
w
1
,
w
2
)
 obtained from one iteration, assuming that we initialise 
(
w
1
,
w
2
)
=
(
4
,
−
3.2
)
 and the learning rate 
α
=
0.1
.

==>



To apply the gradient descent algorithm to minimize the function L(w1,w2)=w12+w22 L(w_1, w_2) = w_1^2 + w_2^2 L(w1​,w2​)=w12​+w22​, we need to follow these steps:


(3.2,-2.56)

✓ Correct
Feedback:
Use the following expression to compute the weight:
Wnew=Wold−α∂L∂w


W
2
=
W
1
−
α
∂
L
∂
w
−
0.1
⎡
⎢
⎣
∂
L
∂
w
1
∂
L
∂
w
2
⎤
⎥
⎦
=
[
w
1
w
2
]
−
0.1
[
2
w
1
2
w
2
]
=
[
4
−
3.2
]
−
0.1
[
8
−
6.4
]
=
[
3.2
−
2.56
]

---


Compute the gradient of the function L(w1,w2) L(w_1, w_2) L(w1​,w2​):
The gradient of L(w1,w2) L(w_1, w_2) L(w1​,w2​) is given by the partial derivatives with respect to w1 w_1 w1​ and w2 w_2 w2​:
∇L(w1,w2)=(∂L∂w1,∂L∂w2)
\nabla L(w_1, w_2) = \left( \frac{\partial L}{\partial w_1}, \frac{\partial L}{\partial w_2} \right)
∇L(w1​,w2​)=(∂w1​∂L​,∂w2​∂L​)
Calculate the partial derivatives:
∂L∂w1=2w1
\frac{\partial L}{\partial w_1} = 2w_1
∂w1​∂L​=2w1​
∂L∂w2=2w2
\frac{\partial L}{\partial w_2} = 2w_2
∂w2​∂L​=2w2​
Therefore, the gradient is:
∇L(w1,w2)=(2w1,2w2)
\nabla L(w_1, w_2) = (2w_1, 2w_2)
∇L(w1​,w2​)=(2w1​,2w2​)


Evaluate the gradient at the initial point (w1,w2)=(4,−3.2) (w_1, w_2) = (4, -3.2) (w1​,w2​)=(4,−3.2):
∇L(4,−3.2)=(2⋅4,2⋅(−3.2))=(8,−6.4)
\nabla L(4, -3.2) = (2 \cdot 4, 2 \cdot (-3.2)) = (8, -6.4)
∇L(4,−3.2)=(2⋅4,2⋅(−3.2))=(8,−6.4)


Update the weights using the gradient descent update rule:
The update rule for gradient descent is:
wi(new)=wi(old)−α∂L∂wi
w_i^{(new)} = w_i^{(old)} - \alpha \frac{\partial L}{\partial w_i}
wi(new)​=wi(old)​−α∂wi​∂L​
where α \alpha α is the learning rate.
For w1 w_1 w1​:
w1(new)=w1(old)−α∂L∂w1
w_1^{(new)} = w_1^{(old)} - \alpha \frac{\partial L}{\partial w_1}
w1(new)​=w1(old)​−α∂w1​∂L​
w1(new)=4−0.1⋅8=4−0.8=3.2
w_1^{(new)} = 4 - 0.1 \cdot 8 = 4 - 0.8 = 3.2
w1(new)​=4−0.1⋅8=4−0.8=3.2
For w2 w_2 w2​:
w2(new)=w2(old)−α∂L∂w2
w_2^{(new)} = w_2^{(old)} - \alpha \frac{\partial L}{\partial w_2}
w2(new)​=w2(old)​−α∂w2​∂L​
w2(new)=−3.2−0.1⋅(−6.4)=−3.2+0.64=−2.56
w_2^{(new)} = -3.2 - 0.1 \cdot (-6.4) = -3.2 + 0.64 = -2.56
w2(new)​=−3.2−0.1⋅(−6.4)=−3.2+0.64=−2.56


Result after one iteration:
After one iteration of gradient descent with the initial point (4,−3.2) (4, -3.2) (4,−3.2) and learning rate α=0.1 \alpha = 0.1 α=0.1, the new values of (w1,w2) (w_1, w_2) (w1​,w2​) are:
(w1,w2)=(3.2,−2.56)
(w_1, w_2) = (3.2, -2.56)
(w1​,w2​)=(3.2,−2.56)


Thus, the value of (w1,w2) (w_1, w_2) (w1​,w2​) obtained from one iteration of the gradient descent algorithm is (3.2,−2.56) (3.2, -2.56) (3.2,−2.56).



Question 3
Gradient of Loss Function (Multiple Correct) (Two attempts only)
Consider an n-dimensional setting where the loss function L depends on n parameters. Which of the following statements regarding the gradient of the loss function with respect to the model parameters is/are correct? (Note: More than one option may be correct.)
 

 
The gradient is an n-dimensional vector.

✓ Correct
You missed this!
Feedback:
Since we are operating in an n-dimensional setting, the gradient will be an n-dimensional vector and not a scalar.


The gradient gives the direction in which the loss increases most rapidly.
 

✓ Correct
You missed this!
Feedback:
The gradient vector is in the direction in which the loss value increases most rapidly.


Question 4
Suppose a layer in your neural network has a large number of biases, - n biases, denoted by the variable b. In some iteration of the algorithm, the gradient is computed to be as follows:

∂
L
∂
B
=
⎡
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎣
∂
L
∂
b
1
∂
L
∂
b
2
.
.
.
∂
L
∂
b
J
∂
L
∂
b
j
+
1
∂
L
∂
b
j
+
2
.
.
.
∂
L
∂
b
n
⎤
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎦
=
⎡
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎢
⎣
0.45
−
0.30
.
.
.
∂
L
∂
b
j
0.20
0.00
.
.
.
∂
L
∂
b
n
⎤
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎥
⎦

Imagine an n-dimensional space whose each dimension (axis) corresponds to one parameter of the network. Based on the given scenario, select all the correct statement(s) from below. (Note: More than one option may be correct.)


==>


