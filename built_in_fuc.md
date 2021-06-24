# BUILT IN FUC 
많이 쓰이는 빌트인 펑션을 다루어보자. 

1. abs
2. all
3. any
4. chr
5. dir
6. divmod
7. enumerate
8. eval
9. filter
10. hex
11. id
12. input
13. int
14. isinstance
15. len
16. list
17. map
18. max
19. min
20. oct
21. open
22. ord
23. pow
24. range
25. round
26. sorted
27. str
28. sum
29. tuple
30. type
31. zip


# 1. Abs
Abs(value) = |value|

# 2. all
all(array)
Array 내부에 0(false)가 하나도 없으면 True반환

# 3. Any
Any(array)
array 내부에 True가 하나라도 있으면 True반환\

# 4. Chr
Chr(unicode) 출력

# 5. dir
Dir(variable) = list
Variable( obj ) 가 가지고있는 fun , variable 를 list에 저장

# 6. Divmod
Divmod( dividend, divisor) = ( quotient , remainder )

# 7. Enumerate
Enumerate( array ) = <class 'enumerate’> 
array 에 Index 번호가 매겨진 enumerate class 반환

<pre>
0 body
1 foo
2 bar
</pre>

# 8. Eval

Eval(string)
string이 실행가능한 command라면 실행

# 9. Filter
Filter( fun_name , array ) = list
fuc_name() 함수에 array를 차례차례 입력하여 반환값이 참인경우만 list에 저장

# 10. Hex
hex(num) = hexadecimal

# 11. Id
id(variable) = address

# 12. input
input() = string

# 13. Int
Int( other_data_type_Input , input’s_base  ) = int_type

# 14. isinstance
Isinstance( obj , class) = bool
obj( instance ) 의 자료형이 class 와 같으면 True

# 15. Len
Len( array ) = int 
array의 요소의 개수 

# 16. list
list(array) = list

# 17. Map


map(fuc, array) = result_array

fuc에 array를 차례차례 넣은 결과 값을 반환


<pre>
def two_times(x): 
     return x*2

list(map(two_times, [1, 2, 3, 4]))
[2, 4, 6, 8]
</pre>

# 18. max
max(array) = max_value

# 19. min
min(array) = min_value

# 20. Oct
Oct(int) = “0o “

# 21 Open
Open(file_name , “mode”)  = file_class

# 22. Ord
Ord(char) = unicode

# 23. pow
pow(a,b) = a^b

# 24. range
range([start,] stop [,step] ) = list

# 25 .round 
Round(value [,  digits]) = int

# 26. Sorted
Sorted(array) = list 
list.sort() : list를 솔트해서 list에 바로 저장

# 27. Str
str(input) = string

# 28. sum
Sum( list or tuple) = sum

# 29. Tuple
tuple(array) = tuple

# 30 Type
type(variable) = type_class

# 31 zip
Zip(array1 , array2 , …) = array of tuple 

<pre>
list(zip([1, 2, 3], [4, 5, 6]))
[(1, 4), (2, 5), (3, 6)]
>>> list(zip([1, 2, 3], [4, 5, 6], [7, 8, 9]))
[(1, 4, 7), (2, 5, 8), (3, 6, 9)]
</pre>


