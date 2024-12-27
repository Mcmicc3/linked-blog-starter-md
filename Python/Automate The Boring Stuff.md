
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