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

# 2. Shape
## 1) marker
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


## 2) Linestyle


[you can also use ]()
1. linestyle(ls)
2. color(c)
3. linewidth(lw)

<pre>
plt.plot(ypoints, linestyle = 'dotted')
plt.plot(ypoints, color = 'r')
plt.plot(ypoints, linewidth = '20.5')
</pre>

## 3)  shortcut string notation 

You can use the shortcut string notation parameter to specify the marker.
[fmt(Format Strings) = marker|line|color]()

<pre>
plt.plot(xpoints, ypoints, 'o:r')
</pre>

## 4) Labels and Titles 

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

