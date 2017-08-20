
# Introduction to Jupyter Notebook


For the next 10-15 minutes we're all going to go through the Jupyter Notebook interface and figure out exactly how it's used. 

Each of the "boxes" you can see here are called "cells", and these allow you to write and run code, or take notes. Every time you make a new cells it defaults to being a "code" cell, for programming. 

However, you'll notice that this section is just plain text. This is known as a "markdown" cell, and this can be used to take notes, or even to help format reports. You can change whether a cell is in the markdown or code format using the toggle bar up the top. 

There are also a range of keyboard shortcuts that allow you to easily perform a variety of actions on these cells. You can find these under the "help" menu item, or in the "command palette" (looks like a keyboard) on the side of command toggle bar. An external file for jupyter commands can be found on the [github](https://github.com/resbaz/introPython_July2017/blob/master/jupyterNotebook_Cheatsheet.pdf).

This is a markdown cell, before you "run" it

To "run" a cell, you can use the keyboard command Shift-Enter, or the control bar





```python

```

# Introduction to Python

Now that we're a bit more familiar with the Jupyter environment, let's play around with some Python

### Learning Objectives:
- Learn the basic numeric and string data types
- Type conversion
- Be able to apply type-specific functions to each of:
    - **Integers (int)**: 
        - Basic numeric functions: addition, subtraction, division, multiplication, power
        - Less common function: remainder/modulo, divide and floor
    - **Strings (str)**:
        - Joining two strings (concatentation), length (len), duplication
- Know how to assign something to a variable, and perform basic operations on it
    


```python
# Type in something

```

You may have noticed while playing around that 'running' a code cell usually gives you some errors. This is because the cell didn't contain any *commands* that the computer could recognise.

A computer is very much like a dog - it can only understand and obey the commands that it's been taught to recognise

![a dog](http://janfennellthedoglistener.com/static/cms/ConfusedDog.png "When you try to give you computer human words")


Python, the programming language, is essentially just a system of commands that lets you command the computer to do the tricks that you want it to do. Imagine that your computer is like a very well trained dog that you've adopted from the shelter, and now you need to learn what commands your computer-dog responds to. 


An example of a command that your computer understands is some very simple math. Let try to do some basic arithmetic


```python
# You can add and subtract numbers
(5 + 10) - 3
```




    12




```python
# Work with negative numbers
-5 + 2
```




    -3




```python
# As well as multiply and divide
3 * 4 / 2
```




    6.0




```python
# You can square numbers using the "power" command, **
2**2
```




    4




```python
# And even use a few different commands, like:

#Divide and floor, //
5//2
```




    2




```python
# and Modulo (a.k.a the remainder), %
# Think of this one as a "divide" function that returns you the amount left over after division
6%2
```




    0



Python uses the general BODMAS/PEMDAS rules when trying to decide which order to evaluate your statements in.

What do you think would happen here?


```python
5 + 4 / 2 * 5

```




    15.0



This was your first introduction to the **_numeric_** data types of Python. Namely, integers (int) and floats (floating point numbers, or decimals). You can do almost the same things with floats as you can with integers, except with greater precision. However, sometimes you *need* to know which data type you're working with. You can do this with a **function**, called `type()`.

We will learn more about functions later, but for now all you need to know is that a function allows you to perform specific, and often complicated, actions on your code or data. 

In this instance, `type()` will output the data type that you're working with.


```python
type(3)
```




    int




```python
type(2.0)
```




    float



##### Challenge

    first = 1.0
    second = "1"
    third = "1.1"

Which of the following will print 2.0? Note: there may be more than one right answer.

1. first + float(second)
2. float(second) + float(third)
3. first + int(third)
4. first + int(float(third))
5. int(first) + int(float(third))
6. 2.0 * second


```python

```


```python

```

### Strings
Another useful data type are *strings*. These are essentially text. You can tell Python that something is a string type by wrapping it in quotes marks


```python
"This is a string"
```




    'This is a string'




```python
'As is this'
```




    'As is this'




```python
# You can use either single or double quotes for strings - just be consistent!
'This is quite handy if I wanted to "quote" someone, eh?'
```




    'This is quite handy if I wanted to "quote" someone, eh?'




```python
type('This is too')
```




    str




```python
# What type of data is this?
type('3.56')
```




    str



Since it's not a numeric type, we can't do the same things to a string that we can to an int or float. But there are a few other things we can do instead!

An example of this is concatentation, or adding two strings together. Try adding your first name and last name


```python
#Example: "FirstName" + "Last Name"
#Try it yourself! What do you notice when you add two strings?
"My"+ "name"
```




    'Myname'



Oh no! That happened because Python doesn't automatically add in a space between two strings, which means that we have to do it ourselves. Let's try again.


```python
# We have two options, "FirstName " + "LastName"
"My " + "name"
```




    'My name'




```python
# Or "FirstName" + " " + "LastName"
"My" + " " + "name"
```




    'My name'



We can also multiply our strings by a number to duplicate it


```python
"Mine " * 5
```




    'Mine Mine Mine Mine Mine '



^

\* this reminds me a little of finding nemo\*
![seagulls shuouting mine](https://vignette3.wikia.nocookie.net/disney/images/9/99/Nemo-Seagulls_.jpg/revision/latest?cb=20110913023141)

There are also some great functions that you can apply to strings. An example of this is `len()`, which tells you how long your string is


```python
len("Give me a string")
```




    16




```python
len("Type")
```




    4



A couple of other string functions that are good to know are `upper()`, `lower()`, and `capitalize()`.

Unlike `type()` and `len()`, you actually use these in a slightly different way. This is because, while `upper()`, `lower()`, and `capitalize()` are functions, they can **ONLY** be used on strings. With these types of functions, we call them *methods* instead, and *methods* can be used with the `str.functionName()` format


```python
#Upper capitalises everything
"This".upper()
```




    'THIS'




```python
#While lower makes everything lower case
"examPlE of A StRinG".lower()
```




    'example of a string'




```python
#.capitalize() will capitalise the first letter
"examPlE of A StRinG".capitalize()
```




    'Example of a string'



_**Question**: what happens if you try to use these on an int?_


```python
3.lower()
```


      File "<ipython-input-83-85eda88e0154>", line 1
        3.lower()
              ^
    SyntaxError: invalid syntax
    


### Data Type Coercion

You can also convert different data types into another using *type coercion*.

For example, say that I've done some calculations to figure out how many people can fit into an elevator, and got a decimal number, like 3.14159265359. It doesn't make much sense to have 0.14159265359 of person, does it? So I would just want to convert this into an integer.


```python
# But be warned! This ALWAYS rounds down
int(3.14159265359),int(3.6)
```


```python
float(3)
```

Type conversion will only work where it makes sense to do so. Try to turn a string into a number


```python
int("35")
```


```python
#This won't work
int("int")
```


```python
# But this one is perfectly fine
str(1000000)
```

Similarly, certain functions won't work on certain data types. Try to take the `len()` of a number, for example


```python
len(3000000)
```

Dang! But I'd forgotten how many 0's were in a million! What if you turn that number into a string first?


```python
len(str(3000000))
```

_**Question:** What type of value is 3.25 + 4?_


```python

```

##### Challenge

What will these do? What will be the final data type in each case?_

1. `str(4.0)`
2. `int(str(4.0))`
3. `float(str(3.5))`
4. `int(float(str(3.2)))`


```python

```


```python

```


```python

```

##### Challenge
What type of value (integer, floating point number, or character string) would you use to represent each of the following? Try to come up with more than one good answer for each problem. For example, in # 1, when would counting days with a floating point variable make more sense than using an integer?

1. Number of days since the start of the year.
2. Time elapsed since the start of the year.
3. Serial number of a piece of lab equipment.
4. A lab specimen’s age.
5. Current population of a city.
6. Average population of a city over time.


```python

```


```python

```

### Variables

Some of these things are getting a bit lengthy. Could you imagine needing to type out the *same* numbers, and the *same* string every time you want to use it? What about if you wanted to do some math on the number? How are you going to save that number for later?

Simple! What we can do is assign these values to a variable. 

We can do this using the '=' sign. What this does is use Python to tell the computer to carve out a piece of memory somewhere, give it the name you told it to, and assign it a user-specified (i.e. by you) value. 


```python
# Makes "name", and gives it the value 'mine'
name = 'mine'

# tells the computer to find that piece of memory called "name", and then give it back to you
print(name)
```

This was your first introduction to the "print" function. Print statements take the data that you put into them, and then output it (as a string) to the consolecan be extremely useful for 


```python
# takes the value of name, adds something else to it, and then updates the old 'name' with the new value
name = "mine"
name = name + " " + "chips"
print(name)
```


```python
# You can use commas in print to add different elements together without adding your own spaces
# PLUS it auto-coerces data types to strings, AND removes those awkward 'quote' marks from output
print("Kahli","Flekac","Is","An", "Awesome", "Teacher", "x", 100)
```

But be careful! If you're writing a large number, you might be tempted to use commas. While this is "illegal" in Python, if you were to put it in a print statement then this happens:


```python
print(1,000,000)
```

This is an example of a semantic, or silent, error. Python has still _worked_ - it ran your code, and gave you a valid result...but it hasn't done what you intended it to do.

A new feature of Python 3 means that you _can_ use underscores when writing numbers. How exciting!


```python
print(1_000_000)
```

I can over-write this variable


```python
name = 'Q: Mine?'

print ("Before,",name)

name = "A: Nope!"

print("After,",name)
```

And even perform operations and functions on it


```python
number = 3

# What will be the answer here?
number**2 + 5
```


```python
str((number**2 + 5)/2)
```

I can also assign the results of an operation into a new variable too.


```python
number = 10
times = 3

example_operation = number * times

#What will this print out?
print(example_operation)
```


```python

```

And use it in a print statement just as I would any other data type


```python
temp_number = 4
```


```python
print("Temporary = " + str(temp_number))
```


```python

```

_**Question**: What is wrong with the following code?_


```python
primt "Hello world!'
```


```python

```

##### Optional Challenge 

You are given two positive integers, `a` and `b`, which each correspond to the sides of a right-angle triangle. 

Print the integer value corresponding to the square of the hypotenuse of that right triangle.


i.e. given sides `a` and `b`, print `c^2`
![image.png](attachment:image.png)

Hint: if `a = 3` and `b = 5`, then the answer = 34


```python
# This will randomly generate a value for a and b between 1 to 100
from numpy import random

a = random.randint(1,100)
b = random.randint(1,100)

# what do you need to do from here?



```

#### The dark art of variable Names:

Python has basically only three rules about naming variables:
- names you define must start with a letter (a-z,A-Z) or underscore (_) and can be followed by any number of letters, >digits (0-9), or underscores
- names you define cannot be the same as any of Python's reserved words (see below table)
- names are case-sensitive: 'YOU', 'you', 'You', and 'yOu' are all different names in Python
- Note that '-', '+', '*', and '/' are used by Python for defining operations on data and cannot be used in names


Also, try to make your variable names mean something. It can be very confusing for someone else reading your code (or even yourself, after a long break) if you write something filled with a number of different `temp` or `foo1`, `foo2`, etc variables.


| |Reserved | Words | |
| --- | --- | --- | --- | 
|False|True|None|and|
|as|assert|break|class|
|continue|class|del|def|
|if|else|elif|import|
|for|from|return|global|
|try|except|finally|raise|
|while|not|in|is|
|or|with|yield|lambda|
|pass|nonlocal| | |

##### Challenge

In this list of variable names, which ones are legal? Which ones are legal, but generally frowned upon? How could we make these better?

1. 76trombones = "big parade"
2. more$ = 1000000
3. class = "Computer Science 101"
4. Price_of_tea_in_china
5. my name = "Scooby Doo"
6. A_good_grade_is_A+




```python

```



#### Mini Challenge 1
Assign your team name, how many members you have, and your average (mean) age to three separate variables. Print these out on the same line in this format:

"Our team name is TeamName. We have X members and we are, on average, Y years old"


```python

```


```python

```


```python

```


```python

```


```python

```
