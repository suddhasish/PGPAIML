Introduction
Welcome to the module on  Convolutional Neural Networks.

 

Convolutional Neural Networks, or CNNs, are neural networks specialised to work with visual data, i.e. images and videos (though not restricted to them). They are very similar to the vanilla neural networks (multilayer perceptrons) - every neuron in one layer is connected to every neuron in the next layer, they follow the same general principles of forward and backpropagation, etc. However, there are certain features of CNNs that make them perform extremely well on image processing tasks. 

 

By the end of this module, you will be able to understand the working principles of CNNs, compare various CNN architectures and be able to choose the right architecture for specific tasks. In transfer learning, you will learn to use large pre-trained networks for your own computer vision tasks. You will also be able to train CNNs using Python + Keras.


In this session
The first session covers the following topics:

The need for a new type of architecture for images
Reading digital images 
Understanding convolutions
The structure and topology of convolutional neural networks
Feature Maps 
Training the network




## A Specialised Architecture for Visual Data
Convolutional Neural Networks, or CNNs, are specialised architectures which work particularly well with visual data, i.e. images and videos. They have been largely responsible for revolutionalizing 'deep learning' by setting new benchmarks for many image processing tasks that were very recently considered extremely hard.

 

Let's start by understanding some common challenges in image processing.

 

Challenges in image processing


Let's consider the common task of visual recognition (like identifying a ‘cat’ or a ‘dog’) - trivial as it is for humans, it is still a big challenge for algorithms. Let’s look at some of the challenges:

Viewpoint variation: Different orientations of the image with respect to the camera.

Viewpoint  variation
Viewpoint variation
Scale variation: Different sizes of the object with respect to the image size.
Scale variation
Scale variation
Illumination conditions: Illumination effects.
Illumination condition
Illumination condition
Background clutter: Varying backgrounds.
Background clutter
Background clutter

CNNs - A specialised architecture for visual data
Although the vanilla neural networks can learn extremely complex functions, their architecture does not exploit what we know about how the 
brain reads and processes images. For this reason, although the vanilla neural networks are successful in solving many complex problems, 
they haven't been able to achieve any major breakthroughs in the image processing domain.    

 
On the other hand, the architecture of CNNs uses many of the working principles of the animal visual system, 
and thus they have been able to achieve extraordinary results in image-related learning tasks. 


The ImageNet Challenge
CNNs had first demonstrated their extraordinary performance in the ImageNet Large Scale Visual Recognition Challenge (ILSVRC).
The ILSVRC uses a list of about 1000 image categories or 'classes' and has about 1.2 million training images.

The original challenge is an image classification task.



You can see the impressive results of CNNs in the ILSVRC where they now outperform humans (having 5% error rate). 
The error rate of the ResNet, a recent variant in the CNN family, is close to 3%. In the following 
image a bar graph is drawn depicting the error rate of different models, as discussed the ResNet has an error rate of 3.5% close to 3. 


In the next segment, you will study the different ways in which CNNs are used for image-processing tasks.

## Applications of CNNs


In this segment, you will study some common types of image processing tasks which can be solved using CNNs. 

Some applications that we have discussed are:

Object localization: Identifying the local region of the objects (as a rectangular area) and classifying them.

Semantic segmentation: Identifying the exact shapes of the objects (pixel by pixel) and classifying them.

Optical Character Recognition (OCR): Recognise characters in an image. For example, in the top-left image, the output will be ‘1680’.



Let's see some more examples of image processing applications.


There are various other applications of CNNs in the healthcare sector. Many medical imaging applications used in radiology, cardiology, gastroenterology etc. involve classification, detection, and segmentation of objects which can be analysed using CNNs. 

In the next segment, you will study the motivation behind CNNs' architecture coming from the visual system of mammals. 

Q1)

Applications of CNN
Which of the following types of data can be analysed using CNNs? More than one options may be correct.


Images

✓ Correct
Feedback:
CNNs are most commonly used for analysing images. 


Video

✓ Correct
Feedback:
A video is a series of images (or frames). CNNs are commonly used for processing videos.


Audio

✓ Correct
Feedback:
CNN can also be used for audio processing. 


Text

✓ Correct
Feedback:
CNNs can also be applied to text, although their use is limited in this area.


# Understanding the Visual System of Mammals - I

We had mentioned that the architecture of CNNs is motivated by the visual system of mammals. In this segment, we will discuss an influential paper named '[Receptive field for single neurons in the cat’s striate cortex](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1363130/pdf/jphysiol01298-0128.pdf)' published by Hubel and Wiesel.


This was basically a bunch of experiments conducted to understand the visual system of a cat. In the experiments, spots of light (of various shapes and size) were made to fall on the retina of a cat and, using an appropriate mechanism, the response of the neurons in the cat's retina was recorded. This provided a way to observe which types of spots make some particular neurons 'fire', how groups of neurons respond to spots of certain shapes, etc.

Let’s look at some of the statements made in this paper.

Some of the important observations made in the study were:


Each neuron in the retina focuses on one part of the image and that part of the image is called the receptive field of that neuron.



Some of the important observations made in the study were:


Each neuron in the retina focuses on one part of the image and that part of the image is called the receptive field of that neuron.

There are excitatory and inhibitory regions in the receptive field. The neurons only ‘fire’ when there is a contrast between the excitatory and the inhibitory regions. If we splash light over the excitatory and inhibitory regions together, because of no contrast between them, the neurons don’t ‘fire’ (respond). If we splash light just over the excitatory region, neurons respond because of the contrast.

The figure below shows a certain region of the receptive field of a cat. The excitatory region (denoted by the triangular marks) is at the centre surrounded by the inhibitory region marked by the crosses.


The strength of the response is proportional to the summation over only the excitatory region (not inhibitory region). 
Later, you will study the pooling layer in CNNs which corresponds to this observation.



In the next segment, we will study some more observations from this study that influenced the CNN architecture.



The strength of the response is proportional to the summation over only the excitatory region (not inhibitory region). Later, you will study the pooling layer in CNNs which corresponds to this observation.

 

In the next segment, we will study some more observations from this study that influenced the CNN architecture.

Q1) 
Receptive Field
Each neuron in the retina is trained to 'look at':
==>

A particular patch (region) of the image

✓ Correct
Feedback:
Each neuron is trained to look at only a certain patch of the image. This patch is called the receptive field of that neuron.

Q2) Understanding the Visual System of Mammals
The following figure shows the excitatory and the inhibitory regions (crosses and triangles respectively) of a certain receptive field of a cat:
Which of the following shapes of light will invoke the strongest response by the neurons?

==>

A vertical slit shaped light falling only on the excitatory region

✓ Correct
Feedback:
Neuron only ‘fires’ when there is a contrast between the excitatory region and the inhibiting region.

Q3) 

Understanding the Visual System of Mammals
The excitatory and the inhibitory regions are:

==>


Regions in the receptive field which invoke a ‘response’ from the neurons trained to focus on that receptive field

✓ Correct
Feedback:
All neurons do not respond to light falling on a receptive field, only the ones trained to focus on that receptive field do

Reference
The paper ['Receptive field for single neurons in the cat’s striate cortex'](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC1363130/pdf/jphysiol01298-0128.pdf) by Hubel and Wiesel. 


# Understanding the Visual System of Mammals -II

 You have already seen that every neuron is trained to look at a particular patch in the retina, called the receptive field of that neuron.

 This raises some questions such as: Are the shapes and sizes of these receptive fields identical across neurons or do they vary? Do all the neurons 'see' the same 'features', or are some neurons specialised to 'see' certain features?

 Let's seek answers to some of these questions. You will also study, at a high level, how higher-level abstract 'features' such as 'movement’ are detected by the visual system.


 In this lecture, we studied two main observations from the paper:

The receptive fields of all neurons are almost identical in shape and size

There is a hierarchy in the units: Units at the initial level do very basic tasks such as picking raw features (such as horizontal edges) in the image. The subsequent units extract more abstract features, such as identifying textures, detecting movement, etc. The layers 'higher' in the hierarchy typically aggregate the features in the lower ones.


The image below illustrates the hierarchy in units  - the first level extracts low-level features (such as vertical edges) from the image, while the second level calculates the statistical aggregate of the first layer to extract higher-level features (such as texture, colour schemes etc.).


Using this idea, if we design a complex network with multiple layers to do image classification (for example), the layers in the network should do something like this:

The first layer extracts raw features, like vertical and horizontal edges

The second layer extracts more abstract features such as textures (using the features extracted by the first layer)

The subsequent layers may identify certain parts of the image such as skin, hair, nose, mouth etc. based on the textures.

Layers further up may identify faces, limbs etc. 

Finally, the last layer may classify the image as 'human', 'cat' etc.



Apart from explaining the visual system, the paper also suggested that similar phenomena have been observed in the auditory system and touch and pressure in the somatosensory system. This suggests that CNN-like architectures can be used for speech processing and analysing signals coming from touch sensors or pressure sensors as well. 


Let's have a look at some of the conclusions.






We have already discussed most of the key ideas of the CNN architecture through this paper. Summarising the main points below:

Each unit, or neuron, is dedicated to its own receptive field. Thus, every unit is meant to ignore everything other than what is found in its own receptive field.

The receptive field of each neuron is almost identical in shape and size.

The subsequent layers compute the statistical aggregate of the previous layers of units. This is analogous to the 'pooling layer' in a typical CNN.

Inference or the perception of the image happens at various levels of abstraction. The first layer pulls out raw features, subsequent layers pull out higher-level features based on the previous features and so on. Finally, the network gets an overall perception of an image in the last layer.


Layers in Your Visual Cortex While Driving
CNNs are similar to normal neural networks (MLPs) in that they have layers of neurons arranged sequentially. The paper suggested that the layers are arranged in a hierarchical manner, i.e. the layers further up (towards the right in usual notation) extract more 'abstract' features than the previous layers.

Let's assume that your visual cortex (the region of the brain that receives and processes visual information) has five layers (apart from the input) of neurons. Also, say you are driving, and in the process, you are doing object detection -  i.e. detecting the area where an object is on the road or footpath (a pedestrian, a car, a traffic signal, a tree etc.) and recognising it:

 '

 Which of the following statements can be true? Mark all correct possibilities:


The first layer extracts basic features from the image, such as edges, while the second extracts textures, colour patterns, etc.

✓ Correct
Feedback:
The initial layers extract basic patterns, while the latter ones extract higher-level patterns.


The fourth layer may be detecting the area (the rectangular box) where an object is located, while the fifth (last) layer classifies it into one of the categories (person, car etc.)

✓ Correct
Feedback:
Classification of the object can only be done after finding where it is located

## Introduction to CNNs

Let's dig a little deeper into CNN architectures now. In this segment, we will analyse the architecture of a popular CNN called VGGNet. 
Observing the VGGNet architecture will give you a high-level overview of the common types of CNN layers before you study each one of them in detail.


To summarise, there are three main concepts you will study in CNNs:

Convolution, and why it 'shrinks' the size of the input image
Pooling layers
Feature maps



The VGGNet architecture is shown below.

The VGGNet was specially designed for the ImageNet challenge which is a classification task with 1000 categories. Thus, the softmax layer at the end has 1000 categories. The blue layers are the convolutional layers while the yellow ones are pooling layers. You will study each one of them shortly.

 
Finally, the green layer is a fully connected layer with 4096 neurons, the output from which is a vector of size 4096.


The most important point to notice is that the network acts as a feature extractor for images. For example, the CNN above extracts a 4096-dimensional feature vector representing each input image. In this case, the feature vector is fed to a softmax layer for classification, but you can use the feature vector to do other tasks as well (such as video analysis, object detection, image segmentation etc.).

 

Next, you will see how one can do video analysis using the feature vector extracted by the network.

Q2) 

Feature Extractor
Which of the following operation acts as a feature extractor?

==> 

Convolution

✓ Correct
Feedback:
Convolution operation acts as a feature extractor.


Q3) 

Softmax Layer
 


Which of the following is correct for last softmax layer in the CNN?

Note - More than one option maybe correct. 

==> 



Each class probability lies in the range 0-1

✓ Correct
Feedback:
Probability always lies between 0 and 1



Sum of class probability is 1

✓ Correct
Feedback:
Sum of probability is 1

# Reading Digital Images

Before we dig deeper into the architecture of CNNs, let's understand what images are and how they are fed into CNNs.

You already know that the input to any neural network should be numeric. Fortunately, images are naturally represented as arrays (or matrices) of numbers. Let's study the typical structure of images.
 
To summarize:

Images are made up of pixels.

A number between 0-255 represents the colour intensity of each pixel.

Each pixel in a colour image is an array representing the intensities of red, blue and green. The red, blue and green layers are called channels.


In a grayscale image (a 'black and white' image), only one number is required to represent the intensity of white. 
Thus, grayscale images have only one channel.  

Now that you know that images can be represented as numbers, let’s see an example of how one would read images into Python.

You can download the notebook at this [link](https://github.com/ContentUpgrad/Convolutional-Neural-Networks). 

Let’s summarise the important points. Consider this sample image of a 'zero' from the MNIST dataset.



The height and width of this image are 18 pixels, so it is stored as an 18 x 18 array

Each pixel's value lies between 0-255

The pixels having a value close to 255 appear white (since the pixels represent the intensity of white), and those close to 0 appear black

 

Let’s see this for a colour image.


The height and width of the image are 4 pixels.

Here, three numbers make each pixel (representing RGB). So, there are 3 channels here.

The size of the matrix is thus 4 x 4 x 3


Note that all colours can be made by mixing red, blue and green at different degrees of 'saturation' (0-100% intensity). For example, a pure red pixel has 100% intensity of red, and 0% intensity of blue and green. So, it is represented as (255,0,0). White is the combination of 100% intensity of red, green and blue. So, it is represented as (255,255,255).

 

Why is the Range of Pixel Values 0-255?

Usually, 8-bits (1 byte) are used to represent each pixel value. Since each bit can be either 0 or 1, 8-bits of information allows for 
2^8=256 possible values. Therefore, the range of each pixel is 0-255.

Let's now quickly summarise what you have learnt about images.


In the next few segments, you will study the architecture of CNNs in detail. 

Q1)
Channels
How many channels are there in an image? Mark all correct statements:


If it is a grayscale image, number of channels is 1

✓ Correct
Feedback:
A greyscale image has single channel. 



If it is a colour image, and if we represent by RGB (Red, Green, Blue), the number of channels is 3

✓ Correct
Feedback:
If it is a colour image, and if we represent by RGB (Red, Green, Blue), the number of channels is 3 for Red, Green and Blue. 


If we represent an image in HSV (Hue, Saturation, Value) format, the number of channels is 3.

✓ Correct
Feedback:
If we represent an image in HSV (Hue, Saturation, Value) format, the number of channels is 3 for Hue, Saturation and Value


# Video Analysis
In this segment, you will understand the process of video analysis using CNNs. A video is basically a sequence of frames where each frame is an image. You already know that CNNs can be used to extract features from an image. Let's now see how CNNs can be used to process a series of images (i.e. videos). 


Let's summarise the process of video analysis using a CNN + RNN (Recurrent Neural Network) stack. At this point, you only need to understand that RNNs are good at processing sequential information such as videos (a sequence of images), text (a sequence of words or sentences), etc. You will study RNN in the next module. 

 

For a video classification task, here's what we can do. Suppose the videos are of length 1 minute each. If we extract frames from each video at the rate of 2 frames per second (FPS), we will have 120 frames (or images) per video. Push each of these images into a convolutional net (such as VGGNet) and extract a feature vector (of size 4096, say) for each image. Thus, we have 120 feature vectors representing each video. 

 

These 120 feature vectors, representing a video as a sequence of images, can now be fed sequentially into an RNN which classifies the videos into one of the categories.

 

The main point here is that a CNN acts as a feature extractor for images, and thus, can be used in a variety of ways to process images.

 

In the next few segments, you will study the main elements of CNNs in detail - convolutions, pooling, feature maps etc.






## Understanding Convolutions - I
We had mentioned three main terminologies related to the CNN architecture:

Convolutions
Pooling 
Feature Maps
 

In this and the next few segments, we will go through each one of them in detail. Let's start by understanding how convolutions work.

Convolution
Mathematically, the convolution operation is the summation of the element-wise product of two matrices. Let’s take two matrices, X and Y. If you 'convolve the image X using the filter Y', this operation will produce the matrix Z. 

 

X

1	2	3
2	0	0
7	9	1
 

Y
3	2	0
3	0	1
0	5	2
 

Z
1x3=3	2x2=4	3x0=0
2x3=6	0x0=0	0x1=0
7x0=0	9x5=45	1x2=2
 

Finally, you compute the sum of all the elements in Z to get a scalar number, i.e. 3+4+0+6+0+0+0+45+2 = 60. 

 

In the next segment we will continue and extend our learning and discussions on convolution neural networks.



Understanding Convolution
Given an input matrix X of size (2,2) and filter matrix Y of size (2,2), find the output value after we perform convolution of X and Y.

X
1	4
0	9

Y
4	0
2	1

==>


13

✓ Correct
Feedback:
Convolution of 2 matrices X and Y is : 1x4 + 4x0 + 0x2 + 9x1 = 13

## Understanding Convolutions - II

Now, that you have understood the basic idea of filters and convolutions, let's continue our example from the previous page to understand how convolutions are used to detect features (such as vertical or horizontal edges) in an image.


This was an example of how the convolution operation (using an appropriate filter) detects certain features in images, such as horizontal or vertical edges.

 

In the convolution output using the first filter, only the middle two columns are nonzero while the two extreme columns (1 and 4) are zero. This is an example of vertical edge detection.  


Note that each column of the 4 x 4 output matrix looks at exactly three columns of the input image. The values in the four columns represent the amount of change (or gradient) in the intensity of the corresponding columns in the input image along the horizontal direction.

 

For example the output is 0 (20 - 20 or 10 - 10) in the columns 1 and 4, denoting that there is no change in intensity in the first three and the last three columns of the input image respectively.

 

On the other hand, the output is 30 (20 - (-10)) in the columns 2 and 3, indicating that there is a gradient in the intensity of the corresponding columns of the input image.

 

Other filters
The filter below is used for horizontal edge detection. Convince yourself that this filter will be able to detect horizontal edges in an image.

 

Filter - Horizontal Edge Detection
-1	-1	-1
0	0	0
1	1	1

Note that each column of the 4 x 4 output matrix looks at exactly three columns of the input image. The values in the four columns represent the amount of change (or gradient) in the intensity of the corresponding columns in the input image along the horizontal direction.

 

For example the output is 0 (20 - 20 or 10 - 10) in the columns 1 and 4, denoting that there is no change in intensity in the first three and the last three columns of the input image respectively.

 

On the other hand, the output is 30 (20 - (-10)) in the columns 2 and 3, indicating that there is a gradient in the intensity of the corresponding columns of the input image.

 

Other filters
The filter below is used for horizontal edge detection. Convince yourself that this filter will be able to detect horizontal edges in an image.

 

Filter - Horizontal Edge Detection
-1	-1	-1
0	0	0
1	1	1
 

 

Convolution Example

Let's see one more example of a convolution operation. Consider the image shown below and convolve it with the 3 x 3 filter to produce a 3 x 3 array.

 

Image
1	0	3	7	2
5	7	10	0	7
4	12	0	2	0
0	1	11	1	3
10	7	0	8	1
 

Filter 
1	0	1
-1	0	0
0	1	0
 

The GIF below demonstrates the convolution operation.

 

 Although we have only seen very simple filters, one can design arbitrarily complex filters for detecting edges and other patterns. For example, the image below shows the Sobel filter which can detect both horizontal and vertical edges in complex images. 

 We have discussed some simple examples of filters and convolutions, and you may have some questions such as 'can filters have arbitrary sizes', 'can any filter convolve any image', etc. In the next segment, we will be able to answer these questions using the concepts of stride and padding.


 Diagonal Edge Detection
Which of the following filters can be used to detect a diagonal edge (an edge at an angle of 45 degrees from the x-axis) in an image? Choose all the correct options.


⎡
⎢
⎣
1
1
0
1
0
−
1
0
−
1
−
1
⎤
⎥
⎦

✓ Correct
You missed this!
Feedback:
A diagonal edge will have pixel values such that there is a gradient in the direction perpendicular to the 45-degree line, i.e. a gradient in pixel values from top-left to bottom-right. The filter should also have a gradient in this direction.


⎡
⎢
⎣
2
2
0
2
0
−
2
0
−
2
−
2
⎤
⎥
⎦

✓ Correct
Feedback:
A diagonal edge will have pixel values such that there is a gradient in the direction perpendicular to the 45-degree line, i.e. a gradient in pixel values from top-left to bottom-right. The filter should also have a gradient in this direction.


## Stride and Padding
In the previous segment, while doing convolutions, each time we computed the element-wise product of the filter with the image, we had moved the filter by exactly one pixel (both horizontally and vertically). But that is not the only way to do convolutions - you can move the filter by an arbitrary number of pixels. This is the concept of stride.

 

Let's study strides in a little more detail. The notion of strides will also introduce us to another important concept - padding.

Possible Combinations of Image Size, Filter and Stride Length
The professor mentioned that one cannot use just any combination of image size, filter size and stride length - you need to choose the values such that an integral number of convolutions is possible. 

Consider that you have an image of size (n, n), a square filter of size (k, k) and the stride length is s. Which of the following combinations of n, k and s will result in an integral number of convolutions (without padding)? More than one options may be correct.

You saw that there is nothing sacrosanct about the stride length 1. If you think that you do not need many fine-grained features for your task, you can use a higher stride length (2 or more).

 

You also saw that you cannot convolve all images with just any combination of filter and stride length. For example, you cannot convolve a (4, 4) image with a (3, 3) filter using a stride of 2. Similarly, you cannot convolve a (5, 5) image with a (2, 2) filter and a stride of 2 (try and convince yourself). 

 

To solve this problem, you use the concept of padding.

 

### Padding
The following are the two most common ways to do padding:

Populating the dummy row/columns with the pixel values at the edges

Populating the dummy row/columns with zeros (zero-padding)

 

Stride and Padding
Stride and Padding


You may have noticed that when you convolve an image without padding (using any filter size), the output size is smaller than the image (i.e. the output 'shrinks'). For example. when you convolve a (6, 6) image with a (3, 3) filter and stride of 1, you get an output of (4, 4). 

 

If you want to maintain the same size, you can use padding. Let's see how padding maintains the image size.


You saw that doing convolutions without padding reduces the output size. It is important to note that only the width and height decrease (not the depth) when you convolve without padding.  The depth of the output depends on the number of filters used -  we will discuss this in a later segment.

 

Why Padding is Necessary?

You saw that doing convolutions without padding will 'shrink' the output. For example, convolving a (6, 6) image with a (3, 3) filter and stride of 1 gives a (4, 4) output. Further, convolving the (4, 4) output with a (3, 3) filter will give a (2, 2) output. The size has reduced from (6, 6) to (2, 2) in just two convolutions. Large CNNs have tens (or even hundreds) of such convolutional layers (recall VGGNet), so we will be incurring massive 'information loss' as we build deeper networks!

 

This is one of the main reasons padding is important - it helps maintain the size of the output arrays and avoid information loss. Of course, in many layers, you actually want to shrink the output (as shown below), but in many others, you maintain the size of the output.

Until now, you have been computing the output size (using the input image size, padding and stride length) manually. In the next segment, you will learn generic formulas which will help reduce some of the manual work that you have been doing.



Given the following size :

Image  - n x n
Filter - k x k
Padding - P
Stride - S
 

After padding, we get an image of size (n + 2P) x (n+2P). After we convolve this padded image with the filter, we get:

 

Size of convolved image = 
(
n
+
2
P
−
k
S
+
1
)
,
(
n
+
2
P
−
k
S
+
1
)

 


Until now, we have applied convolution only on 2D arrays, but most images are coloured and thus have multiple channels (e.g. RGB). In the next segment, you will learn to convolve images with multiple channels.

Stride
Given an input image of size 224x224, a filter of size 5x5 and padding of 3, what are the possible values of stride S?


==>


✓ Correct
You missed this!
Feedback:
(n+2P-k) should be divisible by stride 's'. So, (224+ 2x3 - 5) = 225. should be divisible by any possible values


Feedback:
(n+2P-k) should be divisible by stride 's'. So, (224+ 2x3 - 5) = 225 should be divisible by any possible . 225 is divisible by 3. 


Q2)
Padding
Given an input image of size 224x224, a filter of size 5x5 and stride of 2, what are the possible values of padding?
==>


Not possible

✓ Correct
Feedback:
(n+2P-k) should be divisible by stride 's'. So, (224 + 2xPadding -5) should be divisible by 2. This is not possible for any value of padding. 

Q3) 

Output Size
The tables below enlist some combinations of the input size, filter size, stride length, padding and the output size. Match the rows in the left table corresponding to the outputs in the right table: (One or more options may be correct)



==>


a->e, b->f, c->d 

✓ Correct
You missed this!
Feedback:
calculate the output size using ((n+2P-k)/S +1, (n+2P-k)/S) +1))

Q4) 

Padding and Output Size
Doing convolution without padding (assume that you are using a normal convolution with a k x k filter ,where k>1, without shrinking it towards the edges etc.) : 

==>

Always reduces the size of the output

✓ Correct
Feedback:
Doing convolutions without padding always reduces the output size. You can see that from the formula as well: (n - k)/s will be less than n for all positive values of k >1.


# Weights of a CNN

So far, we have been doing convolutions only on 2D arrays (images), say of size 6x6. But most real images are coloured (RGB) images and are 3D arrays of size m x n x 3. Generally, we represent an image as a 3D matrix of size height x width x channels.

 


To convolve such images, we simply use 3D filters. The basic idea of convolution is still the same - we take the element-wise product and sum up the values. The only difference is that now the filters will be 3-dimensional, For example: 3 x 3 x 3, or 5 x 5 x 3 (the last '3' represents the fact that the filter has as many channels as the image). 

 

Let's now see how convolutions are performed on 3D arrays and what it is that a CNN 'learns' during training.

To summarise, you learnt the following:

We use 3D filters to perform convolution on 3D images. For example: if we have an image of size (224, 224, 3), we can use filters of sizes (3, 3, 3), (5, 5, 3), (7, 7, 3) etc. (with appropriate padding etc.). We can use a filter of any size as long as the number of channels in the filter is the same as that in the input image.
The filters are learnt during training (i.e. during backpropagation). Hence, the individual values of the filters are often called the weights of a CNN.

 

Comprehension - weights and biases 
In the discussion so far, we have talked about only weights, but convolutional layers (i.e. filters) also have biases. Let's see an example to understand this concretely.

 

Suppose we have an RGB image and a (2, 2, 3) filter as shown below. The filter has three channels, and each channel of the filter convolves the corresponding channel of the image. Thus, each step in the convolution involves the element-wise multiplication of 12 pairs of numbers and adding the resultant products to get a single scalar output.




The GIF below shows the convolution operation - note that in each step, a single scalar number is generated, and at the end of the convolution, a 2D array is generated:



You can express the convolution operation as a dot product between the weights and the input image. If you treat the (2, 2, 3) filter as a vector 
w
 of length 12, and the 12 corresponding elements of the input image as the vector 
p
 (i.e. both unrolled to a 1D vector), each step of the convolution is simply the dot product of 
w
T
 and 
p
. The dot product is computed at every patch to get a (3, 3) output array, as shown above.

 

Apart from the weights, each filter can also have a bias. In this case, the output of the convolutional operation is a (3, 3) array (or a vector of length 9). So, the bias will be a vector of length 9. However, a common practice in CNNs is that all the individual elements in the bias vector have the same value (called tied biases). For example, a tied bias for the filter shown above can be represented as:

 

w
T
.
x
+
b
=
⎡
⎢
⎢
⎣
s
u
m
(
w
T
.
p
11
)
s
u
m
(
w
T
.
p
12
)
s
u
m
(
w
T
.
p
13
)
s
u
m
(
w
T
.
p
21
)
s
u
m
(
w
T
.
p
22
)
s
u
m
(
w
T
.
p
23
)
s
u
m
(
w
T
.
p
31
)
s
u
m
(
w
T
.
p
32
)
s
u
m
(
w
T
.
p
33
)
⎤
⎥
⎥
⎦
+
⎡
⎢
⎣
b
b
b
b
b
b
b
b
b
⎤
⎥
⎦

                      

                      
=
⎡
⎢
⎣
−
4
−
5
5
3
11
6
0
1
0
⎤
⎥
⎦
+
⎡
⎢
⎣
b
b
b
b
b
b
b
b
b
⎤
⎥
⎦

 


 

The other way is to use untied biases where all the elements in the bias vector are different, i.e. 
b
11
,
b
12
,
.
.
.
.
,
b
m
n
, but that is much less common than using tied biases.

 

In the next segment, we will study feature maps.



# Feature Maps

From the previous segment, you know that the values of the filters, or the weights, are learnt during training. Let's now understand how multiple filters are used to detect various features in images. In this lecture, you will study neurons and feature maps.

Let's summarise the important concepts and terms discussed above: 

A neuron is basically a filter whose weights are learnt during training. For example, a (3, 3, 3) filter (or neuron) has 27 weights. Each neuron looks at a particular region in the input (i.e. its 'receptive field').
A feature map is a collection of multiple neurons each of which looks at different regions of the input with the same weights. All neurons in a feature map extract the same feature (but from different regions of the input). It is called a 'feature map' because it is a mapping of where a certain feature is found in the image. 



The figure below shows two neurons in a feature map (the right slab) along with the regions in the input from which the neurons extract features. 



In the figure above, the two neurons produce two feature maps. You can have multiple such neurons convolve an image, each having a different set of weights, and each produces a feature map.


## Comprehension - Feature Maps
Consider the VGGNet architecture shown below. The first convolutional layer takes the input image of size (224, 224, 3), uses a (3, 3, 3) filter (with some padding), and produces an output of (224, 224). This (224, 224) output is then fed to a ReLU to generate a (224, 224) feature map. Note that the term 'feature map' refers to the (non-linear) output of the activation function, not what goes into the activation function (i.e. the output of the convolution).

 

Similarly, multiple other (224, 224) feature maps are generated using different (3, 3, 3) filters. In the case of VGGNet, 64 feature maps of size (224, 224) are generated, which are denoted in the figure below as the tensor 224 x 224 x 64. Each of the 64 feature maps try to identify certain features (such as edges, textures etc.) in the (224, 224, 3) input image.


The (224, 224, 64) tensor is the output of the first convolutional layer.  In other words, the first convolutional layer consists of 64 (3, 3, 3) filters, and hence contains 64 x 27 trainable weights (assuming there are no biases).

 

The 64 feature maps, or the (224, 224, 64) tensor, is then fed to a pooling layer. You will study the pooling layer in the next segment

Q2)

Output Size
Given an image of size 128x128x3, a stride of 1, padding of 1, what will be the size of the output if we use 32 kernels of size 3x3x3?

==>


128x128x32

✓ Correct
Feedback:
Each filter will produce a feature map of size 128x128 (with stride and padding of 1).  Thus, 32  filters will produce 32 feature maps of size 128x128.

Q3)

Output Size
Given an image of size 128x128x3, a stride of 1, zero padding, what will be the size of the output if we use 32 kernels of size 3x3x3?

==>

To determine the output size of a convolutional layer, we need to consider the input dimensions, the filter size, the stride, and the padding. Let's break down the problem step by step.
Given:

Input image size: 128x128x3 (Height x Width x Depth)
Filter size: 3x3x3 (Height x Width x Depth)
Number of filters: 32
Stride: 1
Padding: 1

Step-by-Step Calculation:


Calculate the output height and width:
The formula to calculate the output dimensions (height and width) of a convolutional layer is:
Output dimension=Input dimension−Filter size+2×PaddingStride+1
\text{Output dimension} = \frac{\text{Input dimension} - \text{Filter size} + 2 \times \text{Padding}}{\text{Stride}} + 1
Output dimension=StrideInput dimension−Filter size+2×Padding​+1
Plugging in the values for height and width:
Output height=128−3+2×11+1=128−3+21+1=1271+1=128
\text{Output height} = \frac{128 - 3 + 2 \times 1}{1} + 1 = \frac{128 - 3 + 2}{1} + 1 = \frac{127}{1} + 1 = 128
Output height=1128−3+2×1​+1=1128−3+2​+1=1127​+1=128
Output width=128−3+2×11+1=128−3+21+1=1271+1=128
\text{Output width} = \frac{128 - 3 + 2 \times 1}{1} + 1 = \frac{128 - 3 + 2}{1} + 1 = \frac{127}{1} + 1 = 128
Output width=1128−3+2×1​+1=1128−3+2​+1=1127​+1=128
So, the output height and width are both 128.


Calculate the output depth:
The depth of the output feature map is determined by the number of filters used. Since we are using 32 filters, the output depth will be 32.


Final Output Size:
Combining the output height, width, and depth, the size of the output feature map will be:
128×128×32
128 \times 128 \times 32
128×128×32
Explanation:

Each of the 32 filters will produce a feature map of size 128x128.
Therefore, with 32 filters, we will have 32 such feature maps, each of size 128x128.
The depth of the output feature map corresponds to the number of filters, which is 32.

Thus, the final output size is 128×128×32128 \times 128 \times 32128×128×32.
Summary:
Given an input image of size 128x128x3, a stride of 1, and padding of 1, using 32 kernels of size 3x3x3 will produce an output of size 128x128x32.


Q4)
Feature Map and Activation
FIll in the blank: The values in a feature map are ____ related to the weights of the filter generating the map.

==>

Non-linearly

✓ Correct
Feedback:
Feature map is the output from the activation function, which is usually non-linear (such as ReLU). That is, for a patch vector p and weight vector w, the values in the feature map will be 
f
(
w
T
.
p
)
 where 
f
 is a non-linear activation function.


 # Pooling
In our earlier discussion on the experiments by Hubel and Wiesel, we had observed the following statement:

The strength of the response (of the retinal neurons) is proportional to the summation over the excitatory region. 
After extracting features (as feature maps), CNN's typically aggregate these features using the pooling layer. Let's see how the pooling layer works and how it is useful in extracting higher-level features.



Pooling tries to figure out whether a particular region in the image has the feature we are interested in or not. It essentially looks at larger regions (having multiple patches) of the image and captures an aggregate statistic (max, average etc.) of each region. In other words, it makes the network invariant to local transformations.

 

The two most popular aggregate functions used in pooling are 'max' and 'average'. The intuition behind these are as follows:

Max pooling: If any one of the patches says something strongly about the presence of a certain feature, then the pooling layer counts that feature as 'detected'.
Average pooling: If one patch says something very firmly but the other ones disagree,  the pooling layer takes the average to find out.

Let's now look at an example of max pooling and understand some potential drawbacks of the pooling operation.



Let's summarise the example of pooling used in the lecture:

In the above figure, you can observe that only the width and height of the input reduces. Let's extend this pooling operation to multiple feature maps:


You can observe that pooling operates on each feature map independently. It reduces the size (width and height) of each feature map, but the number of feature maps remains constant. 

 

Pooling has the advantage of making the representation more compact by reducing the spatial size (height and width) of the feature maps, thereby reducing the number of parameters to be learnt. On the other hand, it also loses a lot of information, which is often considered a potential disadvantage. Having said that, pooling has empirically proven to improve the performance of most deep CNNs.

 

Can we design a network without pooling? Capsule networks were designed to address some of these potential drawbacks of the conventional CNN architecture. The paper on Capsule networks  is provided below.



In the next segment, we will summarise all the concepts discussed till now.

Q1)

Pooling
Which of the following statements related to pooling are correct?

==>

It makes the network invariant to local transformations.

✓ Correct
You missed this!
Feedback:
Since it takes an average, max or some other operation over group of pixel, it does not look at an individual pixel, making network invariant to local transformation.  



It makes the representation of the feature map more compact, thereby reducing the number of parameters in the network.

✓ Correct
Feedback:
It decreases the height and width, which reduces the number of parameters in a feature map. 


It reduces only the width and the height.

✓ Correct
Feedback:
It reduces only the width and the height, not the depth.


Q2) 

Pooling parameters
How many trainable parameters are there in the pooling layer?

==>

0

✓ Correct
Feedback:
There are no parameters in pooling. The pooling layer just computes the aggregate of the input. For e.g. in max pooling, it takes max over group of pixels. We do not need to adjust any parameter to take max

Q3)

Average Pooling
Find the output of the 'average pooling' in the following matrix X with a stride length of 2.


X

1	6	12	9
3	9	0	5
3	5	1	7
6	4	0	1



==>

4.75	6.5
4.5	2.25
✓ Correct
Feedback:
Average pooling is , take for example the first number, 4.75 is average of first 4 numbers, that is (1+6+3+9) /4 .  Similarly, calculate for others.  

# Putting the Components Together
You have now studied all the main components of a typical CNN - convolutions, feature maps, pooling layers etc. Let’s now quickly summarise and put them together to get an overall picture of CNNs' architecture. 

To summarise, a typical CNN layer (or unit) involves the following two components in sequence:

1. We start with an original image and do convolutions using multiple filters to get multiple feature maps.

2. A pooling layer takes the statistical aggregate of the feature maps

Typically, deep CNNs have multiple such CNN units (i.e. feature map-pooling pairs) arranged sequentially. The following lecture will discuss this in detail.



To summarise, a typical CNN has the following sequence of CNN layers:

1. We have an input image which is convolved using multiple filters to create multiple feature maps
2. Each feature map, of size (c, c), is pooled to generate a (c/2, c/2) output (for a standard 2 x 2 pooling). 
3. The above pattern is called a CNN layer or unit. Multiple such CNN layers are stacked on top of one another to create deep CNN networks.


Note that pooling reduces only the height and the width of a feature map, not the depth (i.e. the number of channels). For example, if you have m feature maps each of size (c, c), the pooling operation will produce m outputs each of size (c/2, c/2).


Q1)

Pooling Operation
Given an input of size 224x224x3 and stride of 2 and filter size of 2x2, what will be the output after the pooling operation?

==>

112x112x3

✓ Correct
Feedback:
Padding will reduce the feature shape after convolving. The feature shape and input shape will be different from each other.

Q2)
A CNN Unit
What does a typical CNN 'unit' (also called a CNN 'layer') comprise of?

==>

A collection of feature maps followed by a pooling operation

✓ Correct
Feedback:
What we refer to as a CNN layer or unit is a collection of m feature maps each of which is pooled to generate m outputs. Typically, the output of pooling reduces the size to half, since the most common form of pooling is with a stride of 2.

Q3)
Size of Feature Maps
In a typical deep CNN, the size of each subsequent feature map reduces with the depth of the network. The size reduction is typically done in two ways  - 1) convolution without padding or 2) by pooling. 

What is the main reason we prefer a lower dimensional output of an image from the network?

==>

We want a compact representation of the image as the output, one which preferably captures only the useful features in the image

✓ Correct
Feedback:
The reason we want a compact representation of the image is to get rid of all the redundancies in the image. For e.g. all the 224 x 224 x 3 pixels may not be required to do a classification or object detection task, just a smaller vector (say of length 5000) may be enough.

Summary
In this session, you learnt the basics of convolutional neural networks and their common applications in computer vision such as image classification, object detection, etc. You also learnt that CNNs are not limited to images but can be extended to videos, text, audio etc. 

 

The design of CNNs uses many observations from the animal visual system, such as each retinal neuron looks at its own (identical) receptive field, some neurons respond proportionally to the summation over excitatory regions (pooling), the images are perceived in a hierarchical manner, etc.  

 

You learned that images are naturally represented in the form of arrays of numbers. Greyscale images have a single channel while colour images have three channels (Red Green Blue). The number of channels or the 'depth' of the image can vary depending on how we represent the image. Each channel of a pixel, usually between 0-255, indicates the 'intensity' of a certain colour.

 

You saw that specialised filters, or kernels can be designed to extract specific features from an image (such as vertical edges). A filter convolves an image and extracts features from each 'patch'. Multiple filters are used to extract different features from the image. Convolutions can be done using various strides and paddings.

 

The formula to calculate the output shape after convolution is given by:

(
n
+
2
P
−
k
S
+
1
)
,
(
n
+
2
P
−
k
S
+
1
)
 , where

The image  is of size- n x n
The filter is k x k
Padding is P
Stride is S
 

The filters are learned during training (backpropagation). Each filter (consisting of weights and biases) is called a neuron. Multiple neurons are used to convolve an image (or feature maps from the previous layers) to generate new feature maps.  The feature maps contain the output of convolution + non-linear activation operations on the input. 

 

A typical CNN unit (or layer) in a large CNN-based network comprises multiple filters (or neurons), followed by non-linear activations, and then a pooling layer. The pooling layer computes a statistical aggregate (max, sum etc.) over various regions of the input and reduces sensitivity to minor, local variations in the image.  Multiple such CNN units are stacked together, finally followed by some fully connected layers, to form deep convolutional networks.

 

In the next session, you will learn to build and train CNNs using Python + Keras + GPUs.



Graded Questions
The following questions are graded.


Q1) Visualizing CNNs
You know that layers in a CNN 'learn' in a hierarchical manner. The initial layers extract low-level features while the layers deep into the network extract more abstract features. Suppose we have trained a 4-layer CNN on a large dataset. After training, we visualise the four layers as given below. Match the layers with what they are expected to have learnt:

==>


Layer1-(c), Layer2-(b), Layer3-(a), Layer4-(d)

✓ Correct
Feedback:
 The projections from each layer show the hierarchical nature of the features in the network. Layer 1 has corners and edges, Layer 2 responds to more complex corners and other edges/ colour conjunctions, Layer 3 captures textures e.g. mesh patterns and Layer 4 shows entire objects with significant pose variation, e.g. dogs.

 Q2)

 Pixel range
What is the range of possible values of each channel of a pixel if we represent each pixel with 5 bits?
==>


0 to 31

✓ Correct
Feedback:
Since we are representing each pixel by 5 bits, the total pixels will be 2^5 = 32. So the range is 0-31

Q3)

Average filter
Suppose we want to take the average over a (3, 3) patch in an image using a filter. Which of the following represents the 'average filter'?

==>


(
1
/
9
)
∗
⎡
⎢
⎣
1
1
1
1
1
1
1
1
1
⎤
⎥
⎦

✓ Correct
Feedback:
The convolution operation in this case should produce an expression like 1/n(x1+x2+x3...xn). In this case 1/n = 1/9 which is the correct factor as the average of 9 numbers will be computed by this filter at one time. Also since all the entries are 1, the convolution operation of this filter over a patch of 9*9 input will produce the sum of 9 numbers.


Q3)

Convolution
Suppose we convolve an image X of size 4x4 with filter Y. We use 'zero-padding' of 1 (i.e. adding zeros around each edge of the image) and a stride length of 1. Find the output of the convolution X*Y.

X
=
⎡
⎢
⎢
⎢
⎣
1
0
0
1
−
1
2
1
0
0
1
0
0
0
0
1
−
3
⎤
⎥
⎥
⎥
⎦
,
Y
=
⎡
⎢
⎣
0
1
0
0
0
0
0
1
0
⎤
⎥
⎦

==>

⎡
⎢
⎢
⎢
⎣
−
1
2
1
0
1
1
0
1
−
1
2
2
−
3
0
1
0
0
⎤
⎥
⎥
⎥
⎦

✓ Correct
Feedback:
Pad zeros all around the image X and then do the convolution X*Y.

Q5)
Trainable parameters
Which of the following layers contains trainable parameters and which does not?

==>

Convolution and fully connected layers contain parameters, pooling does not.

✓ Correct
Feedback:
The pooling layer does not contain any trainable parameters, Convolution and fully connected layers do. We learn the value of those parameters during backpropagation. Since pooling is just taking aggregate, there are no parameters involved in it. Say, we want to take an average of 4 numbers, we will just do (1/4) ( 4 numbers). There are no parameters that need to be learned.  Fully connected layer obviously has weights, we already know that from multilayer perceptron. 

Q6)Padding
What is the advantage of padding other than to keep the spatial dimension (width and height) of the output constant?

==>

If we don’t do padding then the information at the borders would be “washed away” too quickly.

✓ Correct
Feedback:
Padding helps to preserve the information at the edges, otherwise, the convolution operation would extract information only from the central regions of the image . 

Q7)

Pooling
Which of the following statements related to pooling are correct? More than one options may be correct.

==>


Pooling reduces the width and height of the output, thereby reducing the number of parameters and the amount of computation being done in the network.

✓ Correct
Feedback:
Pooling reduces the width and height, thereby reducing the number of parameters and the amount of computation (since with less number of parameters there will be fewer computations involved in feedforward/backpropagation etc.). 



Since it reduces the number of parameters in the network, it also helps control overfitting.

✓ Correct
Feedback:
Pooling reduces the number of parameters and computation, it also controls overfitting.


Pooling makes the network invariant to certain local transformations.

✓ Correct
Feedback:
Since pooling takes a statistical aggregate over multiple regions of an image, it makes the network invariant to 'local transformations' (such as the face being tilted a little, or an object being located in a different region than what the training data had seen).

Q8) 
Compact representation of network
Which of the following methods can be deployed to reduce the spatial dimensions of feature maps (width and height), and thereby, to make the representation of the network more compact? More than one options may be correct.

==>

Pooling operation 

✓ Correct
Feedback:
Pooling reduces the spatial dimension of the output.



Convolution operation 

✓ Correct
Feedback:
If we use convolution operation with stride > 1, e.g. with a filter of 2x2 and stride of 2, the output spatial dimension will reduce to half. 




# Introduction
In this session, you will learn to train CNNs using Python + Keras. Compared to the previous session, this session will be more hands-on. You will spend a lot of time reading and modifying Python + Keras code and train your models on GPUs.

 

To get started with the syntax and the process of building CNNs in Keras, you will first use the MNIST dataset (since you are already familiar with it). You will also learn to compute the number of parameters, output sizes etc. of each layer of a network.

 

Throughout the rest of the session, you will use the CIFAR-10 dataset which has 60000 (32 x 32) colour images of 10 classes as shown below. In these exercises, we will also experiment with some hyperparameters of CNNs. 


In this session
You will define your own convolutional layers in Keras and train those layers on the CIFAR-10 dataset. You will implement everything on a GPU.

Get familiar with CNNs in Keras: The MNIST dataset
Setting up your notebook on a GPU
Conduct experiments with the CIFAR-10 dataset:
Build a base model using the CIFAR-10 dataset
Experiment with hyperparameters and draw observations

# Building CNNs in Keras - MNIST


In this segment, you will learn to build CNNs in Keras. Specifically, you will learn to build and train a CNN on the MNIST dataset to classify the digits into one of the ten classes (0-9). 

 

This is a text only page (with an IPython notebook) whose objective is to make you familiar with building CNNs in Keras. In the next few segments, the professor will demonstrate some more experiments with CNNs using Python + Keras using the CIFAR-10 dataset. 

 

Please download the notebook below and go through it.  You do not need to download the dataset separately, it can be downloaded from Keras directly (as done in the notebook). 


Please run this notebook locally, not on a GPU. You will use the GPU in the upcoming segments. Make sure you understand the section 'Understanding Model Summary' in the notebook well - it will be required to solve the questions on the next page.

In the next segment, you will test your understanding of the concepts covered in the notebook by solving some questions on the VGG-16 architecture.

# Comprehension - VGG16 Architecture


In this exercise, we will dissect each layer of the VGG-16 architecture. This exercise will help you apply all the concepts learnt so far.


The VGG-16 was trained on the ImageNet challenge (ILSVRC) 1000-class classification task. The network takes a (224, 224, 3) RBG image as the input. The '16' in its name comes from the fact that the network has 16 layers with trainable weights - 13 convolutional layers and 3 fully connected ones (the VGG team had tried many other configurations, such as the VGG-19, which is also quite popular).

 

The architecture is given in the table below (taken from the original paper). Each column in the table (from A-E) denotes an architecture the team had experimented with. In this discussion, we will refer only to column D which refers to VGG-16 (column E is VGG-19).

VGG-16
VGG-16
The convolutional layers are denoted in the table as conv<size of filter>-<number of filters>. Thus, conv3-64 means 64 (3, 3) square filters.  Note that all the conv layers in VGG-16 use (3, 3) filters and that the number of filters increases in powers of two (64, 128, 256, 512). 

 

In all the convolutional layers, the same stride length of 1 pixel is used with a padding of 1 pixel on each side, thereby preserving the spatial dimensions (height and width) of the output.

 

After every set of convolutional layers, there is a max pooling layer. All the pooling layers in the network use a window of 2 x 2 pixels with stride 2. Finally, the output of the last pooling layer is flattened and fed to a fully connected (FC) layer with 4096 neurons, followed by another FC layer of 4096 neurons, and finally to a 1000-softmax output. The softmax layer uses the usual cross-entropy loss. All layers apart from the softmax use the ReLU activation function.

 

The number of parameters and the output size from any layer can be calculated as demonstrated in the MNIST notebook on the previous page. For example, the first convolutional layer takes a (224, 224, 3) image as the input and has 64 filters of size (3, 3, 3). Note that the depth of a filter is always equal to the number of channels in the input which it convolves. Thus, the first convolutional layer has 64 x 3 x 3 x 3 (weights) + 64 (biases) = 1792 trainable parameters. Since stride and padding of 1 pixel are used, the output spatial size is preserved, and the output will be (224, 224, 64).

 

Now answer the following questions (you will need a calculator). Keep track of the number of channels at each layer. Don't forget to add the biases.

 


Q1) 
Conv Layer-2
The output of the first convolutional layer is (224, 224, 64), i.e. 64 feature maps of size (224, 224). The second conv layer uses 64 filters of size (3, 3, 64). Note that the number of channels in the filters (64) is implicit since the filters have to convolve a tensor of 64 channels.

The number of parameters in the second conv layer are: 

==>

36928

Feedback:
The 64 (3, 3, 64) filters have 64*3*3*64 (weights) + 64 (biases).

Q2)

Conv Layer-2 Output
The output of the first convolutional layer is (224, 224, 64) which is fed to the second conv layer with 64 filters of size (3, 3, 64). 

The output of the second conv layer is:

==>

(224, 224, 64)

✓ Correct
Feedback:
64 filters will produce 64 feature maps. The size of each map will be preserved to (224, 224) since stride and padding of 1 are used.

Q3) 

The Pooling Layer
The output of the second conv layer, (224, 224, 64), is fed to a max pooling layer. All the pooling layers in the network use a window size of 2 x 2 with stride 2. The output of the pooling layer is:

==>

(112, 112, 64)

✓ Correct
Feedback:
The pooling layer simply reduces the spatial size to half and preserves the number of channels.

Q4)

Conv Layer-3
The output from the first pooling layer, (112, 112, 64), is fed to the third conv layer. The number of trainable parameters in the third conv layer is:

==>

Feedback:
Each filter is of size (3, 3, 64). Thus 128 filters have 128*3*3*64 (weights) +128 (biases).


Q5) Conv Layer-3 Output
The output from the first pooling layer, (112, 112, 64), is fed to the third conv layer. The output of the third convolutional layer is:

==>

(112, 112, 128)

✓ Correct
Feedback:
Since all the convolutions are with stride 1 and padding 1, the size (height x width) is maintained. The third layer has 128 filters each of which will produce a 112 x 112 feature map.


Q6)



The First FC Layer
Let's now come to the latter part of the network. The output from the last (13th) convolutional layer is of size (14, 14, 512) which is fed to a max pooling layer to give a (7, 7, 512) output. The output from the max pooling layer is then fed to a fully connected layer (FC) with 4096 neurons (after flattening). 

The number of trainable parameters in this FC layer is:

==>


102764544

✓ Correct
Feedback:
The output of the pooling layer, after flattening, will be a vector of length 7*7*512. Thus, the FC layer will have 7*7*512*4096 (weights) + 4096 (biases).

Q7)

Shrinkage in VGG-16
In the VGG-16 network, the size of the output is shrunk (i.e. the height x width of the input):

==>
By only the pooling layers

✓ Correct
Feedback:
Since all the conv layers use a stride and padding of 1 with a (3, 3) filter, the spatial size is preserved in all the convolutional layers (only the depth increases). The height and width is reduced only by the pooling layers.


The total number of trainable parameters in the VGG-16 is about 138 million (138,357,544 exactly), which is enormous. In an upcoming session, you will see that some of the recent architectures (such as ResNet etc.) have achieved much better performance with far less number of parameters.

 

In the next few segments, the professor will demonstrate some experiments with various CNN hyperparameters on the CIFAR-10 dataset. 


## CIFAR-10 Classification with Python - I


In the next few segments, you will train various CNN networks on the CIFAR-10 dataset. It has 10 classes of 60,000 RGB images each of size (32, 32, 3). The 10 classes are aeroplane, automobile, bird, cat, deer, dog, frog, horse, ship and truck. A similar dataset is the CIFAR-100 dataset which has 100 classes. You do not need to download the dataset separately, it can be downloaded directly through the Keras API.

 

Getting started with Google Colab
Google Colab is a free cloud service and provides free GPU access. You can learn how to get started with Google Colab here. We recommend that you use a GPU to run the CIFAR-10 notebooks (running each notebook locally will take 2-3 hours, on a GPU it will take 8-10 minutes). 
 

CIFAR-10 experiments
In the coming few lectures, you will experiment with some hyperparameters and architectures and draw insights from the results. Some hyperparameters we will play with are:

Adding and removing dropouts in convolutional layers

Batch Normalization (BN)

L2 regularisation

Increasing the number of convolution layers

Increasing the number of filters in certain layers 

 

Experiment - I: Using dropouts after conv and FC layers

In the first experiment, we will use dropouts both after the convolutional and fully connected layers. 

 

Download - Notebook

You can download the notebook here.


The results of the experiment are as follows:

 

Experiment - I: Dropouts After Conv and FC layers

Training accuracy =  84%, validation accuracy = 79%
 

In the next few segments, we will conduct some more experiments (without dropouts, using batch normalisation, adding more convolutional layers etc) and compare the results.

 
 # CIFAR-10 Classification with Python - II

 In the first experiment (using dropouts after both convolutional and FC layers), we got training and validation accuracies of about 84% and 79% respectively. Let's now run three different experiments as mentioned below and compare the performance:


 Experiment - II: Remove the dropouts after the convolutional layers (but retain them in the FC layer). Also, use batch normalization after every convolutional layer.

 

Recall that batch normalisation (BN) normalises the outputs from each layer with the mean and standard deviation of the batch. You can revisit this lecture in Module 2 (Introduction to Neural Networks Part 2) -> Neural Network Implementation Using Keras -> Batch Normalisation.

 

Experiment - III: Use batch normalization and dropouts after every convolutional layer. Also, retain the dropouts in the FC layer.

 

Experiment - IV: Remove the dropouts after the convolutional layers and use L2 regularization in the FC layer. Retain the dropouts in FC.

 

You can download the notebooks here.

Cifar_10_Notebook_with_BN_without_dropout
Cifar_10_notebook
Cifar10_l2_notebook


CNN Experiments
The results of the experiments done so far are summarised below. Based on these, choose all the correct options:

Experiment - I (Use dropouts after conv and FC layers, no BN): 
Training accuracy =  84%, validation accuracy  =  79%
Experiment - II (Remove dropouts from conv layers, retain dropouts in FC, use BN): 
Training accuracy =  98%, validation accuracy  =  79%
Experiment - III (Use dropouts after conv and FC layers, use BN):
Training accuracy =  89%, validation accuracy  =  82%
Experiment - IV (Remove dropouts from conv layers and use L2 + dropouts in FC, use BN):
Training accuracy = 94%, validation accuracy = 76%. 

The ideal configuration (from the ones tried so far) is to use dropouts after both conv and FC layers with BN

✓ Correct
You missed this!
Feedback:
This corresponds to experiment-III which has given the best results so far.


Removing dropouts after the conv layers affects the performance adversely

✓ Correct
Feedback:
In experiments II and IV, we had removed the dropouts after the conv layers, and the performance reduced drastically (the model overfits).


Using BN (keeping other things constant) improves the performance significantly

✓ Correct
Feedback:
Compare experiments I and III - using BN improves both the training and validation accuracies.

# CIFAR-10 Classification with Python - III

 Let's continue our experiments further. From the previous experiments, we have learnt that dropouts are pretty useful, batch normalisation somewhat helps improve performance, and that L2 regularisation is not very useful on its own (i.e. without dropouts).

 

Let's now conduct an experiment with all these thrown in together. After this experiment, let's conduct another one to test whether adding a new convolutional layer helps improve performance.

 


Experiment-V: Dropouts after conv layer, L2 in FC, use BN after convolutional layer

 

Experiment-VI: Add a new convolutional layer to the network. Note that by a 'convolutional layer', the professor is referring to a convolutional unit with two sets of Conv2D layers with 128 filters each (we are abusing the terminology a bit here). The code for the additional conv layer is shown below.

 

# an additional conv unit 
model.add(Conv2D(128, (3, 3), padding='same'))
model.add(Activation('relu'))
model.add(BatchNormalization())
model.add(Conv2D(128, (3, 3)))
model.add(Activation('relu'))
model.add(BatchNormalization())
model.add(MaxPooling2D(pool_size=(2, 2)))
model.add(Dropout(0.25))

You can download the notebooks below:

 

[Cifar10_l2_dropout_notebook](https://github.com/ContentUpgrad/Convolutional-Neural-Networks/blob/main/Building%20CNNs%20with%20Python%20and%20Keras/5.%2BCifar10_l2_dropout_notebook.ipynb)
[Cifar10_morelayer_notebook](https://github.com/ContentUpgrad/Convolutional-Neural-Networks/blob/main/Building%20CNNs%20with%20Python%20and%20Keras/6.%2BCifar10_morelayer_notebook.ipynb)



The results of these two experiments are summarised below.

 

Experiment-V: Dropouts after conv layer, L2 in FC, use BN after convolutional layer

Train accuracy =  86%, validation accuracy = 83%

 

Experiment-VI: Add a new convolutional layer to the network

Train accuracy =  89%, validation accuracy = 84%
 

The additional convolutional layer boosted the validation accuracy marginally, but due to increased depth, the training time increased.


Adding feature maps
In the previous experiment, we tried to increase the capacity of the model by adding a convolutional layer. Let's now try adding more feature maps to the same architecture.

 

Experiment - VII: Add more feature maps to the conv layers: from 32 to 64 and 64 to 128.

 

You can download the notebook below:


The results of our final experiment are mentioned below.

 

Experiment-VII: Add more feature maps to the convolutional layers to the network

Train accuracy =  92%, validation accuracy = 84%



On adding more feature maps, the model tends to overfit (compared to adding a new convolutional layer). This shows that the task requires learning to extract more (new) abstract features, rather than trying to extract more of the same features.


## Summary
In this session, you learnt to build and train CNNs in Keras and experimented some hyperparameters of the model. You also practised manually computing the number of parameters, output sizes etc. of CNN-based architectures.

 

Based on these experiments, we saw that the performance of CNNs depends heavily on multiple hyperparameters - the number of layers, number of feature maps in each layer, the use of dropouts, batch normalisation, etc. Thus, it is advisable to first fine-tune your model hyperparameters by conducting lots of experiments. Only when you are convinced that you have found the right set of hyperparameters you should train the model with a larger number of epochs (since almost always the amount of time and computing power you have is limited).

 

In the next session, you will study the architectures of some popular deep convolutional networks, learn to train CNNs in Python + Keras, and use large pre-trained networks for your own tasks using transfer learning.




## Graded Questions
The following questions are graded.

 

Comprehension - A three-class classification CNN
Let's consider a CNN based architecture designed to classify an image into one of the three classes - a pedestrian, a tree or a traffic signal. Each input image is of size (512, 512, 3) (RGB).

 

The network contains the following 11 layers in order. Note that we will address the input layer as the first layer, the next conv layer as the second layer and so on (i.e. according to the numbers).

 

1. Input image (512,512,3)

2. Convolution: 32  5x5 filters, stride 's1', padding 'p1'

3. Convolution: 32  3x3 filters, stride 1, padding 1

4, Max Pooling: 2x2 filter, stride 2

5. Convolution: 64  3x3 filters, stride 1, padding 1

6. Convolution: 64  3x3 filters, stride 1, padding 1

7. Max Pooling: 2x2 filter, stride 2

8. Layer 'l'

9. Fully-connected: 4096 neurons

10. Fully-connected: 512 neurons

11. Fully-connected: 'F' neurons

Question 1/5
Mandatory
Comprehension
If the spatial dimensions (width and height) of the output going into the third layer are the same as the input from the previous layer, what can be the possible values of stride 's1' and padding 'p1'?

==>


stride 1, padding 2

✓ Correct
Feedback:
Calculate the output using ((n+2p-k)/s +1). With s=1, p=2, the output is (512 + 4 - 5)/1 + 1 = 512



Comprehension2
The 8th layer is named layer 'l'. Which of the following types could be the layer 'l'?
==>

Flatten

✓ Correct
Feedback:
The 'Flatten' layer connects the convolutional layer to the fully connected layer by flattening the multidimensional tensor output from the conv layer to a long vector.


C3)

Comprehension
What is the output from the last max pooling layer (layer 7) assuming that the width and the height do not change after the convolution operation in step-2?

==>

128x128x64

✓ Correct
Feedback:
After two pooling operations (starting from the starting 512 x 512), the width and the height will reduce 2 times, i.e. from 512 to 256 (in the first max pooling layer) and from 256 to 128 (in the second max pooling layer). 

C4)

Comprehension
What is the value of 'F' in the last layer?

==>


3

✓ Correct
Feedback:
Since we are classifying an image into 3 classes, it has to have 3 neurons.

C5) 

Question 5/5
Mandatory
Comprehension

Calculate the total number of trainable parameters in layer-3 (the conv layer with 32 3x3 filters)?

==>

9248

✓ Correct
Feedback:
The output from the previous layer is (512, 512, 32), so each filter is of size (3, 3, 32). The number of parameters is thus 32 filters *3*3*32 (weights) + 32 (biases) = 9248.


# CNN Architectures and Transfer Learning

## Overview of CNN Architectures
In this session, we will take an overview of some of the most popular CNN architectures which have set the benchmark for state-of-the-art results in computer vision tasks. The acid test for almost CNN-based architectures has been the ImageNet Large Scale Visual Recognition Competition(ImageNet). The dataset contains roughly 1.2 million training images, 50,000 validation images, and 150,000 testing images of about 1000 classes.

 

We will discuss the following architectures in this session:

AlexNet
VGGNet
GoogleNet
ResNet


To summarise the important points:

    The depth of the state-of-the-art neural networks has been steadily increasing (from AlexNet with 8 layers to ResNet with 152 layers).

    The developments in neural net architectures were made possible by significant advancements in infrastructure. For example, many of these networks were trained on multi GPUs in a distributed manner.
    
    Since these networks have been trained on millions of images, they are good at extracting generic features from a large variety of images. Thus, they are now commonly being used as commodities by deep learning practitioners around the world.


You will learn to use large pre-trained networks in the next section on transfer learning. In the next segment, we will study the architectures of AlexNet, VGGNet and GoogleNet.


# AlexNet and VGGNet

In this session, we will briefly look into the architectures of AlexNet and VGGNet.


In this session, we will briefly look into the architectures of AlexNet and VGGNet.

 

The AlexNet was one of the very first architectures to achieve extraordinary results in the ImageNet competition (with about a 17% error rate). It had used 8 layers (5 convolutional and 3 fully connected). One distinct feature of AlexNet was that it had used various kernels of large sizes such as (11, 11), (5, 5), etc. Also, AlexNet was the first to use dropouts, which were quite recent back then.

 

You are already familiar with VGGNet from the previous session. Recollect that the VGGNet has used all filters of the same size (3, 3) and had more layers (The VGG-16 had 16 layers with trainable weights, VGG-19 had 19 layers etc.). 

 

The VGGNet had succeeded AlexNet in the ImageNet challenge by reducing the error rate from about 17% to less than 8%. Let's compare the architectures of both the nets.



There are some other important points to note about AlexNet which are summarised below. We highly recommend you to go through the AlexNet paper (you should be able to read most CNN papers comfortably now). 

 

Because of the lack of good computing hardware, it was trained on smaller GPUs (with only 3 GB of RAM). Thus, the training was distributed across two GPUs in parallel (figure shown below). AlexNet was also the first architecture to use the ReLU activation heavily.



Comprehension - Effective Receptive Field

The key idea in moving from AlexNet to VGGNet was to increase the depth of the network by using smaller filters. Let's understand what happens when we use a smaller filter of size (3, 3) instead of larger ones such as (5, 5) or (7, 7).

 

Consider the example below. Say we have a 5 x 5 image, and in two different convolution experiments, we use two different filters of size (5, 5) and (3, 3) respectively.

In the first convolution, the (5, 5) filter produces a feature map with a single element (note that the convolution is followed by a non-linear function as well). This filter has 25 parameters.

 

In the second case with the (3, 3) filter, two successive convolutions (with stride=1, no padding) produce a feature map with one element.

 

We say that the stack of two (3, 3) filters has the same effective receptive field as that of one (5, 5) filter.  This is because both these convolutions produce the same output (of size 1 x1 here) whose receptive field is the same 5 x 5 image.

 

Notice that with a smaller (3, 3) filter, we can make a deeper network with more non-linearities and fewer parameters. In the above case:

The (5, 5) filter has 25 parameters and one non-linearity
The (3, 3) filter has 18 (9+9) parameters and two non-linearities.
 

Since VGGNet had used smaller filters (all of 3 x 3) compared to AlexNet (which had used 11 x 11 and 5 x 5 filters), it was able to use a higher number of non-linear activations with a reduced number of parameters.

 

In the next segment, we will briefly study GoogleNet which had outperformed VGGNet.


Effective Receptive Field
A (7, 7) filter has the same effective receptive field as (assuming zero padding and stride length 1):

==>

Three (3, 3) filters

✓ Correct
Feedback:
Consider an (n, n) image. A (7, 7) filter will result in an (n-6, n-6) output. Now consider some convolutions with a (3, 3) filter. The first convolution will produce an (n-2, n-2) output, the second will produce an (n-4, n-4) output, and the third will produce an (n-6, n-6) output.

Additional readings
We strongly recommend you to read the AlexNet and VGGNet papers provided below. Now you should be able to read many CNN-based papers comfortably.

# GoogleNet

After VGGNet, the next big innovation was the GoogleNet which had won the ILSVRC’14 challenge with an error rate of about 6.7%.


Unlike the previous innovations, which had tried to increase the model capacity by adding more layers, reducing the filter size etc. (such as from AlexNet to VGGNet), GoogleNet had increased the depth using a new type of convolution technique using the Inception module.

The module derives its name from a previous paper by Lin et al and this meme popular in the deep learning community:

Let's study the key features of GoogleNet architecture.


To summarise, some important features of the GoogleNet architecture are as follows:

    1.Inception modules stacked on top of each other, total 22 layers

    2.Use of 1 x 1 convolutions in the modules

    3.Parallel convolutions by multiple filters (1x1, 3x3, 5x5)

    4.Pooling operation of size (3x3)

    5.No FC layer, except for the last softmax layer for classification

    6.Number of parameters reduced from 60 million (AlexNet) to 4 million

 

The details on why the GoogleNet and the inception module work well are beyond the scope of this course, though you are encouraged to read the GoogleNet paper (provided below). 

 

In the next segment, we will look at the architecture of ResNet.

 

Additional reading
The GoogleNet, Christian Szegedy et al - A detailed study and representation of Google net architecture and the convolution layers used in it.



# Residual Net
Until about 2014 (when the GoogleNet was introduced), the most significant improvements in deep learning had appeared in the form of increased network depth - from the AlexNet (8 layers) to GoogleNet (22 layers). Some other networks with around 30 layers were also introduced around that time. 

 

Driven by the significance of depth, a team of researchers asked the question: Is learning better networks as easy as stacking more layers? 

 

The team experimented with substantially deeper networks (with hundreds of layers) and found some counterintuitive results (shown below). In one of the experiments, they found that a 56-layered convolutional net had a higher training (and test) error than a 20-layered net on the CIFAR-10 dataset. 


Analyse the results in the plot above and list down at least 1-2 possible explanations for them.



Deeper Nets
We mentioned that a team of deep learning researchers, in their experiments with deeper networks, found that a 56-layered conv net performed worse than a 20-layered net. The results from their experiments are shown below. What can be a possible reason for these results?

This is a poll question. Choose an option and compare your answer with your peers.





The team found that the results are not because of overfitting. If that were the case, the deeper net would have achieved much lower training error rate, while the test error would have been high.

 

What could then explain these results? Let's find out.


Thus, the key motivator for the ResNet architecture was the observation that, empirically, adding more layers was not improving the results monotonically.  This was counterintuitive because a network with n + 1 layers should be able to learn at least what a network with n layers could learn, plus something more.

 

The ResNet team (Kaiming He et al) came up with a novel architecture with skip connections which enabled them to train networks as deep as 152 layers. The ResNet achieved groundbreaking results across several competitions - a 3.57% error rate on the ImageNet and the first position in many other ILSVRC and COCO object detection competitions.

 


Let's look at the basic mechanism, the skip connections or residual connections, which enabled the training of very deep networks.


Thus, the skip connection mechanism was the key feature of the ResNet which enabled the training of very deep networks. Some other key features of the ResNet are summarised below. You are also encouraged to read the detailed results in the ResNet paper provided at the bottom of this page:


ILSVRC’15 classification winner (3.57% top 5 error)

152 layer model for ImageNet

Has other variants also (with 35, 50, 101 layers)

Every 'residual block' has two 3x3 convolution layers

No FC layer, except one last 1000 FC softmax layer for classification

Global average pooling layer after the last convolution

Batch Normalization after every convolution layer

SGD + momentum (0.9)

No dropout used

 

In the next few segments, you will learn how to use these large pre-trained networks to solve your own deep learning problems using the principles of transfer learning.


# Introduction to Transfer Learning


So far, we have discussed multiple CNN based networks which were trained on millions of images of various classes. The ImageNet dataset itself has about 1.2 million images of 1000 classes.

 

However, what these models have 'learnt' is not confined to the ImageNet dataset (or a classification problem). In an earlier session, we had discussed that CNNs are basically feature-extractors, i.e. the convolutional layers learn a representation of an image, which can then be used for any task such as classification, object detection, etc.



So far, we have discussed multiple CNN based networks which were trained on millions of images of various classes. The ImageNet dataset itself has about 1.2 million images of 1000 classes.

 

However, what these models have 'learnt' is not confined to the ImageNet dataset (or a classification problem). In an earlier session, we had discussed that CNNs are basically feature-extractors, i.e. the convolutional layers learn a representation of an image, which can then be used for any task such as classification, object detection, etc.

 

This implies that the models trained on the ImageNet challenge have learnt to extract features from a wide range of images. Can we then transfer this knowledge to solve some other problems as well? 


Thus, transfer learning is the practice of reusing the skills learnt from solving one problem to learn to solve a new, related problem.  Before diving into how to do transfer learning, let's first look at some practical reasons to do transfer learning in the first place.



To summarise, some practical reasons to use transfer learning are as follows:

Data abundance in one task and data crunch in another related task,

Enough data available for training, but lack of computational resources.

 

An example of the first case is this - say you want to build a model (to be used in a driverless car to be driven in India) to classify 'objects' such as a pedestrian, a tree, a traffic signal, etc. Now, let's say you don't have enough labelled training data from Indian roads, but you can find a similar dataset from an American city. You can try training the model on the American dataset, take those learned weights, and then train further on the smaller Indian dataset.

 

Examples of the second use case are more common - say you want to train a model to classify 1000 classes, but don't have the infrastructure required. You can simply pick up a trained VGG or ResNet and train it a little more on your limited infrastructure. You will implement such a task in Keras shortly.

 

In the next segment, we will see some other use cases where we can use transfer learning.

# Use Cases of Transfer Learning
Let's continue our discussion on use cases of transfer learning using some examples from natural language processing.


Let’s revisit the example of document summarisation. If you want to do document summarisation in some other language, such as Hindi, you can take the following steps:


Use word embeddings in English to train a document summarisation model (assuming a significant amount of data in English is available)

Use word embeddings of another language such as Hindi (where you have a data crunch) to tune the English summarisation model


Let's now summarise the main idea of transfer learning.


In the next segment, you will see some common use cases of transfer learning applied to computer vision tasks.

# Transfer Learning With Pre-Trained CNNs

For most computer vision problems, you are usually better off using a pre-trained model such as AlexNet, VGGNet, GoogleNet, ResNet etc. Let's study how exactly one should go about doing this. 

Thus, the initial layers of a network extract the basic features, the latter layers extract more abstract features, while the last few layers are simply discriminating between images. 


In other words, the initial few layers are able to extract generic representations of an image and thus can be used for any general image-based task. Let's see some examples of tasks we can use transfer learning for.


Thus, transfer learning is not just limited to image classification but can be extended to a wide variety of tasks. In the next segment, you will learn how to train pre-trained models for specific purposes.


# Practical Implementation of Transfer Learning

There are two main ways of using pre-trained nets for transfer learning:

Freeze the (weights of) initial few layers and training only a few latter layers
Retrain the entire network (all the weights) initialising from the learned weights
 

Let's look at these two techniques in detail.

Thus, you have the following two ways of training a pre-trained network:

1. ‘Freeze’ the initial layers, i.e. use the same weights and biases that the network has learnt from some other task, remove the few last layers of the pre-trained model, add your own new layer(s) at the end and train only the newly added layer(s).

2. Retrain all the weights starting (initialising) from the weights and biases that the net has already learnt. Since you don't want to unlearn a large fraction of what the pre-trained layers have learnt. So, for the initial layers, we will choose a low learning rate.

When you implement transfer learning practically, you will need to take some decisions such as how many layers of the pre-trained network to throw away and train yourself. Let's see how one can answer these questions. 

To summarise:

If the task is a lot similar to that of the pre-trained model had learnt from, you can use most of the layers except the last few layers which you can retrain 

If you think there is less similarity in the tasks, you can use only a few initial trained weights for your task.

 

In the next segment, you will see a demonstration of Transfer Learning in Python + Keras. 

# Transfer Learning in Python

In this segment, you will learn to implement transfer learning in Python. For this implementation, we will use the flower recognition dataset from Kaggle. This dataset has around 4000 images from 5 different classes, namely daisy, dandelion, rose, sunflower and tulip. 


Getting started with Google Colab
Google Colab is a free cloud service and provides free GPU access. You can learn how to get started with Google Colab here. We recommend that you use a GPU to run the CIFAR-10 notebooks (running each notebook locally will take 2-3 hours, on a GPU it will take 8-10 minutes). 

You can download the notebook from this Github repository

 The following lecture demonstrates the notebook.

To summarise, we conducted two transfer learning experiments. In the first experiment, we removed the last fully connected layers of ResNet (which had learnt how to classify the 1000 ImageNet images). Instead, we added our own pooling, fully connected and a 5-softmax layer and trained only those. Notice that we got very good accuracy in just a few epochs. In case we weren't satisfied with the results, we could modify this network further (add an FC layer, modify the learning rate, replace the global average pooling layer with max pool, etc.).

To summarise, we conducted two transfer learning experiments. In the first experiment, we removed the last fully connected layers of ResNet (which had learnt how to classify the 1000 ImageNet images). Instead, we added our own pooling, fully connected and a 5-softmax layer and trained only those. Notice that we got very good accuracy in just a few epochs. In case we weren't satisfied with the results, we could modify this network further (add an FC layer, modify the learning rate, replace the global average pooling layer with max pool, etc.).

 

In the second experiment, we froze the first 140 layers of the model (i.e. used the pre-trained ResNet weights from layers 1-140) and trained the rest of the layers. Note that while updating the pre-trained weights, we should use a small learning rate. This is because we do not expect the weights to change drastically (we expect them to have learnt some generic patterns, and want to tune them only a little to accommodate for the new task). 

 

In the next two segments, you will go through an interesting recent paper which compares various CNN architectures from an efficiency and deployment point of view.

# An Analysis of Deep Learning Models - I

In the past few years, the performance of CNN based architectures such as AlexNet, VGGNet, ResNet etc. has been steadily improving. But while deploying deep learning models in practice, you usually have to consider multiple other parameters apart from just accuracy. 

 

For example, say you've built a mobile app which uses a conv net for real-time face detection. Since it will be deployed on smartphones, some of which may have low memory etc., you might be more worried about it working 'fast enough', rather than the accuracy.  

In the next two segments, we will discuss a recent paper that appeared in 2017 - 'An Analysis of Deep Neural Network Models for Practical Applications'. This paper compares the popular architectures on multiple metrics related to resource utilisation such as accuracy, memory footprint, number of parameters, operations count, inference time and power consumption.  

An important point to notice here is that although the VGGNet (VGG-16 and VGG-19) is used widely, it is by far the most expensive architecture — both in terms of the number of operations (and thus computational time) and the number of parameters (and thus memory requirement). 

 



In the next lecture, we will continue to discuss some other results. 


To summarise, some key points we have discussed are:

Architectures in a particular cluster, such as GoogleNet, ResNet-18 and ENet, are very attractive since they have small footprints (both memory and time) as well as pretty good accuracies. Because of low-memory footprints, they can be used on mobile devices, and because the number of operations is small, they can also be used in real time inference.
In some ResNet variants (ResNet-34,50,101,152) and Inception models (Inception-v3,v4), there is a trade-off between model accuracy and efficiency, i.e. the inference time and memory requirement. 


There is a marginal decrease in the (forward) inference time per image with the batch size. Thus, it might not be a bad idea to use a large batch size if you need to. 

In the next segment, we will continue our discussion of the paper.

 

 # An Analysis of Deep Learning Models - II

 
 In the following lecture, we will continue our discussion on some other results related to inference time and 'accuracy density'. 

 Let's conclude the important points from the latter part of the paper:

Accuracy and inference time are in a hyperbolic relationship: a little increment in accuracy costs a lot of computational time.
Power consumption is independent of batch size and architecture. 
The number of operations in a network model can effectively estimate inference time.
ENet is the best architecture in terms of parameters space utilisation.


# Summary 

Summary
In this session, you compared the architectures of some popular networks which had achieved state-of-the-art results in ImageNet: AlexNet, VGGNet, GoogleNet and ResNet.

 

Until the VGGNet, most of the major innovations had appeared in the form of increased depth, smaller filters, etc. In 2014, GoogleNet introduced an unconventional idea in the form of the Inception module, which performs multiple parallel convolutions (1 x 1, 3 x 3, 5 x 5, pooling etc.) on the input. This enabled GoogleNet to increase both the depth and the 'width' of the network (it has 22 layers with multiple inception modules stacked one over another). In the quest for training deeper networks, the ResNet team introduced another novel idea - skip connections, which enabled training extremely deep networks by 'by-passing the additional layers if they do not learn anything useful, else keeping them'.   

 

Since these models have already been trained on millions of images, and therefore are good at extracting generic features, they are well-suited to solve other computer vision problems (with no or little re-training). This is the main idea of transfer learning.

 

In transfer learning, a pre-trained network can be repurposed for a new task depending on how much the new task differs from the original one. In two transfer learning experiments, we 1) trained a ResNet-50 by freezing the original weights and adding only a few FC layers, and 2) re-trained the last few layers of ResNet-50. The latter model gave us a boost in accuracy.

 

Finally, we compared various popular CNN architectures in terms of metrics (other than accuracy) which are important considerations for deployment (inference time, memory requirements etc.). We compared the architectures along metrics such as the number of parameters (proportional to memory), operations involved in a feed-forward (proportional to inference time), accuracy, power consumption etc. We saw that some of the oldest architectures (AlexNet) are not suited for most tasks, some architectures are extremely accurate but have very high memory footprints, and that there are some clear trade-offs between accuracy and efficiency (computational time and memory). 

 

You can download the lecture notes for this module from the link below:


Graded:

More layers
Suppose you make two CNN architectures, one with 15 layers (A) and another with 35 layers (B), and train them both (with identical infrastructure, training scheme etc.) on a 10-class classification task. The performance of the models is as follows:


Model-A: Training accuracy = 85%, validation accuracy = 82%
Model-B: Training accuracy = 78%, validation accuracy = 73%
Which of the following could be a possible explanation for these results?

==>


Model-B, being huge, is difficult to train (because of issues such as vanishing/exploding gradient)

✓ Correct
Feedback:
This is the most likely explanation - larger networks are harder to train. They suffer from the notorious problem of vanishing/exploding, which hamper convergence from the beginning.

Q2) 

Transfer Learning
In which of the following cases can we use transfer learning? More than one options may be correct.

==>


Transfer Learning
In which of the following cases can we use transfer learning? More than one options may be correct.



We have a massive dataset in one domain and a smaller dataset in other similar domain.

✓ Correct
Feedback:
We should definitely use transfer learning in this case since we do not have enough training data. 



We have a pre-trained model in one domain and a massive dataset in other similar domain

✓ Correct
Feedback:
We can use the pre-trained model and retrain it a little for our own purpose. Since we also have a massive dataset, the model should achieve good accuracy as well. 



We have a pre-trained model in one domain and a smaller dataset in another similar domain

✓ Correct
Feedback:
We should definitely use transfer learning in this case since we do not have enough training data. 


Q3) 

Learning rate in Transfer Learning
Suppose we are using the pre-trained weights from a large model and re-training our own model in a transfer learning setting. What should be the learning rate of the pre-trained weights? Assume that we can use a different learning rate for each layer. More than one options may be correct.

==>

Learning rate in Transfer Learning
Suppose we are using the pre-trained weights from a large model and re-training our own model in a transfer learning setting. What should be the learning rate of the pre-trained weights? Assume that we can use a different learning rate for each layer. More than one options may be correct.


As we move from the last layer to the initial layers, we should decrease the learning rate because the initial layers are good at extracting generic features while the last few layers are usually trained for a specific task 

✓ Correct
Feedback:
Self-explanatory.


Q4) 

Analysis of Deep Neural Networks
Which of the following statements are correct? More than one options may be correct.

==>

The number of operations in a network is directly proportional to the inference time (i.e. the time taken for a feed-forward).

✓ Correct
Feedback:
The computational time is proportional to the number of operations required.

Q5)

Analysis of Deep Neural Networks
Which of the following network is the most suited for a real-time face recognition task in a mobile app?


==>


ENet

✓ Correct
Feedback:
ENet has much lesser parameters (small bubble size) than the others, so it requires much less memory. Also, the inference time is the lowest (proportional to the number of operations), which is important for a real-time task. It also has decent accuracy. 





