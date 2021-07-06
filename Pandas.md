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

## 1) [pd.Series()](): Create Series

<pre>
import pandas as pd

column = [1, 7, 2]

myvar = pd.Series(column, index = ["item1", "item2", "item3"])

print(myvar)
</pre>
*# If you not have index , The values are labeled with index number started with index 0*


Create a Series from dict

You can also use a key/value object, like a dictionary, when creating a Series.



<pre>
import pandas as pd

column = {"item1": 1, "item2": 7, "item3": 2}

myvar = pd.Series(column)

print(myvar)
</pre>


<pre>
import pandas as pd

calories = {"day1": 420, "day2": 380, "day3": 390}

myvar = pd.Series(calories, index = ["day1", "day2"])

print(myvar)
</pre>

# 2. DataFrames
Data sets in Pandas are usually multi-dimensional tables, called DataFrames.

Series is like a column, a DataFrame is the whole table.


## 1) [pd.DataFrame()]() : create_DataFrames
<pre>
import pandas as pd

data = {
  "calories": [420, 380, 390],
  "duration": [50, 40, 45]
}

df = pd.DataFrame(data)
print(df) 
</pre>

## 2) access to value 

### a. [df["column"] , df.column]() : access to column( Series )
Data Frame is tabel of Series  , you can use [] as used in two-dimensional arrays.

<pre>
df["col_name"]
</pre>



### b. [df.loc['label']]() : access to row ( item )
<pre>
#use a list of indexes:
print(df.loc[[0, 1]])
</pre>
###### < Using index , reference to the name index >
<pre>
df = pd.DataFrame(data, index = ["day1", "day2", "day3"])
print(df.loc["day2"])
</pre>

## 3) [pd.read_csv("name")]() : Read CSV Files

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

## 4) [pd.read_Json("name")]() :Read JSON FILE

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
df.dropna(subset=['Date'], inplace = True)
</pre>
*# If you want to change the original DataFrame, use the inplace = True argument:*

*# If you want to remove a NULL in specified column , use the subset argument*


#### Solution (2) : Replace Empty specified Values [fillna( value )]

replaces all empty cells in the whole Data Frame.
<pre>
df.fillna(130, inplace = True)
</pre>


To only replace empty values for one column, specify the column name for the DataFrame:

<pre>
df["Calories"].fillna(130, inplace = True)
</pre>

#### Solution (3) : Replace Using Mean, Median, or Mode

<pre>
x1 = df["Calories"].mean()
x2 = df["Calories"].median()
x3 = df["Calories"].mode()[0] # mode = the value that appears most frequently.

df["Calories"].fillna(  x    ,inplace=True )
</pre>

### b. Data of Wrong Format

#### Solution (1) : Remove Rows [dropna()]()
#### Solution (2) : Convert Into a Correct Format [to_datetime()]()
Fix a wrong format with another correct format , but empty value is remaning as it is
<pre>
df['Date'] = pd.to_datetime(df['Date'])
</pre>

### c.  Fixing Wrong Data
"Wrong data" does not have to be "empty cells" or "wrong format", it can just be wrong, like if someone registered "199" instead of "1.99".




#### Solution (1) : Replacing Values
<pre>
df.loc[7, 'Duration'] = 45 # df.loc[7]['Duration'] = 45 not operate
</pre>

If you have som boundaries for legal values , and replace any. values that are outside of the boundaries.

<pre>
import pandas as pd

df = pd.read_csv('data.csv')
for index in df.index:
    if(df.loc[index]["Duration"] > 120):
        df.loc[index ,"Duration"] = 120 # or df.drop(index,inplace=True
</pre>


### d. Removing Duplicates

#### Solution (1) : duplicated() , drop_duplicates()
Simply delete all duplicate row

# 3. Data Correlations

The corr() method calculates the relationship between each column in your data set

<pre>
df.corr()
            Duration     Pulse  Maxpulse  Calories
  Duration  1.000000 -0.155408  0.009403  0.922721
  Pulse    -0.155408  1.000000  0.786535  0.025120
  Maxpulse  0.009403  0.786535  1.000000  0.203814
  Calories  0.922721  0.025120  0.203814  1.000000
</pre>

