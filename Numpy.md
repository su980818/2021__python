# What is NumPy?

NumPy is a Python library used for working with arrays.

It also has functions for working in domain of linear algebra, fourier transform, and matrices.

[NumPy stands for Numerical Python.]()


# Why Use NumPy?
In Python we have lists that serve the purpose of arrays, but they are slow to process.

NumPy aims to provide an array object that is up to 50x faster than traditional Python lists.

The array object in NumPy is called ndarray, it provides a lot of supporting functions that make working with ndarray very easy.

Arrays are very frequently used in data science, where speed and resources are very important.

# Why is NumPy Faster Than Lists?
NumPy arrays are stored at one continuous place in memory unlike lists, so processes can access and manipulate them very efficiently.

This behavior is called locality of reference in computer science.

This is the main reason why NumPy is faster than lists. Also it is optimized to work with latest CPU architectures.

# 1. Create a NumPy ndarray Object [np.array()]()
NumPy is used to work with arrays. The array object in NumPy is called ndarray.
<pre>
arr = np.array([1, 2, 3, 4, 5])
</pre>

## 1) Check Number of Dimensions
<pre>
ndarray.ndim
</pre>

## 2) Higher Dimensional Arrays
When the array is created, you can define the number of dimensions by using the ndmin argument.
<pre>
arr = np.array([1, 2, 3, 4], ndmin=5)
print(arr)
</pre>



# 2. NumPy Array Indexing

<pre>
arr = np.array([[1,2,3,4,5], [6,7,8,9,10]])

print('2nd element on 1st dim: ', arr[0, 1])
</pre>

# 3. NumPy Slicing
<pre>
print(arr[1, 1:4])
print(arr[0:2, 2])
</pre>

# 4. NumPy Data Types

**Default Python data type**  
+ strings - used to represent text data, the text is given under quote marks. e.g. "ABCD"
+ integer - used to represent integer numbers. e.g. -1, -2, -3
+ float - used to represent real numbers. e.g. 1.2, 42.42
+ boolean - used to represent True or False.
+ complex - used to represent complex numbers. e.g. 1.0 + 2.0j, 1.5 + 2.5j

**Extra data type** 
NumPy has some extra data types, and refer to data types with one character, like i for integers, u for unsigned integers etc.

+ i - integer
+ b - boolean
+ u - unsigned integer
+ f - float
+ c - complex float
+ m - timedelta
+ M - datetime
+ O - object
+ S - string
+ U - unicode string
+ V - fixed chunk of memory for other type ( void )


## 1) Checking the Data Type of an Array
<pre>
arr.dtype
</pre>

## 2) Creating Arrays With a Defined Data Type
<pre>
arr = np.array([1, 2, 3, 4], dtype='S')
</pre>

### a. Creating Arrays With a Defined Size
 For i, u, f, S and U we can define size as well. with number of byte append to end
<pre>
arr = np.array([1, 2, 3, 4], dtype='i4')
</pre>
*# 4byte = 32bit int*
### b. If a value can not be converted
ValueError: In Python ValueError is raised when the type of passed argument to a function is unexpected/incorrect.

<pre>
import numpy as np

arr = np.array(['a', '2', '3'], dtype='i')
</pre>

### c. Converting Data Type on Existing Arrays

<pre>
arr = np.array([1.1, 2.1, 3.1])

newarr = arr.astype('i')
</pre>





# 5. NumPy Array Copy vs View
The main difference between a copy and a view of an array is that the copy is a new array, and the view is just a view of the original array.
<pre>
arr = np.array([1,2,3,4])
arr_copy = arr.copy()
arr_view = arr.view()
</pre>


## Check if Array Owns it's Data ( if is copy or view )
As mentioned above, copies owns the data, and views does not own the data, but how can we check this?

Every NumPy array has the attribute base that returns None if the array owns the data.

<pre>
arr = np.array([1, 2, 3, 4, 5])

arr_copy = arr.copy()
arr_view = arr.view()

print(arr.base)
print(arr_copy.base)
print(arr_view.base)
</pre>

# 6. Numpy Array Shape

The shape of an array is the number of elements in each dimension.

## 1) Get a shape
<pre>
arr = np.array([[1, 2, 3, 4], [5, 6, 7, 8]])
print(arr.shape)
</pre>

Shape value that returns a tuple with each index having the number of corresponding elements.



## 2) Reshaping arrays

Reshaping means changing the shape of an array.

By reshaping we can add or remove dimensions or change number of elements in each dimension.

<pre>
arr = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12])

newarr = arr.reshape(4, 3)

print(newarr)
</pre>

[As long as the elements required for reshaping are equal in both shapes , It can be reshaping ]()

### a. [Of course Does reshape method return a copy?. NO]()
<pre>
arr = np.array([1, 2, 3, 4, 5, 6, 7, 8])

print(arr.reshape(2, 4).base)
</pre>

### b. Unknown Dimension

Pass -1 as the value, and NumPy will calculate this number for you.
<pre>
arr = np.array([1, 2, 3, 4, 5, 6, 7, 8])

newarr = arr.reshape(2, 2, -1)
</pre>

### c. Flattening the arrays

Flattening array means converting a multidimensional array into a 1D array.

<pre>
arr = np.array([[1, 2, 3], [4, 5, 6]])

newarr = arr.reshape(-1)

print(newarr)
</pre>

# 7. NumPy Array Iterating

The function nditer() is a helping function that can be used from very basic to very advanced iterations. It solves some basic issues which we face in iteration, lets go through it with examples.

<pre>
arr = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]]])

for x in np.nditer(arr):
  print(x)
</pre>









