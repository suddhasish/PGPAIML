Introduction to Matplotlib:
Data visualisation is an important skill to possess for anyone trying to extract and communicate insights from data. Great business narratives and presentations often stem from brilliant visualisations that convey the key ideas in a concise and aesthetic manner. In the field of machine learning, visualisation plays a key role throughout the entire process of analysis - to obtain relationships, observe trends and portray the final results as well. Therefore, it is imperative that you learn and master this tool which will aid you throughout this program.

 
This session will help you learn how to visualise data in Python using the Matplotlib library.


In the previous module, you learnt how to handle numerical data using the NumPy library. You could load data in the form of arrays and then perform operations on the same. In this session, we will try to visualise the arrays using another library in Python, namely, Matplotlib.


Facts and Dimensions
Graphics and visuals, when used intelligently and innovatively, can convey a lot more than what raw data alone can. Matplotlib serves the purpose of providing multiple functions to build graphs from the data stored in your lists, arrays, etc. So, let’s start with the first lecture on Matplotlib.

 

Before we start discussing different types of plots, you need to learn about the elements that help us create charts and plots effectively. 
There are two types of data, which are as follows:

Facts

Dimensions

Facts and dimensions are different types of variables that help you interpret data better. Facts are numerical data, and dimensions are metadata. Metadata explains the additional information associated with the factual variable. Both facts and dimensions are equally important for generating actionable insights from a given data set. For example, in a data set about the height of students in a class, the height of the students would be a fact variable, whereas the gender of the students would be a dimensional variable. You can use dimensions to slice data for easier analysis. In this case, the distribution of height based on the gender of a student can be studied.

 

Identifying facts and dimensions among variables effectively will help you start the analysis of a given data set.



## Bar Graph:
Plots are used to convey different ideas. For example, you can use certain plots to visualise the spread of data across two variables and other plots to gauge the frequency of a label. Depending on the objective of your visualisation task, you can choose an appropriate plot. As part of this session, you will learn how to select an appropriate plot. You can download the Jupyter Notebook attached below. The same notebook will be used in the demonstrations throughout the session.

In this segment, you will learn how to create the first plot: Bar Graph. In the following video, Behzad will explain the process of creating a bar graph. 


As you saw in the video above, the subpackage pyplot is used to build plots and graphs throughout this session. To load the subpackage, you need to run the following command:

 

import matplotlib.pyplot as plt
 

To recap, Matplotlib allows you to use a simple and intuitive workflow to create plots. The important Matplotlib commands used in the video above are as follows:

## plt.bar(x_component, y_component): Used to draw a bar graph
plt.show(): Explicit command required to display the plot object
A bar graph is helpful when you need to visualise a numeric feature (fact) across multiple categories. In the example covered in the video, you plotted the sales amount (numeric feature) under three different product categories. Using the bar graph, you could easily distinguish between the performance of these categories.



more than one color for each category:

Feedback:
Colours can be provided as a list to the matplotlib.pyplot.bar function under the attribute ‘color’.: matplotlib.pyplot.bar(x, y, color = [‘red’, ‘blue’, ‘green’]) [Note: if there are more than three bars, the colours will start repeating themselves.]


## Scatter Plot
Scatter plot, as the name suggests, displays how the variables are spread across the range considered. It can be used to identify a relationship or pattern between two quantitative variables and the presence of outliers within them.


You can use the following command to build a scatter plot:

##  plt.scatter(x_axis, y_axis) ##
 

Using this command, the data points will spread across the graph corresponding to the values on the y and x axes.
The plot that was developed in the demonstration is given below. 

Take a look at the rightmost point in the plot. It represents a product that made a profit of 1,50,000 units when the sales generated were 8,00,000 units. Similarly, all the points in the plot represent a product and its profit and sales values. Just by looking at the chart, can you find the products that are more lucrative to trade than others? Yes, a lucrative product has high profit value with preferably low sales value, that is the points to the right side in the plot preferably also towards the bottom.
-----
Now that you have learnt how to read a scatter plot, let’s proceed to more complex features of a scatter plot.
Matplotlib offers a feature that allows you to incorporate a categorical distinction between the points plotted on a scatter plot.
Using this feature, you can colour-code the points based on the category and distinguish them accordingly. 


You can run the scatter function with the following attributes to specify the colours and labels of the categories in a data set:

plt.scatter(x_axis, y_axis, c = color, label = labels)
 

Here, all the information (x_axis, y_axis, colour, labels) need to be provided in the form of a list or an array. You can use this command to assign colours to categories and distinguish them accordingly. 
 
Another feature of a scatter plot allows you to use labels to further distinguish points over another dimension variable. Suppose you have the array ‘country’, which indicates the country where the sales were generated. Now you want to highlight the points belonging to a particular country in the previous scatter plot.


You can use the following command to add a note (annotate) with a point in the scatter plot:

 

plt.scatter(profit[product_category == "Technology"], sales[product_category == "Technology"], 
            c= 'Green', alpha= 0.7, s = 150, label="Technology" )  --> Identifying technology products from numpy arrary and plotting them with green.

plt.scatter(profit[product_category == "Office Supplies"], sales[product_category == "Office Supplies"], 
            c= 'Yellow', alpha= 0.7, s = 100, label="Office Supplies" ) --> Identifying Office Supplies products from numpy arrary and plotting them with yellow.

plt.scatter(profit[product_category == "Furniture"], sales[product_category == "Furniture"], 
            c= 'Cyan', alpha= 0.7, s = 50, label="Furniture" ) --> Identifying furniture products from numpy arrary and plotting them with cyan.

for xy in zip (profit[country == "India"], sales[country == "India"]):
	plt.annotate(s = "India", xy = xy)   --> depicting or annotating the Country name in each plot

# Adding and formatting title
plt.title("Sales versus Profits across various Countries and Product Categories\n", fontdict={'fontsize': 20, 'fontweight' : 5, 'color' : 'Green'}) ---> This will be title of the chart

# Labeling Axes
plt.xlabel("Profit", fontdict={'fontsize': 12, 'fontweight' : 5, 'color' : 'Brown'})  --> This is used to label x axis 
plt.ylabel("Sales", fontdict={'fontsize': 12, 'fontweight' : 5, 'color' : 'Brown'}) --> This is used to label y axis

plt.legend() --> This will help user to identify which color in plot dedicated to which type of product.

plt.show() --> This will finally plot the chart.


After using the command to add a note, your scatter plot will look like the one given below. 


As you can see in the figure above, the products that were traded in India are marked. This is how the annotate statement that was added to a point in the scatter plot helps you distinguish the data points. 


In this segment, you learnt how a scatter plot helps you visualise two numeric variables. Attempt the following questions to cement the concepts that were covered in this segment. 


# Realtime use case of scatterplot :

1) To check whether a relationship exists between the age of a person and their income.
2) To check whether stock prices are positively related to the profit of a company.


