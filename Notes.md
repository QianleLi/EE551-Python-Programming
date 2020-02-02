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
* [Other functions](Notes.md#Other-functions)

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
### Other functions

- Count function  
    This function returns the number of times a value occurs in a list.
	```
	li = [1,1,1,1,1,4,4,4,3]
	print(li.count(4))   #3
	```
	