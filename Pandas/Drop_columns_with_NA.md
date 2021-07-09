# Drop columns with NA in pandas DataFrame

# The `DataFrame.dropna()` function

We can use this pandas function to remove columns from the DataFrame with values Not Available(NA).

<pre>
DataFrame.dropna(axis=0, how='any', thresh=None, subset=None, inplace=False)
</pre>

# 1) Drop column where at least one value is missing 'axis'
If we need to drop such columns that contain NA, we can use the axis=column

<pre>
student_dict = {"name": ["Joe", "Sam", "Harry"], "age": [20, 21, 19], "marks": [85.10, np.nan, 91.54]}

# Create DataFrame from dict
student_df = pd.DataFrame(student_dict)
print(student_df)

# drop column with NaN
student_df = student_df.dropna(axis='columns')

print(student_df)
</pre>

# 2) Drop column where only all values are missing 'how'

+ If how='all', it drops the column where all the values are NA.
+ By default, how='any', it removes the columns where one or more values are NA.


<pre>
student_df = student_df.dropna(axis='columns', how='all')
</pre>



# 3) Drop column with the number of available 'thresh'
We need to use the parameter thresh=no_of_nonNA_values of DataFrame.drop() to specify the number of values that must be available in the column. Else, drop the column.

<pre>
student_df = student_df.dropna(axis='columns', thresh=3)
</pre>

# 4) Drop NA from defined rows 'subset=[rows]`

Suppose we are interested in dropping the column only if it contains null values in some particular rows.

In such a case, we can use subset=[row1, row2] of DataFrame.dropna() to specify the list of row indexes so that it drops the columns containing missing values in these rows only, i.e., row1 and row2 in this case.








