# What is a Random Number?

Random means something that can not be predicted logically.


# Pseudo Random and True Random

Computers work on programs, and programs are definitive set of instructions. So it means there must be some algorithm to generate a random number as well.

If there is a program to generate random number it can be predicted, thus it is not truly random.

Random numbers generated through a generation algorithm are called pseudo random.

In order to generate a truly random number on our computers we need to get the random data from some outside source. This outside source is generally our keystrokes, mouse movements, data on network etc.


# 1. Generate Randmo

NumPy offers the random module to work with random numbers.

### a. randomm.randint

<pre>
from numpy import random
x = random.randint( 10 ,size=(3, 5))
</pre>


### b. random.random
<pre>
x = random.random(size = 100)
</pre>
### c. choice random number from specify array

<pre>
x = random.choice([3, 5, 7, 9])
x = random.choice([3, 5, 7, 9], size=(3, 5))
</pre>
*# It can alose use size_parameter*


# 2. Random Data Distribution

**What is Data Distribution?**
Data Distribution is a list of all possible values, and how often each value occurs.


**Random Distribution**
A random distribution is a set of random numbers that follow a certain probability density function.
`obability Density Function: A function that describes a continuous probability. i.e. probability of all values in an array`

We can generate random numbers based on defined probabilities using the choice() method of the random module.

The probability is set by a number between 0 and 1, where 0 means that the value will never occur and 1 means that the value will always occur.

<pre>
x = random.choice([3, 5, 7, 9], p=[0.1, 0.3, 0.6, 0.0], size=(100))
</pre>
*# You can set a probabliliteis parameter-p*

# 3. Random Permutations of Elements

A permutation refers to an arrangement of elements ( shuffle ). 

<pre>
arr = np.array([1, 2, 3, 4, 5])

random.shuffle(arr) # inplace
permutation_arr = random.permutation(arr) # non_inplace
</pre>

# 4. Distributions

Seaborn is a library that uses Matplotlib underneath to plot graphs. It will be used to visualize random distributions.

<pre>
sns.distplot(array)
plt.show()
</pre>


## 1) Gaussain(Normal) Distribution**

The Normal Distribution is one of the most important distributions.
Use the `random.normal(loc , scale , size)` method to get a Normal Data Distribution.

+ loc - (Mean) where the peak of the bell exists.
+ scale - (Standard Deviation = Root variance) how flat the graph distribution should be.
+ size - The shape of the returned array.


<pre>
arr = random.normal(170, 10, 250)

sns.distplot(arr) # hist=True
plt.show()

plt.hist(arr)
plt.show()

print(arr)
</pre>

## 2) Binomial Distribution

Binomial Distribution is a Discrete Distribution.

It describes the outcome of binary scenarios, e.g. toss of a coin, it will either be head or tails.

<pre>
random.binomial(n, p, size)
</pre>

+ n - number of trials.
+ p - probability of occurence of each trial (e.g. for toss of a coin 0.5 each).
+ size - The shape of the returned array.

<pre>
x = random.binomial(n=10, p=0.5, size=10)
</pre>
*# n = Trials of fliping coin , p = probablility of 1 -> 1-p = probablilty of 0 , return = number of 1*



<pre>
sns.distplot(random.binomial(n=10, p=0.5, size=1000), hist=True, kde=False)
plt.show()
</pre>



## 3) Poisson Distribution
Poisson Distribution is a Discrete Distribution.

it estimates how many times an event can happen in a specified time. e.g. If someone eats twice a day what is probability he will eat thrice?


+ lam - Expected Value ( rate or known number of occurences ) e.g. 2 for above problem.
+ size - The shape of the returned array.

<pre>
x = random.poisson(lam=2, size=10)
</pre>


[Binomial distribution is for discrete trials, whereas poisson distribution is for continuous trials in specified time.]()

## 4) Uniform Distribution

Used to describe probability where every event has equal chances of occuring.

E.g. Generation of random numbers.

+ a - lower bound - default 0 .0.
+ b - upper bound - default 1.0.
+ size - The shape of the returned array.


<pre>
x = random.uniform(size=1000)
y = random.rand(1000)

sns.distplot(x,label='uniform',kde=False)
sns.distplot(y,label='rand',kde=False)
</pre>

## 5) Logistic Distribution

Logistic Distribution is used to describe growth.

Used extensively in machine learning in logistic regression, neural networks etc.
+ loc - mean, where the peak is. Default 0.
+ scale - standard deviation, the flatness of distribution. Default 1.
+ size - The shape of the returned array.

[Both distributions are near identical, but logistic distribution has more area under the tails. ie. It representage more possibility of occurence of an events further away from mean.]()

<pre>
x = random.logistic(scale=1, size=1000)
y = random.normal(scale=1,size=1000)

sns.distplot(x,label='log',color='r')
sns.distplot(y,label='normal',color='b')

plt.show()
</pre>

## 6) Multinomial Distribution

Multinomial distribution is a generalization of binomial distribution.

It describes outcomes of multi-nomial scenarios unlike binomial where scenarios must be only one of two. e.g. Blood type of a population, dice roll outcome.

+ n - number of trials.
+ pvals - list of probabilties of outcomes (e.g. [1/6, 1/6, 1/6, 1/6, 1/6, 1/6] for dice roll).
+ size - The shape of the returned array.


<pre>
x = random.multinomial(n=6, pvals=[1/6, 1/6, 1/6, 1/6, 1/6, 1/6])
</pre>
*# outcome is array of number of each outcome*

## 7) Other supported Distribution
|Distribution|
|-|
|Exponential Distribution|
|Chi Square Distribution|
|Rayleigh Distribution|
|Pareto Distribution|
|Zipf Distribution|

# 5. NumPy ufunc

**What are ufuncs?**
ufuncs stands for "Universal Functions" and they are NumPy functions that operates on the ndarray object.

**Why use ufuncs?**
ufuncs are used to implement vectorization in NumPy which is way faster than iterating over elements.

**What is Vectorization?**
Converting iterative statements into a vector based operation is called vectorization.

<pre>
# Add the Elements of Two Lists!
x = [1, 2, 3, 4]
y = [4, 5, 6, 7]

z = np.add(x, y) ; print(z)
</pre>

## 1) How To Create Your Own ufunc
To create you own ufunc, you have to define a function, like you do with normal functions in Python, then you add it to your NumPy ufunc library with the frompyfunc() method.

<pre>
frompyfunc(function , inputs ,outputs)
</pre>

+ function - the name of the function.
+ inputs - the number of input arguments (arrays).
+ outputs - the number of output arrays.


<pre>
def myadd(x, y):
  return x+y

myadd = np.frompyfunc(myadd, 2, 1)

print(myadd([1, 2, 3, 4], [5, 6, 7, 8]))
</pre>

## 2) Simple Arithmetic
|ufuc|
|-|
|np.add|
|np.substract|
|np.multiply|
|np.divide|
|np.power|
|np.remainder|
|np.divmod|
|np.absolute|


## 3) Rounding Decimals

There are primarily five ways of rounding off decimals in NumPy:

|round off |method|description|
|-|-|-|
|truncation|np.trunc() |Remove the decimals|
|fix|np.fix() | |
|rounding|np.around(,decimal place)|function increments preceding digit or specified decimal by 1 if >=5 else do nothing.|
|floor| np.floor()| rounds off decimal to nearest lower integer.|
|ceil  | np.ceil()|  rounds off decimal to nearest upper integer.|

## 4) NumPy Logs

NumPy provides functions to perform log at the base 2, e and 10.

<pre>
arr = np.arange(1, 11)

print(np.log2(arr))
print(np.log(arr))
print(np.log10(arr))
</pre>

NumPy does not provide any function to take log at any base, so we can use the `frompyfunc()` function along with inbuilt function `math.log()` with two input parameters and one output parameter

<pre>
# 1
def my_rog(value , base):
    return math.log(value,base)
my_rog = np.frompyfunc(my_rog,2,1)

# 2
my_rog = np.frompyfunc(math.log,2,1)

arr = np.arange(1, 11)
print(my_rog(arr,3))
</pre>


## 5) Summations

summation happens over n elements.
<pre>
arr1 = np.array([1, 2, 3])
arr2 = np.array([1, 2, 3])

newarr = np.sum([arr1, arr2]) # 1+2+3+1+2+3
newarr = np.sum([arr1, arr2], axis=1)
</pre>

**Cummulative Sum**

Cummulative sum means partially adding the elements in array.

E.g. The partial sum of [1, 2, 3, 4] would be [1, 1+2, 1+2+3, 1+2+3+4] = [1, 3, 6, 10].

<pre>
newarr = np.cumsum(arr)
</pre>


## 6) Products

E.g. The Products of [1,2,3,4] would be 1\*2\*3\*4 = 24
<pre>

arr1 = np.array([1, 2, 3, 4])
arr2 = np.array([5, 6, 7, 8])

newarr = np.prod([arr1,arr2]) # 1*2*3*4*5*6*7*8
newarr = np.prod([arr1, arr2], axis=1)  
</pre>

**Cummulative Product**

E.g. The partial product of [1, 2, 3, 4] is [1, 1*2, 1*2*3, 1*2*3*4] = [1, 2, 6, 24]
<pre>
newarr = np.cumprod(arr)
</pre>

## 7) Differences

A discrete difference means subtracting two successive elements.

E.g. for [1, 2, 3, 4], the discrete difference would be [2-1, 3-2, 4-3] = [1, 1, 1]
<pre>

arr = np.array([10, 15, 25, 5])

newarr = np.diff(arr, n=2) # if you use n , we can perform this operation repeatedly

print(newarr)
</pre>


## 8) LCM and GCD

LCM : Lowest Common Multiple

GCD : Greatest Common Denominator
<pre>
x = np.lcm(4, 6)
y = np.gcd(9,12)
</pre>


To find the LCM or GCD of all values in an array, you can use the reduce() method.
<pre>
arr = np.array([20, 8, 32, 36, 16])
x = np.lcm.reduce(arr)
y = np.gcd.reduce(arr)
print(x,y)
</pre>


## 9) Trigonometric Functions

### a. sin()
NumPy provides the ufuncs sin(), cos() and tan() that take values [in radians]() and produce the corresponding sin, cos and tan values.


<pre>
arr = np.array([np.pi/2, np.pi/3, np.pi/4, np.pi/5])

x = np.sin(arr)

print(x)
</pre>

### b. Convert Degrees Into Radians

<pre>
arr = np.array([90, 180, 270, 360])
x = np.deg2rad(arr) 

arr = np.array([np.pi/2, np.pi, 1.5*np.pi, 2*np.pi])
x = np.rad2deg(arr)
</pre>

### c. arcsin()
NumPy provides ufuncs arcsin(), arccos() and arctan() that produce [radian values]() for corresponding sin, cos and tan values given.

<pre>
arr = np.array([1, -1, 0.1])
x = np.arcsin(arr)
</pre>

### d. Hypotenues

<pre>
base = 3
perp = 4

x = np.hypot(base, perp)
</pre>


## 10) Numpy Set
A set in mathematics is a collection of unique elements.

### a. Create sets in Numpy

<pre>
x = np.unique(arr)
</pre>

### b. Set operation

|Operation|method|
|-|-|
| Union| unionld()|
| Intersection| intersect1d()|
| Difference| setdiff1d()|
| Symmetric Difference| setxor1d()|

<pre>
arr1 = np.array([1, 2, 3, 4])
arr2 = np.array([3, 4, 5, 6])

newarr = np.union1d(arr1, arr2,assume_unique=True)
</pre>
*# If arr1 or arr2 is not unique ,The assume_unique=True cause an error.*
