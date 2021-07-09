# 2. Reset index in pandas DataFrame


#### The `DataFrame.reset_index()` function
[After dropping and filtering the rows, this function is used to reset the index of the resultant Python DataFrame. ]()


<pre>
DataFrame.reset_index(level=None, drop=False, inplace=False, col_level=0, col_fill='')
</pre>

## 1) Reset index to starts at 0

<pre>
student_dict = {'Name': ['Joe', 'Nat', np.NaN, 'Harry'], 'Age': [20, 21, np.NaN, 19],
                'Marks': [85.10, 77.80, np.NaN, 91.54]}

# create DataFrame from dict
student_df = pd.DataFrame(student_dict, index=['s1', 's2', 's3', 's4'])
print(student_df)

# drop NA
student_df = student_df.dropna()
print(student_df)

# reset index
student_df = student_df.reset_index()
print(student_df)
</pre>
*# You can see prior_index changed to column*


## 2) Reset index without new column 'drop'
If we do not want to add the new column as above case, we can use the drop parameter.(of simply del df['column'] )


If `drop=True` then it does not add the new column of the current row index in the DataFrame.
<pre>
student_df = student_df.reset_index(drop=True)
print(student_df)
</pre>


## 3) Reset index to the range of numbers
When we want to reset the index of the DataFrame such that the new index should start with 1, you simpy
<pre>
student_df.index = student_df.index + 1 
</pre>

As you can see , index object automatically iterablely operate.



AND ,If you want to assign the Identity number to each student starting from 101
'pd.RangeIndex'
<pre>
student_df.index = pd.RangeIndex(start=101, stop=101+len(student_df), step=1)
student_df.index += 100
</pre>


# 4) Change column name or index`DataFrame.rename()'

If we change a name of column
<pre>
student_df.rename(columns={'index':'ID'},inplace=True)
</pre>

OR If we chang a name of specific index
<pre>
student_df.rename(index={'index_name':'new_index_name'},inplace=True)
</pre>


## 5) Reset multi-level index

![image](https://user-images.githubusercontent.com/78835559/124863933-f75bcb80-dff2-11eb-8d40-d1e866598a31.png)

How to create such DataFrame

<pre>

index = pd.MultiIndex.from_tuples([('Standard 1', 'Class A'),
                                   ('Standard 1', 'Class B'),
                                   ('Standard 2', 'Class A'),
                                   ('Standard 2', 'Class B')],
                                  names=['Standard', 'Class'])
columns = pd.MultiIndex.from_tuples([('Name', 'Surname'),
                                     ('Marks', 'Percentage')])

# create multi-index dataframe
student_df = pd.DataFrame([('Joe', 91.56),
                           ('Nat', 87.90),
                           ('Harry', 70.10),
                           ('Sam', 65.48)],
                          index=index, columns=columns)
print(student_df)
</pre>

NOW we need to see how reset_method operate.

<pre>
student_df = student_df.reset_index()
print(student_df)
</pre>
By default, it reset the index of all the levels and add the new range of indexes in the DataFrame.


## 6) Reset index by level `col_level`

 If we want to reset the index of the specific level only then, we can use the level parameter of the DataFrame.reset_index() function.




<pre>
student_df = student_df.reset_index(level='Standard', col_level=1)
print(student_df)
</pre>

## 7) Reset index and name other level 'col_fill`
As we see in the above section, in multi-level DataFrame,   
we have added the ‘Standard’ index at level 1. If there is a case when we need to rename the other level, we need to use the col_fill parameter of DataFrame.

<pre>
student_df = student_df.reset_index(level='Standard', col_level=1, col_fill='New_Header')
print(student_df)
</pre>


