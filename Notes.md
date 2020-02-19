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
- re.search(): find a pattern in a string
- re.match(): does this entire string conform to this pattern
- re.findall(): find all patterns in this string and returns all the matches in it not just the first match
- re.group(): to get the matched string  
- Searching with Regex match = re.search(pattern,string)  

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
```
### Other functions

- Count function  
    This function returns the number of times a value occurs in a list.
	```
	li = [1,1,1,1,1,4,4,4,3]
	print(li.count(4))   #3
	```
	
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
[Return to Index](Notes.md#Index)  
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