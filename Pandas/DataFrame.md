

# Pandas DataFrame


In this lesson, you will learn pandas DataFrame. It covers the basics of DataFrame, its attributes, functions, and how to use DataFrame for Data Analysis.




# 1. What is DataFrame in Pandas?

Dataframe is a tabular(rows, columns) representation of data. It is a two-dimensional data structure with potentially heterogeneous data.

Dataframe is a size-mutable structure that means data can be added or deleted from it, unlike data series, which does not allow operations that change its size.


![image](https://user-images.githubusercontent.com/78835559/125009194-fe401800-e09e-11eb-9ca3-0cd102decbc4.png)
 
 
#### DataFrame constructor

<pre>
pandas.DataFrame(data=None, index=None, columns=None, dtype=None, copy=False)
</pre>



+ data: It takes input dict, list, set, ndarray, Iterable, or DataFrame. If the input is not provided, then it creates an empty DataFrame. The resultant column order follows the insertion order.
+ index: (Optional) It takes the list of row index for the DataFrame. The default value is a range of integers 0, 1,…n.
+ columns : (Optional) It takes the list of columns for the DataFrame. The default value is a range of integers 0, 1,…n.
+ dtype : (Optional) By default, It infers the data type from the data, but this option applies any specific data type to the whole DataFrame.
+ copy : (Optional) Copy data from inputs. Boolean, Default False. Only affects DataFrame or 2d array-like inputs






# 2 .DataFrame Options
When DataFrame is vast, and we can not display the whole data while printing. In that case, we need to change how DataFrame gets display on the console using the print function. For that, pandas have provided many options and functions to customize the presentation of the DataFrame.


##### `pd.options` or `pd.set_option()` change the setting number of row printed
<pre>
pd.options.display.max_rows = 20
pd.set_option("display.min_rows", 5)
</pre>
*# Both can be used interchangealby*

# 3. DataFrame metadata




Sometimes we need to get metadata of the DataFrame and not the content inside it. Such metadata information is useful to understand the DataFrame as it gives more details about the DataFrame that we need to process.


## 1) Metadata info of DataFrame `DataFrame.info()`

<pre>
student_df.info()
</pre>


## 2) Get the statistics of DataFrame `DataFrame.describe()`

 This function gives mathematical statistics of the data in DataFrame. But, it applies to the columns that contain numeric values.
 <pre>
 print(student_df.describe())
 </pre>
 


## 3) DataFrame Attributes

DataFrame has provided many built-in attributes. [Attributes do not modify the underlying data, unlike functions](), but it is used to get more details about the DataFrame.
|Attribute|	Description|
|-|-|
|DataFrame.index	|It gives the Range of the row index|
|DataFrame.columns	|It gives a list of column labels|
|DataFrame.dtypes|	It gives column names and their data type|
|DataFrame.values	|It gives all the list of rows list in DataFrame|
|DataFrame.empty	|It is used to check if the DataFrame is empty|
|DataFrame.size|	It gives a total number of values in DataFrame|
|DataFrame.shape	|It a number of rows and columns in DataFrame|




# 4. DataFrame selection

While dealing with the vast data in DataFrame, a data analyst always needs to select a particular row or column for the analysi


Following are the functions that help in selecting the subset of the DataFrame.

|Function	|Description|
|-|-|
|DataFrame.head(n)	|It is used to select top ‘n’ rows in DataFrame.|
|DataFrame.tail(n)	|It is used to select bottom ‘n’ rows in DataFrame.|
|DataFrame.at[row,col]	|It is used to get and set the particular value of DataFrame using row and column labels.|
|DataFrame.iat[row,col]|	It is used to get and set the particular value of DataFrame using row and column index positions.|
|DataFrame.get(key) == df[key]	|It is used to get the value of a key in DataFrame where Key is the column name.|
|DataFrame.loc()	|It is used to select a group of data based on the row and column labels. It is used for slicing and filtering of the DataFrame.|
|DataFrame.iloc()	|It is used to select a group of data based on the row and column index position. Use it for slicing and filtering the DataFrame.|

















e



































































