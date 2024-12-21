# Introduction
Welcome to the module on ‘Principal Component Analysis’. 

 

Principal component analysis (PCA) is one of the most commonly used dimensionality reduction techniques in the industry. By converting large data sets into smaller ones containing fewer variables, it helps in improving model performance, visualising complex data sets, and in many more areas. 

 

In this module
Let's hear from your SME Mirza Rahim Baig as he introduces the topic of PCA

Now let's get to know what you'll be studying in this module and what are the necessary pre-requisites for the same.

As explained in the aforementioned video, the  entire module has been divided into the following main sections:

Fundamentals of PCA: Here, you will get an idea of why you should learn about PCA and its essential building blocks before understanding the process. This has been divided into 2 sub-sessions:
- Fundamentals of PCA I 
- Fundamentals of PCA II
- PCA Using Python:  Here, you will implement PCA using Python and get to know its various applications.


Prerequisites
This module requires prior knowledge of certain linear algebra concepts, such as matrices, vectors, etc. You will get to know about those prerequisites, along with a brief overview of each, as you go through the sessions. You can also learn the same from the additional module on ‘Math for Data Analysis’, which contains some useful additional content and questions to improve your understanding of these concepts. Here is a checklist of the concepts that you need to know to understand this module:

- Vectors and their properties
- Vector operations (addition, scaling, linear combination and dot product)
- Matrices 
- Matrix operations (matrix multiplication and matrix inverses)


In this session
First, in order to fully appreciate PCA’s usefulness, you will look at a wide variety of situations - some of which you may have encountered in your earlier modules, like the multicollinearity problem and how PCA helps us solve it. Then, you will learn the basic definition of PCA, followed by a brief introduction to linear algebra topics that are crucial for understanding PCA and its building blocks. After this, you will look at two key ideas that form the workings of PCA: change of basis and variance as information.

# The Why of PCA
The first thing to know before learning anything new is to understand why and how that knowledge is useful. Hence, let's start by understanding the motivation for studying PCA and then look at a brief overview of the technique and its applications.

 

Note: At 3:05, for 100 variables we will need 4950 plots to visualise the associations, not 450.


As explained by Rahim, a couple of situations where having a lot of features posed problems for us are as follows:

The predictive model setup: Having a lot of correlated features leads to the multicollinearity problem. Iteratively removing features is time-consuming and also leads to some information loss.
Data visualisation: It is not possible to visualise more than two variables at the same time using any 2-D plot. Therefore, finding relationships between the observations in a data set having several variables through visualisation is quite difficult. 
 

Now, PCA helps in solving both the problems mentioned above which you'll study shortly.

Let’s listen to the following lecture to understand the various applications of PCA.



Fundamentally, PCA is a dimensionality reduction technique, i.e., it approximates the original data set to a smaller one containing fewer dimensions(Note that dimension is just another term for referring to columns or variables in a dataset). To understand it visually, take a look at the following image.


In the image above, you can see that a data set having N dimensions has been approximated to a smaller data set containing 'k' dimensions. In this module, you will learn how this manipulation is done. And this simple manipulation helps in several ways such as follows:

For data visualisation and EDA
For creating uncorrelated features that can be input to a prediction model:  With a smaller number of uncorrelated features, the modelling process is faster and more stable as well.
Finding latent themes in the data: If you have a data set containing the ratings given to different movies by Netflix users, PCA would be able to find latent themes like genre and, consequently, the ratings that users give to a particular genre.
Noise reduction
 

Now attempt the following questions to test your understanding.

# The What of PCA
As discussed in the previous segment, PCA is fundamentally a dimensionality reduction technique; it helps in manipulating a data set to one with fewer variables. The following lecture will give you a brief idea of what dimensionality reduction is and how PCA helps in achieving dimensionality reduction.

In simple terms, dimensionality reduction is the exercise of dropping the unnecessary variables, i.e., the ones that add no useful information. Now, this is something that you must have done in the previous modules. In EDA, you dropped columns that had a lot of nulls or duplicate values, and so on. In linear and logistic regression, you dropped columns based on their p-values and VIF scores in the feature elimination step.

 

Similarly, what PCA does is that it converts the data by creating new features from old ones, where it becomes easier to decide which features to consider and which not to. 


Now that you have an idea of the basics of what PCA does, let’s understand its definition in the following lecture.


PCA is a statistical procedure to convert observations of possibly correlated variables to ‘principal components’ such that:

They are uncorrelated with each other.
They are linear combinations of the original variables.
They help in capturing maximum information in the data set.
 

Now, the aforementioned definition introduces some new terms, such as ‘linear combinations’ and ‘capturing maximum information’, for which you will need some knowledge of linear algebra concepts as well as other building blocks of PCA. In the next session, we will start our journey in the same direction with the introduction of a very basic idea: the vectorial representation of data.
 

Answer the following question to better understand the upcoming segments.

Q1)

PCA - Properties
Consider the following statements

Statement 1 - PCA helps in solving the multicollinearity problem by creating new uncorrelated features which are used as input for the predictive model.

Statement 2 - With a dimensionality reduction technique like PCA, you convert a dataset having N dimensions to another dataset having k dimensions where N > k.

Now choose the correct option.

==>

Both the statements are correct

✓ Correct
Feedback:
PCA does create uncorrelated features which solve the problem of multicollinearity. PCA also reduces the number of dimensions from N to k (or N > k )

---
# Fundamentals of PCA - I
# Introduction
Welcome to the session on Fundamentals of PCA - I!

 

Here we'll learn about two of the most important building blocks of PCA - basis and change of basis. But before that, we'll go through a brief refresher on basic linear algebra concepts. 

 

In this session
This session covers some important linear algebra concepts required for understanding PCA and how it works. These main concepts are as follows

 

Vectors
Matrices and their Inverse
Basis vectors
Change of Basis
PCA and Change of Basis

# Vectorial Representation of Data


To summarise what you're going to learn in this segment here's a handy checklist:

- Vectors and their properties
- Vector operations (addition, scaling, linear combination and dot product)
- Matrices 
- Matrix operations (matrix multiplication and matrix inverses)
Let's start with understanding the dataset as a matrix of vectors in the following lecture.

Note - In the video at 1:48 the graphic mistakenly shows 
[
165
65
]
 instead of 
[
165
55
]

 

As mentioned in the video, consider the following data set containing the height and weight of five patients.

 



 

The height and weight information can be represented in the form of a matrix as follows



 

with each row representing a particular patient's data and each column representing the original variable. Geometrically, these patients can be represented as shown in the following image.



 

[Note: The point P5 is slightly off from its actual position in the graph given above and in the video.]

 

Vector Representation
The vector associated with the first patient is given by the values (165, 55). This value can also be written in the following way:

 A column containing the values along the rows. This is also known as the column-vector representation.
[165
55]
As a transpose of the above form. Essentially, it is the same column vector but now written as a transpose of a row vector.
[165
55]T

[Note: Transpose is something you must have learnt in your Python for DS  module. If you need some brushing up on this topic, you can take a look at this link]
In terms of the basis vectors 
This is something that you'll learn in detail in later segments. To give a brief idea, the vector (165,55) can also be written as 165i +55j, where i and j are the unit vectors along X and Y respectively and are the basis vectors used to represent all vectors in the 2-D space.

Vector Representation for n-dimensional data
Each vector will contain values representing all the dimensions or variables in the data. For example, if there was an age variable also included in the above dataset and the first patient had an age of 22 years, then the vector representing him would be written as  (165, 55, 22). Similarly, if the dataset had 10 variables, there would be 10 dimensions in the vector representation. Similarly, you can extend it for n dimensions or variables.


Now, these vectors have certain properties and operations associated with them. Let's go ahead and learn them in the next segment. Before that, you can attempt the following question to test your understanding until now.

Coming Up
In the next segment, you will study vector properties and operations relevant to the module.

# Vector Operations

Now that you've understood what vectors are, let's go ahead and learn about some vector properties and a few associated operations.

Let's summarise the learnings of the above lecture. Major outcomes from the above video are:

Vectors have a direction and magnitude
Each vector has a direction and magnitude associated with it. The direction is given by an arrow starting from the origin and pointing towards the vector's position. The magnitude is given by taking a sum of squares of all the coordinates of that vector and then taking its square root.

For example, the vector (2,3) has the direction given by the arrow joining (0,0) and (2,3) pointing towards (2,3). Its magnitude is given by  
√22+32=√13.

Similarly, for a vector in 3 dimensions, say (2,-3,4) its direction is given by the arrow joining (0,0,0) and (2,-3,4) pointing towards (2,-3,4). And as in the 2D case, we get the magnitude of this vector as  
√(2)2+(−3)2+(4)2=√29 .

2. Vector Addition
When you add two or more vectors, we essentially add their corresponding values element-wise. The first elements of both the vectors get added, the second element of both get added, and so on.
For example, if you've two vectors say 
V1=(2,3) and 
V2=(1,2) then 
V1+V2=(2+1,3+2)=(3,5).

3. In the i, j notations that we introduced earlier, the above addition can be written as 
V1+V2=(2i+3j)+(i+2j)=(2+1)i+(3+2)j=3i+5j

Similarly, this idea can be extended to multiple dimensions as well. 

4. Scalar Multiplication
If you multiply any real number or scalar by a vector, 
then there is a change in the magnitude of the vector and the direction remains same or turns completely opposite 
depending on whether the value is positive or negative respectively.


Q1)

Unit Vectors
Unit vectors are those vectors that have a unit magnitude and are signifiers of a particular direction. To find a unit vector along the direction of another vector, you divide that vector by its magnitude.

For example, if there is a vector 
A=Axi+Ayj whose magnitude is 
M, then a unit vector along the direction of 
A is given by 
AxMi+AyMj

What is the unit vector along the direction of the vector 3i + 4j?

0.6i + 0.8j

✓ Correct
Feedback:
The magnitude of the vector is given by 
√(32+42)=√25=5). Therefore a unit vector along A is given by (3/5)i + (4/5)j = 0.6i+0.8j

Q2)
Vector Addition
Let v1 and
v2 be two vectors given by 
v1=i+2j and
v2=2i−3j. Find the value of 
2⋅v1+3⋅v2.


==>

8
i
−
5
j

✓ Correct
Feedback:
2*v1 +  3*v2 = 2(i + 2j) + 3(2i -3 j) = 2i +4j + 6i - 9j = 8i -5j



# Matrix Multiplication

Apart from the vector operations that we learnt previously, we need some knowledge of matrix operations as well. 
Let's hear from Mirza as he explains the idea of matrix multiplication.

As you saw in the video, the process of matrix multiplication is quite simple, and it involves element-wise multiplication followed by the addition of all the elements present in it. The one key rule that it must satisfy is when you multiply 2 matrices, say A and B, the number of columns of A must equal the number of rows in B. Visually, you can take a look at the following image to get the idea of how that should be.

As shown in the example, since the number of columns in the first matrix and the number of rows in the second matrix are equal to 4, matrix multiplication is possible and the resultant matrix has a shape of 5 x 6.

 

The element-wise multiplication followed by addition is also pretty straightforward as can be seen in the following example.



 

Here is a short video that shows how to do matrix multiplication in Python.


Q1)

Matrix Multiplication
If matrix dimensions of two matrices are given, say,  A =a1 x a2 (dimensions) and  B=b1 x b2 (dimensions), then matrix multiplication A*B  is valid if __?

==>

a2=b1

✓ Correct
Feedback:
We need the number of columns of A, i.e a2, to be equal to the number of rows of B, i.e b1, for matrix multiplication to be possible.

Inverse of a Matrix
To understand what the inverse of a matrix is, let's take a look at the following example:

 

Let's say you have 2 matrices 
A and B such that  
A=
[2 −1
1 1]
 and 
B
 = [1/3 1/3
 −1/3 2/3 ]

 

If you multiply B with A like this: 
B x
A = 
[1/31/3−1/32/3][2−111]
 you get the following result-  
[1001]


# Inverse of a Matrix
To understand what the inverse of a matrix is, let's take a look at the following example:

 

Let's say you have 2 matrices 
A and B such that  
A= [2 −1
1 1] and 
B = [1/3 1/3
−1/3 2/3]


If you multiply B with A like this: 
B x A = 
[1/3 1/3
−1/3 2/3]
[2 −1
1 1]
 you get the following result-  
[1 0
0 1]

The matrix that you got after the multiplication above is also known as an Identity matrix. In matrix notation, it serves the same function as that of the number 1 in the real number system. To establish an analogy, in the real number system if you multiply any number by 1, you get the number itself. Similarly, when you multiply any matrix with the identity matrix, also denoted by I, you get the same matrix once again. ( You can calculate this and verify yourselves)

 

Now taking the analogy of the real number system, when you multiply 2 numbers  a and b and it comes out to be 1, i.e.

a×b=1 then 
a and b are called reciprocal of each other.

In the matrix world, if you have two matrices 
A and B, and their multiplication results in the identity matrix  
I, i.e.

B  x A = I,

then 
A and B are called inverses of each other.


The inverse of 
A is also written as 
A−1.  Therefore 
B=A−1

In a later segment, we'll get to know how these inverses are useful.

Note that 
A−1 A=I=AA−1. You can verify this using the above matrix.

 
Here's a short video showing how to find the inverse of a matrix in Python.


Additional Reading
If you want to learn how to find the inverse of a Matrix mathematically, please refer to this link.
 

In the next segment, you will learn how we express the vectors of a matrix.


# Basis
In the previous segments, you have learnt how to represent vectors and matrices and understood some of their important operations. We will dive into one of the most fundamental building blocks of PCA: Basis. But before we get into the math part of it, let’s understand, in a very intuitive way, what it represents, in the following lecture.


Essentially, ‘basis’ is a unit in which we express the vectors of a matrix.

 

For example, we describe the weight of an object in terms of the kilogram, gram, and so on; to describe length, we use a metre, centimetre, etc. So for example, when you say that an object has a length of 23 cm, what you are essentially saying is that the object’s length is 
23×1 cm. Here, 1 cm is the unit in which you are expressing the length of the object.

Similarly, vectors in any dimensional space or matrix can be represented as a linear combination of basis vectors. 


Let’s discuss them in further detail in the following lecture.




Essentially, ‘basis’ is a unit in which we express the vectors of a matrix.

 

For example, we describe the weight of an object in terms of the kilogram, gram, and so on; to describe length, we use a metre, centimetre, etc. So for example, when you say that an object has a length of 23 cm, what you are essentially saying is that the object’s length is 
23
×
1
 cm. Here, 1 cm is the unit in which you are expressing the length of the object.

 

Similarly, vectors in any dimensional space or matrix can be represented as a linear combination of basis vectors. 

 

Let’s discuss them in further detail in the following lecture.


Let's unpack the ideas that you learnt in the above video. Since i and j themselves represent (1,0) and (0,1), you can represent any vector in the 2-D space with these i and j vectors.

 Any vector '
a
' 
(
a
x
,
a
y
)
 can be represented in a 2-D space, using the following notation:

 

a
=
a
x
i
+
a
y
j
 
or 

a
=
a
x
⋅
[
1
0
]
+
a
y
⋅
[
0
1
]

 

Visually, it can be represented as follows:

 



 

 

For example, a vector A (2,3) can be written as 
2
⋅
[
1
0
]
+
3
⋅
[
0
1
]
. In order to obtain the vector A, we scaled i by 2 and j by 3 and then finally added them up.

 

This scaling and adding the vectors up to obtain a new vector is also known as a linear combination. 

 

For the patients' dataset that we had earlier, we can denote each patient vector by the following notation.



 

Therefore, now we can say that Patient 1 is represented by 165(1 cm,0) + 55(0,1kg). And similarly, we can express other patients' information as well.

 

The basic definition of basis vectors is that they're a certain set of vectors whose linear combination is able to explain any other vector in that space. 

 

In a 2D space, the standard basis vectors are given by 
[
1
0
]
 and 
[
0
1
]
. In a 3D space, the same are given by 
⎡
⎢
⎣
1
0
0
⎤
⎥
⎦
, 
⎡
⎢
⎣
0
1
0
⎤
⎥
⎦
 and 
⎡
⎢
⎣
0
0
1
⎤
⎥
⎦
. As you can see, an n-dimensional space or a dataset having n variables would have n standard basis vectors.

 

In the next segment you will learn how you can use different basis to explain the same set of vectors.



Question 1/1
Mandatory
Basis Vectors
The vectors i and j are the basis of two-dimensional space. Which of the following is true?

=>

Feedback:
i =(1,0) and j=(0,1) are unit vectors with magnitudes of 1.

Any point on the 2-D space is a linear combination of i and j.

i and j are orthogonal/ perpendicular vectors, and hence, one can't be represented by the other.

# Change of Basis: Introduction
In the previous segment, you understood the concept of basis vectors and how they're the most fundamental units through which you explain the vectors. Now, let's go ahead and understand how you can use different basis to explain the same set of vectors, similar to how you can use different units to explain the same measure.


As explained in the video above, using the analogy of basis as a unit of representation, different basis vectors can be used to represent the same observations, just like you can represent the weight of a patient in kilograms or pounds. As in the previous case, the basis vectors for the representation of the patient’s information are given by 
[
1
f
t
0
l
b
s
]
 and 
[
0
f
t
1
l
b
s
]
.
The following table summarises the results you get when you make the change.



 

As you can see, the patient's height and weight have not changed physically. It's just that you're using a different set of basis vectors now to explain the same patients. So 
[
165
55
]
 is the same as 
[
5.4
121.3
]
when different basis vectors are being used.

 

Relationship between the two sets of  basis vectors
To understand the relationship between the two basis vectors in concrete terms, recall the way we introduced it in the previous segment. We said that every vector in the 2D space can be written as a linear combination of the basis vectors. 

 

So Patient 1's information in the cm/kg space is given by 
165
⋅
[
1
0
]
+
55
⋅
[
0
1
]
 whereas in the ft/lbs space is given by 
5.4
⋅
[
1
0
]
+
121.3
⋅
[
0
1
]

 

Now, 1 ft = 30.48 cm and 1 cm = 0.033 ft

Similarly, 1 kg = 2.205 lbs and 1lbs = 0.454 kg.

 

Therefore, comparing the basis vectors, we can say

 

[
1
f
t
0
l
b
s
]
​in ft/lbs space = 
[
30.48
c
m
0
k
g
]
 in cm/kg space and 

[
0
f
t
1
l
b
s
]
 in ft/lbs space = ​
[
0
c
m
0.45
k
g
]
​

 

Here's a neat manipulation that you can do to understand the way the numbers arrange amongst themselves using the linear combination property.

 

[
165
55
]
  = 165
[
1
0
]
 + 55
[
0
1
]
 = 5.4
[
30.48
0
]
 + 121.3
[
0
0.45
]
in the cm/kg space.

 

In the above case, we considered the new basis vectors as 
[
30.48
0
]
 and 
[
0
0.45
]
 in the cm/kg space which is equivalent to (1,0) and (0,1) in the ft/lbs space. And using this, we got the representation of 
[
5.4
121.3
]
 for the patient.

 

Therefore, we can choose a completely different set of vectors, say v1 and v2 as the basis vectors and find the representation of  Patient 1 (originally in the standard basis vectors) in the new basis system. They should be satisfying the following linear combination equation

[
165
55
]
= 
a
1
⋅
v
1
+
a
2
⋅
v
2

 

where 
(
a
1
,
a
2
)
 is the representation of Patient 1 in the v1 and v2 space.

 

To understand better, 

Taking 
v
1
=
[
30.48
0
]
 and 
v
2
=
[
0
0.45
]
 we got 
a
1
=
5.4
 and 
a
2
=
121.3

Similarly, taking 
v
1
=
[
55
0
]
 and 
v
2
=
[
0
55
]
 we get 
a
1
=
3
 and 
a
2
=
1

Again, taking 
v
1
=
[
3
1
]
 and 
v
2
=
[
2
0
]
 we get 
a
1
=
55
 and 
a
2
=
0

and so on..

 

Did you notice something different in the above example where we considered  
v
1
=
[
3
1
]
 and 
v
2
=
[
2
0
]
? This means that the new basis need not be parallel to the original basis.

 

Simply put, you have the flexibility of choosing a different set of basis vectors apart from the standard basis vectors that are provided to you to represent your information. The information won't change, just the numbers representing the information would change.

 

In the next segment you will do all the necessary calculations that come along in change of basis.


Q1)
Different Basis Vectors
Let's say that you're representing the vector 
[
120
35
]
 using a new set of basis vectors 
[
1
c
]
 and 
[
d
0.25
]
, where 
c
 and 
d
 are unknowns. 

In this new representation, that vector in the original standard basis is now written as 
[
30
20
]
.

From this information, find out the values of 
c
 and 
d


c =1,  d = 4.5

✓ Correct
Feedback:
We have 
a
1
=
30
,
a
2
=
20
,
v
1
=
(
1
,
c
)
 
a
n
d
 
v
2
=
(
d
,
0.25
)

Substituting the values given above in the equation 
[
120
35
]
=
a
1
∗
v
1
+
a
2
∗
v
2
 you'll get the following  
[
120
35
]
=
30
∗
[
1
c
]
+
20
∗
[
d
0.25
]

Thus our equations are 
120
=
30
+
20
∗
d
 
a
n
d
 
35
=
30
∗
c
+
20
∗
0.25

Solving both the equations give the value of c as 1 and d as 4.5

# Change of Basis: Calculations

In the previous segment, you saw a demonstration on how the change of basis led to dimensionality reduction. Let's go ahead and understand the elegant way of doing the same calculations.


[Important Note - There's an error in the video below. The ft and cm corresponding to the New Basis Representation and the Old Basis Representation have been interchanged. The correct one is shown below]


As you saw above, when you have one dimension, the calculations for the change of basis are pretty straightforward. All you need to do here is to multiply the factor M which gives you the method of transforming from one basis to another.


But when the transformation requires 2 or more dimensions, what to do then? Let's find out.\

You saw that when more than one dimensions are involved, M becomes a matrix rather than a simple scalar. In this case, the first equation remains the same, just that here M is a matrix instead of a scalar. 

 

Note that in the above example, in the old basis, representation of a data point is 
[5.4
121.3]
 and you have to convert it to the new basis. Hence, the M here will be the old basis representation which is 
[
30.48 0
0 0.45
]
.

But what if you want to go the other way around? Surely, you can't go ahead and simply take a reciprocal right? This is where the concept of matrix inverse comes into the picture. 


As you saw in the demonstration above the original matrix gets inversed when we want to go the other way around. Therefore, the equation remains the same in both the cases, but here the 
M
−
1
 would mean the inverse of the matrix rather than a simple reciprocal.

 

So to summarise what you saw in the video,  
M
=
[
30.48
0
0
0.454
]
which is the matrix that shows the change of basis from ft/lbs to cm/kgs


and 
M
−
1
=
[
0.0328
0
0
2.205
]
 which shows the changes from cm/kgs to ft/lbs

 

 

In the next segment, we'll go ahead and generalise the idea of the change of basis using some more solved examples.

# Change of Basis: Solved Examples
In this segment, we'll take a look at how we compute the transformation matrix M that helps us navigate between multiple basis vectors. We'll generalise the conventions on how to move from one basis to another basis so that it becomes easier while using the formula.


The fundamental equation to move between different basis vectors that we studied in the previous session is shown as follows:

 



 

Our target was to represent M in the terms of the old basis vectors and the new basis vectors.

 

Before we move to that part, we need to set some conventions for ease of use. These conventions are given as follows:

B1 will represent the old basis and v1 is the old basis representation
B2 will represent the new basis and v2 is the new basis representation
This would mean that the equation shown just previously can be written as: 

 

          
v
2
=
M
∗
v
1

Let's consider this as equation 1.

 

Now, when we shift between multiple basis vectors the following equation remains valid,

 

B
1
∗
v
1
=
B
2
∗
v
2

 

A slight manipulation of this equation gives us the following equation:

 

B
−
1
2
∗
B
1
∗
v
1
=
B
−
1
2
∗
B
2
∗
v
2

 

which gets converted to:

 

v
2
=
B
−
1
2
∗
B
1
∗
v
1

 

Let's consider this as equation 2.

 

On comparing equations 1 and  2, we get the following equation for M as follows:

 

M
=
B
−
1
2
B
1

 

Now let's go ahead and solve some problems.


The following image summarises the learnings of the video above (click on the image to enlarge it)


Mainly when we're moving between multiple basis vectors, it's important to know that the point's position in space doesn't change. The point's representation might be different in different basis vectors but it would be representing the same point.

Q1) 

Change of Basis
Let's say you have a set of basis vectors B given by 
[
1
2
]
 and 
[
1
−
1
]
. What is the change of basis matrix M when you move from this basis to the standard basis of 
[
1
0
]
 and 
[
0
1
]
 ?


 ==>


 
[
1
1
2
−
1
]

✓ Correct
Feedback:
Here, we're moving from 
[
1
1
2
−
1
]
to 
[
1
0
0
1
]
. Therefore, by convention, 

B1 = 
[
1
1
2
−
1
]

 

B2 = 
[
1
0
0
1
]

 

Observe that in this case, we're moving from a non-standard basis to a standard basis. Hence, M will be equal to the non-standard basis vector matrix itself. Alternatively, if you use the formula for M,

 

M
=
B
−
1
2
∗
B
1

 

In this case, B1 is the non-standard basis and B2 is the standard basis. Since the standard basis is also the identity matrix, the inverse of B2 will be the identity matrix itself. Therefore M = B1.


Next, let's go ahead and solve some examples in python. Download the notebook from the link below

Please find the files here



There are 3 major steps that need to be performed while doing change of basis operations in python. After you've set the proper conventions for moving from B1 to B2, you need to

 

- Store the basis vector matrices in numpy arrays. Make sure that you're passing the rows of the basis vector matrix as arguments while creating the matrices.

 

- Create the transformation matrix by using the formula mentioned below:

 

M
=
B
−
1
2
B
1

 

- Finally, use the change of basis equation for finding a point's new representation from old representation,

v
2
=
M
∗
v
1

 

 

Comprehension

 

Let's say you have a point 
[
8
6
]
 in the standard basis vectors in 2-d 
[
1
0
]
 
a
n
d
 
[
0
1
]

 

You want to find its representation on the following basis :

 

[
2
−
2
1
1
]

 

Answer the following questions to sequentially solve the aforementioned problem.




Q1) Change of Basis - Conventions
Choose the correct option

The correct set of conventions as per the problem statement are


v
2
=
[
8
6
]
 

B
1
=
[
1
0
0
1
]
 
a
n
d
 
B
2
=
[
2
−
2
1
1
]
 

 -->

 v
1
=
[
8
6
]
 

B
1
=
[
1
0
0
1
]
 
a
n
d
 
B
2
=
[
2
−
2
1
1
]

✓ Correct
Feedback:
The original basis vectors and representation are given by B1 and v1 respectively. Similarly, the new basis and the new basis representation is given by B2 and v2 respectively. Therefore, as per the problem statement, this will be the correct answer.

Q2) 

Finding the new representation
What is the representation of the point i.e. 
[
8
6
]
 in the new basis?

 ==>

 
[
5
1
]

✓ Correct
Feedback:
We know that 

v
2
=
M
∗
v
1

 

Now

v
1
=
[
8
6
]

 

M
=
[
0.25
0.5
−
0.25
0.5
]

Substituting the values,  we can get the value of v2. In python, the following code would work for us

First, store v1 using numpy arrays

v1 = np.array([[8],[6]])
v2 = M @ v1
 

The value of v2 comes out to be 

v
2
=
[
5
1
]




# Comprehension: I
Imagine you went to a different planet for exploratory reasons to find intelligent life there. You met an alien and you started showing it where you came from and location of Earth from that planet.

 

You realised that the basis used by the alien is not the same as yours.

 

You use the basis

 

B
1
=
[
1
0
]
 
a
n
d
 
[
0
1
]

 

while the alien uses the basis 
B
2
=
[
1
−
2
]
 
a
n
d
[
1
1
]
. 

 

 

Now answer the following questions.




Q1)


Position of Saturn
You want to tell the new alien friend about the beautiful Saturn.

The location of Saturn in your basis is
[
25
28
]
.

What is the representation of the same in Alien's basis?


==>

[
−
1
26
]

✓ Correct
Feedback:
We simply multiply by the matrix we found.

[
1
1
−
2
1
]
−
1
⋅
[
25
28
]

Q2) 

Position of Kappa
The Alien also tells you the location of a planet that also has intelligent life, Kappa. The position is however in Alien's basis. To make this information useful to Earth people you have to convert the position to Earth's Basis 
B
1
. The representation of Kappa in Alien's basis is 
[
−
3
12
]
.

What is the representation in your Basis?

==>

    [
9
18
]

✓ Correct
Feedback:
We saw, to get the representation we multiply by the matrix obtained by writing basis of Alien as column vectors

[
1
1
−
2
1
]
⋅
[
−
3
12
]
=
[
9
18
]

# PCA and Change of Basis

In the previous segments, you learnt the concept of basis and the change of basis. Now, you might wonder what role does it have to play in PCA. Let's understand how the change of basis plays an important role in the case of dimensionality reduction.



You understood intuitively in the above lecture how a change in basis is the fundamental concept behind PCA. To summarise,

 

PCA finds new basis vectors for us. These new basis vectors are also known as Principal Components.
We represent the data using these new Principal Components by performing the change of basis calculations.
After doing the change of basis, we can perform dimensionality reduction. In fact, PCA finds new basis vectors in such a way that it becomes easier for us to discard a few of the features.
 

In the next video let's take a look at a numerical example to drive home this concept.

Calculations for the demonstration
In the above video, you took a look at a change of basis demonstration for the roadmap example. Here are the relevant calculations that were done to obtain the new dataset from the original dataset.

 

We had the following dataset in the beginning.

Visually, the above image can be shown as follows.

And, PCA gave us the following basis vectors as the new principal components.


[
0.8944
0.4472
]
 
a
n
d
 
[
−
0.4472
0.8944
]

These basis vectors are shown as follows.

The basis vector matrix would come out to be :

 

[
0.8944 −0.4472
0.4472 0.8944
]

The next step would be to compute the change of basis matrix M, which in this case will be the inverse of the matrix above since we're moving from the standard basis to a non-standard basis.

 

M
=
[
0.8944
−
0.4472
0.4472
0.8944
]
−
1
=
[
0.8944
0.4472
−
0.4472
0.8944
]

(Note - You can verify this calculation in python by using the np.linalg.inv() function.)


Now, all we have to do is multiply the matrix M that has been calculated above by each of the points in the dataset to obtain the representation in the new set of basis vectors. 

 

For P1, the original representation is given as (2,1) or 
[
2
1
]

 

and therefore the new representation is M multiplied by the above vector or

 

                                           
[
0.8944
0.4472
−
0.4472
0.8944
]
[
2
1
]
=
[
2.24
0
]

 

Similarly, when you perform the above calculation for all the points, you get the following representation for the dataset.


This can be represented visually as below.


Additional Notes

*As explained in the video we haven't yet discussed how Principal Components are found numerically.

 

We'll be learning that in the next session.




Q2)

Basis
A vector is represented as 
[
1
1
]
 in basis 
{
[
1
1
]
,
[
2
1
]
}
. What is the vector in our standard basis 
[
1
0
0
1
]

==>

[
3
2
]

✓ Correct
Feedback:
You're moving from non-standard basis vectors to the standard basis. Therefore, in this case, the change of basis matrix 
M
 would be the same as the non-standard basis vectors. Therefore, the new point is given by

 

 
[
1
2
1
1
]
⋅
[
1
1
]
=
[
3
2
]





# Summary: I
That was the end of quite a hectic session! Here's a summary of what you've learnt so far.

 

First, you came to know about PCA and how it is essentially a dimensionality reduction technique.  You saw the necessity for doing PCA in a couple of situations like 

A predictive model setup where there are a lot of features to eliminate
A dataset where you needed to perform EDA and Data Visualisation
You understood how PCA not only helps in resolving the above two issues but has applications in several other areas like noise reduction, finding latent Themes and so on. Then you got a brief understanding of its definition:

 

It is a statistical procedure that finds principal components or directions that are:

Linear combination of the original variables
Are uncorrelated
Capture Maximum information in the dataset.
 

After that, you went ahead and learnt some essential linear algebra concepts like vectors and their properties along with their associated operations. Then you studied another tool called matrix multiplication and matrix inverse, both of which proved invaluable in understanding the first fundamental building block of PCA: Basis

 

Basis is essentially the fundamental units in which you express your data. As you saw in the lecture videos, it is similar to how we use units for physical objects to measure things like height, weight, temperature, etc. 

 

In vectors and vector spaces, we use basis vectors to represent the points in space. You understood how every observation in the space can be represented by scaling and adding the scaled basis vectors. This process is also called a linear combination.

 

Then you learnt one of the key ideas that helped you connect basis vectors and the idea of dimensionality reduction: using different basis vectors to represent the same points.

 

From there, you learnt how to change from one basis space to another using matrices. Here's a list of rules to help you revise the same.

 

1.) If you're moving from a basis space 
B
  to the standard basis, then the change of basis matrix 
M
 is the same as the basis vectors of 
B
 written as its column vectors. Therefore, if there is a vector 
v
  represented in 
B
 and you want to find its representation in the standard basis, then you'd have to perform 
M
v
.

 

2.) If you want to go the other way around, where you have 
v
 represented in the standard basis and want to find its representation in 
B
  you multiply it by its inverse  - 
M
−
1
v

 

3.) Finally, if you want to find the change of basis matrix 
M
 where you move from two non-standard basis vectors - say from 
B
1
 to 
B
2
 then you can get that by calculating this value - 

B
−
1
2
B
1
. Note that in all the above cases, the basis vectors should be represented in the same units.



Q1) 

Graded Questions
Attempt the following graded questions to solidify your understanding. Use Python functions where ever required. All the best!



Change in Basis
You're given a vector 
[
3
2
]
 in the standard basis.

You need to find its representation on a new basis-- 
[
3
−
3
4
−
5
]

What's the change of basis matrix M in this scenario?


==>

[
1.667
−
1
1.333
−
1
]

✓ Correct
Feedback:
In this scenario, we're moving from the standard basis to a non-standard basis. Therefore, M will be the inverse of the non-standard basis vectors.

M
=
[
3
−
3
4
−
5
]
−
1

The following code calculates the above value in python

B2 = np.array([[3,-3],[4,-5]])
M = np.linalg.inv(B2)
 

M comes out to be 
[
1.667
−
1
1.333
−
1
]
 approximately.


 Q2) 

 Find the new representation
Now that you have the change of basis matrix M, compute the representation of the vector 
[
3
2
]
 in the new basis.

 ==>

 [3
2]

✓ Correct
Feedback:
From the previous question, we obtained that 
M
=
[1.667
−1
1.333
−1
]

and given 
v1=[3
2
]

Therefore, 
v2=M∗v1=[1.667
−
1
1.333
−
1
]
[
3
2
]
=
[
3
2
]

 

In python, you can use the following code - 

v1 = np.array([[3],[2]])
v2 = M@v1



# Introduction
Welcome to the session on Fundamentals of PCA - II!

 

Here we'll learn about the concept of variance and its importance and use in the PCA, concept of basis vectors and how you can use different basis vectors to represent the same information.

 

In this session
This session covers some important linear algebra concepts required for understanding PCA and how it works. These main concepts are as follows

 

# Introduction to Variance
Variance as Information
Directions of Maximum Variance
The Workings of PCA


Introduction to Variance
In the previous session, you learnt about the first fundamental building block for learning PCA - the idea of basis and the change of basis. You saw how a simple change of basis led to dimensionality reduction in the case of the roadmap example and then understood how you can represent the same data in multiple basis vectors.

 

However, we didn't know how to find those "ideal basis vectors" and what exact properties they must satisfy. In this session, we'll get to do that by understanding the idea of variance as information.



As mentioned previously, you have already learnt certain methods through which you delete columns – by checking the number of null values, unnecessary information and in modelling by checking the p-values and VIF scores.

 

PCA gauges the importance of a column by another metric called ‘variance’ or how varied a column’s values are.
 

Let's go ahead and look at some examples in the next segment and get an intuitive idea of what variance actually means.


# Variance as Information
Let's take a look at a simple example that will help us intuitively understand how variance in the data is equivalent to information we can extract out of the data.


As you saw in the example, the first image didn't have much information in it. Speaking of it in the ways the pixels are arranged, it is the same colour throughout. However, there are a lot of things that you could distinguish easily in the second image and therefore that image has a lot to offer in terms of information. The pixels have a lot of variety and therefore that image has more variance and equivalently, more information.


Q1)
So the key takeaway from the above lecture is to measure the importance of a column by checking its variance values. If a column has more variance, then this column will contain more information.

 

Geometrical Interpretation of  Variance

 

In the above example, you saw that the variance of height was only 14, whereas that of weight was 311.14. This gave you an idea that Weight is a more important column than Height. Now, there is another elegant way of looking at variance geometrically. Take a look at the following image.



 

The red line on the Height and Weight axes shows the spread of the projections of the vectors on those axes. As you can see here, the spread of the line is quite good on the Weight axis as compared to the Height axis. Hence you can say that Weight has more variance than Height. This idea of the spread of the data being equivalent to the variance is quite an elegant way to distinguish the important directions from the non-important ones.




Q1)

PCA: Variance
Which axis captures more variance in the following plot between Age and Weight?

==>

Age 

✓ Correct
Feedback:
When the farthest points of the data are projected on the axis, the length of the projection becomes proportional to the variance. In the given image, the length of the projection of the farthest points of data on the Y-axis is more than the length of the projection on the X-axis.

# Directions of Maximum Variance
So you saw that when the variances are unequally distributed among the original features or columns i.e. some columns have much less variance than others, it is easier to remove those columns and do dimensionality reduction.

 

But what about the scenario when the variances are pretty similar? For example, take a look at the following image containing the height and weight information of a different group of patients.

 



 

 

As you can see, the spread along both the axes is quite comparable and therefore, you can't directly go and say that one direction is more useful than the other. What to do now?

 

Let’s look at the next lecture to further understand this problem and appreciate how PCA solves this problem smartly.

Play Video3219582
After going through the above lecture, you have more or less understood what PCA does. It changes the basis vectors in such a way that the new basis vectors capture the maximum variance or information. In the next video, we'll get to know how this happens visually.

Play Video3219582
 

Basically, the steps of PCA for finding the principal components can be summarised as follows.

First, it finds the basis vector which is along the best- fit line that maximises the variance. This is our first principal component or PC1.
The second principal component is perpendicular to the first principal component and contains the next highest amount of variance in the dataset.
This process continues iteratively, i.e. each new principal component is perpendicular to all the previous principal components and should explain the next highest amount of variance.
If the dataset contains n independent features, then PCA will create n Principal components.
 

For a 2-D dataset that has the representation as shown in the image below.

 



 

 

 The principal components can be visually represented as shown in the image below.

(Click on the image to enlarge it.)

 



 

 

 

Also, once the Principal Components are found out, PCA assigns a %age variance to each PC. Essentially it's the fraction of the total variance of the dataset explained by a particular PC. This helps in understanding which Principal Component is more important than the other and by how much. This is shown in the images below.

 

Original Dataset


PCA Modified Dataset

 

Directions of Maximum Variance
So you saw that when the variances are unequally distributed among the original features or columns i.e. some columns have much less variance than others, it is easier to remove those columns and do dimensionality reduction.

 

But what about the scenario when the variances are pretty similar? For example, take a look at the following image containing the height and weight information of a different group of patients.


As you can see, the spread along both the axes is quite comparable and therefore, you can't directly go and say that one direction is more useful than the other. What to do now?

 

Let’s look at the next lecture to further understand this problem and appreciate how PCA solves this problem smartly.



After going through the above lecture, you have more or less understood what PCA does. It changes the basis vectors in such a way that the new basis vectors capture the maximum variance or information. In the next video, we'll get to know how this happens visually.


Basically, the steps of PCA for finding the principal components can be summarised as follows.

First, it finds the basis vector which is along the best- fit line that maximises the variance. This is our first principal component or PC1.
The second principal component is perpendicular to the first principal component and contains the next highest amount of variance in the dataset.
This process continues iteratively, i.e. each new principal component is perpendicular to all the previous principal components and should explain the next highest amount of variance.
If the dataset contains n independent features, then PCA will create n Principal components.


For a 2-D dataset that has the representation as shown in the image below.


For a 2-D dataset that has the representation as shown in the image below.

  The principal components can be visually represented as shown in the image below.

(Click on the image to enlarge it.)

 

Also, once the Principal Components are found out, PCA assigns a %age variance to each PC. Essentially it's the fraction of the total variance of the dataset explained by a particular PC. This helps in understanding which Principal Component is more important than the other and by how much. This is shown in the images below.

Since 100% of the total variance or information of the entire dataset is present in only one of the columns (PC1) we can safely drop PC2 and still be assured of losing no information.

 

In the next video you will learn about the objectives that PCA aims to achieve.

#  The Workings of PCA
Until now, you've learnt the two building blocks of PCA: Basis and variance. In the following video, we will make use of both the terms to make you understand the objective that PCA aims to achieve.


The steps  of PCA as summarised in the above video are as follows:

 

Find n new features - Choose a different set of n basis vectors (non-standard). These basis vectors are essentially the directions of maximum variance and are called Principal Components
Express the original dataset using these new features
Transform the dataset from the original basis to this PCA basis.
Perform dimensionality reduction - Choose only a certain k (where k < n) number of the PCs to represent the data.  Remove those PCs which have fewer variance (explain less information) than others.
 

PCA's role in the ML pipeline almost solely exists as a dimensionality reduction tool. Basically, you choose a fixed number of PCs that explained a certain threshold of variance that you have chosen and then use only that many columns to represent the original dataset. This modified dataset is then passed on to the ML pipeline for further prediction algorithms to take place. PCA helps us in improving the model performance significantly and helps us in visualising higher-dimensional datasets as well.

 

Additional Reading

As mentioned in the video, you can take a look at the Algorithm of PCA optional session to understand in detail about how PCA finds the new basis vectors using the eigendecomposition of the covariance matrix method.
Report an error

# Summary: II
Let's reiterate the learnings of the past two sessions:

You understood the concept of basis vectors and how they're helpful in the representation of data points.
You then learnt about how you can use different basis vectors to represent the same information.
Using the previous knowledge, you came to know that when represented under some 'ideal basis vectors', it becomes easier for us to do dimensionality reduction. However, you didn't exactly know how to find those ideal basis vectors.
Then you learnt about the concept of variance and how more variance meant more information.
Then you derived that the more important columns in a dataset are the ones which capture more variance than the others.
Subsequently, you deduced that the most important directions, rather than just columns, are those that capture maximum variance. The ideal basis vectors that we talked about in the previous case are in fact those that do the same.
These basis vectors or directions that capture the maximum variance are essentially the Principal Components for the dataset.


# PCA in python 

Introduction



Welcome to the final session of PCA. In the previous session, you discovered and learnt the theoretical concepts of PCA. In this session, you will learn how to implement PCA in python on some real examples.

 

In this session, you will learn how to use PCA on a problem you have already encountered before - predicting telecom churn using logistic regression. You will now learn to implement PCA in tandem with logistic regression.

 

In this session

Let's look at the broad flow of this session.


# Applying PCA using Python
For this demonstration, we begin with a very popular machine learning dataset - 'Iris'. In the next few segments, you will learn the necessary steps needed to perform PCA on a dataset and then appreciate how it helps in visualising your data that contains more than two dimensions.

 

You can download the dataset and the python notebook used in the demonstration from the link given below:

Please find the files here




Here is a summary of the important steps that you've performed in the video and something that you should do whenever you perform PCA on any other dataset as well.

 

1. After basic data cleaning procedures, standardise your data

 

2. Once standardisation has been done, you can go ahead and perform PCA on the dataset. For doing this you import the necessary libraries from sklearn.decomposition.

 

from sklearn.decomposition import PCA
 

3. Instantiate the PCA function and set the random state to some specific number so that you get the same result every time you execute that code. (If you want to learn more about random state and how it works, you can check this StackOverflow answer)

 

pca = PCA(random_state=42)
 

4.  Perform PCA on the dataset by using the pca.fit function. 

pca.fit(x)
 

5. The Principal Components can be accessed using the following code:
pca.components_

Executing the above code will give the list of Principal components of the original dataset. They'll be of the same number as the original variables in your dataset. In the next segment, you shall see how to choose the optimal number of principal components.


# Scree Plots
In the previous segment, you learnt how to perform PCA on your dataset and obtain the Principal Components. The final PCs that you got were as follows:

 

array([[ 0.52237162, -0.26335492,  0.58125401,  0.56561105],
       [ 0.37231836,  0.92555649,  0.02109478,  0.06541577],
       [-0.72101681,  0.24203288,  0.14089226,  0.6338014 ],
       [-0.26199559,  0.12413481,  0.80115427, -0.52354627]])
 
 PC1 is given by the direction - [0.52  -0.26  0.58   0.56], PC2 by  [0.37 0.92 0.02 0.06] and so on. The principal components of the same number as that of the original variables with each Principal Component explaining some amount of variance of the entire dataset. This information would enable us to know which Principal Components to keep and which to discard to perform Dimensionality Reduction. 

 

Let's understand it further in the following demonstration, where you'll also come to know about scree plots and how they help in communicating the variance information very effectively.




Here's a summary of the important steps that you performed :

 

1. First, you came to know how much variance is being explained by each Principal Component using the following code:

 

pca.explained_variance_ratio_
 

The values that you got were as follows:

 

array([0.72770452, 0.23030523, 0.03683832, 0.00515193])
 

The above values can be summarised in the following table:

 

Principal

Component

Variance explained

(in %)

PC1	72.8
PC2	23
PC3	3.6
PC4	0.5


So as you can see, the first PC, i.e. Principal Component 1([0.52  -0.26  0.58   0.56]) explains the maximum information in the dataset followed by PC2 at 23% and PC3 at 3.6%. In general, when you perform PCA, all the Principal Components are formed in decreasing order of the information that they explain. Therefore, the first principal component will always explain the highest variance, followed by the second principal component and so on. This order helps us in our dimensionality reduction exercise, as now we know which directions are more important than the others. 

 

Now, in our dataset, we only had 4 columns and equivalently 4 PCs. Therefore it was easy to visualise the amount of variance explained by them using a simple bar plot and then we're able to make a call as to how much variance to keep in the data. For example, using the table above, you only need 2 principal components or 2 directions (PC1 and PC2) to explain more than 95% of the variation in the data.

 

But what happens when there are hundreds of columns? Using the above process would be cumbersome since you'd need to look at all the PCs and keep adding their variances up to find the total variance captured.

 

2. Using a Scree-Plot

 

An elegant solution here would be to simply add a plot of "Cumulative variance explained chart". Here against each number of components, we have the total variance explained by all the components till then.

 

Principal  Component	Variance Explained(in %)	Cumulative Variance Explained (in %)
PC1	72.8	72.8
PC2	23	95.8
PC3	3.6	99.4
PC4	.5	99.9
 

So for example, cumulative variance explained by the top 2 principal components is the sum of their individual variances, given by 72.8 +23 =95.8 %. Similarly, you can continue this for 3 and 4 components.

 

If you plot the number of components on the X-axis and the total variance explained on the Y-axis, the resultant plot is also known as a Scree-Plot. It would look somewhat like this:


Q1)

Scree- Plots
In the following scree plot, how much total information is retained using only three principal components?



=>>

More than 80%

✓ Correct
Feedback:
Note that the fourth component explains just above 10% variance but less than 20% variance.  Therefore, the rest of the three components explain more than 80% variance.

# Dimensionality Reduction
In the previous two segments, you understood how to apply PCA on a dataset followed by the importance of scree-plots. Now that you know how many principal components you need to explain a certain amount of variance, let's go and finally do dimensionality reduction on our dataset using the Principal Components that we've chosen.


Here's a summary of the important steps that you saw above:

 

1.) Choosing the required number of components

From the scree plot that you saw previously, you decided to keep ~95% of the information in the data that we have and for that, you need only 2 components. Hence you instantiate a new PCA function with the number of components as 2. This function will perform the dimensionality reduction on our dataset and reduce the number of columns from 4 to 2.

 

pc2 = PCA(n_components=2, random_state=42)
 

2.) Perform Dimensionality Reduction on our dataset.

Now you simply transform the original dataset to the new one where the columns are given by the Principal Components. Here you've finally performed the dimensionality reduction on the dataset by reducing the number of columns from 4 to 2 and still retain 95% of the information. The code that you used to perform the same step is as follows:

 

newdata = pc2.fit_transform(x)
 

and the new dataset is given as follows:

3) Data Visualisation using the PCs

 

Now that you have got the data in 2 dimensions, it is easier for you to visualise the same using a scatterplot or some other chart. By plotting the observations that we have and dividing them on the basis of the species that they belong to we got the following chart:



As you can see, you clearly see that all the species are well segregated from each other and there is little overlap between them. This is quite good as such insight was not possible with higher dimensions as you won't be able to plot them on a 2-D surface. So, therefore, applying  PCA on our data is quite beneficial for observing the relationship between the data points quite elegantly.


Important Note: When you perform PCA on datasets generally, you may need more than 2 components to explain an adequate amount of variance in the data. In those cases, if you want to visualise the relationship between the observations, choose the top 2 Principal Components as your X and Y axes to plot a scatterplot or any such plot to do the same. Since PC1 and PC2 explain the most variance in the dataset, you'll be getting a good representation of the data when you visualise your dataset on those 2 columns.


#Practice Questions: I
Here's a brief summary of what you've learnt so far:

Applying PCA on a dataset in python
Evaluate the amount of variance explained by each component
Use the scree-plot to choose how much variance you need to explain with your transformed dataset
Transform the dataset to the new chosen Principal Components and then perform dimensionality reduction
Use the new dataset for visualisation of the observations
 

Now here are some questions to test your understanding of the same.

Q1)

PCA in Python
The pca.fit() function does which of the following tasks?

==>

Performs PCA on the dataset and finds the Principal Componets.

✓ Correct
Feedback:
pca.fit() is used to perform PCA on the dataset.

Q2)

PCA in Python
Let's say a friend of yours performed PCA on a dataset containing 10 columns and decided to keep only 3 components for the final transformed data. For finding the final transformed data, he used the following code. Evaluate the code and choose the right option.

pca = PCA(random_state = 42)

newdata = pca.fit_transform(dataset)

==>

Another parameter n_components = 3 should be present in the pca function

✓ Correct
Feedback:
The function should be 

pca = PCA(n_components =3 ,random_state=42

Q3)

PCA in Python
For data visualisation purposes after performing PCA, mostly PC1 and PC2 are chosen because

==>

They have the highest variances  explained along their directions.

✓ Correct
Feedback:
Since PC1 and PC2 have the highest and the second highest variances explained along their directions, they'll be able to summarise the dataset more effectively than any other pair of components.

# Improving Model Performance - I
In the previous segments, you saw how to perform dimensionality reduction using PCA and then immediately were introduced to one of its key applications which is for data visualisation. However, the most common application of PCA is to improve your model's performance. So in real life, you use PCA in conjunction with any other model like Linear Regression, Logistic Regression, Clustering amongst others in order to make the process more efficient. In the following demonstration, you'll be looking at both the scenarios - performing model building without PCA and then with PCA to appreciate how much faster it is to get similar or better results in the latter case.


Download the datasets and the python notebook for this demonstration from the link given below.

Please find the files here.

    


Overview of the Demo


For this demonstration, our main model will be a logistic regression setup. As mentioned above, first we'll be performing Logistic Regression directly without any PCA. For this demo, we'll be using the Telecom Churn dataset that you have worked earlier with.

 

Model Building without PCA

 

Since you're already familiar with the data and the logistic regression model that you built, here's a quick walkthrough to refresh your memory.



 deo Correction: At 03:52, Rahim says 'linear regression' though he meant 'logistic regression'.

 

In the video below, we will apply PCA on the data and visualise it by the transformations done by the PCA. 





You saw the process of building a churn prediction model using logistic regression. Some important problems with this process that Rahim pointed out are:

Multicollinearity among a large number of variables, which is not totally avoided even after reducing variables using RFE (or a similar technique)
Need to use a lengthy iterative procedure, i.e. identifying collinear variables, using variable selection techniques, dropping insignificant ones etc.
A potential loss of information due to dropping variables
Model instability due to multicollinearity
 

If you remember the first session, we discussed all these points as potential issues that plague our model building activity. Now let's go ahead and perform PCA on the dataset and then apply Logistic Regression and see if we get any better results.

 

Model Building with PCA

 

In the second part, first, we'll reduce the dimensions that we have using PCA and then create a logistic regression model on it.

 

As you could see, with PCA, you could achieve the same results with just a couple of lines of code. It will be helpful to note that the baseline PCA model has performed at par with the best Logistic Regression model built after the feature elimination and other steps.

 

PCA helped us solve the problem of multicollinearity (and thus model instability), loss of information due to the dropping of variables, and we don't need to use iterative feature selection procedures. Also,  our model becomes much faster because it has to run on a smaller dataset. And even then, our ROC score, which is a key model performance metric is similar to what we achieved previously.

 

To sum it up, if you're doing any sort of modelling activity on a large dataset containing lots of variables, it is a good practice to perform PCA on that dataset first, reduce the dimensionality and then go ahead and create the model that you wanted to make in the first place. You are advised to perform PCA on the datasets that you worked on in Linear Regression and Clustering as well, to see how it makes our job easier.

 

In the next segment you will learn about another functionality in PCA where you can select the amount of variance that you want your final dataset to capture.

As you saw above, all you needed to do was select a particular amount of variance that you want to be explained by the Principal Components of the transformed dataset. PCA automatically chooses the appropriate number of components on its own and proceeds with the transformation. This again saves us a lot of time!

 

In the next segment we have provided practise questions, answer them based on the concepts learnt in this session.


# Practice Questions: II
Here's a summary of your learnings in the last two segments:

You understood the importance of PCA in model building. Essentially before you build any model, you perform PCA to reduce its dimensionality.
This results in a smaller dataset with uncorrelated features - thereby leading to faster execution and a much more stable model.
You observed that performing PCA and then doing the actual model greatly improves its efficiency and also does that without any iterative procedures.
 

Now answer the following questions by applying PCA on the given dataset. Note that you don't need to perform any scaling operation here. Just directly perform PCA


Q1) 

PCA in Python
Once you perform PCA on the dataset provided in this segment and project the data, what is the approximate variance explained by the first principal component?
==>
65%

✓ Correct
Feedback:
Use pca.explained_variance_ratio to find the variance explained by all the components. You can clearly see that the first principal component explains about 65% of the variance.



# Practical Considerations and Alternatives
Until now, you know the in and out of PCA and how to implement it in Python, and hence, you should be aware of when to apply PCA. Let's now look at some practical considerations that need to be kept in mind while applying PCA.


Those were some important points to remember while using PCA. To summarise:

Most software packages use SVD to compute the principal components and assume that the data is scaled and centred, so it is important to do standardisation/normalisation.
PCA is a linear transformation method and works well in tandem with linear models such as linear regression, logistic regression, etc., though it can be used for computational efficiency with non-linear models as well.
It should not be used forcefully to reduce dimensionality (when the features are not correlated).
 

In the next short lecture, Rahim will talk about some shortcomings of PCA. 


You learnt some important shortcomings of PCA:

PCA is limited to linearity, though we can use non-linear techniques such as t-SNE as well (you can read more about t-SNE in the optional reading material below).
PCA needs the components to be perpendicular, though in some cases, that may not be the best solution. The alternative technique is to use Independent Components Analysis. 
PCA assumes that columns with low variance are not useful, which might not be true in prediction setups (especially classification problem with a high class imbalance).
 

If you are interested in reading about t-SNE (t-Distributed Stochastic Neighbor Embedding) or ICA, you can go through the additional reading provided below.

 

This brings us to the end of this segment.

Additional Reading 
t-SNE

[Laurens van der Maaten's (creator of t-SNE) website](https://lvdmaaten.github.io/tsne/)
[Visualising data using t-SNE: Journal of Machine Learning Research](http://www.jmlr.org/papers/volume9/vandermaaten08a/vandermaaten08a.pdf)
[How to use t-SNE effectively](https://distill.pub/2016/misread-tsne/)
[Independent Components Analysis](https://sgfin.github.io/files/notes/CS229_Lecture_Notes.pdf)

[Stanford notes on ICA](https://sgfin.github.io/files/notes/CS229_Lecture_Notes.pdf) (Check pages 122 -127)




# Summary
Here's a summary of what you've learnt so far.

 

First, you implemented PCA in Python on the iris dataset. In that demonstration, you understood the basic steps that you need to follow in PCA - on how to perform PCA, find the Principal Components, choose a particular number of components using the scree-plot, transform your data and then visualise the data.

 

After that, you saw an implementation where you wanted to improve the model efficiency in a Logistic Regression Setup. Here you were able to see that with PCA, you're able to maintain the same level of efficiency without going through all the iterative feature elimination procedures. You also saw how to perform PCA faster by just giving it how much variance you need to be explained.

 

Here's a list of useful functions that use after importing the PCA function from sklearn libraries.

pca.fit() - Perform PCA on the dataset.
pca.components_ -  Explains the principal components in the data
pca.explained_variance_ratio_ - Explains the variance explained by each component
pca.fit(n_components = k) - Perform PCA and choose only k components
pca.fit_transform  - Transform the data from original basis to PC basis.
pca(var) -  Here 'var' is a number between 0-1. Perform PCA on the dataset and choose the number of components automatically such that the variance explained is (100*var)%.

 

Please download the lecture notes for this module from the link below


Q1)

Graded Question
Which two independent variables have the highest correlation between them?

-->

area and areaperbedroom

✓ Correct
Feedback:
ij_max = np.unravel_index(corrmat_diag_zero.argmax(), corrmat_diag_zero.shape)
print("ij_max",ij_max)

The highest correlation is between (0,13)

Q2) Graded Question
What is the value of the highest correlation amongst the explanatory variables?

==>

Approximately 0.8

✓ Correct
Feedback:
print("Maximum correlation :", corrmat_diag_zero[ij_max])

Q3)

Graded Question
Which of the following preprocessing steps is the most crucial before performing PCA?

==>


Standardisation of data

✓ Correct
Feedback:
If variables are on a different scale (e.g. fractions and millions), then PCA (while trying to maximise the variance) will give higher importance to the variables with high variance simply because of scale. For example, if you change one variable from km to cm (increasing its variance), it may go from having little impact to dominating the first.

