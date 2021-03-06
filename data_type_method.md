

# 1. Python String Methods
#### Note: All string methods returns new values. They do not change the original string.

### [1) Convert case]()
|Method	|Description|
|-|-|
|capitalize() |	Converts the first character to upper case|
|lower()|	Converts a string into lower case|
|upper()	|Converts a string into upper case|
|casefold()	|Converts string into lower case , more powerful than upper() |
|swapcase()	|Swaps cases, lower case becomes upper case and vice versa|
|title()	|Converts the first character of each word to upper case|




### [2) Return integer]()
|Method	|Description|
|-|-|
|count()|	Returns the number of times a specified value occurs in a string|
|find()	| Searches the string for a specified value and returns the position of where it was found,if you not find -1|
|rfind()	|Searches the string for a specified value and returns the last position of where it was found|
|index()|	Searches the string for a specified value and returns the position of where it was found ,if you not find return ERROR |
|rindex()|	Searches the string for a specified value and returns the last position of where it was found|



### [3) Return list ]()
|Method	|Description|
|-|-|
|split(sep, maxsplit)	|Splits the string at the specified separator, and returns a list|
|rsplit(sep, maxsplit)	|Splits the string at the specified separator, and returns a list (starting from the right)|
|splitlines()	|Splits the string at line breaks and returns a list|


### [4) Modify string]()
|Method	|Description|
|-|-|
|replace()|	Returns a string where a specified value is replaced with a specified value|
|expandtabs()	|Sets the tab size of the string|
|ljust()|	Returns a left justified version of the string|
|rjust()|	Returns a right justified version of the string|
|strip()|	Returns a trimmed version of the string|
|lstrip()|	Returns a left trim version of the string|
|rstrip()|	Returns a right trim version of the string|
|zfill()|	Fills the string with a specified number of 0 values at the beginning|
|join()	| Joins the elements of an iterable to the end of the string|
|maketrans()|	Returns a translation table to be used in translations|
|translate()	|Returns a translated string|



### [5) Return bool_value]()
|Method	|Description|
|-|-|
|endswith()|	Returns true if the string ends with the specified value|
|startswith()	|Returns true if the string starts with the specified value|
|isalnum()	|Returns True if all characters in the string are alphanumeric|
|isalpha()|	Returns True if all characters in the string are in the alphabet|
|isdecimal()|	Returns True if all characters in the string are decimals|
|isdigit()|	Returns True if all characters in the string are digits|
|isidentifier()|	Returns True if the string is an identifier|
|islower()|	Returns True if all characters in the string are lower case|
|isnumeric()|	Returns True if all characters in the string are numeric|
|isprintable()|	Returns True if all characters in the string are printable|
|isspace()	|Returns True if all characters in the string are whitespaces|
|istitle()|	Returns True if the string follows the rules of a title|
|isupper()|	Returns True if all characters in the string are upper case|

# 2. Python List/Array Methods
### [1) Add value and del]()
|Method	|Description|
|-|-|
|append()|	Adds an element at the end of the list|
|extend()	|Add the elements of a list (or any iterable), to the end of the current list|
|insert()	|Adds an element at the specified position|
|pop()|	Removes the element at the specified position|

### [2) Search with specified value and ..]()
|Method	|Description|
|-|-|
|remove()|	Removes the first item with the specified value|
|count()|	Returns the number of elements with the specified value|
|index()|	Returns the index of the first element with the specified value|

### [3) Overall Modify]()
|Method	|Description|
|-|-|
|copy()|	Returns a copy of the list|
|clear()|	Removes all the elements from the list||
|reverse()	|Reverses the order of the list|
|sort()|	Sorts the list|



# 3. Dictionary Methods




### [1) Add value and del]()
|Method	|Description|
|-|-|
|pop()|	Removes the element with the specified key|
|popitem()	|Removes the last inserted key-value pair|
|get()	|Returns the value of the specified key|
|setdefault( key , value )	|Returns the value of the specified key. If the key does not exist: insert the key, with the specified value|

### [2) Return a list]()
|Method	|Description|
|-|-|
|items()|	Returns a list containing a tuple for each key value pair|
|keys()|	Returns a list containing the dictionary's keys|
|values()|	Returns a list of all the values in the dictionary|




### [3) Overall Modify]()
|Method	|Description|
|-|-|
|clear()	|Removes all the elements from the dictionary|
|copy()|	Returns a copy of the dictionary|
|fromkeys(keys_array , fixed_value)	|Returns a dictionary with the specified keys_array and FIXED VALUE|
|update(dic)	|Updates the dictionary to append the specified other dictionary|


# 4. Python Tuple Methods

|Method	|Description|
|-|-|
|count()|	Returns the number of times a specified value occurs in a tuple|
|index()	|Searches the tuple for a specified value and returns the position of where it was found|

# 5. Python Set Methods
A set is a collection which is both Unordered ,Unindexed ,Unchangeable and  Duplicates Not Allowed(Just combined)







### [1) Item modfiy]()
|Method	|Description|
|-|-|
|add()|	Adds an element to the set|
|pop()|	Removes an element from the set|
|remove()|	Removes the specified element (If the specified item does not exist, it will raise an error.)|
|discard()	|Remove the specified item( it don't raise an error )|


### [2) Set operation]()
|Method	|Description|
|-|-|
|difference()|	Returns a set containing the difference between two or more sets|
|difference_update()	|Removes the items in this set that are also included in another, specified set|
|intersection()|	Returns a set, that is the intersection of two or more sets|
|intersection_update()|	Removes the items in this set that are not present in other, specified set(s)|
|symmetric_difference()|	Returns a set with the symmetric differences of two sets|
|symmetric_difference_update()	|inserts the symmetric differences from this set and another|
|union()|	Return a set containing the union of sets|
###### < symmetric_difference >
![image](https://user-images.githubusercontent.com/78835559/124404673-e7d04e80-dd76-11eb-9990-74db84eb5232.png)


### [3) Retrun bool]()
|Method	|Description|
|-|-|
|isdisjoint()	|Returns whether two sets have a intersection or not|
|issubset()	|Returns whether another set contains this set or not|
|issuperset()|	Returns whether this set contains another set or not|

### [4) Overall Modify]()
|Method	|Description|
|-|-|
|clear()	|Removes all the elements from the set|
|copy()	|Returns a copy of the set|
|update()	|Update the set with another set, or any other iterable by adding items from another set |



# 6. Python File Methods

### [1) Read]()
|Method	|Description|
|-|-|
|readable()	|Returns whether the file stream can be read or not|
|read()|	Returns the file content ( string )|
|readline()|	Returns one line from the file ( line_string )|
|readlines()|	Returns a list of lines from the file ( list of readline() )

### [2) Write]()
|Method	|Description|
|-|-|
|writable()	|Returns whether the file can be written to or not|
||write()	|Writes the specified string to the file|
|writelines()	|Writes a list of strings to the file|


### [3) File position]()
|Method	|Description|
|-|-|
|seekable()|	Returns whether the file allows us to change the file position||
|seek()|	Change the file position|
|tell()|	Returns the current file position also returns the new postion.|

**#file position** : ???????????? ????????? ??????????????? ?????? ( char ????????? 1??? count )


### [4) ]()
|Method	|Description|
|-|-|
|isatty()	|Returns whether the file stream is interactive or not|
|flush()	|Flushes the internal buffer|
|detach()|	Returns the separated raw stream from the buffer|
|fileno()|	Returns a number that represents the stream, from the operating system's perspective|
|truncate(char_size)|	Resizes the file to a specified size |
|close()	|Closes the file|


**# Truncate** : consider a text entry field in an electronic form. If a program limits the size of the field to 255 characters, it may allow you to continue typing past the maxiumum number of characters. However, when the information is submitted or saved, the program truncates the data to the first 255 characters and any additional characters are disregarded.
<pre>
f = open("demofile2.txt", "w")
f.write("123456789012345678901234567890")
f.truncate(20)
f.close()
</pre>



# Python Built-in Exceptions

|Exception	|Description|
|-|-|
|ArithmeticError	|Raised when an error occurs in numeric calculations|
|AssertionError|	Raised when an assert statement fails|
|AttributeError	|Raised when attribute reference or assignment fails|
|Exception|	Base class for all exceptions|
|EOFError|	Raised when the input() method hits an "end of file" condition (EOF)|
|FloatingPointError|	Raised when a floating point calculation fails|
|GeneratorExit|	Raised when a generator is closed (with the close() method)|
|ImportError|	Raised when an imported module does not exist|
|IndentationError|	Raised when indendation is not correct|
|IndexError|	Raised when an index of a sequence does not exist|
|KeyError	|Raised when a key does not exist in a dictionary|
|KeyboardInterrupt|	Raised when the user presses Ctrl+c, Ctrl+z or Delete|
|LookupError	|Raised when errors raised cant be found|
|MemoryError	|Raised when a program runs out of memory|
NameError|	Raised when a variable does not exist|
|NotImplementedError|	Raised when an abstract method requires an inherited class to override the method|
|OSError	|Raised when a system related operation causes an error|
|OverflowError	|Raised when the result of a numeric calculation is too large|
|ReferenceError	|Raised when a weak reference object does not exist|
|RuntimeError|	Raised when an error occurs that do not belong to any specific expections|
|StopIteration	|Raised when the next() method of an iterator has no further values|
|SyntaxError	|Raised when a syntax error occurs|
|TabError|	Raised when indentation consists of tabs or spaces|
|SystemError	|Raised when a system error occurs|
|SystemExit|	Raised when the sys.exit() function is called|
|TypeError	|Raised when two different types are combined|
|UnboundLocalError|	Raised when a local variable is referenced before assignment|
|UnicodeError|	Raised when a unicode problem occurs|
|UnicodeEncodeError	|Raised when a unicode encoding problem occurs|
|UnicodeDecodeError	|Raised when a unicode decoding problem occurs|
|UnicodeTranslateError|	Raised when a unicode translation problem occurs|
|ValueError|	Raised when there is a wrong value in a specified data type|
|ZeroDivisionError|	Raised when the second operator in a division is zero|


