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


### b. random.rand
<pre>
x = random.rand(size = 100)
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

+ n - number of possible outcomes (e.g. 6 for dice roll).
+ pvals - list of probabilties of outcomes (e.g. [1/6, 1/6, 1/6, 1/6, 1/6, 1/6] for dice roll).
+ size - The shape of the returned array.


<pre>
x = random.multinomial(n=6, pvals=[1/6, 1/6, 1/6, 1/6, 1/6, 1/6])
</pre>


