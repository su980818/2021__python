# 4. Drop duplicates in pandas DataFrame
Data is gathered from various sources. It may not be in the proper form. It contains garbage values and duplicate data. Before analyzing a dataset, it must be clean and precise.

##### The `DataFrame.drop_duplicates()` function


<pre>
DataFrame.drop_duplicates(subset=None, keep='first', inplace=False, ignore_index=False)
</pre>

2. `subset` : This parameter is used to specify the columns that only need to be considered for identifying duplicates.
3. `keep` : Determines which duplicates (if any) to keep
4. `ignore_index` :  It is a boolean flag to indicate if row index should be reset after dropping duplicate rows.


## 1) Drop duplicates but keep first

The rows that contain the same values in all the columns then are identified as duplicates. If the row is duplicated then by default DataFrame.drop_duplicates() keeps the first occurrence of that row and drops all other duplicates of it.

<pre>
import pandas as pd

student_dict = {"name": ["Joe", "Nat", "Harry", "Joe", "Nat"], "age": [20, 21, 19, 20, 21],
                "marks": [85.10, 77.80, 91.54, 85.10, 77.80]}

# Create DataFrame from dict
student_df = pd.DataFrame(student_dict)
print(student_df)

# drop duplicate rows
student_df = student_df.drop_duplicates()

print(student_df)
</pre>


## 2) Drop duplicates from defined columns `subset`
By default, DataFrame.drop_duplicate() removes rows with the same values in all the columns. But, we can modify this behavior using a subset parameter.

For example, subset=[col1, col2] will remove the duplicate rows with the same values in specified columns **only** col1 and col2.

<pre>
student_df = student_df.drop_duplicates(subset=['age','marks'])
</pre>
*# name Nat and Sam is recognized as through even though their names are different





## 3) Drop duplicates but keep last `keep`
To keep only one occurrence of the duplicate row, we can use the keep parameter

+ first –Default behavior.
+ last – Drop duplicates except for the last occurrence of the duplicate row.
+ False – Drop all the rows which are duplicate.
<pre>
student_df = student_df.drop_duplicates(keep=False)
</pre>
## 4) Drop duplicates and reset the index `ignore_index`

When we drop the rows from DataFrame, by default, it keeps the original row index as is. But, if we need to reset the index of the resultant DataFrame, we can do that using the ignore_index parameter

You can also use reset_index() to do as ignore_index

+ If ignore_index=True, it reset the row labels of resultant DataFrame to 0, 1, …, n – 1.

<pre>
student_df = student_df.drop_duplicates(keep=False, ignore_index=True)
</pre>


