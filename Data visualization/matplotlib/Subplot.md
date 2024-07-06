Subplots
In the previous segments, you learnt the basic ways to create plots. 


Sometimes, it is beneficial to draw different plots on a single grid next to each other to get a better overview of the data set. 
For example, suppose you have some data on e-commerce purchases. If you want to analyse the number of purchases across different categories, 
you can create multiple bar charts for each category, for example, one for male buyers and another for female buyers. These two charts, when placed next to each other, make it easy for you to compare the buying patterns of the male and female consumers.


Different plots presented in a single plot object are commonly referred to as subplots. 

By default plot will change color.

To recap, you can use the following Matplotlib command to create subplots in Python:

fig, ax = plt.subplots(): It initiates a figure that will be used to comprise multiple graphs in a single chart.
Subplots are a good way to show multiple plots together for comparison. In the video above, you learnt how to plot different categories together in the same chart.

Subplots offer the ability to create an array of plots, and you can create multiple charts next to each other to make it look like the elements of an array

fig, ax = plt.subplots(ncols=3, nrows=2, sharex=True, sharey=True)  this divides x axis into 3 and y to 2 but keep ranges intact for better comparision. 2*3 blank figure sharing x axis and y axis.
we can access each plot using ax[i][j].plot as mentioned in below code 

europe, = ax[0][0].plot(years, sales_Europe)
europe.set_label("Europe")


You can use the following command to create an array of plots.

plt.subplot(nrow, ncol, x): It creates a subplot. 'nrow' and 'ncol' are the dimensions of the array inside the figure, and 'x' is the position in the array.
(You can visit this web page to understand the attributes associated with the subplot method in detail.)
In plt.subplot()method, the numbering of subplots starts from the top-left element of the grid and moves rightward along each row. The numbering then continues to the next row from left to right. For example, suppose you have created a grid of nine subplots. The numbering would look like this:


Subplot 1	Subplot 2	Subplot 3
Subplot 4	Subplot 5	Subplot 6
Subplot 7	Subplot 8	Subplot 9


Suppose you need to access the subplot present in the second row and the second column (i.e., 'Subplot 5' in the table above). You can do so by using the following command:
plt.subplot(3, 3, 5)

In this segment, you learnt how to add multiple plots to the same graph and create an array of plots in the same picture.
 
However, as you saw in an earlier video, the picture was quite small in size and the information was not easily understandable. Let’s watch the next video to learn how to modify the size of the overall plot. 

In the video above, you learnt how to use the set_size_inches() function to modify the size of the plot. You also learnt how to combine both the two techniques, plotting on the same graph and plotting an array of subplots. With this, we have covered all the basics of subplots.

 

Also, please note that in the last video legend for the Latin America region has been fetched incorrectly due to variable name inconsistency ("LATM has been used for legend creation instead of LATAM")