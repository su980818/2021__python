

# 1. Python String Methods
#### [Note: All string methods returns new values. They do not change the original string.]()

## [1) Convert case]()
|Method	|Description|
|-|-|
|capitalize() |	Converts the first character to upper case|
|lower()|	Converts a string into lower case|
|upper()	|Converts a string into upper case|
|casefold()	|Converts string into lower case , more powerful than upper() |
|swapcase()	|Swaps cases, lower case becomes upper case and vice versa|
|title()	|Converts the first character of each word to upper case|




## [2) Return integer]()
|Method	|Description|
|-|-|
|count()|	Returns the number of times a specified value occurs in a string|
|find()	| Searches the string for a specified value and returns the position of where it was found,if you not find -1|
|rfind()	|Searches the string for a specified value and returns the last position of where it was found|
|index()|	Searches the string for a specified value and returns the position of where it was found ,if you not find return ERROR |
|rindex()|	Searches the string for a specified value and returns the last position of where it was found|



## [3) Return list ]()
|Method	|Description|
|-|-|
|split(sep, maxsplit)	|Splits the string at the specified separator, and returns a list|
|rsplit(sep, maxsplit)	|Splits the string at the specified separator, and returns a list (starting from the right)|
|splitlines()	|Splits the string at line breaks and returns a list|


## [4) Modify string]()
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



## [5) Return bool_value]()
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
## [1) Add value and del]()
|Method	|Description|
|-|-|
|append()|	Adds an element at the end of the list|
|extend()	|Add the elements of a list (or any iterable), to the end of the current list|
|insert()	|Adds an element at the specified position|
|pop()|	Removes the element at the specified position|

## [2) Search with specified value and ..]()
|Method	|Description|
|-|-|
|remove()|	Removes the first item with the specified value|
|count()|	Returns the number of elements with the specified value|
|index()|	Returns the index of the first element with the specified value|

## [3) Overall Modify]()
|Method	|Description|
|-|-|
|copy()|	Returns a copy of the list|
|clear()|	Removes all the elements from the list||
|reverse()	|Reverses the order of the list|
|sort()|	Sorts the list|



# 3. Dictionary Methods




## [1) Add value and del]()
|Method	|Description|
|-|-|
|pop()|	Removes the element with the specified key|
|popitem()	|Removes the last inserted key-value pair|
|get()	|Returns the value of the specified key|
|setdefault( key , value )	|Returns the value of the specified key. If the key does not exist: insert the key, with the specified value|

## [2) Return a list]()
|Method	|Description|
|-|-|
|items()|	Returns a list containing a tuple for each key value pair|
|keys()|	Returns a list containing the dictionary's keys|
|values()|	Returns a list of all the values in the dictionary|




## [3) Overall Modify]()
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





# Python File Methods

## [1) Read]()
|Method	|Description|
|-|-|
|readable()	|Returns whether the file stream can be read or not|
|read()|	Returns the file content ( string )|
|readline()|	Returns one line from the file ( line_string )|
|readlines()|	Returns a list of lines from the file ( list of readline() )

## [2) Write]()
|Method	|Description|
|-|-|
|writable()	|Returns whether the file can be written to or not|
||write()	|Writes the specified string to the file|
|writelines()	|Writes a list of strings to the file|


## [3) File position]()
|Method	|Description|
|-|-|
|seekable()|	Returns whether the file allows us to change the file position||
||seek()|	Change the file position|
|tell()|	Returns the current file position also returns the new postion.|

**file position : 열려있는 파일의 내부에서의 위치 ( char 하나당 1씩 count )**


## [4) ]()
|Method	|Description|
|-|-|
||isatty()	|Returns whether the file stream is interactive or not|
|flush()	|Flushes the internal buffer|
|detach()|	Returns the separated raw stream from the buffer|
|fileno()|	Returns a number that represents the stream, from the operating system's perspective|
|truncate()|	Resizes the file to a specified size|
|close()	|Closes the file|
