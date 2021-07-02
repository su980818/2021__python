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

###### < Use Numpy_method and Scipy_method >
<pre>
numpy.mean(array)
numpy.median(array)
scipy.mode(array)
</pre>

# 2. Standard Deviation?

## 1)  Standard Deviation
[Standard deviation is a number that describes how spread out the values are.]()

A low standard deviation means that most of the numbers are close to the mean (average) value.

A high standard deviation means that the values are spread out over a wider range.

###### < Use Numpy_method >
<pre>
x = numpy.std(array)
</pre>
## 2) Variance
[Variance is another number that indicates how spread out the values are.]()

In fact, if you take the square root of the variance, you get the standard deviation!
> √ Variance = Standard Deviation

[< To calculate the variance you have to do as follows >]()
1. For each value, find the difference from the mean:
2. For each difference, find the square value:
3. The variance is the average number of these squared differences
4. If you want Standard Deviation , take the square root of the variance,
 


###### < Use Numpy_method >
<pre>
x = numpy.var(array)
</pre>
   
   
# 3. What are Percentiles?
[Percentiles are used in statistics to give you a number that describes the value that a given percent of the values are lower than.]()
   

if the answer of 80 percentile is 20 value ,  then 80% of array are lower then 20_value.
<pre>
x = numpy.percentile(ages, 80) # percentile
</pre>
   
   
# 4. Normal Data Distribution
In probability theory this kind of data distribution is known as the normal data distribution, or the Gaussian data distribution, after the mathematician Carl Friedrich Gauss who came up with the formula of this data distribution.


###### < create a normal data distribution >
<pre>
x = np.random.normal(5.0, 1.0, 100000) # mean value is 5.0 , standard deviation is 1.0.
plt.hist(x,100) # draw a histogram with 100 bars.
</pre>
*# 
   


# 5. Linear Regression
#### Regression
[The term regression is used when you try to find the relationship between variables.]()

In Machine Learning, and in statistical modeling, that relationship is used to predict the outcome of future events.
#### Linear Regression
Linear regression uses the relationship between the data-points to draw a [straight line]() through all them.

This line can be used to predict future values.

###### < use scipy.linregress to get straight line value >
<pre>
import matplotlib.pyplot as plt
from scipy import stats

x = [5,7,8,7,2,17,2,9,4,11,12,9,6]
y = [99,86,87,88,111,86,103,87,94,78,77,85,86]

slope, intercept, r, p, std_err = stats.linregress(x, y)

def myfunc(x):
  return slope * x + intercept

mymodel = list(map(myfunc, x))

plt.scatter(x, y)
plt.plot(x, mymodel)
plt.show()
</pre>

#### R for Relationship
What it is mean the r in return value of linregress ?
[This relationship - the coefficient of correlation - is called r.]()


The r value ranges from -1 to 1, where 0 means no relationship, and 1 (and -1) means 100% related.


# 6. Polynomial Regression


[If your data points clearly will not fit a linear regression (a straight line through all data points), it might be ideal for polynomial regression.]()

<pre>
a0,a1,a2,a3= np.polyfit(x, y, 3)  # return Cubic_equation's Coefficient
cubic_fuc = np.poly1d((a0,a1,a2,a3)) # return cubic_fuc  using coefficent
</pre>

#### R-Squared

The r-squared value ranges from 0 to 1, where 0 means no relationship, and 1 means 100% related.
###### < use r2_score to get R-squared >
<pre>
r2_score( y , expected_y )
</pre>

# 7. Multiple Regression with linear
Multiple regression is like linear regression, but with more than one independent value, meaning that we try to predict a value based on two or more variables.

1. we have modules that will do the work for us
<pre>
import pandas
</pre>

2. The pandas module allows us to read csv files and return a DataFrame object
<pre>
df = pandas.read_csv("cars.csv")
</pre>

3. Then make a list of the independent values and call this variable X.

Put the dependent values in a variable called y.

<pre>
X = df[['Weight', 'Volume']]
y = df['CO2']
</pre>
*# It is common to name the list of independent values with a upper case X, and the list of dependent values with a lower case y.#
 
4. import sklearn 
<pre>
from sklearn import linear_model
regr = linear_model.LinearRegression()
regr.fit(X, y)
</pre>
  
  
5. predict
<pre>
predictedCO2 = regr.predict([[2300, 1300]])
</pre>
  
#### Coefficient
describe the weight of independence value
<pre>
import pandas
from sklearn import linear_model

df = pandas.read_csv("cars.csv")

X = df[['Weight', 'Volume']]
y = df['CO2']

regr = linear_model.LinearRegression()
regr.fit(X, y)

print(regr.coef_)
>> [weight_coef , volume_coef]
</pre>
   
# 8. Train/Test

Train/Test is a method to measure the accuracy of your model.

It is called Train/Test because you split the the data set into two sets: a training set and a testing set.

EX ) you can use a 80% for train set to create the model , 20% for test set to test the accurancy of model 


### a. Split into Train/Test

<pre>
train_x = x[:80]
train_y = y[:80]

test_x = x[80:]
test_y = y[80:]
</pre>
*# If you suffle in list , it should be better*

### b. create_model
### c. R2 
we use test_set to get R-squared

<pre>
r2 = r2_score(train_y, mymodel(train_x))
r2 = r2_score(test_y, mymodel(test_x))
</pre>


# 9. Decision Tree
https://www.w3schools.com/python/img_ml_decision_tree.png

