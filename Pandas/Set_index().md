



# 1. Set index in pandas DataFrame


In this article, we learn how to set the index of the Pandas DataFrame using existing columns or a list of labels. We cover all the cases of replacing the existing row labels or assign new ones.


DataFrame is the tabular structure in the Python pandas library. It represents each row and column by the label. Row label is called an index, whereas column label is called column index/header.

#### The `DataFrame.set_index()` funtion
This function is used to re-assign a row label using the existing column of the DataFrame
<pre>
DataFrame.set_index(keys, drop=True, append=False, inplace=False, verify_integrity=False)
</pre>

## 1) Set index using a column


<pre>
student_dict = {'Name': ['Joe', 'Nat', 'Harry'], 'Age': [20, 21, 19], 'Marks': [85.10, 77.80, 91.54]}

student_df = pd.DataFrame(student_dict)
print(student_df)

student_df = student_df.set_index('Name')
print(student_df)
</pre>



## 2)Set index using a Index object created by `pd.Index()`


<pre>
index = pd.Index(['s1', 's2', 's3'])
student_df = student_df.set_index(index)
print(student_df)
</pre>


## 3) Set index using multiple columns
You can access onlyg with first level-index

<pre>
student_df = student_df.set_index(['Name', 'Marks'])
print(student_df)
</pre>


*#Referencing df.column , you can have same result*

Set index by column number*
 
<pre>
student_df.set_index( list((student_df.columns[[0,1]])), inplace=True)
print(student_df)
</pre>


## 4) Set multi-index using a list and column


<pre>
index = pd.Index(['s1', 's2', 's3'])
student_df = student_df.set_index([index, 'Name'])
print(student_df)
</pre>

Of course , you can use two list 

## 5) Set index but keep column
If drop=True (default case), it deletes the column and uses it as an index
<pre>
student_df = student_df.set_index('Name', drop=False)
print(student_df)
</pre>


## 6) Set index by keeping old index
Using append parameter = TRUE (default False) , We can update the index by append to the existing index.

<pre>
student_df = student_df.set_index('Name', append=True)
print(student_df)
</pre>

## 7) Set index using a column with duplicates
Indexing with a column , The column may contain duplicate values.

By default , Set_index() method allow duplicate index .
But if verify_integrity=False , then it checks the new index for duplicates and throws ValueError.
*# Nevertheless, you can access it with duplicate index.*


<pre>
student_dict = {'Name':['Joe','Nat','Joe'], 'Age':[20,21,19], 'Marks':[85.10, 77.80, 91.54]}

student_df = student_df.set_index('Name', verify_integrity=True)
print(student_df)
</pre>





