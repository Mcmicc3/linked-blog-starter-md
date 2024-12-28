
## Basic Python Operators
|**Operator**|**Operation**|**Example**|**Evaluates to . . .**|
|---|---|---|---|
|**|Exponent|2 ** 3|8|
|%|Modulus/remainder|22 % 8|6|
|//|Integer division/floored quotient|22 // 8|2|
|/|Division|22 / 8|2.75|
|*|Multiplication|3 * 5|15|
|-|Subtraction|5 - 2|3|
|+|Addition|2 + 2|4|


## String Naming Conventions
|**Valid variable names**|**Invalid variable names**|
|---|---|
|current_balance|current-balance (hyphens are not allowed)|
|currentBalance|current balance (spaces are not allowed)|
|account4|4account (can’t begin with a number)|
|_42|42 (can’t begin with a number)|
|TOTAL_SUM|TOTAL_$UM (special characters like $ are not allowed)|
|hello|'hello' (special characters like ' are not allowed)|

|**Operator**|**Meaning**|
|---|---|
|==|Equal to|
|!=|Not equal to|
|<|Less than|
|>|Greater than|
|<=|Less than or equal to|
|>=|Greater than or equal to|

**Table 2-2:** The and Operator’s Truth Table

| **Expression**  | **Evaluates to . . .** |
| --------------- | ---------------------- |
| True and True   | True                   |
| True and False  | False                  |
| False and True  | False                  |
| False and False | False                  |

**Table 2-3:** The or Operator’s Truth Table

| **Expression** | **Evaluates to . . .** |
| -------------- | ---------------------- |
| True or True   | True                   |
| True or False  | True                   |
| False or True  | True                   |
| False or False | False                  |

**Table 2-4:** The not Operator’s Truth Table

| **Expression** | **Evaluates to . . .** |
| -------------- | ---------------------- |
| not True       | False                  |
| not False      | True                   |

**Table 4-1:** The Augmented Assignment Operators

| **Augmented assignment statement** | **Equivalent assignment statement** |
| ---------------------------------- | ----------------------------------- |
| spam += 1                          | spam = spam + 1                     |
| spam -= 1                          | spam = spam - 1                     |
| spam *= 1                          | spam = spam * 1                     |
| spam /= 1                          | spam = spam / 1                     |
| spam %= 1                          | spam = spam % 1                     |

**Table 6-1:** Escape Characters

| **Escape character** | **Prints as**        |
| -------------------- | -------------------- |
| \'                   | Single quote         |
| \"                   | Double quote         |
| \t                   | Tab                  |
| \n                   | Newline (line break) |
| \\                   | Backslash            |

# Loops
###### Break Statements in While loops
``` Python
➊ while True:  
       print('Please type your name.')  
    ➋ name = input()  
    ➌ if name == 'your name':  
        ➍ break  
➎ print('Thank you!')
```

###### Continue Statements in While loops
Starts a loop back to the beginning

``` Python
 while True:  
      print('Who are you?')  
      name = input()  
    ➊ if name != 'Joe':  
        ➋ continue  
       print('Hello, Joe. What is the password? (It is a fish.)')  
    ➌ password = input()  
       if password == 'swordfish':  
        ➍ break  
➎ print('Access granted.')
```

**“TRUTHY” AND “FALSEY” VALUES**

Conditions will consider some values in other data types equivalent to True and False. When used in conditions, 0, 0.0, and '' (the empty string) are considered **False**, while all other values are considered True. For example, look at the following program:

##### **The Starting, Stopping, and Stepping Arguments to range()**

Some functions can be called with multiple arguments separated by a comma, and range() is one of them. This lets you change the integer passed to range() to follow any sequence of integers, including starting at a number other than zero.

The first argument will be where the for loop’s variable starts, and the second argument will be up to, *but not including, the number to stop at*.

``` python
for i in range(12, 16):  
    print(i)
```


The range() function can also be called with three arguments. The first two arguments will be the *start and stop* values, and the third will be the _step argument_. The step is the amount that the variable is increased by after each iteration.

``` python
for i in range(0, 10, 2):  
    print(i)
```

Negative values are also supported
``` python
for i in range(5, -1, -1):  
    print(i)
```


# Import
random
- Introduces random.randint()
```python
import random  
for i in range(5):  
    print(random.randint(1, 10))
```

 sys
- Introduces functions like shutting down the program
- Introduces sys.exit()
``` python
import sys  
  
while True:  
    print('Type exit to exit.')  
    response = input()  
    if response == 'exit':  
        sys.exit()  
    print('You typed ' + response + '.')
```

## **DON’T OVERWRITE MODULE NAMES**

When you save your Python scripts, take care not to give them a name that is used by one of Python’s modules, such as _random.py_, _sys.py_, _os.py_, or _math.py_. If you accidentally name one of your programs, say, _random.py_, and use an import random statement in another program, your program would import your _random.py_ file instead of Python’s random module. This can lead to errors such as AttributeError: module 'random' has no attribute 'randint', since your _random.py_ doesn’t have the functions that the real random module has. Don’t use the names of any built-in Python functions either, such as print() or input().

#### **_from import Statements_**

An alternative form of the import statement is composed of the from keyword, followed by the module name, the import keyword, and a star; for example, from random import *.

With this form of import statement, calls to functions in random will not need the random. prefix. However, using the full name makes for more readable code, so it is better to use the import random form of the statement.


# Functions

### **def Statements with Parameters**

When you call the print() or len() function, you pass them values, called _arguments_, by typing them between the parentheses. You can also define your own functions that accept arguments. Type this example into the file editor and save it as _helloFunc2.py_:

``` python
➊ def hello(name):  
    ➋ print('Hello, ' + name)  
  
➌ hello('Alice')  
   hello('Bob')
```

### **Return Values and return Statements**
When creating a function using the def statement, you can specify what the return value should be with a return statement. A return statement consists of the following:
``` python
➊ import random  
  
➋ def getAnswer(answerNumber):  
    ➌ if answerNumber == 1:  
           return 'It is certain'  
       elif answerNumber == 2:  
           return 'It is decidedly so'  
       elif answerNumber == 3:  
           return 'Yes'  
       elif answerNumber == 4:  
           return 'Reply hazy try again'  
       elif answerNumber == 5:  
           return 'Ask again later'  
       elif answerNumber == 6:  
           return 'Concentrate and ask again'  
       elif answerNumber == 7:  
           return 'My reply is no'  
       elif answerNumber == 8:  
           return 'Outlook not so good'  
       elif answerNumber == 9:  
           return 'Very doubtful'  
  
➍ r = random.randint(1, 9)  
➎ fortune = getAnswer(r)  
➏ print(fortune)
```

### **The None Value**

In Python, there is a value called None, which represents the absence of a value. The None value is the only value of the NoneType data type. (Other programming languages might call this value null, nil, or undefined.) Just like the Boolean True and False values, None must be typed with a capital _N_.

### **The end value**
You can set the end keyword argument to change the newline character to a different string. For example, if the code were this:

``` python
print('Hello', end='')  
print('World')
```
the output would look like this:
``` output
HelloWorld
```

### **The sep value**
Similarly, when you pass multiple string values to print(), the function will automatically separate them with a single space. Enter the following into the interactive shell:
``` python
print('cats', 'dogs', 'mice')  
cats dogs mice
```
But you could replace the default separating string by passing the sep keyword argument a different string. Enter the following into the interactive shell:
``` python
print('cats', 'dogs', 'mice', sep=',')  
cats,dogs,mice
```

### **The global Statement**

If you need to modify a global variable from within a function, use the **global statement**. If you have a line such as global eggs at the top of a function, it tells Python, “In this function, eggs refers to the global variable, so don’t create a local variable with this name.” For example, enter the following code into the file editor and save it as _globalStatement.py_:

``` python
def spam():  
  ➊ global eggs  
  ➋ eggs = 'spam'  
  
eggs = 'global'  
spam()  
print(eggs)

Output: spam
```

###### Example of changing a global variable through a global statement
``` Python
def spam():  
  ➊ global eggs  
     eggs = 'spam' # this is the global  
  
def bacon():  
  ➋ eggs = 'bacon' # this is a local  
  
def ham():  
  ➌ print(eggs) # this is the global  
  
eggs = 42 # this is the global  
spam()  
print(eggs)
```

### **Exception Handling**
``` python
def spam(divideBy):  
    try:  
        return 42 / divideBy  
    except ZeroDivisionError:  
        print('Error: Invalid argument.')  
  
print(spam(2))  
print(spam(12))  
print(spam(0))  
print(spam(1))
```


# Lists

### **Lists example**
``` python
   >>> [1, 2, 3]  
   [1, 2, 3]  
   >>> ['cat', 'bat', 'rat', 'elephant']  
   ['cat', 'bat', 'rat', 'elephant']  
   >>> ['hello', 3.1415, True, None, 42]  
   ['hello', 3.1415, True, None, 42]  
➊ >>> spam = ['cat', 'bat', 'rat', 'elephant']  
   >>> spam  
   ['cat', 'bat', 'rat', 'elephant']
```

### **More Examples**
``` python
   >>> spam = ['cat', 'bat', 'rat', 'elephant']  
   >>> spam[0]  
   'cat'  
   >>> spam[1]  
   'bat'  
   >>> spam[2]  
   'rat'  
   >>> spam[3]  
   'elephant'  
   >>> ['cat', 'bat', 'rat', 'elephant'][3]  
   'elephant'  
➊ >>> 'Hello, ' + spam[0]  
➋ 'Hello, cat'  
   >>> 'The ' + spam[1] + ' ate the ' + spam[0] + '.'  
   'The bat ate the cat.'
```

**Note:** Index's only accept integers.
#### **_Getting Individual Values in a List with Indexes_**
Lists can also contain other list values. The values in these lists of lists can be accessed using multiple indexes, like so:

``` python
>>> spam = [['cat', 'bat'], [10, 20, 30, 40, 50]]  
>>> spam[0]  
['cat', 'bat']  
>>> spam[0][1]  
'bat'  
>>> spam[1][4]  
50
```

The first index dictates which list value to use, and the second indicates the value within the list value. For example, spam[0][1] prints 'bat', the second value in the first list. If you only use one index, the program will print the full list value at that index.

#### **_Negative Indexes_**
``` python
>>> spam = ['cat', 'bat', 'rat', 'elephant']  
>>> spam[-1]  
'elephant'  
>>> spam[-3]  
'bat'  
>>> 'The ' + spam[-1] + ' is afraid of the ' + spam[-3] + '.'  
'The elephant is afraid of the bat.'
```

#### **_Getting a List from Another List with Slices_**
In a slice, the first integer is the index where the slice starts. The second integer is the index where the slice ends. A slice goes up to, but will not include, the value at the second index. A slice evaluates to a new list value. Enter the following into the interactive shell:

``` python
>>> spam = ['cat', 'bat', 'rat', 'elephant']  
>>> spam[0:4]  
['cat', 'bat', 'rat', 'elephant']  
>>> spam[1:3]  
['bat', 'rat']  
>>> spam[0:-1]  
['cat', 'bat', 'rat']
```

As a shortcut, you can leave out one or both of the indexes on either side of the colon in the slice. Leaving out the first index is the same as using 0, or the beginning of the list. Leaving out the second index is the same as using the length of the list, which will slice to the end of the list. Enter the following into the interactive shell:

``` python
>>> spam = ['cat', 'bat', 'rat', 'elephant']  
>>> spam[:2]  
['cat', 'bat']  
>>> spam[1:]  
['bat', 'rat', 'elephant']  
>>> spam[:]  
['cat', 'bat', 'rat', 'elephant']
```

#### **_Getting a List’s Length with the len() Function_**
``` python
>>> spam = ['cat', 'dog', 'moose']  
>>> len(spam)  
3
```

#### **_Changing Values in a List with Indexes_**
``` python
>>> spam = ['cat', 'bat', 'rat', 'elephant']  
>>> spam[1] = 'aardvark'  
>>> spam  
['cat', 'aardvark', 'rat', 'elephant']  
>>> spam[2] = spam[1]  
>>> spam  
['cat', 'aardvark', 'aardvark', 'elephant']  
>>> spam[-1] = 12345  
>>> spam  
['cat', 'aardvark', 'aardvark', 12345]
```

#### **_List Concatenation and List Replication_**
``` python
>>> [1, 2, 3] + ['A', 'B', 'C']  
[1, 2, 3, 'A', 'B', 'C']  
>>> ['X', 'Y', 'Z'] * 3  
['X', 'Y', 'Z', 'X', 'Y', 'Z', 'X', 'Y', 'Z']  
>>> spam = [1, 2, 3]  
>>> spam = spam + ['A', 'B', 'C']  
>>> spam  
[1, 2, 3, 'A', 'B', 'C']
```

#### **_Removing Values from Lists with del Statements_**
``` python
>>> spam = ['cat', 'bat', 'rat', 'elephant']  
>>> del spam[2]  
>>> spam  
['cat', 'bat', 'elephant']  
>>> del spam[2]  
>>> spam  
['cat', 'bat']
```

### Example of creating a list during execution
``` python
catNames = []  
while True:  
    print('Enter the name of cat ' + str(len(catNames) + 1) +  
      ' (Or enter nothing to stop.):')  
    name = input()  
    if name == '':  
        break  
    catNames = catNames + [name]  # list concatenation  
print('The cat names are:')  
for name in catNames:  
    print('  ' + name)
```

#### **_Using for Loops with Lists_**
A common Python technique is to use range(len(someList)) with a for loop to iterate over the indexes of a list. For example, enter the following into the interactive shell:

``` python
>>> supplies = ['pens', 'staplers', 'flamethrowers', 'binders']  
>>> for i in range(len(supplies)):  
...     print('Index ' + str(i) + ' in supplies is: ' + supplies[i])  
  
Index 0 in supplies is: pens  
Index 1 in supplies is: staplers  
Index 2 in supplies is: flamethrowers  
Index 3 in supplies is: binders
```

Using range(len(supplies)) in the previously shown for loop is handy because the code in the loop can access the index (as the variable i) and the value at that index (as supplies[i]). Best of all, range(len(supplies)) will iterate through all the indexes of supplies, no matter how many items it contains.

#### **_The in and not in Operators_**

You can determine whether a value is or isn’t in a list with the in and not in operators. Like other operators, in and not in are used in expressions and connect two values: a value to look for in a list and the list where it may be found. These expressions will evaluate to a Boolean value. Enter the following into the interactive shell:

``` python
>>> 'howdy' in ['hello', 'hi', 'howdy', 'heyas']  
True  
>>> spam = ['hello', 'hi', 'howdy', 'heyas']  
>>> 'cat' in spam  
False  
>>> 'howdy' not in spam  
False  
>>> 'cat' not in spam  
True
```

the following program lets the user type in a pet name and then checks to see whether the name is in a list of pets. Open a new file editor window, enter the following code, and save it as _myPets.py_:

``` python
myPets = ['Zophie', 'Pooka', 'Fat-tail']  
print('Enter a pet name:')  
name = input()  
if name not in myPets:  
    print('I do not have a pet named ' + name)  
else:  
    print(name + ' is my pet.')
```

#### **_The Multiple Assignment Trick_**

The _multiple assignment trick_ (technically called _tuple unpacking_) is a shortcut that lets you assign multiple variables with the values in a list in one line of code. So instead of doing this:

``` python
>>> cat = ['fat', 'gray', 'loud']  
>>> size = cat[0]  
>>> color = cat[1]  
>>> disposition = cat[2]
```

you could type this line of code:
``` python
>>> cat = ['fat', 'gray', 'loud']  
>>> size, color, disposition = cat
```

The number of variables and the length of the list must be exactly equal, or Python will give you a ValueError:

``` python
>>> cat = ['fat', 'gray', 'loud']  
>>> size, color, disposition, name = cat  
Traceback (most recent call last):  
  File "<pyshell#84>", line 1, in <module>  
    size, color, disposition, name = cat  
ValueError: not enough values to unpack (expected 4, got 3)
```

#### **_Using the enumerate() Function with Lists_**

Instead of using the range(len(someList)) technique with a for loop to obtain the integer index of the items in the list, you can call the enumerate() function instead. On each iteration of the loop, enumerate() will return two values: the index of the item in the list, and the item in the list itself. For example, this code is equivalent to the code in the “[Using for Loops with Lists](https://learning.oreilly.com/library/view/automate-the-boring/9781098122584/xhtml/ch04.xhtml#ch04lev2sec8)” on [page 84](https://learning.oreilly.com/library/view/automate-the-boring/9781098122584/xhtml/ch04.xhtml#page_84):

``` python
>>> supplies = ['pens', 'staplers', 'flamethrowers', 'binders']  
>>> for index, item in enumerate(supplies):  
...     print('Index ' + str(index) + ' in supplies is: ' + item)  
  
Index 0 in supplies is: pens  
Index 1 in supplies is: staplers  
Index 2 in supplies is: flamethrowers  
Index 3 in supplies is: binders
```
The enumerate() function is useful if you need both the item and the item’s index in the loop’s block.

#### **_Using the random.choice() and random.shuffle() Functions with Lists_**

The random module has a couple functions that accept lists for arguments. The random.choice() function will *return a randomly selected item* from the list. Enter the following into the interactive shell:

``` python 
>>> import random  
>>> pets = ['Dog', 'Cat', 'Moose']  
>>> random.choice(pets)  
'Dog'  
>>> random.choice(pets)  
'Cat'  
>>> random.choice(pets)  
'Cat'
```

The random.shuffle() function will *reorder the items in a list*. This function modifies the list in place, rather than returning a new list. Enter the following into the interactive shell:

``` python
>>> import random  
>>> people = ['Alice', 'Bob', 'Carol', 'David']  
>>> random.shuffle(people)  
>>> people  
['Carol', 'David', 'Alice', 'Bob']  
>>> random.shuffle(people)  
>>> people  
['Alice', 'David', 'Bob', 'Carol']
```

### **Augmented Assignment Operators**
``` python
>>> spam = 42  
>>> spam += 1  
>>> spam  
43
```

There are augmented assignment operators for the +, -, *, /, and % operators, described in [Table 4-1](https://learning.oreilly.com/library/view/automate-the-boring/9781098122584/xhtml/ch04.xhtml#ch04tab01).

**Table 4-1:** The Augmented Assignment Operators

|**Augmented assignment statement**|**Equivalent assignment statement**|
|---|---|
|spam += 1|spam = spam + 1|
|spam -= 1|spam = spam - 1|
|spam *= 1|spam = spam * 1|
|spam /= 1|spam = spam / 1|
|spam %= 1|spam = spam % 1|
The += operator can also do string and list concatenation, and the *= operator can do string and list replication. Enter the following into the interactive shell:

``` python 
>>> spam = 'Hello,'  
>>> spam += ' world!'  
>>> spam  
'Hello world!'  
>>> bacon = ['Zophie']  
>>> bacon *= 3  
>>> bacon  
['Zophie', 'Zophie', 'Zophie']
```

#### **_Finding a Value in a List with the index() Method_**

List values have an index() method that can be passed a value, and if that value exists in the list, the index of the value is returned. If the value isn’t in the list, then Python produces a ValueError error. Enter the following into the interactive shell:

``` python
>>> spam = ['hello', 'hi', 'howdy', 'heyas']  
>>> spam.index('hello')  
0  
>>> spam.index('heyas')  
3  
>>> spam.index('howdy howdy howdy')  
Traceback (most recent call last):  
  File "<pyshell#31>", line 1, in <module>  
    spam.index('howdy howdy howdy')  
ValueError: 'howdy howdy howdy' is not in list
```

When there are duplicates of the value in the list, the index of its first appearance is returned. Enter the following into the interactive shell, and notice that index() returns 1, not 3:

``` python 
>>> spam = ['Zophie', 'Pooka', 'Fat-tail', 'Pooka']  
>>> spam.index('Pooka')  
1
```

#### **_Adding Values to Lists with the append() and insert() Methods_**
``` python
>>> spam = ['cat', 'dog', 'bat']  
>>> spam.append('moose')  
>>> spam  
['cat', 'dog', 'bat', 'moose']
```

Insert

``` python
>>> spam = ['cat', 'dog', 'bat']  
>>> spam.insert(1, 'chicken')  
>>> spam  
['cat', 'chicken', 'dog', 'bat']
```

#### **_Removing Values from Lists with the remove() Method_**

The remove() method is passed the value to be removed from the list it is called on. Enter the following into the interactive shell:

``` python
>>> spam = ['cat', 'bat', 'rat', 'elephant']  
>>> spam.remove('bat')  
>>> spam  
['cat', 'rat', 'elephant']
```

If the value appears multiple times in the list, only the first instance of the value will be removed. Enter the following into the interactive shell:

``` python
>>> spam = ['cat', 'bat', 'rat', 'cat', 'hat', 'cat']  
>>> spam.remove('cat')  
>>> spam  
['bat', 'rat', 'cat', 'hat', 'cat']
```

The **del statement** is good to use when you *know the index* of the value you want to remove from the list. The **remove() method** is useful when you *know the value* you want to remove from the list.

#### **_Sorting the Values in a List with the sort() Method_**

Lists of number values or lists of strings can be sorted with the sort() method. For example, enter the following into the interactive shell:

``` python 
>>> spam = [2, 5, 3.14, 1, -7]  
>>> spam.sort()  
>>> spam  
[-7, 1, 2, 3.14, 5]  
>>> spam = ['ants', 'cats', 'dogs', 'badgers', 'elephants']  
>>> spam.sort()  
>>> spam  
['ants', 'badgers', 'cats', 'dogs', 'elephants']
```

You can also pass True for the reverse keyword argument to have sort() sort the values in reverse order. Enter the following into the interactive shell:

``` python 
>>> spam.sort(reverse=True)  
>>> spam  
['elephants', 'dogs', 'cats', 'badgers', 'ants']
```

sort() uses “ASCIIbetical order” rather than actual alphabetical order for sorting strings. This means *uppercase letters come before lowercase letters*. Therefore, the lowercase _a_ is sorted so that it comes _after_ the uppercase _Z_. For an example, enter the following into the interactive shell:

If you need to sort the values in regular alphabetical order, pass str.lower for the key keyword argument in the sort() method call.

``` python
>>> spam = ['a', 'z', 'A', 'Z']  
>>> spam.sort(key=str.lower)  
>>> spam  
['a', 'A', 'z', 'Z']
```

#### **_Reversing the Values in a List with the reverse() Method_**

If you need to quickly reverse the order of the items in a list, you can call the reverse() list method. Enter the following into the interactive shell:

``` python
>>> spam = ['cat', 'dog', 'moose']  
>>> spam.reverse()  
>>> spam  
['moose', 'dog', 'cat']
```

### **Indentation**
You can also split up a single instruction across multiple lines using the \ _line continuation character_ at the end. Think of \ as saying, “This instruction continues on the next line.” The indentation on the line after a \ line continuation is not significant. For example, the following is valid Python code:

``` python
print('Four score and seven ' + \  
      'years ago...')
```

### **Sequence Data Types**

Lists aren’t the only data types that represent ordered sequences of values. For example, strings and lists are actually similar if you consider a string to be a “list” of single text characters. The Python sequence data types include lists, strings, range objects returned by range(), and tuples (explained in the “[The Tuple Data Type](https://learning.oreilly.com/library/view/automate-the-boring/9781098122584/xhtml/ch04.xhtml#ch04lev2sec19)” on [page 96](https://learning.oreilly.com/library/view/automate-the-boring/9781098122584/xhtml/ch04.xhtml#page_96)). Many of the things you can do with lists can also be done with strings and other values of sequence types: indexing; slicing; and using them with for loops, with len(), and with the in and not in operators. To see this, enter the following into the interactive shell:

``` python
>>> name = 'Zophie'  
>>> name[0]  
'Z'  
>>> name[-2]  
'i'  
>>> name[0:4]  
'Zoph'  
>>> 'Zo' in name  
True  
>>> 'z' in name  
False  
>>> 'p' not in name  
False  
>>> for i in name:  
...     print('* * * ' + i + ' * * *')  
  
* * * Z * * *  
* * * o * * *  
* * * p * * *  
* * * h * * *  
* * * i * * *  
* * * e * * *
```

#### **_Mutable and Immutable Data Types_**

But lists and strings are different in an important way. A list value is a _mutable_ data type: it can have values added, removed, or changed. However, a string is _immutable_: it cannot be changed. Trying to reassign a single character in a string results in a TypeError error, as you can see by entering the following into the interactive shell:

``` python
>>> name = 'Zophie a cat'  
>>> name[7] = 'the'  
Traceback (most recent call last):  
  File "<pyshell#50>", line 1, in <module>  
    name[7] = 'the'  
TypeError: 'str' object does not support item assignment
```

The proper way to “mutate” a string is to use slicing and concatenation to build a _new_ string by copying from parts of the old string. Enter the following into the interactive shell:

``` python
>>> name = 'Zophie a cat'  
>>> newName = name[0:7] + 'the' + name[8:12]  
>>> name  
'Zophie a cat'  
>>> newName  
'Zophie the cat'
```

We used [0:7] and [8:12] to refer to the characters that we don’t wish to replace. Notice that the original 'Zophie a cat' string is not modified, because strings are immutable.

#### **_The Tuple Data Type_**

The _tuple_ data type is almost identical to the list data type, except in two ways. First, tuples are typed with parentheses, ( and ), instead of square brackets, [ and ]. For example, enter the following into the interactive shell:

``` python
>>> eggs = ('hello', 42, 0.5)  
>>> eggs[0]  
'hello'  
>>> eggs[1:3]  
(42, 0.5)  
>>> len(eggs)  
3
```

If you have only one value in your tuple, you can indicate this by placing a trailing comma after the value inside the parentheses. Otherwise, Python will think you’ve just typed a value inside regular parentheses. The comma is what lets Python know this is a tuple value. (Unlike some other programming languages, it’s fine to have a trailing comma after the last item in a list or tuple in Python.) Enter the following type() function calls into the interactive shell to see the distinction:

``` python
>>> type(('hello',))  
<class 'tuple'>  
>>> type(('hello'))  
<class 'str'>
```

#### **_Converting Types with the list() and tuple() Functions_**

Just like how str(42) will return '42', the string representation of the integer 42, the functions list() and tuple() will return list and tuple versions of the values passed to them. Enter the following into the interactive shell, and notice that the return value is of a different data type than the value passed:

``` python
>>> tuple(['cat', 'dog', 5])  
('cat', 'dog', 5)  
>>> list(('cat', 'dog', 5))  
['cat', 'dog', 5]  
>>> list('hello')  
['h', 'e', 'l', 'l', 'o']
```

Converting a tuple to a list is handy if you need a mutable version of a tuple value.

### **References**
lists don’t work this way, because list values can change; that is, lists are _mutable_. Here is some code that will make this distinction easier to understand. Enter this into the interactive shell:

``` python
➊ >>> spam = [0, 1, 2, 3, 4, 5]  
➋ >>> cheese = spam # The reference is being copied, not the list.  
➌ >>> cheese[1] = 'Hello!' # This changes the list value.  
   >>> spam  
   [0, 'Hello!', 2, 3, 4, 5]  
   >>> cheese # The cheese variable refers to the same list.  
   [0, 'Hello!', 2, 3, 4, 5]
```

This might look odd to you. The code touched only the cheese list, but it seems that both the cheese and spam lists have changed.

When you create the list ➊, *you assign a reference to it in the spam variable*. But the next line ➋ *copies only the list reference* in spam to cheese, *not the list value itself*. This means the *values stored in spam and cheese now both refer to the same list*. There is only one underlying list because the *list itself was never actually copied.* So when you modify the first element of cheese ➌, you are modifying the same list that spam refers to.

#### **_Identity and the id() Function_**
Using the ID function to see which location in memory a variable is referrencing
``` python
>>> bacon = 'Hello'  
>>> id(bacon)  
44491136  
>>> bacon += ' world!' # A new string is made from 'Hello' and ' world!'.  
>>> id(bacon) # bacon now refers to a completely different string.  
44609712
```

However, lists can be modified because they are mutable objects. The append() method doesn’t create a new list object; it changes the existing list object. We call this “modifying the object _in-place._”

``` python
>>> eggs = ['cat', 'dog'] # This creates a new list.  
>>> id(eggs)  
35152584  
>>> eggs.append('moose') # append() modifies the list "in place".  
>>> id(eggs) # eggs still refers to the same list as before.  
35152584  
>>> eggs = ['bat', 'rat', 'cow'] # This creates a new list, which has a new  
identity.  
>>> id(eggs) # eggs now refers to a completely different list.  
44409800
```

#### **_The copy Module’s copy() and deepcopy() Functions_**

Although passing around references is often the handiest way to deal with lists and dictionaries, if the function modifies the list or dictionary that is passed, you may not want these changes in the original list or dictionary value. For this, Python provides a module named copy that provides both the copy() and deepcopy() functions. The first of these, copy.copy(), can be used to make a duplicate copy of a mutable value like a list or dictionary, not just a copy of a reference. Enter the following into the interactive shell:

``` python
>>> import copy  
>>> spam = ['A', 'B', 'C', 'D']  
>>> id(spam)  
44684232  
>>> cheese = copy.copy(spam)  
>>> id(cheese) # cheese is a different list with different identity.  
44685832  
>>> cheese[1] = 42  
>>> spam  
['A', 'B', 'C', 'D']  
>>> cheese  
['A', 42, 'C', 'D']
```

Now the spam and cheese variables refer to separate lists, which is why only the list in cheese is modified when you assign 42 at index 1. As you can see in [Figure 4-7](https://learning.oreilly.com/library/view/automate-the-boring/9781098122584/xhtml/ch04.xhtml#ch04fig07), the reference ID numbers are no longer the same for both variables because the variables refer to independent lists.

![image](https://learning.oreilly.com/api/v2/epubs/urn:orm:book:9781098122584/files/images/04fig07.jpg)

_Figure 4-7: cheese = copy.copy(spam) creates a second list that can be modified independently of the first._

If the list you need to copy contains lists, then use the copy.deepcopy() function instead of copy.copy(). The deepcopy() function will copy these inner lists as well.

# Dictionaries and Structuring Data

### **The Dictionary Data Type**

Like a list, a _dictionary_ is a mutable collection of many values. But unlike indexes for lists, indexes for dictionaries can use many different data types, not just integers. Indexes for dictionaries are called _keys_, and a key with its associated value is called a _key-value pair_.

In code, a dictionary is typed with braces, {}. Enter the following into the interactive shell:

``` PYTHON
>>> myCat = {'size': 'fat', 'color': 'gray', 'disposition': 'loud'}
```
This assigns a dictionary to the myCat variable. This dictionary’s keys are 'size', 'color', and 'disposition'. The values for these keys are 'fat', 'gray', and 'loud', respectively. You can access these values through their keys:

``` python
>>> myCat['size']  
'fat'  
>>> 'My cat has ' + myCat['color'] + ' fur.'  
'My cat has gray fur.'
```

Dictionaries can still use integer values as keys, just like lists use integers for indexes, but they do not have to start at 0 and can be any number.

``` python
>>> spam = {12345: 'Luggage Combination', 42: 'The Answer'}
```

#### **_Dictionaries vs. Lists_**

Unlike lists, items in dictionaries are unordered. The first item in a list named spam would be spam[0]. But there is no “first” item in a dictionary. While the order of items matters for determining whether two lists are the same, it does not matter in what order the key-value pairs are typed in a dictionary. Enter the following into the interactive shell:

``` python
>>> spam = ['cats', 'dogs', 'moose']  
>>> bacon = ['dogs', 'moose', 'cats']  
>>> spam == bacon  
False  
>>> eggs = {'name': 'Zophie', 'species': 'cat', 'age': '8'}  
>>> ham = {'species': 'cat', 'age': '8', 'name': 'Zophie'}  
>>> eggs == ham  
True
```

Because dictionaries are not ordered, they **can’t be sliced like lists**.

Though dictionaries are not ordered, the fact that you can have arbitrary values for the keys allows you to organize your data in powerful ways. Say you wanted your program to store data about your friends’ birthdays. You can use a dictionary with the names as keys and the birthdays as values. Open a new file editor window and enter the following code. Save it as _birthdays.py_.

```  python
➊ birthdays = {'Alice': 'Apr 1', 'Bob': 'Dec 12', 'Carol': 'Mar 4'}  
  
   while True:  
       print('Enter a name: (blank to quit)')  
       name = input()  
       if name == '':  
           break  
  
    ➋ if name in birthdays:  
        ➌ print(birthdays[name] + ' is the birthday of ' + name)  
       else:  
           print('I do not have birthday information for ' + name)  
           print('What is their birthday?')  
           bday = input()  
        ➍ birthdays[name] = bday  
           print('Birthday database updated.')
```

### **ORDERED DICTIONARIES IN PYTHON 3.7**

While they’re still not ordered and have no “first” key-value pair, dictionaries in Python 3.7 and later will remember the insertion order of their key-value pairs if you create a sequence value from them. For example, notice the order of items in the lists made from the eggs and ham dictionaries matches the order in which they were entered:

``` python
>>> eggs = {'name': 'Zophie', 'species': 'cat', 'age': '8'}  
>>> list(eggs)  
['name', 'species', 'age']  
>>> ham = {'species': 'cat', 'age': '8', 'name': 'Zophie'}  
>>> list(ham)  
['species', 'age', 'name']
```

#### **_The keys(), values(), and items() Methods_**

There are three dictionary methods that will return list-like values of the dictionary’s keys, values, or both keys and values: keys(), values(), and items(). The values returned by these methods are not true lists: they cannot be modified and do not have an append() method. But these data types (dict_keys, dict_values, and dict_items, respectively) _can_ be used in for loops. To see how these methods work, enter the following into the interactive shell:

``` python
>>> spam = {'color': 'red', 'age': 42}  
>>> for v in spam.values():  
...     print(v)  
  
red  
42
```

Here, a for loop iterates over each of the values in the spam dictionary. A for loop can also iterate over the keys or both keys and values:

``` python 
>>> for k in spam.keys():  
...     print(k)  
  
color  
age  
>>> for i in spam.items():  
...     print(i)  
  
('color', 'red')  
('age', 42)
```

Notice that the values in the dict_items value returned by the items() method are tuples of the key and value.

If you want a true list from one of these methods, pass its list-like return value to the list() function. Enter the following into the interactive shell:

``` python
>>> spam = {'color': 'red', 'age': 42}  
>>> spam.keys()  
dict_keys(['color', 'age'])  
>>> list(spam.keys())  
['color', 'age']
```

You can also use the multiple assignment trick in a for loop to assign the key and value to separate variables. Enter the following into the interactive shell:

``` python
>>> spam = {'color': 'red', 'age': 42}  
>>> for k, v in spam.items():  
...     print('Key: ' + k + ' Value: ' + str(v))  
  
Key: age Value: 42  
Key: color Value: red
```

#### **_Checking Whether a Key or Value Exists in a Dictionary_**

Recall from the previous chapter that the in and not in operators can check whether a value exists in a list. You can also use these operators to see whether a certain key or value exists in a dictionary. Enter the following into the interactive shell:

``` python
>>> spam = {'name': 'Zophie', 'age': 7}  
>>> 'name' in spam.keys()  
True  
>>> 'Zophie' in spam.values()  
True  
>>> 'color' in spam.keys()  
False  
>>> 'color' not in spam.keys()  
True  
>>> 'color' in spam  
False
```

#### **_The get() Method_**

It’s tedious to check whether a key exists in a dictionary before accessing that key’s value. Fortunately, dictionaries have a get() method that takes two arguments: the key of the value to retrieve and a fallback value to return if that key does not exist.

Enter the following into the interactive shell:

``` python
>>> picnicItems = {'apples': 5, 'cups': 2}  
>>> 'I am bringing ' + str(picnicItems.get('cups', 0)) + ' cups.'  
'I am bringing 2 cups.'  
>>> 'I am bringing ' + str(picnicItems.get('eggs', 0)) + ' eggs.'  
'I am bringing 0 eggs.'
```

Because there is no 'eggs' key in the picnicItems dictionary, the default value 0 is returned by the get() method. Without using get(), the code would have caused an error message, such as in the following example:

``` python
>>> picnicItems = {'apples': 5, 'cups': 2}  
>>> 'I am bringing ' + str(picnicItems['eggs']) + ' eggs.'  
Traceback (most recent call last):  
  File "<pyshell#34>", line 1, in <module>  
    'I am bringing ' + str(picnicItems['eggs']) + ' eggs.'  
KeyError: 'eggs'
```

#### **_The setdefault() Method_**

You’ll often have to set a value in a dictionary for a certain key only if that key does not already have a value. The code looks something like this:

``` python
spam = {'name': 'Pooka', 'age': 5}  
if 'color' not in spam:  
    spam['color'] = 'black'
```

The setdefault() method offers a way to do this in one line of code. The first argument passed to the method is the key to check for, and the second argument is the value to set at that key if the key does not exist. If the key does exist, the setdefault() method returns the key’s value. Enter the following into the interactive shell:

``` python
>>> spam = {'name': 'Pooka', 'age': 5}  
>>> spam.setdefault('color', 'black')  
'black'  
>>> spam  
{'color': 'black', 'age': 5, 'name': 'Pooka'}  
>>> spam.setdefault('color', 'white')  
'black'  
>>> spam  
{'color': 'black', 'age': 5, 'name': 'Pooka'}
```

### **Pretty Printing**

If you import the pprint module into your programs, you’ll have access to the pprint() and pformat() functions that will “pretty print” a dictionary’s values. This is helpful when you want a cleaner display of the items in a dictionary than what print() provides. Modify the previous _characterCount.py_ program and save it as _prettyCharacterCount.py_.

``` python 
import pprint  
message = 'It was a bright cold day in April, and the clocks were striking  
thirteen.'  
count = {}  
  
for character in message:  
    count.setdefault(character, 0)  
    count[character] = count[character] + 1  
  
pprint.pprint(count)
```

This time, when the program is run, the output looks much cleaner, with the keys sorted.

``` python
{' ': 13,  
 ',': 1,  
 '.': 1,  
 'A': 1,  
 'I': 1,  
 --snip--  
 't': 6,  
 'w': 2,  
 'y': 1}
```

If you want to obtain the prettified text as a string value instead of displaying it on the screen, call pprint.pformat() instead. These two lines are equivalent to each other:

``` python
pprint.pprint(someDictionaryValue)  
print(pprint.pformat(someDictionaryValue))
```

#### **_Nested Dictionaries and Lists_**

Modeling a tic-tac-toe board was fairly simple: the board needed only a single dictionary value with nine key-value pairs. As you model more complicated things, you may find you need dictionaries and lists that contain other dictionaries and lists. Lists are useful to contain an ordered series of values, and dictionaries are useful for associating keys with values. For example, here’s a program that uses a dictionary that contains other dictionaries of what items guests are bringing to a picnic. The totalBrought() function can read this data structure and calculate the total number of an item being brought by all the guests.

``` python
allGuests = {'Alice': {'apples': 5, 'pretzels': 12},  
             'Bob': {'ham sandwiches': 3, 'apples': 2},  
             'Carol': {'cups': 3, 'apple pies': 1}}  
  
def totalBrought(guests, item):  
    numBrought = 0  
  ➊ for k, v in guests.items():  
      ➋ numBrought = numBrought + v.get(item, 0)  
     return numBrought  
  
print('Number of things being brought:')  
print(' - Apples         ' + str(totalBrought(allGuests, 'apples')))  
print(' - Cups           ' + str(totalBrought(allGuests, 'cups')))  
print(' - Cakes          ' + str(totalBrought(allGuests, 'cakes')))  
print(' - Ham Sandwiches ' + str(totalBrought(allGuests, 'ham sandwiches')))  
print(' - Apple Pies     ' + str(totalBrought(allGuests, 'apple pies')))
```

The output of this program looks like this:

``` python 
 Number of things being brought:  
 - Apples 7  
 - Cups 3  
 - Cakes 0  
 - Ham Sandwiches 3  
 - Apple Pies 1
```


# Manipulating Strings
##### **Double Quotes**

Strings can begin and end with double quotes, just as they do with single quotes. One benefit of using double quotes is that the string can have a single quote character in it. Enter the following into the interactive shell:

``` python 
>>> spam = "That is Alice's cat."
```

Since the string begins with a double quote, Python knows that the single quote is part of the string and not marking the end of the string. However, if you need to use both single quotes and double quotes in the string, you’ll need to use escape characters.

Here's how to do it with an escape character

``` python
>>> spam = 'Say hi to Bob\'s mother.'
```

##### **Raw Strings**

You can place an r before the beginning quotation mark of a string to make it a raw string. A _raw string_ completely ignores all escape characters and prints any backslash that appears in the string. For example, enter the following into the interactive shell:

``` python
>>> print(r'That is Carol\'s cat.')  
That is Carol\'s cat.
```

Because this is a raw string, Python considers the backslash as part of the string and not as the start of an escape character. Raw strings are helpful if you are typing string values that contain many backslashes, such as the strings used for Windows file paths like *r'C:\Users\Al\Desktop'* or regular expressions described in the next chapter.

##### **Multiline Strings with Triple Quotes**

While you can use the \n escape character to put a newline into a string, it is often easier to use multiline strings. A multiline string in Python begins and ends with either three single quotes or three double quotes. Any quotes, tabs, or newlines in between the “triple quotes” are considered part of the string. Python’s indentation rules for blocks do not apply to lines inside a multiline string.

Open the file editor and write the following:

``` python 
print('''Dear Alice,  
  
Eve's cat has been arrested for catnapping, cat burglary, and extortion.  
  
Sincerely,  
Bob''')
```

Save this program as _catnapping.py_ and run it. The output will look like this:

``` python
Dear Alice,  
  
Eve's cat has been arrested for catnapping, cat burglary, and extortion.  
  
Sincerely,  
Bob
```


##### **Multiline Comments**

While the hash character (#) marks the beginning of a comment for the rest of the line, a multiline string is often used for comments that span multiple lines. The following is perfectly valid Python code:

``` python
"""This is a test Python program.  
Written by Al Sweigart al@inventwithpython.com  
  
This program was designed for Python 3, not Python 2.  
"""  
  
def spam():  
    """This is a multiline comment to help  
    explain what the spam() function does."""  
    print('Hello!')
```

#### **_Indexing and Slicing Strings_**
``` python
>>> spam = 'Hello, world!'  
>>> spam[0]  
'H'  
>>> spam[4]  
'o'  
>>> spam[-1]  
'!'  
>>> spam[0:5]  
'Hello'  
>>> spam[:5]  
'Hello'  
>>> spam[7:]  
'world!'
```

#### **_The in and not in Operators with Strings_**

The in and not in operators can be used with strings just like with list values. An expression with two strings joined using in or not in will evaluate to a Boolean True or False. Enter the following into the interactive shell:

``` python
>>> 'Hello' in 'Hello, World'  
True  
>>> 'Hello' in 'Hello'  
True  
>>> 'HELLO' in 'Hello, World'  
False  
>>> '' in 'spam'  
True  
>>> 'cats' not in 'cats and dogs'  
False
```

These expressions test whether the first string (the exact string, case-sensitive) can be found within the second string.

### **Putting Strings Inside Other Strings**

Putting strings inside other strings is a common operation in programming. So far, we’ve been using the + operator and string concatenation to do this:

``` python
>>> name = 'Al'  
>>> age = 4000  
>>> 'Hello, my name is ' + name + '. I am ' + str(age) + ' years old.'  
'Hello, my name is Al. I am 4000 years old.'
```

However, this requires a lot of tedious typing. A simpler approach is to use _string interpolation_, in which the %s operator inside the string acts as a marker to be replaced by values following the string. One benefit of string interpolation is that str() doesn’t have to be called to convert values to strings. Enter the following into the interactive shell:

``` python
>>> name = 'Al'  
>>> age = 4000  
>>> 'My name is %s. I am %s years old.' % (name, age)  
'My name is Al. I am 4000 years old.'
```

Python 3.6 introduced _f-strings_, which is similar to string interpolation except that braces are used instead of %s, with the expressions placed directly inside the braces. Like raw strings, f-strings have an f prefix before the starting quotation mark. Enter the following into the interactive shell:

``` python
>>> name = 'Al'  
>>> age = 4000  
>>> f'My name is {name}. Next year I will be {age + 1}.'  
'My name is Al. Next year I will be 4001.'
```

Remember to include the f prefix; otherwise, the braces and their contents will be a part of the string value:

``` python
>>> 'My name is {name}. Next year I will be {age + 1}.'  
'My name is {name}. Next year I will be {age + 1}.'
```

#### **_The upper(), lower(), isupper(), and islower() Methods_**

The upper() and lower() string methods return a new string where all the letters in the original string have been converted to uppercase or lowercase, respectively. Nonletter characters in the string remain unchanged. Enter the following into the interactive shell:

``` python
>>> spam = 'Hello, world!'  
>>> spam = spam.upper()  
>>> spam  
'HELLO, WORLD!'  
>>> spam = spam.lower()  
>>> spam  
'hello, world!'
```

The isupper() and islower() methods will return a Boolean True value if the string has at least one letter and all the letters are uppercase or lowercase, respectively. Otherwise, the method returns False. Enter the following into the interactive shell, and notice what each method call returns:

``` python
>>> spam = 'Hello, world!'  
>>> spam.islower()  
False  
>>> spam.isupper()  
False  
>>> 'HELLO'.isupper()  
True  
>>> 'abc12345'.islower()  
True  
>>> '12345'.islower()  
False  
>>> '12345'.isupper()  
False
```

#### **_The isX() Methods_**

Along with islower() and isupper(), there are several other string methods that have names beginning with the word _is_. These methods return a Boolean value that describes the nature of the string. Here are some common isX string methods:

isalpha() Returns True if the string consists only of letters and isn’t blank

isalnum() Returns True if the string consists only of letters and numbers and is not blank

isdecimal() Returns True if the string consists only of numeric characters and is not blank

isspace() Returns True if the string consists only of spaces, tabs, and newlines and is not blank

istitle() Returns True if the string consists only of words that begin with an uppercase letter followed by only lowercase letters

Enter the following into the interactive shell:

``` python
>>> 'hello'.isalpha()  
True  
>>> 'hello123'.isalpha()  
False  
>>> 'hello123'.isalnum()  
True  
>>> 'hello'.isalnum()  
True  
>>> '123'.isdecimal()  
True  
>>> '    '.isspace()  
True  
>>> 'This Is Title Case'.istitle()  
True  
>>> 'This Is Title Case 123'.istitle()  
True  
>>> 'This Is not Title Case'.istitle()  
False  
>>> 'This Is NOT Title Case Either'.istitle()  
False
```

Example of this code being used to validate user input:
``` python
while True:  
    print('Enter your age:')  
    age = input()  
    if age.isdecimal():  
        break  
    print('Please enter a number for your age.')  
  
while True:  
    print('Select a new password (letters and numbers only):')  
    password = input()  
    if password.isalnum():  
        break  
    print('Passwords can only have letters and numbers.')
```

#### **_The startswith() and endswith() Methods_**

The startswith() and endswith() methods return True if the string value they are called on begins or ends (respectively) with the string passed to the method; otherwise, they return False. Enter the following into the interactive shell:

``` python
>>> 'Hello, world!'.startswith('Hello')  
True  
>>> 'Hello, world!'.endswith('world!')  
True  
>>> 'abc123'.startswith('abcdef')  
False  
>>> 'abc123'.endswith('12')  
False  
>>> 'Hello, world!'.startswith('Hello, world!')  
True  
>>> 'Hello, world!'.endswith('Hello, world!')  
True
```

#### **_The join() and split() Methods_**

The join() method is useful when you have a list of strings that need to be joined together into a single string value. The join() method is called on a string, gets passed a list of strings, and returns a string. The returned string is the concatenation of each string in the passed-in list. For example, enter the following into the interactive shell:

``` python
>>> ', '.join(['cats', 'rats', 'bats'])  
'cats, rats, bats'  
>>> ' '.join(['My', 'name', 'is', 'Simon'])  
'My name is Simon'  
>>> 'ABC'.join(['My', 'name', 'is', 'Simon'])  
'MyABCnameABCisABCSimon'
```

Remember that join() is called on a string value and is passed a list value. (It’s easy to accidentally call it the other way around.) The split() method does the opposite: It’s called on a string value and returns a list of strings. Enter the following into the interactive shell:

``` python 
>>> 'My name is Simon'.split()  
['My', 'name', 'is', 'Simon']
```

By default, the string 'My name is Simon' is split wherever whitespace characters such as the space, tab, or newline characters are found. These whitespace characters are not included in the strings in the returned list. You can pass a delimiter string to the split() method to specify a different string to split upon. For example, enter the following into the interactive shell:

``` python
>>> 'MyABCnameABCisABCSimon'.split('ABC')  
['My', 'name', 'is', 'Simon']  
>>> 'My name is Simon'.split('m')  
['My na', 'e is Si', 'on']
```

A common use of split() is to split a multiline string along the newline characters. Enter the following into the interactive shell:

``` python
>>> spam = '''Dear Alice,  
How have you been? I am fine.  
There is a container in the fridge  
that is labeled "Milk Experiment."  
  
Please do not drink it.  
Sincerely,  
Bob'''  
>>> spam.split('\n')  
['Dear Alice,', 'How have you been? I am fine.', 'There is a container in the  
fridge', 'that is labeled "Milk Experiment."', '', 'Please do not drink it.',  
'Sincerely,', 'Bob']
```

Passing split() the argument '\n' lets us split the multiline string stored in spam along the newlines and return a list in which each item corresponds to one line of the string.

#### **_Splitting Strings with the partition() Method (HUH?)_**

The partition() string method can split a string into the text before and after a separator string. This method searches the string it is called on for the separator string it is passed, and returns a tuple of three substrings for the “before,” “separator,” and “after” substrings. Enter the following into the interactive shell:

``` python
>>> 'Hello, world!'.partition('w')  
('Hello, ', 'w', 'orld!')  
>>> 'Hello, world!'.partition('world')  
('Hello, ', 'world', '!')
```

If the separator string you pass to partition() occurs multiple times in the string that partition() calls on, the method splits the string only on the first occurrence:

``` python
>>> 'Hello, world!'.partition('o')  
('Hell', 'o', ', world!')
```

If the separator string can’t be found, the first string returned in the tuple will be the entire string, and the other two strings will be empty:

``` python
>>> 'Hello, world!'.partition('XYZ')  
('Hello, world!', '', '')
```

You can use the multiple assignment trick to assign the three returned strings to three variables:

``` python
>>> before, sep, after = 'Hello, world!'.partition(' ')  
>>> before  
'Hello,'  
>>> after  
'world!'
```

The partition() method is useful for splitting a string whenever you need the parts before, including, and after a particular separator string.

#### **_Justifying Text with the rjust(), ljust(), and center() Methods_**

The rjust() and ljust() string methods return a padded version of the string they are called on, with spaces inserted to justify the text. The first argument to both methods is an integer length for the justified string. Enter the following into the interactive shell:

``` python
>>> 'Hello'.rjust(10)  
'     Hello'  
>>> 'Hello'.rjust(20)  
'              Hello'  
>>> 'Hello, World'.rjust(20)  
'         Hello, World'  
>>> 'Hello'.ljust(10)  
'Hello     '
```

'Hello'.rjust(10) says that we want to right-justify 'Hello' in a string of total length 10. 'Hello' is five characters, so five spaces will be added to its left, giving us a string of 10 characters with 'Hello' justified right.

An optional second argument to rjust() and ljust() will specify a fill character other than a space character. Enter the following into the interactive shell:

``` python
>>> 'Hello'.rjust(20, '*')  
'***************Hello'  
>>> 'Hello'.ljust(20, '-')  
'Hello---------------'
```

The center() string method works like ljust() and rjust() but centers the text rather than justifying it to the left or right. Enter the following into the interactive shell:

``` python
>>> 'Hello'.center(20)  
'       Hello        '  
>>> 'Hello'.center(20, '=')  
'=======Hello========'
```

These methods are especially useful when you need to print tabular data that has correct spacing.

``` python
def printPicnic(itemsDict, leftWidth, rightWidth):  
    print('PICNIC ITEMS'.center(leftWidth + rightWidth, '-'))  
    for k, v in itemsDict.items():  
        print(k.ljust(leftWidth, '.') + str(v).rjust(rightWidth))  
  
picnicItems = {'sandwiches': 4, 'apples': 12, 'cups': 4, 'cookies': 8000}  
printPicnic(picnicItems, 12, 5)  
printPicnic(picnicItems, 20, 6)
```

results

``` python
---PICNIC ITEMS--  
sandwiches..    4  
apples......   12  
cups........    4  
cookies..... 8000  
-------PICNIC ITEMS-------  
sandwiches..........     4  
apples..............    12  
cups................     4  
cookies.............  8000
```

#### **_Removing Whitespace with the strip(), rstrip(), and lstrip() Methods_**

Sometimes you may want to strip off whitespace characters (space, tab, and newline) from the left side, right side, or both sides of a string. The strip() string method will return a new string without any whitespace characters at the beginning or end. The lstrip() and rstrip() methods will remove whitespace characters from the left and right ends, respectively. Enter the following into the interactive shell:

``` python 
>>> spam = '    Hello, World    '  
>>> spam.strip()  
'Hello, World'  
>>> spam.lstrip()  
'Hello, World    '  
>>> spam.rstrip()  
'    Hello, World'
```

Optionally, a string argument will specify which characters on the ends should be stripped. Enter the following into the interactive shell:

``` python
>>> spam = 'SpamSpamBaconSpamEggsSpamSpam'  
>>> spam.strip('ampS')  
'BaconSpamEggs'
```

Passing strip() the argument 'ampS' will tell it to strip occurrences of a, m, p, and capital S from the ends of the string stored in spam. The order of the characters in the string passed to strip() does not matter: strip('ampS') will do the same thing as strip('mapS') or strip('Spam').

