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
</pre>

*# By default, the plot() function draws a line from point to point.

<pre>
plt.plot([1,2] , [2,4])
plt.show()
</pre>

### a. marker
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


You can use the shortcut string notation parameter to specify the marker.
[fmt(Format Strings) = marker|line|color]()

<pre>
plt.plot(xpoints, ypoints, 'o:r')
</pre>



### b. Linestyle

[add a plot parameter of linestyle(ls) ]()
<pre>
plt.plot(ypoints, linestyle = 'dotted')
</pre>

[you can set color of line with color(c)]()
<pre>
plt.plot(ypoints, color = 'r')
</pre>

[you can use the argument linewidth(lw) to change the width of line]()
<pre>
plt.plot(ypoints, linewidth = '20.5')
</pre>


