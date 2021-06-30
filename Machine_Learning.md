# Machine Learning?

Machine Learning is making the computer learn from studying data and statistics.

Machine Learning is a step into the direction of artificial intelligence (AI).

Machine Learning is a program that analyses data and learns to predict the outcome.


# Data Types 

[To analyze data, it is important to know what type of data we are dealing with.]()

+ [**Numerical**]()  data are numbers, and can be split into two numerical categories:

   Discrete Data- numbers that are limited to integers. Example: The number of cars passing by.

   Continuous Data- numbers that are of infinite value. Example: The price of an item, or the size of an item

+ [**Categorical data**]() are values that cannot be measured up against each other. Example: a color value, or any yes/no values.

+ [**Ordinal data**]() are like categorical data, but can be measured up against each other. Example: school grades where A is better than B and so on.


# 1. Mean Median Mode

+ **Mean** - The average value
+ **Median** - The mid point value ( in sorted array )
+ **Mode** - The most common value

###### <Use Numpy_method and Scipy_method>
<pre>
numpy.mean(array)
numpy.median(array)
scipy.mode(array)
</pre>

# 2 . Standard Deviation?

## 1)  Standard Deviation
[Standard deviation is a number that describes how spread out the values are.]()

A low standard deviation means that most of the numbers are close to the mean (average) value.

A high standard deviation means that the values are spread out over a wider range.

###### Use Numpy_method
<pre>
x = numpy.std(array)
</pre>
## 2) Variance
[Variance is another number that indicates how spread out the values are.]()

In fact, if you take the square root of the variance, you get the standard deviation!
> √ Variance = Standard Deviation

[<To calculate the variance you have to do as follows>]()
1. For each value, find the difference from the mean:
2. For each difference, find the square value:
3. The variance is the average number of these squared differences
4. If you want Standard Deviation , take the square root of the variance,
 


###### <Use Numpy_method>
<pre>
x = numpy.var(array)
</pre>

