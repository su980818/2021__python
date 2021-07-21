# What is Matplotlib?

Matplotlib is a low level graph plotting library in python that serves as a visualization utility.

*# you can check a virson of matplotlib using a matplotlib.__version__*

# matplotlib.pyplot

Most of the Matplotlib utilities lies under the pyplot submodule, and are usually imported under the plt alias:

<pre>import matplotlib.pyplot as plt</pre>

# 1. Plotting

<pre>
plt.plot(x_points , y_poinets)
plt.show()

plt.plot(x_points_1 ,y_points_1 , x_points_2 ,y_points_2)
plt.show()
</pre>

*# By default, the plot() function draws a line from point to point.*

<pre>
plt.plot([1,2] , [2,4])
plt.show()
</pre>

## 1) Shape
### a) marker
if you want plotting without line?

[add a plot parameter of marker(ms) ]()
<pre>
plt.plot(xpoints, ypoints, marker = 'o')
</pre>

[you can also use ]()
1. ms(marker size)
2. mec(marker edge color)
3. mfc(marker face color)


[you can set color with]()
1. colorname (like 'hotpink' )
2. hexadecimal color values( like #4CAF50 )


### b) Linestyle


[you can also use ]()
1. linestyle(ls)
2. color(c)
3. linewidth(lw)

<pre>
plt.plot(ypoints, linestyle = 'dotted')
plt.plot(ypoints, color = 'r')
plt.plot(ypoints, linewidth = '20.5')
</pre>

### c)  shortcut string notation 

You can use the shortcut string notation parameter to specify the marker.
[fmt(Format Strings) = marker|line|color]()

<pre>
plt.plot(xpoints, ypoints, 'o:r')
</pre>

### d) Labels and Titles 

 you can use the xlabel() and ylabel() functions to set a label for the x- and y-axis. and  you can you the title() method to set a title
 <pre>
plt.xlabel("x_axis)
plt.ylabel("y_axis")
plt.title("title")
 </pre>
 
if you want particular pont , use fontdict parameter in method 

<pre>
font1 = {'family':'serif','color':'blue','size':20}
font2 = {'family':'serif','color':'darkred','size':15}

plt.title("TITLE", fontdict = font1)
</pre>
*# you have to put dictinary parameter*

position the Title using loc parameter

<pre>
plt.title("TITLE", loc = 'left') # right , center
</pre>


### e) Grid
you can use the grid() function to add grid lines to the plot.


<pre>
plt.grid(color = 'green', linestyle = '--', linewidth = 0.5 , axis = 'both')
plt.show()
</pre>
*# you cas also use parameter learned at linestyles above*

*# with axis, you can specify which grid lines to display*

### f) Tick Display

<pre>
plt.xticks(x_array) # or any array can be
</pre>

## 2) subplots
With the subplots() function you can draw multiple plots in one figure:

<pre>
plt.subplots(row , columns , index_of_position)
</pre>


<pre>
#plot 1

plt.subplot(1, 2, 1)
plt.plot(x,y)

#plot 2

plt.subplot(1, 2, 2)
plt.plot(x,y)

plt.show()
</pre>


### a. Super Title
you can add a super title
<pre>
#plot 1:
plt.subplot(1, 2, 1)
plt.plot(x,y)
plt.title("plot1 title")

#plot 2:
plt.subplot(1, 2, 2)
plt.plot(x,y)
plt.title("plot2 title")

plt.suptitle("MY SHOP")
plt.show()
</pre>

# 2. Scatter Plots
you can use the scatter() function to draw a scatter plot.

[Use scatter() instead of plot()]()

### a. color
you also use color argument.
Moreover can even set a specific color for each dot by using a array of colors


<pre>
color = ['r','g','b']
plt.scatter( range(3) , range(3) ,c = color)
plt.show()
</pre>


### What is ColorMap ?
A colormap is like a list of colors, where each color has a value that ranges from 0 to 100 ( accoroding to value , range changing! )

[using a colormap , you automatically set a color according to color_value]()

<pre>
plt.scatter(np.arange(0,1,0.1), np.arange(0,1,0.1), c = np.arange(0,1,0.1), cmap='viridis')
plt.colorbar()
plt.show()
</pre>
*# using color bar , you can see color of value*

### b. size
You can change the size of the dots with the s argument.
Like colors , array is ok.

<pre>
plt.scatter(x, y, s=[1,2,100])
</pre>

### c. transparency

You can adjust the transparency of the dots with the alpha argument.
Of course , array is ok


<pre>
plt.scatter(x, y, alpha=0.5)
</pre>

# 3. Bars


With Pyplot, you can use the bar() function to draw bar graphs:

In bar , x_axis is categories and y_axis is value

<pre>
plt.bar(["a","b"],[3,2])
plt.show()
</pre>

Simply add a h at the end than you can use Horizontal Bar

<pre>
plt.barh(x, y)
plt.show()
</pre>

### a. colors 

### b. Width and Height
The bar() takes the keyword argument width to set the width of the bars
In horizontal bar, use Height argument

<pre>
lt.bar(x, y, width = 0.1)
plt.show()
</pre>

# 4. Histogram

[A histogram is a graph showing frequency distributions.]()

[It is a graph showing the number of observations within each given interval.]()

In Matplotlib, we use the hist() function to create histograms.
<pre>
x = np.random.normal(170, 10, 250)
plt.hist(x)
plt.show() 
</pre>

# 5. Pie Charts
<pre>
y = np.array([35, 25, 25, 15])

plt.pie(y, labels = [ a, b, c, d] ,startangle = 90)
plt.show() 
</pre>

# 6. Save
If you want to capture plot with png_format,

<pre>
plt.savefig('pass')
plt.show()
</pre>
