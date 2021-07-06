# What is Pandas?
Pandas is a Python library used for working with data sets.

It has functions for analyzing, cleaning, exploring, and manipulating data.

The name "Pandas" has a reference to both "Panel Data", and "Python Data Analysis" and was created by Wes McKinney in 2008.

# Why Use Pandas?
Pandas allows us to analyze big data and make conclusions based on statistical theories.

Pandas can clean messy data sets, and make them readable and relevant.

Relevant data is very important in data science.

# 1. Series



A Pandas Series is like a column in a table.

It is a one-dimensional array holding data of any type. 

Label = first column

## 1) Create Series

<pre>
import pandas as pd

a = [1, 7, 2]

myvar = pd.Series(a, index = ["x", "y", "z"])

print(myvar)
</pre>
*# If you not have index , The values are labeled with index number started with index 0*



You can also use a key/value object, like a dictionary, when creating a Series.


<pre>
import pandas as pd

calories = {"x": 1, "y": 7, "z": 2}

myvar = pd.Series(calories)

print(myvar)
</pre>

Create a Series from dict

<pre>
import pandas as pd

calories = {"day1": 420, "day2": 380, "day3": 390}

myvar = pd.Series(calories, index = ["day1", "day2"])

print(myvar)
</pre>

# 2. DataFrames
Data sets in Pandas are usually multi-dimensional tables, called DataFrames.

Series is like a column, a DataFrame is the whole table.


## 1) create_DataFrames
<pre>
import pandas as pd

data = {
  "calories": [420, 380, 390],
  "duration": [50, 40, 45]
}

df = pd.DataFrame(data)
print(df) 
</pre>

## 2) Return a Row ( one data )

<pre>
#use a list of indexes:
print(df.loc[[0, 1]])
</pre>
###### < Using index , reference to the name index >
<pre>
df = pd.DataFrame(data, index = ["day1", "day2", "day3"])
print(df.loc["day2"])
</pre>

## 3) Read CSV Files

#### CSV FILES ?
A simple way to store big data sets is to use CSV files (comma separated files).

CSV files contains plain text and is a well know format that can be read by everyone including Pandas.


<pre>
import pandas as pd

df = pd.read_csv('data.csv')

print(df) 
print(df.to_string()) # if you want string output
</pre>
*# By default, when you print a DataFrame, you will only get the first 5 rows, and the last 5 rows:*

## 4) Read JSON FILE

JSON is plain text, but has the format of an object, and is well known in the world of programming, including Pandas.
[JSON objects have the same format as Python dictionaries.]()

## 5) Viewing the Data Overview

#### a. [head(num)]() , [tail()]()
Get a quick overview by printing the first num rows ,  Get a quick overview by printing the last num rows

#### b. [info()]()
The DataFrames object has a method called info(), that gives you more information about the data set.

## 6) Data Cleaning
Data cleaning means fixing bad data in your data set.

Bad data could be:
+ Empty cells 
+ Data in wrong format
+ Wrong data
+ Duplicates

### a. Empty cells
Empty cells can potentially give you a wrong result when you analyze data.

#### Solution (1) : Remove Rows [dropna()]()

Remove all rows with NULL values
<pre>
new_df = df.dropna()
</pre>
*# If you want to change the original DataFrame, use the inplace = True argument:*


#### Solution (2) : Replace Empty Values [fillna( value )]

replaces all empty cells in the whole Data Frame.
<pre>
df.fillna(130, inplace = True)
</pre>










