---
layout: post
title: Python Notes
tags: 
category: Tech
---

Python is interpreted language

~~~
>>> means entering code into interpretor
~~~

Python is white space specific

#### Console

~~~
print("hello world")
age = input("Enter your age")
~~~

#### Numbers

Python has two types of numbers, ints and floats

Division returns a float

~~~
4 / 2 = 2.0
~~~

We can use integer division which requires a //

~~~
4 // 2 = 2
~~~

Make sure a number is within a range of 0 to 255

~~~
min(255, max(x, 0))
~~~

#### Range

~~~
range(10)               # 1, 2, 3, 4, 5, 6, 7, 8, 9, 10
range(10,1,-1)          # 10, 9, 8, 7, 6, 5, 4, 3, 2, 1
~~~

#### Variables

~~~
variable_name = 60 / 30
~~~

Naming rules: 
* no spaces and you cannot start a name with a special character
* we tend to use underscores to seperate names e.g. your_name

[See PEP 8 style guide](https://www.python.org/dev/peps/pep-0008/)  

#### Importing Modules

~~~
import math
math.ceil(1.23)
~~~

importing specific methods from modules

~~~
from socket import gethostname as method_name           # calling method_name will execute gethostname method from socket
~~~

#### String Interpolation

Python doesn't have string interpolation perse, but it does have something similar called format...

~~~
denominator = 123
numerator = 456

print("{a}/{b}".format(a = numerator, b = denominator))         # prints "456/123"
~~~

#### Strings

single or double quotes indicate a string

~~~
name = "Your Name"
print(name)
~~~

converting numbers to strings
~~~
name_and_age = "Mark Pearl" + str(35)
~~~

Strings are arrays

~~~
name = "hello_boy"
name[0]             # Returns the first element from the string - h
name[0:2]           # Slices name from 0 index to 2 index and returns he
name[:2]            # Shorthand for slicing from 0 to 2
name[2:]            # Shorthand for slicing from 2 to end of word
~~~

Reversing strings

~~~
'hello world'[::-1]     # Returns 'dlrow olleh'
~~~

Filling space

~~~
"123".rjust(6,"0")  # 000123
"123".ljust(6,"0")  # 123000
~~~

Converting case

~~~
"This is a message".upper()     # THIS IS A MESSAGE
~~~

#### Conitionals

~~~
<       # Less than
<=      # Less or equal to
==      # Equal
>=      # Greater or equal
>       # Greater
!=      # Not equal to
~~~

If statements

~~~
num = 4

if num < 1:
    doSomething()
elif num < 5:
    doSomethingMore()
else:
    doSomethingElse()
~~~

#### Classes

~~~
class ClassName:

    def __init__(self, name):
        self.name = name


anObject = ClassName("this object")
print(anObject.name)
~~~

#### Lists 

~~~
mixed_list = ["one", 2 , "three"]       # one, 2, three
my_list = ["one", "two", "three"]
my_list.append("four")                  # one, two, three, four
my_list.delete("four")                  # one, two, three
del mylist(2)                           # one, two 
~~~

list equality requires each element in the list to be the same and the order to be the same

~~~
[1, 2, 3] == [3, 2, 1]      # return False
[1, 2, 3] == [1, 2, 3]      # return True
~~~

Getting the average of an list of numbers

~~~
def find_average(array):
    return sum(array) / len(array) if array else 0
~~~

Sorting lists

~~~
items = [1, 3, 2, 4]
sorted_items = sorted(items)                            # 1, 2, 3, 4
reverse_sorted_items = sorted(items, reverse = True)    # 4, 3, 2, 1
~~~

Any

~~~
listitems = ['aa', 'bb', 'cc,' baa']
any(item = 'baa' for item in listitems)                 # returns true
~~~

### Dictionaries

~~~
example_dict = {'key1':'value1', 'key2':'value2'}
print(example_dict['key1'])                         # prints value1

example_dict['key2'] = 'new value'                  
print(example_dict['key2'])                         # prints new value
del example_dict['key2']                            # deletes key value pair key2 from dictionary

result = example_dict['unknown key']                # result gets value None
if result:
    print(result)
else:
    print("key does not exist")


example_dict['new key'] = 'something new'           # adds a new key value pair to the dict
~~~

Dictionary equality requires each element in the dictionary to be the same but does not require the order to be the same

~~~
dict_1 = {1:1, 2:2, 3:3, 4:4}
dict_2 = {4:4, 3:3, 2:2, 1:1}
dict_1 == dict2                                 # return true
~~~

~~~
[1, 2, 3] == [3, 2, 1]      # return False
[1, 2, 3] == [1, 2, 3]      # return True
~~~

# The get() method on dicts and its "default" argument

~~~
name_for_userid = {
    382: "Alice",
    590: "Bob",
    951: "Dilbert",
}

def greeting(userid):
    return "Hi %s!" % name_for_userid.get(userid, "there")
~~~

>>> greeting(382)
"Hi Alice!"

>>> greeting(333333)
"Hi there!"

#### Copying Dictionaries

~~~
dict1 = {'1' : '1', '2':'2' }
dict2 = {'3' : '3', '4':'4' }

matches = dict1.copy()
matches.update(dict2)
~~~

#### Merging Dictionaries

~~~

x = {'a': 1, 'b': 2}
y = {'b': 3, 'c': 4}

>>> z = {**x, **y}
>>> z
{'c': 4, 'a': 1, 'b': 3}
~~~

#### Conditionals

~~~
return "A" if x > 1 else "B"
~~~

#### Enumerate

~~~
seasons = ['Spring', 'Summer', 'Fall', 'Winter']
list(enumerate(seasons))
[(0, 'Spring'), (1, 'Summer'), (2, 'Fall'), (3, 'Winter')]
~~~

[read more](https://docs.python.org/2/library/functions.html#enumerate)  

#### For Loops

~~~
for n in range(50):
    ...
~~~

Looping through a dictionary

~~~
for key,item in dictionary.items():
    ...
~~~

Enumerating in pairs...

~~~
stuff = [1,2,3,4,5,6]
for (a,b) in enumerate(stuff):
    print(a)
    print(b)

# 0 1 1 2 2 3 3 4 4 5 5 6
~~~

#### While Loops

~~~
while x != 3:
    x = x + 1
~~~

or

~~~
while (True):
    if (x == 3): break
~~~

#### Functions

~~~
def function_name(param1):
  ...
  return ...
~~~

Main function - not required but a good pracice

~~~
def main():
    ...

main()
~~~

#### Lambdas

~~~
f = lambda x, y: x + y
f(1,2)                      # returns 3
~~~

#### Object Orientation

#### Classes

Declaring a class with inheritance

~~~
class parent_class:
	pass
   
class child_class(parent_class): 
	pass
~~~

Instantiating a class

~~~
object = child_class()
~~~

#### Dynamic Objects

~~~
class TheObject:
    pass

def makeit():
    dynamicObject = TheObject()
    dynamicObject.someproperty = "this is dynamically set"
~~~

#### Writing with files

~~~
file_stream = open('file.txt', 'w')         # mode w overrites the existing file, a appends to an existing file
file_stream.write("Write something"
file_stream.close()
~~~

#### Reading from files

~~~
file_stream = open('file.txt', 'r')
print(file_stream.readline())
file_stream.close()
~~~

#### Checking Types

~~~
number = 123
if not isinstance(number, int) ...      # return true or false depending if the variable is an instance consumable of the function
isinstance("this is text", str) ...     # return true
isinstance(True, bool) ...              # retrun true
isinstance(True, int) ...               # !! return true, boolean is considered a sub instance of integer
isinstance(2.4, float) ...              # return true
~~~

#### Exceptions

~~~
try:
  schedule_file = open('schedule.txt', 'r')
except FileNotFoundError as err:
  print(err)
~~~

#### Regex

~~~
import re

updatedsample = re.sub("regexpatter", "replacementtext", "sample")
~~~

Another way to use regex

~~~
parm = "some string to search"
regexpression = '(.*)\/(.*)'
compiled = re.compile(regexpression)
result = compiled.match(parm)
~~~

Find all matches in text

~~~
import re

re.findall('[a-z]', 'ab12cd')     # ['a', 'b', 'c', 'd']
~~~

[Read more](https://docs.python.org/2/library/re.html#re.RegexObject.search)  

#### Sets

~~~
mylist = [1, 2, 3, 4, 1, 2, 3, 4]
myset = set(mylist)                 # 1, 2, 3, 4
back_to_list = list(myset)          # converts set to list
~~~

#### Map

~~~
items = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x**2, items))
~~~

#### Modules

~~~
pip install modulename
~~~

#### Counting

~~~
print collections.Counter(['a', 'b', 'c', 'a', 'b', 'b'])

c = collections.Counter('abcdaab')
for letter in 'abcde':
    print '%s : %d' % (letter, c[letter])
~~~

[Read more](https://pymotw.com/2/collections/counter.html)

#### Method Parameters

Handle variable length method parameters

~~~
def doSomething(*multiple):
  params = list(multiple)           # 1, 2, 3
  return params

doSomething(1, 2, 3)
~~~

#### Permutations

~~~
>>> import itertools
>>> for p in itertools.permutations('ABCD'):
...     print(p)

('A', 'B', 'C', 'D')
('A', 'B', 'D', 'C')
('A', 'C', 'B', 'D')
('A', 'C', 'D', 'B')
('A', 'D', 'B', 'C')
('A', 'D', 'C', 'B')
('B', 'A', 'C', 'D')
('B', 'A', 'D', 'C')
('B', 'C', 'A', 'D')
('B', 'C', 'D', 'A')
('B', 'D', 'A', 'C')
('B', 'D', 'C', 'A')
('C', 'A', 'B', 'D')
('C', 'A', 'D', 'B')
('C', 'B', 'A', 'D')
('C', 'B', 'D', 'A')
('C', 'D', 'A', 'B')
('C', 'D', 'B', 'A')
('D', 'A', 'B', 'C')
('D', 'A', 'C', 'B')
('D', 'B', 'A', 'C')
('D', 'B', 'C', 'A')
('D', 'C', 'A', 'B')
('D', 'C', 'B', 'A')
~~~

#### Finding the most common elements in an iterable

~~~
# collections.Counter lets you find the most common
# elements in an iterable:

>>> import collections
>>> c = collections.Counter('helloworld')

>>> c
Counter({'l': 3, 'o': 2, 'e': 1, 'd': 1, 'h': 1, 'r': 1, 'w': 1})

>>> c.most_common(3)
[('l', 3), ('o', 2), ('e', 1)]
~~~

#### Python List Comprehension

~~~
# Python's list comprehensions are awesome.

vals = [expression 
        for value in collection 
        if condition]

# This is equivalent to:

vals = []
for value in collection:
    if condition:
        vals.append(expression)

# Example:

>>> even_squares = [x * x for x in range(10) if not x % 2]
>>> even_squares
[0, 4, 16, 36, 64]
~~~

#### In Place Swapping

~~~
# Why Python Is Great:
# In-place value swapping

# Let's say we want to swap
# the values of a and b...
a = 23
b = 42

# The "classic" way to do it
# with a temporary variable:
tmp = a
a = b
b = tmp

# Python also lets us
# use this short-hand:
a, b = b, a
~~~

### Class Methods, Instance Methods & Static Methos

~~~
# @classmethod vs @staticmethod vs "plain" methods
# What's the difference?

class MyClass:
    def method(self):
        """
        Instance methods need a class instance and
        can access the instance through `self`.
        """
        return 'instance method called', self

    @classmethod
    def classmethod(cls):
        """
        Class methods don't need a class instance.
        They can't access the instance (self) but
        they have access to the class itself via `cls`.
        """
        return 'class method called', cls

    @staticmethod
    def staticmethod():
        """
        Static methods don't have access to `cls` or `self`.
        They work like regular functions but belong to
        the class's namespace.
        """
        return 'static method called'

# All methods types can be
# called on a class instance:
>>> obj = MyClass()
>>> obj.method()
('instance method called', <MyClass instance at 0x1019381b8>)
>>> obj.classmethod()
('class method called', <class MyClass at 0x101a2f4c8>)
>>> obj.staticmethod()
'static method called'

# Calling instance methods fails
# if we only have the class object:
>>> MyClass.classmethod()
('class method called', <class MyClass at 0x101a2f4c8>)
>>> MyClass.staticmethod()
'static method called'
>>> MyClass.method()
TypeError: 
    "unbound method method() must be called with MyClass "
    "instance as first argument (got nothing instead)"
~~~

#### References

- [Video - What does it take to be an expert in Python?](https://youtu.be/7lmCu8wz8ro)  
