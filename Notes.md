# This is notes for EE551 Python Programming

I will skip some points that I have already known and I believe that I won't forget.
## Index

* [Lecture 1](Notes.md#Lecture-1)
  * [Dictionary](Notes.md#Dictionary)
  * [List](Notes.md#List)
  * [Tuple](Notes.md#Tuple)
  * [Variables](Notes.md#Variables)
  * [MapLists](Notes.md#MapLists)
* [Lecture 2](Notes.md#Lecture-2)
  * [Build-in Functions](Notes.md#Build-in-Functions)
  * [Filtering Lists](Notes.md#Filtering-Lists)
  * [and & or](Notes.md#and-&-or)
  * [Lambda Functions](Notes.md#Lambda-Functions)
* [Lecture 3](Notes.md#Lecture-3)
  * [Files](Notes.md#Files)
  * [Handling Exceptions](Notes.md#Handling-Exceptions)
  * [Replace function of string](Notes.md#Replace-function-of-string)
  * [Regular expression Class Note 1](Notes.md#Regular-expression-Class-Note-1)
* [Lecture 4](Notes.md#Lecture-4)
  * [Regular expression Class Note 2](Notes.md#Regular-expression-Class-Note-2)
* [Lecture 5](Notes.md#Lecture-5)
  * [List Comprehension](Notes.md#List-Comprehension)
    * [Examples](Notes.md#Examples)
	* [List Comprehensions vs Lambda functions](Notes.md#List-Comprehensions-vs-Lambda-functions)
	* [Multi-conditions](Notes.md#Multi-conditions)
	* [Nesting Loops](Notes.md#Nesting-Loops)
	* [Dictionary Comprehension](Notes.md#Dictionary-Comprehension)
	* [Filtering](Notes.md#Filtering)
* [Lecture 6](Notes.md#Lecture-6)
  * [Web scrapping](Notes.md#Web-scrapping)
  * [Regular expression class note 3](Notes.md#Regular-expression-class-note-3)
    * [Quantifiers — * + ? and {}](Notes.md#Quantifiers-—-*-+-?-and-{})
	* [Substitute](Notes.md#Substitute)
* [Lecture 7](Notes.md#Lecture-7)
  * [Operators](Notes.md#Operators)
    * [Arithmetic Operators](Notes.md#Arithmetic-Operators)
	* [Comparison Operators](Notes.md#Comparison-Operators)
	* [Assignment Operators](Notes.md#Assignment-Operators)
	* [Bitwise Operators](Notes.md#Bitwise-Operators)
	* [Logical Operators](Notes.md#Logical-Operators)
	* [Membership Operators](Notes.md#Membership-Operators)
  * [String Tricks](Notes.md#String-Tricks)
* [Lecture 8](Notes.md#Lecture-8)
  * [Function](Notes.md#Function)
  * [Functional programming](Notes.md#Functional-programming)
* [Lecture 9](Notes.md#Lecture-9)
  * [Module](Notes.md#Module)
  * [NumPy](Notes.md#NumPy)
    * [Difference between array and list](Notes.md#Difference-between-array-and-list)
	* [When to use list or array](Notes.md#When-to-use-list-or-array)
	* [Difference between array and ndarray](Notes.md#Difference-between-array-and-ndarray)
	* [Data Types for ndarrays](Notes.md#Data-Types-for-ndarrays)
	* [Operations between Arrays and Scalars](Notes.md#Operations-between-Arrays-and-Scalars)
	* [Basic Indexing and Slicing](Notes.md#Basic-Indexing-and-Slicing)
	* [2-Dimensional slicing](Notes.md#2-Dimensional-slicing)
	* [Multidimensional arrays](Notes.md#Multidimensional-arrays)
	* [Indexing with slices](Notes.md#Indexing-with-slices)
	* [Add one-more dimension](Notes.md#Add-one-more-dimension)
	* [Adding elements of the array](Notes.md#Adding-elements-of-the-array)
	* [Reshape array](Notes.md#Reshape-array)
	* [Concatenating and Splitting Arrays](Notes.md#Concatenating-and-Splitting-Arrays)
	* [Split the matrix](Notes.md#Split-the-matrix)
	* [Mathematical and Statistical Methods](Notes.md#Mathematical-and-Statistical-Methods)
* [Lecture 10](Notes.md#Lecture-10)
  * [Pandas](Notes.md#Pandas)
    * [Columns in DataFrame](Notes.md#Columns-in-DataFrame)
	* [Select Rows](Notes,md#Select-Rows)
	* [Missing Elements](Notes.md#Missing-Elements)
	* [Grouping](Notes.md#Grouping)
	* [dataFrame without header](Notes.md#dataFrame-without-header)
	* [Filtering Rows](Notes.md#Filtering-Rows)
* [Other functions](Notes.md#Other-functions)
* [Regular Expression Extra materials](Notes.md#Regular-Expression-Extra-Materials)
  * [Using the {n,m} Syntax](Notes.md#Using-the-{n,m}-Syntax)
  * [findall method](Notes.md#findall-method)
  * [Check numbers and letters](Notes.md#Check-numbers-and-letters)
  * [Find letters that appear many times](Notes.md#Find-letters-that-appear-many-times)
  * [^ & $](Notes.md#^-&-$)
  * [Group](Notes.md#Group)
  * [match method](Notes.md#match-method)
  * [Greedy/non-greedy mode](Notes.md#Greedy/non-greedy-mode)
  * [search method](Notes.md#search-method)
  * [sub method](Notes.md#sub-method)
### Lecture 1

#### Dictionary

```
d = {"server":"mpilgrim", "database":"master"}
d["mpilgrim"]  #Error, input a value cannot get a key
d["database"] = "pubs"   #Modify an existing value,You can not have duplicate keys in a dictionary. Assigning a value to an existing key will wipe out the old value.
d["uid"] = "sa"      #Add a pair of key and value
d.get(key, default=None)   #get the value of the key, if there is no such a key in the dict, return the default value.

d = {}
d["key"] = "value"
d["Key"] = "Another value"  #Dictionary keys are case−sensitive.
Dictionaries have no concept of order among elements.

d["retrycount"] = 3
d[42] = "douglas"   
#Dictionary values can be any datatype, including strings, integers, objects, or even other dictionaries.
#Dictionary keys are more restricted, but they can be strings, integers, and a few other types. 

del d[42]   #delete one pair of key and value
d.clear() #clear a dictionary
```
```
params = {"server":"mpilgrim", "database":"master", "uid":"sa", "pwd":"secret"}
params.key() #dict_keys(['server', 'database', 'uid', 'pwd'])
print('%s' %params.key())
params.values()  #dict_values(['mpilgrim', 'master', 'sa', 'secret'])
params.items()  #dict_items([('server', 'mpilgrim'), ('database', 'master'), ('uid', 'sa'), ('pwd', 'secret')])

[k for k, v in params.items()]  #Get all keys of params
[v for k, v in params.items()]  #Get all values of params
["%s=%s" % (k, v) for k, v in params.items()]  
```
[Return to Index](Notes.md#Index)
#### List

```
li = ["a", "b", "mpilgrim", "z", "example"]
li[0]   #The first element is "a"
li[-1]   #output "example"
li[-3]   #output "mpilgrim"

li[1:3]  #output elements 1 to 2, which is ["b", "mpilgrim"]
li[1:-1] #from element 1 to the element before element -1, which is ['b', 'mpilgrim', 'z']
li[:3]   #from the beginning element to element 2, which is ['a', 'b', 'mpilgrim']
li[3:]   #from element 3 to the end element of the list, which is ['z', 'example']
li[:]  #output the whole list
print(li[::2])  #print one and skip one
print(li[::-1])   #reverse the list

li.append('new')  #add a new single element
li.insert(2,'new') #insert a new single element into the list, the list should be ['a', 'b', 'new', 'mpilgrim', 'z', 'example', 'new'] after this command
li.extend(["two", "element"])   #add many elements at once, the list should be ['a', 'b', 'new', 'mpilgrim', 'z', 'example', 'new', 'two', 'elements']
#Difference between append and extend
li=['a', 'b', 'c']
li.extend(['d', 'e', 'f'])  #li should be ['a', 'b', 'c', 'd', 'e', 'f']
li=['a', 'b', 'c']
li.append(['d', 'e', 'f'])  #li should be ['a', 'b', 'c', ['d', 'e', 'f']]

li = ['a', 'b', 'c', 'd', 'e', 'f']
li.index('a')  #output index 0
li.index('e')  #output index 4
'c' in li   #output True

li.remove('a')  #Remove element 'a'
li.pop()  #"pop" does two things: it removes the last element of the list, and it returns the value that it removed. 

li = ['a', 'b', 'mpilgrim']
li = li + ['example', 'new']  #output ['a', 'b', 'mpilgrim', 'example', 'new']
li += ['two']   #['a', 'b', 'mpilgrim', 'example', 'new', 'two']

li = [1, 2] * 3    #[1, 2, 1, 2, 1, 2]
```
[Return to Index](Notes.md#Index)

#### Tuple

```
t = ("a", "b", "mpilgrim", "z", "example")
t[0]  #output 'a'
t[-1]  #output 'example'
t[1:3]  #output ['b', 'mpilgrim']
t.index("example")   #output index 4
"z" in t  #output True
#You can't add elements to a tuple. Tuples have no append or extend method. 
#You can't remove elements from a tuple. Tuples have no remove or pop method. 
#You can't find elements in a tuple. Tuples have no index method.
#You can, however, use 'in' to see if an element exists in the tuple.

('a', )  #This is a tuple with one element
```
Example:
```
1)What is the data type of (1)?   (a)
a) Tuple
b) Integer
c) List
d) Both tuple and integer

2)What will be the output of the following Python code?  (d)
>>> a=(1,2,3,4)
>>> del(a[2])
a) Now, a=(1,2,4)
b) Now, a=(1,3,4)
c) Now, a=(3,4)
d) Error 
```

**Tuples are faster than lists.**  
**If you are defining a constant set of values and all you are ever going to do with it is iterate through it, use a tuple instead of a list.**  
[Return to Index](Notes.md#Index)
#### Variables

```
#Assign multiple values at once
v = ('a', 'b', 'e')
(x, y, z) = v    #x = 'a', y = 'b', z = 'e'

#Assign consecutive values
(MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY) = range(7)

#Format strings and numbers
k = 'uid'
v = 'sa'
'%s = %s' %(k, v)   #output 'uid = sa', (k, v) is a tuple
userCount = 6
print("Users connected: %d" % (userCount, ))   #interger
print("Users connected: " + str(userCount))
p = 50.462500
print("Today's stock price: %f" % p )   #float
print("Today's stock price: %.2f" % p )   #reserves two decimal fractions
print("Today's stock price: %+.2f" % p )
```
[Return to Index](Notes.md#Index)
#### MapLists

```
li = [1, 9, 8, 4]
[elem*2 for elem in li]  #iterate all elements in li and muptiply all of them with 2
Note that this command does NOT have any real effect to li
li = [elem*2 for elem in li]  #This command does

#Join list
params = {"server":"mpilgrim", "database":"master", "uid":"sa", "pwd":"secret"}
["%s=%s" % (k, v) for k, v in params.items()] #Output ['server=mpilgrim', 'database=master', 'uid=sa', 'pwd=secret']
s_add= "|".join(["%s=%s" % (k, v) for k, v in params.items()]) #Output 
'server=mpilgrim|database=master|uid=sa|pwd=secret'
#Split strings
li = ['server=mpilgrim', 'uid=sa', 'database=master', 'pwd=secret']
s = ";".join(li) #'server=mpilgrim;uid=sa;database=master;pwd=secret'
s.split(";")  #['server=mpilgrim', 'uid=sa', 'database=master', 'pwd=secret']
s.split(";", 2)  #only split the left two ";", which is ['server=mpilgrim', 'uid=sa', 'database=master;pwd=secret']
```
[Return to Index](Notes.md#Index)
### Lecture 2

#### Build-in Functions

- type function  
    This function returns datatypes.
	```
	type(10) #int
	
	li = []
	type(li) #list
	```
- dir function  
    dir returns all methods of the object input.
	```
	li = []
	dir(li)
	```  
	
[Return to Index](Notes.md#Index)
#### Filtering Lists

```
li = ["a", "mpilgrim", "foo", "b", "c", "b", "d", "d"]
[elem for elem in li if len(elem) > 1]   #Only select elements that are larger than 1, which is ['mpilgrim', 'foo']
[elem for elem in li if elem != "b"]
[elem for elem in li if li.count(elem) == 1]  
```
[Return to Index](Notes.md#Index)
#### and & or

For and:  
All 1, take the last 1  
All 0, take the last 0  
not all 1 or zero, take the first 0  

For or:  
All 1, take the first 1  
All 0, take the last 0  
else, take the first 1  

For mixed use:
Determine the value from left to right one by one.  
Example:
```
What is the output of the below boolean logic:  (c)
() and 'b'
a) False
b) True
c) ()
d) None of above
```
[Return to Index](Notes.md#Index)
#### Lambda Functions

```
#Normal function:
def my_f(x):
	return x*2
my_f(10)  #20
#A lambda function
x = 5
g = lambda x: x*2   #10
or
print((lambda x: x*2)(3))  #6
```
[Return to Index](Notes.md#Index)
### Lecture 3

#### Files

- Working wih file objects  
	```
	f = open("./blues.mp3", "rb")
	t.tell()  #The tell method tells the current position in the open file. In this example, the output is 0 because we are at the beginning of the file.
	f.seek(-128, 2)
	'''
	The seek method moves to another position in the open file.
	The second parameter specifies what the first means: 
		0 means position move to an absolute position (counting from the start of he file)
		1 means move to a relative position (counting from the current position)
		2 means move to a potion relative to the end of the file
	This statement tells the file object to move to a position 128 bytes to from the end of the file.
	'''
	tafData = f.read(128)
	'''
	read method read exact number of bytes of the file. If the given number is missed or negative, it will read all bytes.
	After reading the file, the position of the file object has changed during the position. If the beginning position is 482847, then the end position is 482975, which moved 128 bytes.
	'''
	f.seek(0)  
	'''
	f.seek(offset[,whence])  
	seek method moves the pointer to assigned position. 
	'offset' is the the relative movement unit. 'whence' is optional, represents from which the pointer starts to move: 
		0 means start from the beginning  of the file; 
		1 means start from the current position; 
		2 means start from the end of the file.
	If the method runs successfully, it returns the new position; wheres it returns -1.
	'''
	f.close()  #We must close the file object after all operations
	f.closed  #After close the file object, this statement will return True, or it will return False.
	```
- Write to files  
	- Clear the content and write new content  
		```
		logfile = open('test.log', 'w')
		logfile.write('test success')
		logfile.close()
		
		print(open('test.log').read())  #output: test success
		```
	- Retain the old stuff and append more content
		```
		logfile = open('test.log', 'a')
		logfile.write('\nline 2')
		logfile.close()
		
		print(open('test.log').read())  
		'''
		output: 
		test success
		line 2
		'''
		```
[Return to Index](Notes.md#Index)
#### Handling Exceptions

- Accessing a non-exsiting dictionary key will raise a KeyError exception.
- Searching a list for a non-exsiting value will raise a ValueError exception.
- Calling a non-exsiting method will raise an AttributeError excepion.
- Referencing a non-existing variable will raise a NameError excepion.
- Mixing datatypes without coercion will raise a TypeError exception.  
If we open a non-existing file:  
```
fsock = open("/notthere", "r")
'''
We will get a FileNotFoundError/ or IOError
FileNotFoundError is one type of IOError
'''
```  
To avoid the error:  
```
try:  
	fsock = open("/notthere")
except IOError:  
	print("The file doe not exist, exiting gracefully.")
print("This line will always be printed")
```  
[Return to Index](Notes.md#Index)
#### Replace function of string

```
s = '100 NORTH MAIN ROAD'
s.replace('ROAD', 'RD') #'100 NORTH MAIN RD'  #replace method will replace all 'ROAD' with 'RD'
s = '100 NORTH BROAD ROAD'
s.replace('ROAD', 'RD') #'100 NORTH BRD,RD'
#We can use list slice to solve this problem
s[:-4] + s[-4:].replace('ROAD', 'RD') #'100 NORTH BROAD RD'
#But we have to adjust the statement as long as s string is different, that's why we need regular expression.
```
[Return to Index](Notes.md#Index)
#### Regular expression Class Note 1

```
import re 
s = '100 NORTH BROAD ROAD'
re.sub('ROAD$', 'RD.', s)    #'100 NORTH BROAD RD.'

s = '100 BROAD'
re.sub('ROAD$', 'RD.', s) # '100 BRD'
```
To match 'ROAD' when it was at the end of the string and it was its own whole word, not a part of some larger word.   
To express this in regular expression, use '\b', which means "a word boundary must occur right there."  
`re.sub('\bROAD$', 'RD', s) # '100 BROAD'`  
```
s = '100 BOARD'
re.sub(r'\bROAD$', 'RD', S)  # '100 BOARD'

s = '100 BROAD ROAD APT. 3'
re.sub(r'\bROAD$', 'RD.', s)  # '100 BROAD ROAD APT. 3'
re.sub(r'\bROAD\b', 'RD.', s)  # '100 BROAD RD. APT. 3'

import re
pattern = '^M?M?M?$'  
re.search(pattern, 'M') #<re.Match object; span=(0, 1), match='M'>
re.search(pattern, 'MM') #<re.Match object; span=(0, 2), match='M'>
re.search(pattern, 'MMM') #<re.Match object; span=(0, 3), match='M'>
re.search(pattern, 'MMMM')
re.search(pattern, '')  # <re.Match object; span=(0, 0), match=''>
```
[Return to Index](Notes.md#Index)

### Lecture 4

#### Regular expression Class Note 2

- re.compile(): To create a regex object
- re.search(): find a pattern in a string, returns None if no match.  
- re.match(): does this entire string conform to this pattern
- re.findall(): find all patterns in this string and returns all the matches in it not just the first match, returns a list.
- re.group(): to get the matched string  
- Searching with Regex match = re.search(pattern,string)   
- If regular expression not able to find that pattern it will return None.
	```
	import re
	example = "Welcome to the world of Python"
	pattern = r'Python'
	match = re.search(pattern,example)
	
	print(match)
	if match:
	    print("found", match.group())
	else:
	    print("No match found")
	```
##### Pattern type(Character Classes)  

- \w : sequence of word-like characters [a-zA-Z0–9_] that are not space  
- \d : Any numeric digit[0–9]  
- \s : whitespace characters(space,newline,tab)  
- \D : match characters that are NOT numeric digits  
- \W : match characters that are NOT words,digit or underscore  
- \S : match characters that are NOT spaces,tab or newline  

##### Repetition Group

```
+ : 1 or more
+ * : 0 or more
? : 0 or 1
{k}: exactly integer K occurence
{m,n}: m to n occurence inclusive
. :matches any character except the newline(\n)
^: start of the string
$: end of string
\: escape character
|: match one of many possible groups
```
##### Examples

```    ?
message = 'my number is 123-4567' # Here we are creating regex object,which define the pattern we are looking for 
myregex = re.compile(r'(\d\d\d-)?\d\d\d-\d\d\d\d') # Then we are trying to find a pattern in the string
match = myregex.search(message) # This will tell us the actual text
print(match.group())
```
```
import re
#Finding the number of punctuations in a particular piece of text
target = [';','.',',','–']
string = "It was the best of times, it was the worst of times, it was the age of wisdom, it was the age of foolishness, it was the epoch of belief, it was the epoch of incredulity, it was the season of Light, it was the season of Darkness, it was the spring of hope, it was the winter of despair, we had everything before us, we had nothing before us, we were all going direct to Heaven, we were all going direct the other way – in short, the period was so far like the present period, that some of its noisiest authorities insisted on its being received, for good or for evil, in the superlative degree of comparison only."
pattern = r'[,;.–]'
print(len(re.findall(pattern,string)))
```
```    findall
#In case we have multiple phone number, use findall
message = 'my number is 510-123-4567 and my office number is 510-555-6677'
#Here we are creating regex object,which define the pattern we are looking for 
myregex = re.compile(r'\d\d\d-\d\d\d-\d\d\d\d')
#Find all pattern of the string and return a list objects
print(myregex.findall(message))
```
```   \
#To find out parentheses literally in string, we need to escape parentheses using backslash \
import re
message = "my number is (123)-555-4567"
myregex = re.compile(r'\(\d\d\d\)-(\d\d\d-\d\d\d\d)')
match = myregex.search(message)
print(match.group())
```
```   group()
message = 'my number is 510-123-4567'
#Here we are creating regex object,which define the pattern we are looking for 
myregex = re.compile(r'(\d\d\d)-(\d\d\d)-(\d\d\d\d)')
#Then we are trying to find a pattern in the string
match = myregex.search(message)
print(match.group())   //510-123-4567
print(match.group(1))  //510
print(match.group(2))  //123
print(match.group(3))   //4567
```
```  ?
myregex = re.compile(r'\(?(\d\d\d)?\)?-?(\d\d\d-\d\d\d\d)') 
#There maybe parentheses, the first three digits and the first strikethrough.
```
```   |
import re
lang = re.compile(r'Pyt(hon|con|mon)')
match = lang.search('Pytmon is a wonderful language')
print(match.group())
```
```
import re
pattern = '^M?M?M?$'   #Start with a M and end with a M, may be one M or nothing in the middle.
print(re.search(pattern, 'M'))
print(re.search(pattern, 'MM'))
print(re.search(pattern, 'MMM'))
print(re.search(pattern, 'MMMM'))
```
```
import re
myphone = re.compile(r'\(?(\d\d\d)?\)?-?\d\d\d-\d\d\d\d')
message1 = "My phone number is 123-4567"
message2 = "My phone number is 201-123-4567"
message3 = "My phone number is (201)-123-4567"
match = myphone.search(message1)
print(match.group())
```
```   ?
import re
myexpr = re.compile(r'Pyt(ho)?n')   //h and o must be or not in the string together, or return none
match = myexpr.search('Python a wonderful language')
print(match.group())
match = myexpr.search('Pythohon a wonderful language')  //The position of (ho)? must be 'ho' or nothing)
print(match.group())   //None
```
``` *
#'*' zero or more time
import re
myexpr = re.compile(r'Pyth(on)*')
match = myexpr.search("Welcome to the world of Pythonon")
print(match.group())     //'Pythonon'
match = myexpr.search("Welcome to the world of Python")
print(match.group())    //'Python'
#'on' has to be together
```
```
#'+' must appear at least 1 or more time
import re
myexpr = re.compile(r'Pyth(on)*')
match = myexpr.search("Welcome to the world of Pythonon")
print(match.group())     //'Pythonon'
match = myexpr.search("Welcome to the world of Python")
print(match.group())    //'Python'
#'on' has to be together
```
```
#Now if we want to match a specific number of times
import re
myregex = re.compile(r'(Re){3}'')
match = myregex.search("My matching string is ReReRe")
print(match.group())   #'ReReRe'
```
```
#Range of repetitions
import re
myregex = re.compile(r'(Re){3,5}')
match = myregex.search("My matching string is ReReReRe")
print(match.group())    #'ReReReRe'
```
```
#The regular expression in Python do greedy matches i.e it try to match longest possible string
import re
mydigit = re.compile(r'(\d){3,5}')   //As more as possible
match = mydigit.search('123456789')
match.group()
```  
[Return to Index](Notes.md#Index)
### Lecture 5

#### List Comprehension

List comprehensions provide a concise way to create lists.  
This is the basic syntax:  
`new_list = [expression for_loop_one_or_more conditions]`  
It consists of brackets containing an expression followed by a for clause, then zero or more for or if clauses. The expressions can be anything, meaning you can put in all kinds of objects in lists.  
The result will be a new list resulting from evaluating the expression in the context of the for and if clauses which follow it.   
The list comprehension always returns a result list.   
[Return to Index](Notes.md#Index) 
##### Examples

```
numbers = [1, 2, 3, 4]
squares = []
for n in numbers:
    squares.append(n**2)
print(squares)  # Output: [1, 4, 9, 16]

#Finding squares using list comprehensions:
numbers = [1, 2, 3, 4]
squares = [n**2 for n in numbers]
'''
Here, square brackets signifies that the output is a list. n**2 is the expression executed for each element and for n in numbers is used to iterate over each element. In other words, execute n**2 (expression) for each element in numbers.
'''
print(squares)  # Output: [1, 4, 9, 16]
```
***
```
#Example: Find common numbers from two lists using for loop.

list_a = [1, 2, 3, 4]
list_b = [2, 3, 4, 5]
common_num = []
for a in list_a:
    for b in list_b:    
        if a == b:      
            common_num.append(a)
print(common_num)  # Output [2, 3, 4]

#Using conditions in list comprehensions:
common_num = [a for a in list_a for b in list_b if a == b]
print(common_num) # Output: [2, 3, 4]

#Another way to simplify the expression
common_num = [i  for i in list_a if i in list_b]
print(common_num) # Output: [2, 3, 4]
```
***
Produce a tuple:  
```
#Example: Return numbers from the list which are not equal as a tuple:
list_a = [1, 2, 3]
list_b = [2, 7]
different_num = [(a, b) for a in list_a for b in list_b if a != b]
print(different_num) # Output: [(1, 2), (1, 7), (2, 7), (3, 2), (3, 7)]
#Here. as we are returning a list of tuples, tuples must be in parenthesis to avoid errors. 
#In the above example, tuples with a and b will be printed such that a and b are not the same.
```
***
Iterate over strings:  
```
#List comprehensions can also be used to iterate over strings, as shown below:
list_a = ["Hello", "World", "In", "Python"]
small_list_a = [str.lower() for str in list_a]
print(small_list_a) # Output: ['hello', 'world', 'in', 'python']
```
***
Produce a list of lists:  
```
#Like tuples, list comprehensions can be used to produce a list of a list, as shown below:
list_a = [1, 2, 3]
square_cube_list = [ [a**2, a**3] for a in list_a]
print(square_cube_list) # Output: [[1, 1], [4, 8], [9, 27]]
```
[Return to Index](Notes.md#Index)  
##### List Comprehensions vs Lambda functions

There are various built in functions and lambda functions that can help play with lists just like list comprehensions.  
```
#Double all the numbers in a list using lambda functions:
num = [1, 2, 3, 4]
double_num = map(lambda x: x + x, num)
print(list(double_num))
```
##### Multi-conditions

```
#create numeric indicators for colors
color_list = ['green', 'red', 'blue', 'yellow']
color_indicator = [0 if color == 'green'else 1 if color == 'red' else 2 if color == 'blue' else 3 for color in color_list]
print(color_list)
print(color_indicator)
```
```
color_list = ['green', 'red', 'blue', 'pink', 'yellow']
color_mapping = {'green': 0, 'red': 1, 'blue':2, 'yellow':3}
color_indicator2 = [color_mapping[color] if color in color_mapping else 'na' for color in color_list]
print(color_list)
print(color_indicator2)
```
[Return to Index](Notes.md#Index) 
##### Nesting Loops

You can nest loops to perform operations and return a matrix. Here we create a matrix of color attributes:  
```
color_list1 = ['green', 'red', 'blue', 'yellow']
color_list2 = ['dark', 'bright', 'tinted', 'glowing']
color_matrix = [[color2 + ' ' + color1 for color1 in color_list1] for color2 in color_list2]
print(color_matrix)
```

##### Dictionary Comprehension

```
words = ['goodbye', 'cruel', 'world']
data = {word: len(word) for word in words}
#Notice that the key word and its value len(word) are separated with a colon ':'
print(data)
```
Another useful trick for creating dictionaries is to zip two lists together. 
```
words = ["hello", "old", "friend"]
lengths = [len(word) for word in words]
data1 = zip(words, lengths)
data2 = dict(zip(words, lengths))   #change tuple to dictionary
print(data1, data2) #<zip object at 0x000002B73FF66308> {'hello': 5, 'old': 3, 'friend': 6}
```
##### Filtering
You can filter the items that are included.
```
words = ['deified', 'radar', 'guns']
palindromes = [word for word in words if word == word[::-1]]
print(palindromes)  #['deified', 'radar']

words = ["not", "on", "my", "watch"]
data = {w: w[::-1] for w in words if len(w) < 5}
print(data)  #{'not': 'ton', 'on': 'no', 'my': 'ym'}
```
[Return to Index](Notes.md#Index)  
### Lecture 6

#### Web scrapping

Import BeautifulSoup from bs4, which is the module that can actually parse the HTML of the web page retrieved from the server.
```
#import get to call a get request on the site
from requests import get

#get the first page of the east bay housing prices
response = get('https://sfbay.craigslist.org/search/eby/apa?hasPic=1&availabilityMode=0') #get rid of those lame-o's that post a housing option without a pic using their filter

from bs4 import BeautifulSoup
html_soup = BeautifulSoup(response.text, 'html.parser')
#get the macro-container for the housing posts
posts = html_soup.find_all('li', class_= 'result-row')

#get the macro-container for the housing posts
posts = html_soup.find_all('li', class_= 'result-row')

#grab the first post and all the variables you want from it, make sure you know how to access each of them for one post before you loop the whole page
post_one=posts[0]
print(post_one)

#grab the price of the first post
post_one_price = post_one.a.text
print(post_one_price)

#remove white space (\n) from the string
post_one_price.strip()

#grab the time and datetime it was posted
post_one_time = post_one.find('time', class_= 'result-date')
print(post_one_time)
post_one_datetime = post_one_time['datetime']
print(post_one_datetime)

#title is 'a'' and the class, link is grabbing the href attribute of that variable
post_one_title = post_one.find('a', class_='result-title hdrlnk')
post_one_link = post_one_title['href']

#easy to grab the post title by taking the text element of the title variable
post_one_title_text = post_one_title.text

#grabs the whole segment of housing details. We will need missing value handling in the loop as this kind of detail is not common in posts
#the text can be split, and we can use indexing to grab the elements we want. number of bedrooms is the first element.
#sqft is the third element

post_one_num_bedrooms = post_one.find('span', class_ = 'housing').text.split()[0]
print(post_one_num_bedrooms)
post_one_sqft = post_one.find('span', class_ = 'housing').text.split()[2][:-3] #cleans the ft2 at the end
print(post_one_sqft)
post_one_hood = posts[0].find('span', class_='result-hood').text #grabs the neighborhood, this is the problem column that requires
#a lot of cleaning and figuring out later.
print(post_one_hood)
```
[Return to Index](Notes.md#Index)
#### Regular expression class note 3

##### Quantifiers — * + ? and {}

- abc*: matches a string that has ab followed by zero or more c 
- abc+: matches a string that has ab followed by one or more c
- abc?: matches a string that has ab followed by zero or one c
- abc{2}: matches a string that has ab followed by 2 c
- abc{2,}: matches a string that has ab followed by 2 or more c
- abc{2,5}: matches a string that has ab followed by 2 up to 5 c
- a(bc)*: matches a string that has a followed by zero or more copies of the sequence bc
- a(bc){2,5}: matches a string that has a followed by 2 up to 5 copies of the sequence bc  
[Return to Index](Notes.md#Index)

##### Substitute

- This is another great functionality. When you work with NLP you sometimes need to substitute integers with X’s. Or you might need to redact some document. Just the basic find and replace in any of the text editors.
- Input: search pattern, replacement pattern, and the target string
- Output: Substituted string  
```
string = "It was the best of times, it was the worst of times."
string = re.sub(r'times', r'life', string)
print(string)
```
```
#remove street number from address
import re
address = '284-12 West Street, Hoboken, 07030 '
test = re.sub(r'^[\d-]+ ', '', address, 2)
print(test)
```
[Return to Index](Notes.md#Index)
### Lecture 7 

#### Operators:  

##### Arithmetic Operators

```
a = 10
b = 20
print(a + b)
print(a - b)
print(a * b)
print(a / b)
print(a % b)
```
[Return to Index](Notes.md#Index)
###### Floor Division

```
#Return the maximum integer that less than or equal to the result
-9//2        #reault of -9/2 = -4.5, so we get -5
```
##### Comparison Operators

```
==, !=, >, <, >=, <=

<> means not equal, but it is only used in python 2.6 or earlier version.
```
##### Assignment Operators

```
=, +=, -=, *=, /=, %=, **=, //=
```
[Return to Index](Notes.md#Index)
##### Bitwise Operators

Bitwise operator works on bits and performs bit by bit operation.   
###### &

& Binary AND Operator copies a bit to the result if it exists in both operands
```
a = 60            # 60 = 0011 1100 
b = 13            # 13 = 0000 1101 
c = 0
c = a & b    
print(bin(c))     #0b1100
```
###### |

| Binary OR It copies a bit if it exists in either operand.
```
c = a | b           # c = 61 = 0011 1101 
```
###### ^

^ Binary XOR It copies the bit if it is set in one operand but not both.
```
c = a ^ b            #  49   0b110001
```
###### ~

~ Binary Ones Complement It is unary and has the effect of 'flipping' bits.
```
a = 60            # 60 = 0011 1100 
b = 13            # 13 = 0000 1101 
c = 0
c =  ~ b          #add 1 and multiply eith -1
print(bin(c))  #-0b1110
c =  ~ a          
print(bin(c))   #-0b111101
```
[Return to Index](Notes.md#Index)
###### <<

<< Binary Left Shift The left operands value is moved left by the number of bits specified by the right operand.
```
b = 13            # 13 = 0000 1101 
c = 0
c =  b << 2
print(bin(c))    #0b110100
```
###### >>

Binary Right Shift The left operands value is moved right by the number of bits specified by the right operand.
```
b = 13            # 13 = 0000 1101 
c =  b >> 2
print(bin(c))
```
##### Logical Operators

```
and, or, not
```
##### Membership Operators

```
a = 10
b = 20
list = [1, 2, 3, 4, 5 ];

if ( a in list ):
    print "Line 1 - a is available in the given list"
else:
    print "Line 1 - a is not available in the given list"

if ( b not in list ):
    print "Line 2 - b is not available in the given list"
else:
    print "Line 2 - b is available in the given list"

a = 2
if ( a in list ):
    print "Line 3 - a is available in the given list"
else:
    print "Line 3 - a is not available in the given list"
```
[Return to Index](Notes.md#Index)
#### String Tricks

- Reversing String
```
a = 'new'
print('Reverse is', a[::-1])
```
- Splitting String into multiples
```
a = 'Who Are You'
b = a.split()
print(b)
```
- Printing out multiples of strings
```
print('me'*3+' '+'no'*4)
```
- Creating a single string
```
a = ['I', 'am', 'here']
print(' '.join(a))
```
- Check if two words are anagrams
```
from collections import Counter 
def is_anagram(str1, str2): 
    return Counter(str1) == Counter(str2) 
print(is_anagram('geek', 'eegk'))   #True
print(is_anagram('geek', 'peek'))   #False
```
- Flatten Lists
```
import itertools
a = [[1, 2], [3, 4], [5, 6]]
b = list(itertools.chain.from_iterable(a))
print(b)   #[1, 2, 3, 4, 5, 6]
```
- Reverse a list
```
a=['10','9','8','7']
print(a[::-1])
```
- Combining two lists
```
a=['a','b','c','d']
b=['e','f','g','h']
for x, y in zip(a, b):
    print(x,y)
	Output: 
		('a', 'e')
		('b', 'f')
		('c', 'g')
		('d', 'h')
		('e', 'f')
```
- Negative Indexing Lists
```
a = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10] 
a[-3:-1]     #[8, 9]
```
- Swapping Values
```
x, y = 1, 2
x, y = y, x
print(x, y)   #(2, 1)
```
[Return to Index](Notes.md#Index)
### Lecture 8

#### Function 

Function example: 
```
def f(x):
    return 2*x + 3
```

Keys To A Good Function:
* Is sensibly named
* Has a single responsibility
* Includes a docstring
* Returns a value
* Is not longer than 50 lines
* Is idempotent and, if possible, pure
***
- Naming

	- The first issue with the name of this function is its use of acronyms/abbreviations. 
	- Prefer full English words to abbreviations and non-universally known acronyms.
- Single Responsibility
	- Single Responsibility Principle states that (in our case) a function should have a single responsibility. That is, it should do one thing and only one thing. 
	- One great reason is that if every function only does one thing, there is only one reason ever to change it: if the way in which it does that thing must change.
	- It also becomes clear when a function can be deleted: if, when making changes elsewhere, it becomes clear the function’s single responsibility is no longer needed, simply remove it.
- Docstrings
	- Every function requires a docstring
	- Use proper grammar and punctuation; write in complete sentences
	- Begins with a one-sentence summary of what the function does
	- Uses prescriptive rather than descriptive language
- Return Values
	- Functions can (and should) be thought of as little self-contained programs. 
	- They take some input in the form of parameters and return some result. 
	- Parameters are, of course, optional. Return values, however, are not optional, from a Python internals perspective. 
	- Even if you try to create a function that doesn’t return a value, you can’t. If a function would otherwise not return a value, the Python interpreter “forces it” to return None.
- Function length
	- The length of a function directly affects readability and, thus, maintainability. 
	- If a function is following the Single Responsibility Principle, it is likely to be quite short. 
	- If it is pure or idempotent (discussed below), it is also likely to be short. 
- Idempotency
An idempotent function always returns the same value given the same set of arguments, regardless of how many times it is called.
- Purity
In functional programming, a function is considered pure if it is both idempotent and has no observable side effects.  
**Using the 'global' keyword**  
```
def myFunction():   #a and b are not returned by the function
    global a
    a = "Cathy"
    b = "Eric"
    print(a,b)
a = "Terra"
b = "Brandol"
myFunction()    #Cathy Eric
print(a,b)    #Cathy Brandol
```
[Return to Index](Notes.md#Index)
#### Functional programming

- Finding the path
```
import sys, os
os.getcwd()    #'D:\\courses\\EE551\\jupyter_note'
```
```
import sys, os, re, unittest
def regressionTest():   #Get a list of file names in the current directory
    path = os.getcwd() 
    sys.path.append(path) 
    files = os.listdir(path)
    for file in files:
        print(file)
regressionTest()   
```
- Filtering lists revisited
	- Python has a built−in filter() function which takes two arguments, a function and a list, and returns a list.
	- The function passed as the first argument to filter must itself take one argument, and the list that filter returns will contain all the elements from the list passed to filter for which the function passed to filter returns true.
```
def odd(n):
    return n % 2
li = [1, 2, 3, 5, 9, 10, 256, -3]
filter(odd, li)    #[1, 3, 5, 9, -3] 
#or 
[e for e in li if odd(e)]      #[1, 3, 5, 9, -3] 
```
	- filter takes two arguments, a function (odd) and a list (li). 
	- It loops through the list and calls odd with each element. If odd returns a true value (remember, any non−zero value is true in Python), then the element is included in the returned list, otherwise it is filtered out. 
	- The result is a list of only the odd numbers from the original list, in the same order as they appeared in the original.
**Combine filter function with regular expression**
```
files = os.listdir(path)
test = re.compile("test\.py$", re.IGNORECASE) 
files = filter(test.search, files)
```
[Return to Index](Notes.md#Index)

### Lecture 9

#### Module

Modules provide an easy way to organize components into a system by serving as self-contained packages of variables known as namespaces. 
All the names defined at the top level of a module file become attributes of the imported module object.
* "import" statement  
	```
	import
		#Lets a client (importer) fetch a module as a whole
	from
		#Allows clients to fetch particular names from a module
	```
	For instance, suppose the file b.py in Figure above defines a function called spam, for external use.  
	```
	def spam(text):                # File b.py 
		print(text, 'spam')
	```
	Now, suppose a.py wants to use spam. To this end, it might contain Python statements such as the following:  
	```
	import b                 # File a.py 
	b.spam('gumby')          # Prints "gumby spam"
	```
* "from" statement  
	By contrast, because "from" copies specific names from one file over to another scope, it allows us to use the copied names directly in the script without going through the module (e.g., spam):  
	```
	from b import spam       # Copy out a variable (one or more) 
	spam('Hello world!')     # No need to qualify name
	```
	This form of from allows us to list one or more names to be copied out, separated by commas.
* "from *" statement  
	when we use a * instead of specific names, we get copies of all names assigned at the top level of the referenced module.  
	Here again, we can then use the copied name printer in our  script without going through the module name:  
	```
	from module1 import *       # Copy out _all_ variables 
	spam('Hello world!')
	```
	**Modules are loaded and run on the first import or from, and only the first.**  
* Changing mutables in modules  
	Names copied with a "from" become references to shared objects; as with function arguments, reassigning a copied name has **no** effect on the module from which it was copied, but changing a shared mutable object through a copied name can also change it in the module from which it was imported.  
	```
	#small.py:
	x = 1
	y = [2, 3]
	```
	```
	from small import x, y   # Copy two names out
	x = 42                   # Changes local x only
	y[0] = 42                # Changes shared mutable in place
	```
	```
	import small             # Get module name (from doesn't) 
	small.x                  # x of small is still 1
	small.y                  # y of small has changed: [42, 3]
	```
* When import is required?
	The only time you really must use import instead of from is when you must use the same name defined in two different modules.  
[Return to Index](Notes.md#Index)  

#### NumPy

NumPy, short for Numerical Python, is the fundamental package required for high performance scientific computing and data analysis. 
* ndarray, a fast and space-efficient multidimensional array providing vectorized arithmetic operations and sophisticated broadcasting capabilities  
* Standard mathematical functions for fast operations on entire arrays of data without having to write loops  
* Tools for reading / writing array data to disk and working with memory-mapped files  
* Linear algebra, random number generation, and Fourier transform capabilities  
* Tools for integrating code written in C, C++, and Fortran  
***
* Create ndarrays  
	**ndarray is a multidimensional array object.**
	```
	import numpy as np
	data1 = [6, 7.5, 8, 0, 1]
	arr1 = np.array(data1)
	print(arr1)
	print(arr1*10)
	print(arr1+arr1)
	```  
[Return to Index](Notes.md#Index)
##### Difference between array and list

* Arrays need to be declared. Lists don’t, since they are built into Python. 
* Arrays can store data very compactly and are more efficient for storing large amounts of data.
* Arrays are great for numerical operations; lists cannot directly handle math operations.  
##### When to use list or array

* If you need to store a relatively short sequence of items and you don’t plan to do any mathematical operations with it, a list is the preferred choice. 
* If you have a very long sequence of items, consider using an array. This structure offers more efficient data storage.
* If you plan to do any numerical operations with your combination of items, use an array. Data analytics and data science rely heavily on (mostly NumPy) arrays.
##### Difference between array and ndarray

- numpy.array is just a convenience function to create an ndarray; it is not a class itself.
- array is the function from numpy
- ndarray is the class generated from numpy.array  
```
import numpy as np
data2 = [[1, 2, 3, 4], [5, 6, 7, 8]]
arr2 = np.array(data2)
print(arr2.ndim)   #row number of matrix: 2
print(arr2.shape)   #Shape of matrix: (2, 4)
print(arr2.dtype)   #data type: int32
print(np.zeros(10))   #[0. 0. 0. 0. 0. 0. 0. 0. 0. 0.]
print(np.zeros((3, 6)))  
Output:[[0. 0. 0. 0. 0. 0.]
		 [0. 0. 0. 0. 0. 0.]
		 [0. 0. 0. 0. 0. 0.]]
print(np.empty((2, 3, 2)))
Output: [[[0. 0.]
		[0. 0.]
		[0. 0.]]
	
	   [[0. 0.]
		[0. 0.]
		[0. 0.]]]
```
It’s not safe to assume that np.empty will return an array of all zeros. 
In many cases, it will return uninitialized garbage values.
```
np.arange(15)
Output: [ 0  1  2  3  4  5  6  7  8  9 10 11 12 13 14]
```  
[Return to Index](Notes.md#Index)
##### Data Types for ndarrays

```
arr1 = np.array([1, 2, 3], dtype=np.float64)
arr2 = np.array([1, 2, 3], dtype=np.int32)
```
NumPy data types: int8, uint8 int16, uint16 int32, uint32 int64, uint64 float16 float32 float64, float128  
```
#In this example, integers were cast to floating point. 
arr = np.array([1, 2, 3, 4, 5])
print(arr.dtype)   #int
float_arr = arr.astype(np.float64)
print(float_arr.dtype)  #float64
```
```
#If cast some floating point numbers to be of integer dtype, the decimal part will be truncated
arr = np.array([3.7, -1.2, -2.6, 0.5, 12.9, 10.1])
arr.astype(np.int32)   #[ 3 -1 -2  0 12 10]
```
```
numeric_strings = np.array(['1.25', '-9.6', '42'], dtype=np.string_)
print(numeric_strings)  #[b'1.25' b'-9.6' b'42']
print(numeric_strings.astype(float))  #[ 1.25 -9.6  42.  ]
```
[Return to Index](Notes.md#Index)
##### Operations between Arrays and Scalars

```
arr = np.array([[1., 2., 3.], [4., 5., 6.]])
print(arr * arr)   #[[ 1.  4.  9.], [16. 25. 36.]]
print(1 / arr)
print(arr**0.5)
```
##### Basic Indexing and Slicing

```
arr = np.arange(10)
print(arr[5])   #5
print(arr[5:8])   #[5 6 7]
arr[5:8] = 12
print(arr)  #[ 0  1  2  3  4 12 12 12  8  9]
```
```
import numpy as np
arr = np.arange(10)
arr_slice = arr[5:8]
arr_slice[1] = 12345
print(arr)  #[0 1 2 3 4 5 12345 7 8 9]
arr_slice[:] = 64
print(arr)  #[ 0  1  2  3  4 64 64 64  8  9]
```
The above example means that the data is not copied, and any modifications to the view will be reflected in the source array.  
If you want a copy of a slice of a ndarray instead of a view, you will need to explicitly copy the array; for example `arr[5:8].copy()`.
```
arr = np.arange(10)
arr_slice = arr[5:8].copy()
arr_slice[1] = 120
print(arr_slice)  #[5 120 7]
```
[Return to Index](Notes.md#Index)
##### 2-Dimensional slicing

```
arr2d = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
print(arr2d[2])  #[7 8 9]
print(arr2d[:,2])  #[3 6 9]
print(arr2d[2,:])    #[7 8 9]
print(arr2d[0][2])   #3 
print(arr2d[0,2])    #3
print(arr2d[0:2,1:3])   #[[2 3] [5 6]]  row 0,1 and column 1,2
```
##### Multidimensional arrays

```
#2 X 2 X 3 array "arr3d"
arr3d = np.array([[[1, 2, 3], [4, 5, 6]], [[7, 8, 9], [10, 11, 12]]])
print(arr3d[0])
'''
[[1 2 3]
 [4 5 6]]
'''
old_values = arr3d[0].copy()
arr3d[0] = 42
print(arr3d[0])
'''
[[42 42 42]
 [42 42 42]]
'''
arr3d[0] = old_values
print(arr3d[0])
'''
[[1 2 3]
 [4 5 6]]
'''
print(arr3d[1, 0])  #[7 8 9]
```
[Return to Index](Notes.md#Index)
##### Indexing with slices

* One-dimentional
```
arr = np.arange(10)
print(arr[1:6])    #[1 2 3 4 5]
```
* Two-dimentional
```
arr2d = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
print(arr2d[2])  #[7, 8, 9]
print(arr2d[:2])  
'''
[[1 2 3]
 [4 5 6]]
'''
print(arr2d[:2,1:]) #row 0, 1 and column 1, 2
'''
[[2, 3],
[5, 6]]
'''
print(arr2d[1, :2])   #[4 5]
print(arr2d[2, :1])   #[7]
```
* Example
```
import numpy as np
array = np.arange(60).reshape((3, 4, 5))
#Indexing with ints gives a scalar
print(array[2, 3, 4] == 59)  #True
#Indexing with slices gives a 3d array
print(array[:2, :2, :2].shape)  #(2, 2, 2)
#Indexing with a mix of slices and ints will give an array with < 3 dims
print(array[0, :2, :3].shape)  #(2, 3)
print(array[:, 2, 0:1].shape)  #(3, 1)
```
##### Add one-more dimension

```
x = np.array([[1,2,3],[4,5,6]])
print(x.shape)          # (2, 3)
y = x[...,None]
print(y.shape)          # (2, 3, 1)
z = x[:,:,np.newaxis]
print(z.shape)          # (2, 3, 1)
```
##### Adding elements of the array

```
import numpy as np
arr2d = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
sum_val = np.sum(arr2d)
print(sum_val)   #45
#sum along the rows
print(np.sum(arr2d,axis=1))  #[ 6 15 24]
#sum along the cols
print(np.sum(arr2d,axis=0))  #[12 15 18]
```
[Return to Index](Notes.md#Index)
##### Reshape array

```
import numpy as np
arr = np.arange(8)
arr2 = arr.reshape(4, 2)
print(arr2)
arr3 = arr.reshape((4, 2)).reshape((2, 4))
print(arr3)
```
One of the passed shape dimensions can be -1, in which case the value used for that dimension will be inferred from the data:  
```
arr = np.arange(15).reshape((5, -1))
print(arr)
'''
[[ 0  1  2]
 [ 3  4  5]
 [ 6  7  8]
 [ 9 10 11]
 [12 13 14]]
'''
arr2 = arr.flatten()
print(arr2)  #[ 0  1  2  3  4  5  6  7  8  9 10 11 12 13 14]
```
Functions like reshape and flatten, accept an order argument indicating the order to use the data in the array. This can be 'C' or 'F' in most cases.  
```
arr = np.arange(12).reshape((3, 4), order = 'c')
print(arr)
'''
[[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]]
'''
arr = np.arange(12).reshape((3, 4), order = 'F')
print(arr)
'''
[[ 0  3  6  9]
 [ 1  4  7 10]
 [ 2  5  8 11]]
'''
```
[Return to Index](Notes.md#Index)
##### Concatenating and Splitting Arrays

```
import numpy as np
arr1 = np.array([[1, 2, 3], [4, 5, 6]])
arr2 = np.array([[7, 8, 9], [10, 11, 12]])
arr = np.concatenate([arr1, arr2], axis=0)
print(arr)
'''
[[ 1  2  3]
 [ 4  5  6]
 [ 7  8  9]
 [10 11 12]]
'''
arr = np.concatenate([arr1, arr2], axis=1)
print(arr)
'''
[[ 1  2  3  7  8  9]
 [ 4  5  6 10 11 12]]
'''
```
There are some convenience functions, like vstack and hstack
```
arr = np.vstack((arr1, arr2))
print(arr)
arr = np.hstack((arr1, arr2))
print(arr)
'''
[[ 1  2  3]
 [ 4  5  6]
 [ 7  8  9]
 [10 11 12]]
[[ 1  2  3  7  8  9]
 [ 4  5  6 10 11 12]]
'''
```
##### Split the matrix

```
from numpy.random import randn
arr = randn(5, 2)
print(arr)
'''
[[ 1.03345176  0.95499481]
 [-0.41724051  0.26435938]
 [ 0.17971512 -1.43196278]
 [ 2.14256596 -0.16677754]
 [ 1.10451902  0.50121965]]
'''
first, second, third = np.split(arr, [1, 3]) 
'''
Split matrix to three part, first part has 1 row, second part has 2 row, third part has three row. 
While there are no enough rows for the third part, so the third part only has 2 rows.
'''
print(first)   #[[ 1.03345176  0.95499481]]
print(second)
'''
[[-0.41724051  0.26435938]
 [ 0.17971512 -1.43196278]]
'''
print(third)
'''
[[ 2.14256596 -0.16677754]
 [ 1.10451902  0.50121965]]
'''
```
[Return to Index](Notes.md#Index)
##### Mathematical and Statistical Methods

* sum: Sum of all the elements in the array or along an axis. 
* mean: Arithmetic mean
* std, var: Standard deviation and variance, respectively
* min, max: Minimum and maximum.
* argmin, argmax: Indices of minimum and maximum elements, respectively
* prod: Product of elements starting from 0
* cumsum: Cumulative sum of elements starting from 0
* cumprod: Cumulative product of elements starting from 0
```
arr = np.random.randn(5, 4) # normally-distributed data arr
arr.mean()  
np.mean(arr)
arr.sum()
arr.std()
arr.mean(axis=1)
arr.sum(0)
```
***
```
arr = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
arr.prod()   #362880      product of all elements
arr.prod(0)   #[ 28,  80, 162]   product of each list
arr.cumsum(0)  
'''
[[ 0,  1,  2],
 [ 3,  5,  7],
 [ 9, 12, 15]]
'''
arr.cumprod(1)
'''
[[  0,   0,   0],
 [  3,  12,  60],
 [  6,  42, 336]]
'''
np.cumsum(arr)
np.cumsum(arr, 0)
'''
[[ 0,  1,  2],
 [ 3,  5,  7],
 [ 9, 12, 15]]
'''
np.cumprod(arr+1,0)
'''
[[  1,   2,   3],
 [  4,  10,  18],
 [ 28,  80, 162]]
'''
```
***
```
b= np.arange(4)   #[0, 1, 2, 3]
b.cumsum()       #[0, 1, 3, 6]
b.cumprod()      #[0, 0, 0, 0]
```
[Return to Index](Notes.md#Index)
### Lecture 10

#### Pandas

With Pandas, we can load data from different sources. Some are loading from CSV or a remote URL or from a database. The loaded data is stored in a Pandas data structure called DataFrame. DataFrame’s are usually refered by the variable name df.
```
import pandas as pd
df = pd.read_csv("SAT.csv")
df
df.head()   #  shows you the top a few lines of the data
df.shape   # dataFrame size 
load data from URL
df2 = pd.read_csv("http://samplecsvs.s3.amazonaws.com/SalesJan2009.csv")   #load data from URL
#http://samplecsvs.s3.amazonaws.com/SalesJan2009.csv
```
##### Columns in DataFrame

A column in a DataFrame can be retrieved by attribute:  
`df['Math']`  
A column in a DataFrame can be retrieved by dict-like notation:  
`df.Math`  
**Select Multiple Columns from DataFrame**  
```
1. Create a list of columns to be selected
columns_to_be_selected = ["Reading", "Math", "Writing"]
2. Use it as an index to the DataFrame
df[columns_to_be_selected]
```
[Return to Index](Notes.md#Index)
##### Select Rows

Unlike the columns, our current DataFrame does not have a label which we can use to refer the row data.  
But like arrays, DataFrame provides numerical indexing(0, 1, 2…) by default.
```
1. using numerical indexes - iloc
df.iloc[0:3, :]  #Row 0~2, all columns
df.loc[0:7]   #Row 0~7, all columns
df.iloc[:,0:3]   # similarly, "iloc" can apply to columns
```
**Difference btw iloc vs loc**  
- loc gets rows (or columns) with particular labels from the index.
- iloc gets rows (or columns) at particular positions in the index (so it only takes integers).  
Examples:  
```
df.loc[2:4, 'Math']   #The 'Math' column, 2~4 row
df.iloc[2:4, 'Math']   #2, 3 row
df.loc[2:4, ['Math', 'Reading']]  
```
##### Missing Elements

- Determine if there is any missing element
  - isnull: If missing, return True, if not, return False.
  - notnull: If missing, return False, if not, return True.
  ```
  print(df.isnull())   #Find those missing elements
  print(df.notnull())   #Find which is not a missing element
  print(df[df.notnull()]*100)  #filtered missing elements and do calculation to those who are not missing elements
  ```
- Delete missing elements: dropna  
  `df.dropna()`  
- Replace missing elements: fillna
  `df.fillna(0)`  
  `df.fillna('T')`  
  `df.fillna(0,inplace=True)`  
  **Add the parameter `inplace` to change the source file.**  
  [Return to Index](Notes.md#Index)  
  
##### Grouping

You can perform statistical operations such as min, max, mean etc., over one or more columns of a Dataframe.  
```
df["Math"].sum()  #Sum of a column
df[["Math", "Reading"]].mean()   #two mean values for the two column
df[["Math", "Reading"]].min()  #two min values for the two column
df[["Math", "Reading"]].max()
df[["Math", "Reading"]].median()  #two median values of two column  中位数
```
##### dataFrame without header

header is the column names. Without header, columns will be represented by numbers just as rows.
```
df_noheader = pd.read_csv('SAT_no_header.csv', header = None)
df_noheader[2]   #The 2 column
df_noheader[0:2]   #The 0 and 1 row
df_noheader.iloc[0:2,2:4]     #The 2,3 column of the 0,1 row
df_noheader.loc[0:2,2:4]    #The 2,3,4 column of the 0,1,2 row
df_noheader.loc[[0, 1, 2, 6,7, 8],2:4]    #The 2,3,4 column of the 0,1,2,6,7,8 row
df_noheader.loc[list(range(0,3)) + list(range(6,9)),2:4]  #Same of the above statement
```
##### Filtering Rows

```
import pandas as pd
df = pd.read_csv("SAT.csv")
df_part = df [ df['numStudents']>30]   # we can filter by conditions
df_refine = df[ (df['numStudents']<30)  &  (df['Reading']>400) & (df['Math']>400) ]   # we can filter by multiple conditions
```
[Return to Index](Notes.md#Index)  
### Other functions

- Counter function
	This function returns a directionary of numbers and relative letters in the word.
```
from collections import Counter 
print(Counter('teeth'))      #Counter({'t': 2, 'e': 2, 'h': 1})
my_count = Counter()   # defining an empty Counter
my_count.update("a")   # adding values to my_count
print(my_count)       #Counter({'a': 1})
my_count.update("ab")
print(my_count)       #Counter({'a': 2, 'b': 1})
```
We can retrieve the highest frequency values using the most_common() function of the Counter object. 
```
my_count = Counter()   # defining an empty Counter
my_count.update("abcdbacadddbbdcaddefabcdd")
my_count.most_common()
#output: [('d', 9), ('a', 5), ('b', 5), ('c', 4), ('e', 1), ('f', 1)]
```
We can also use the most_common() function to find the n least common elements.
```
n=2
my_count.most_common()[:-n:-1]  #[('f', 1)]
```
- count function  
    This function returns the number of times a value occurs in a list.
	```
	li = [1,1,1,1,1,4,4,4,3]
	print(li.count(4))   #3
	```
- zip function  
	Make iterable elements into tuples.  
	```
	a = [1,2,3]
	b = [4,5,6]
	c = [4,5,6,7,8]
	zipped = zip(a,b)     # Get a list of tuples
	#[(1, 4), (2, 5), (3, 6)]
	zip(a,c)              # Number of element is equal to the least lenGth
	#[(1, 4), (2, 5), (3, 6)]
	zip(*zipped)          # doing the opposite of zip()
	#[(1, 2, 3), (4, 5, 6)]
	```
- set function
	Create a set which doesn't has any multiply items.
	```
	a = [10, 20, 30, 40, 20, 20, 30, 10, 40, 40, 40]
	set(a)  #{10, 20, 30, 40}
	print(max(set(a), key = a.count))  #40
	```
[Return to Index](Notes.md#Index)
### Regular Expression Extra Materials

#### Using the {n,m} Syntax

```
pattern = '^M{0,3}$'
'''
This pattern says: "Match the start of the string, then anywhere from zero to three M characters, then the end of the string." The 0 and 3 can be any numbers; if you want to match at least one but no more than three M characters, you could say M{1,3}.
'''
re.search(pattern, 'M') #<_sre.SRE_Match object; span=(0, 1), match='M'>
re.search(pattern, 'MM') #<re.Match object; span=(0, 2), match='M'>
re.search(pattern, 'MMM') #<re.Match object; span=(0, 3), match='M'>
re.search(pattern, 'MMMM')
```

**The following is some notes of other tutorials that I found on the Internet**  
#### findall method

To use the regular expression, we have to use the built-in module `re`.  
Find the exact string in a longer string:  
```
import re
target = 'like is short, I learn python.'
result = re.findall('python', target)  #output ['python']
result1 = re.findall('java', target)  #output[]
```
Now we have a string `target = 'abc acc adc azc atc aec'`, in the following program we are gonna find out substrings that the middle letter is 'd' or 'e'.   
```
import re 
target = 'abc aec adc agc atc amc'
result re.findall('a[de]c', target)  #remember this statement means d or e
print(result)  #output ['aec', 'adc']
```
Now we have a new demand that we need to find all substrings that their middle letters are among 'b' to 'z'.  
```
import re
target = 'abc acc aec agc adc aic'
result = re.findall('a[b-z]c', target)
print(result)  #output['abc', 'acc', 'aec', 'agc', 'adc', 'aic']
```
we can also get all substrings whose middle letters are **not** among the given range.  
```
import re
target = 'abc acc aec agc adc aic'
result = re.find_all('a[^c-z]c', target)
print(result)    #output is ['abc']
```
| Regular Expression | Explanation |
| --- | --- |
| [abf] | Check if the letter in that position is a or b or f |
| [a-z] | Check if the letter in that position is among a to z |
| [^a-z] | Check if the letter in that position is **not** among a to z |

[Return to Index](Notes.md#Index)
***
#### Check numbers and letters

There is a much easier way to check whether there are numbers or other letters.   

| Regular Expression | Explanation | In other words |
| --- | --- | --- |
| \d | Check if it is a number | [0-9] |
| \D | Check if it is **not** a number | [^0-9] |
| \w | Check if it is a letter or ‘_’ | [A-Za-z_] |
| \W | Check if it is **not** a letter or ‘_’ | [^A-Za-z_] |
| \s | Check if it is an invisible character(space, \t, \v, \r, \n, \f) | [\f\n\t\r\v] |
| \S | Check if it is **not** an invisible character | [^\f\n\t\r\v] |

- Check numbers  
    ```
    import re
    target = ‘Number: 12’
    result = re.findall(‘\d’, target)
    print(result)   #output[‘1’,’2’]
    ```
    ```
    import re
    target = ‘NO12’
    result = re.findall(‘\D’target)
    print(result)  #output [‘N’, ‘0’]
    ```
- Check letters or _  
    ```
    import re
    target = ‘I love_’
    result = re.findall(‘\w’, target)
    print(result)   #output [‘i’, ‘l’, ‘o’, ‘v’, ‘e’, ‘_’]
    ```
    ```
    import re
    target = 'I am _'
    result = re.findall('\W', target)
    print(result)   #output [' ', ' ']
    ```
- Check invisible characters
	```
	import re 
	target = 'life is short \n I'
	result = re.findall('\s', target)
	print(result)  #[' ', ' ', ' ', '\n', ' ']
	```
	```
	import re
	target = 'life \n is short'
	result = re.findall('\S', target)
	print(result)  #output ['l', 'i', 'f', 'e', 'i', 's', 's', 'h', 'o', 'r', 't']
	```
[Return to Index](Notes.md#Index)
***
#### Find letters that appear many times

| Example | Explanation |
| ---- | ---- |
| {3} | The letter before '{3}' appears three times |
| {3,8} | The letter before '{3,8}' appears 3 to 8 times |
| ? | The letter before ? appears 0 or 1 time |
| + | The letter before + appears at least 1 times |
| * | The letter before * appears at least 0 times |

The following are the illustration codes:  
```
import re
content = 'To be or not o be, that is a question'
result = re.findall('\w{1,30}', content)
'''
'\w'represents a letter or '_', '{1,30}' means '\w' appears more than 1 but less than 30 times. The above statements pick out every word whose length is between 1 and 30.
'''
print(result) #output ['To', 'be', 'or', 'not', 'to', 'be', 'that', 'is', 'a', 'question']
print(len(result)  #output 10, which means this content has 10 words.
```
The above codes have some flaws, we should adjust it by adding '+':  
```
import re
content = 'To be or not to be, that is a problem.'
result = re.findall('\w+',content)
#'+' means '\w' appears more than 0 times. So a word will be picked up as long as is length is larger than 0
print(result)
```
Another example is:  
```
import re
content = 'comment number: 12'
result = re.findall('\d{1,10}', content)   #We can get the comment number between 0 and 9999999999.
We can also write like this:  
#result = re.findall('\d+', content)
print(result)    #Get 12
```
[Return to Index](Notes.md#Index)
*** 
#### ^ & $

| Regular Expression | Explanation |
| --- | --- |
| ^ | If starts with the letter behind '^', match |
| $ | If ends with the letter behind '$', match |

Example of `^`:   
```
import re
content = 'http://www.zhihu.com'
content1 = '/question/62747717/answer/576934857'
result = re.findall('^http.*', content)
'''
'^http' matches the content begins with 'http', '.' means all strings except for '\n', * means repeat 0 or infinite times.
'''
result1 = re.findall('^http.*', content1)
print(result)  #output ['http://www.zhihu.com']
print(result1)  #output []
```
Example of '$':  
```
import re 
content = 'https://www.zhihu.com/shiyue.png'
content1 = 'https://www.zhihu.com'
result = re.findall('.*png$', content)
result1 = re.findall('.*png$',content1)
print(result)  #output ['https://www.zhihu.com/shiyue.png']
print(result1)  #output []
```
[Return to Index](Notes.md#Index)
***
#### Group

Group: `(\d+)`  
The content inside () makes up a group, if the current position meet the demends of the content, then match successfully.  
Example: Get the date:  
```
import re
content = 'Issued at 2018/9/9'
result = re.findall('.*?(\d.*\d)', content)
(\d.*\d) represents a group, starts with a digit and ends with a digits. 
print(result)  #output ['2018/9/9']
```
A regular expression statement can have more than one groups:  
```
import re
content = 'Issued at 2020/2/6, by: Libenze'
result = re.findall('.*?(\d.*\d).*:(.*)', content)
'''
The above statement means that the first group starts wih a digit and ends with a digit in order to get the date. The second group starts after meeting ':', the content after ':' makes uo the second group.
'''
print(result) #output [('2020/2/6','Libenze')]
```
**Python will add a parenthesis both at the beginning and the end of the regular expression.**  
[Return to Index](Notes.md#Index)
***
#### match method

```
import re
content = 'Issued at 2020/2/6, by: Libenze
result = re.match('.*?(\d.*\d).*:(.*)', content)
#The parameters of match method is the same as those of findall method
print(result.group())
'''
The defaut parameter is 0, which is print(result.group(0)), this statement get the content inside the outermost parenthesis. So the output is 'Issued at 2020/2/6, by: Libenze'.
'''
print(result.group(1))  #output '2020/2/6', get the content of (\d.*\d)
print(result.group(2))  #output 'Libenze', get the content of (.*)
print(result.groups())  #output ('2020/2/6', 'Libenze')
```
There is a point that should pay more attention about the `match` method:  
```
import re
content = 'Comment number: 12'
result = re.match('\d', content)
print(result)  #output None
'''
The output is None because match method starts matching \d from the first character of content. As the first character of content is not a digit, it directly returns None.
'''
```
[Return to Index](Notes.md#Index)
***
#### Greedy/non-greedy mode   

- non-greedy mode  
	```
	import re
	content = 'Issued at 2020/2/6'
	result = re.findall('.*?(\d.*\d)',content)
	'''
	'?' represented non-greedy mode, the firsr .* will match content as little as possible. With \d, it will end as soon as it meets the first digit.
	'''
	print(result)  # output ['2020/2/6']
	```
- greedy mode  
	```
	import re
	content = 'Issued at 2020/02/06'
	result = re.findall('.*(\d.*\d)', content)
	'''
	The first .* matches as much contents as possible, as \d follows, it will not stop when meeting the first digit, when it is at the position of / after 02, te remaining, which is 06 also meets the requirement of (\d.*\d), but when at the position of the last 0, the requirement is not meeted, so the first .* stops matching. Therefore, the output is only ['23']
	'''
	print(result)
	```
Here is another example:  
```
import re 
content = 'Issued at 2020/02/06'
result = re.findall('.*?(\d.*?\d)', content)
'''
The second .* is in non-greedy mode, which starts matching from the first 2 and end at the first 0. Similarly, it can get 18, 12,and 23
'''
print(result)  #output ['20', '18', '12', '23']
```
[Return to Index](Notes.md#Index)
***
#### search method 

```
import re
content = 'Comment number: 12'
result_match = re.match('\d', content)
result_search = re.search('\d', content)
print(result_match)  # None
print(result_search)  # <_sre.SRE_Match object; span=(4, 5), match='1'>
print(result_search.group()) # '1'
'''
search method start match from the beginning, once it metches one target, it returns directly and will not continue.
'''
```
[Return to Index](Notes.md#Index)
***
#### sub method

```
#Purpose: replace all 'php' in the content with 'python'  
import re
content = 'python php java c javascript java php'
result = re.sub('php', 'python', content)
print('result')  #output 'python python java c javascript java python'
```
```
#Purpose: Replace all 'php' with 'python' no matter they are upper or lower case
import re
content = 'python PHP java v javascript java php'
result = re.sub('php', 'python', content)
result1 = re.sub('php', 'python', content, flags=re.I)
#'re.I' means not tell the upper and lower cases.
#Another common attribute is 're.S', means any characters
#In common mode, represents any characters except for \n
print(result) #'python PHP java c javascript java python'
print(result1) #'python python java c javascript java python'
```
```
#Purpose: Replace the first php with python
import re
content = 'python PHP java c transcript java php'
result = re.sub('php', 'python', content, flag=re.I)
result1 = re.sub('php','python',content,count = 1, flag = re.I)
'''
The default value of count = 0, means all 'php' will be replaced with 'python'; count = 1 means that only replace the first 1 'php'.
'''
print(result)
print(result1) #'python python java c javascript java php'
```
The second parameter of `sub` method can be a function. 
```
import re

def judge(value):
	value = value.group()  #get the match result
	if int(value) < 60:
		return 'failed'
	elif int(value) < 80:
		return 'pass'
	elif int(value) <90:
		return 'fair'
	else:
		return 'good'
		
content = 'Libenze:100 Amy:99 John:50 Gary:75'
result = re.sub('\d+',judge,content)
print(result)
'''
The matched result of the first parameter is the value passed into the judge function, the return value will replace the matched result.
'''
#output: Libenze:good Amy:good John:failed Gary:pass
```  
[Return to Index](Notes.md#Index)
