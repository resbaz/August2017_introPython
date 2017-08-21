
# Conditionals

In this session we are going to learn how to program your computer to make choices about which action it should perform


### Learning Objectives

- Write conditional statements including `if`, `elif`, and `else` branches
- Correctly evaluate expressions containing `and` and `or`
- Correctly write and interpret code containing nested conditionals


Conditionals allow you make the computer or program perform a certain action depending on particular conditions.

But to assess a condition, we first need to understand how we can test them.

These tests are usually done using "equality operators". Things like:

- `<`, less than
- `>`, greater than
- `<=` less than or equal to
- `>=` greater than or equal to
- `==`, equals
- `!=`, does not equal
- `is`, `in` and `not`

Let's try using these in our cells


```python
print(5 > 3)
print(4 <= 3)
```

    True
    False
    


```python
print(3 == 3)
print(2 != 6)
```

    True
    True
    


```python
# Can use in to test whether something exists in a data structure
# like a list
odds = [1,3,5,7]
```


```python
4 not in odds
```




    True




```python
var is not None 
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-62-e3a44487a7ea> in <module>()
    ----> 1 var is not None
    

    NameError: name 'var' is not defined



```python
print(var)
```


```python
# or a dictionary
temp_dict = {4: 6}
print(temp_dict)


```


```python
6 in temp_dict
```


```python

```


```python
# or if it is not in a data structure



```

These conditonal statements are returning True and False when you run this code. These just so happen to be another data type, **booleans**. These are the simplest ones, as they can only be `True` or `False`. You can also make vairables have boolean values, and test those.


```python
#example
test = True

# Can test True/False in a few ways. Using ==, or is/not.
```


```python
test == True
```

Now that we've got some basics down, let's try to use these inside something a bit more complicated

Take a situation like this for example - 

It's early morning. I wake up, and need to get ready for the day. What decisions should I make? What should I check before I leave?

Firstly, let's say that it's winter.


```python
winter = True #this is a Boolean type. Booleans are True or False.
num = 3
coffee = True
```

I can now use the function, `if`, to test something and then perform an action based on that.


```python
"""
if (winter is not True) and (coffee is None):
    print("Great, it's not cold")
    
print("Blergh")

if num != 3:
    print ("num is not 3")
    
elif num == 3:
    print("num is 3")
"""

if (num == 3) or (coffee == True):
    print("Huzzah")
    if coffee == True:
        print ("This is the important thing")

    
print ("Look at this weather we're having")
```


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

We can also place conditional statements within a conditional statement. This is known as nesting.

``` python
if condition:
    if condition:
        do thing
```


```python

```

### Challenge 2

Together with your team mates, come up with your own morning routine. Try to use as many of the conditional testers as you can, without nesting more than 2-3 if statements.




```python
#Snake team

Rainy = True
Temperature = 2

if Rainy is True:
    print("Bring an umbrella")
    if Temperature < 6:
        print("put on more clothes")

elif Temperature <6:
    print ("put on more clothes")
    
else:
    print("just go out and enjoy the sun")

```


```python
if alarm == True:
    print("Press snooze")
    snooze = snooze+1
    if snooze >= 3:
        print("wake up begrudgingly")

if time == "a lot":
    print("Yay, fresh clothes")
    
else:
    print("These pjs still smell fresh")

```


```python
sleepwell=True
coffee=True
pants=True

if sleepwell is not True:
    print('I didn\'t sleep well last night. I guess I\'m gonna keep sleeping then.')
elif pants is not True:
    print('I can\'t find my pants. I guess I\'m gonna keep sleeping then.')
elif coffee is not True:
    print('I don\'t have any coffee left. I guess I\'m gonna keep sleeping then.')
else:
    print('I have everything I need to start my day. I guess I\'m gonna keep sleeping then.')

```


```python

```


```python

```


```python

```

# For Loops

- Explain what a for loop does.
- Correctly write for loops to repeat simple calculations.
- Trace changes to a loop variable as the loop runs.
- Trace changes to other variables as they are updated by a for loop.




Suppose we want to print each character in the word "lead" on a line of its own. One way is to use four print statements:


```python
element = "lead"
print(element[0])
print(element[1])
print(element[2])
print(element[3])
```

But that's a bad approach. Firstly, you're doing a lot more typing than you need to, and it doesn't scale well. If you wanted to print every single letter in a sentence, or paragraph, you'd spend more time programming it than if you had just copied it out yourself. 

Secondly, if you were trying to automate something - so that it does something without you needing to be there every step of the way - this approach wouldn't work at all. Not every string, or list, or dictionary, is going to be the exact same size. You would need to program a new code every time you got new data.

Instead, we can use `for` loops. This is a function that lets us "iterate" over your strings and other data structures.

The general structure of a `for` loop looks like this

```python
for variable in collection:
    do a thing
```


```python
for number in [1,4,5,7]:
    print(number)

```


```python
language = 'Python'
for letter in language:
    print(letter)
```


```python
a = ['onion', 'potato', 'ginger', 'cucumber'] # list
print(type(a))
for item in a:
    print(item)
```

Note that a loop variable is just a variable that's being used to record progress in a loop. It still exists after the loop is over, and we can re-use variables previously defined as loop variables as well:


```python
name = "Anwar"
print(name)
for name in 'abc':
    print 
    print (letter)
print ('after the loop, letter is', letter)
```

#### Combining loops and conditionals


##### Optional Challenge

Given the previous list, a = ['onion', 'potato', 'ginger', 'cucumber'], iterate over the ist, but ONLY print out the first element.


```python

```


```python

```


```python

```

##### Challenge

Iterate through a given list of numbers. Add **odd** numbers to another list, called odd. Add **even** numbers to another list called even. Then, print out both lists.


```python
numberList = [1,2,3,4,5,6,7,8,9,10]


```


```python

```


```python

```

#### Range

Generally speaking, you can iterate, or loop, over most data types that act as collections or sequences. We are able to loop over the elements of strings because, inside Python, they are treated as a _sequence of letters_, just as a list is a _sequence of objects_. 

However, sometimes you want to loop over an object that it not naturally iterable, or you may even want to use the list (or string) **indexes** instead of the list item itself. 

e.g. where list = [1,2,3,4,5], I might only want to print out the elements 2, 3 and 4. Rather than programming an `if` statement like:


```python
listed = [1,2,3,4,5]

for num in listed:
    if (num == 2) or (num == 3) or (num == 4):
        print (num)
```

I can instead use the list indexes to get the data I want:


```python
for i in [1,2,3]:
    print(listed[i])
```

Rather than creating a list by hand every time you want to do something like that, you can use the `range()` function to create our own iterators for the values we specify.

`range()` works with 3 "arguments", or options; start, stop and step. Only `start` is compulsory.


```python
# range(start)
range(3)
```


```python
list(range(3))
```


```python
#range(start, stop)
list(range(2,6))
```


```python
#range(start, stop, step)
list(range(2,8,2))
```

Inside a for loop, the iterator produced by `range()` works in much the same way as a list does.


```python
# now implement in for loop
for i in range(5, 16, 2):
    print (i)
```


```python
# from 0 to 3 (non inclusive)
odds = [1,3,5,7]

for i in range(len(odds)):
    print("i =",i)
    print("odds at index i =",odds[i])
```


```python
string = "This is Introduction to Python"
for i in range(len(string)):
    print(string[i])
```


```python

```

#### Challenge

In your teams, write a loop that calculates the same result as 3 \*\* 4 using multiplication, without using exponentiation.

**Extra points**: try to make the loop work for any set of numbers, instead of explicitly programming 3 and 4.


```python
num = 4
e = 4
prod = 0


```


```python

```


```python

```


```python

```


```python

```

#### _Optional Challenge_

Write a program which will find all such numbers which are divisible by 7 but are not a multiple of 5,
between 2000 and 3200 (both included).
The numbers obtained should be printed as a list.

Hints: 
Consider use range(#begin, #end) method


```python

```


```python

```


### Iterating Over Dictionaries

Because dictionaries actually exist as key and value **pairs**, trying to loop over them in the same way that we would a list doesn't quite work:


```python
# dictionary
a = {'Name' : 'Md Anwar Hossain', 'Nickname' : 'Anwar', 'Email' : 'example@gmail.com', 'Phone' : '85450451769682'}
print(a)
print(type(a))

for item in a:
    print(item)
    
```

If you want to access the values, or both the keys **and ** the values, you need to use specific commands


```python
for key,value in a.items():
    print(key,":",value)
```


```python
#You can also use .keys() to get just the keys
for k in a.keys():
    print (k)

#And .values() to get just the values
for v in a.values():
    print (v)
```


```python

```

#### _Optional Challenge_

A robot moves in a plane starting from the original point (0,0). The robot can move toward UP, DOWN, LEFT and RIGHT with a given steps. The trace of robot movement is shown as the following:
UP 5
DOWN 3
LEFT 3
RIGHT 2

The numbers after the direction are steps. Please write a program to compute the distance from current position after a sequence of movement and original point. If the distance is a float, then just print the nearest integer.

Example:
If the following dictionary is given to the program - 

`directions = {"UP": 5, "DOWN": 3, "LEFT": 3, "RIGHT": 2}`

Then, the output of the program should be: 2

Hint: distance is computed as `round(math.sqrt(pos[1]**2+pos[0]**2))`

![image.png](attachment:image.png)


```python
from numpy import random

pos = [0,0]

directions = {"UP": random.randint(0,10),
              "DOWN": random.randint(0,10),
              "LEFT": random.randint(0,10),
              "RIGHT": random.randint(0,10)}



```


```python

```

# While Loops

The while statement allows you to repeatedly execute a block of statements as long as a condition is true. A while statement can have an optional else clause.




```python
n = 0

while n < 5:
    n = n+1
    print("loop number:", n)
else:
    print("end of the liiiiine")

```

How we could use a while loop to do the exponential calculations earlier


```python
power = 4
n = 3
start = 1

while power > 0:
    start = start * n
    power -= 1


print (start)
```


```python

```


```python

```

#### Challenge

Please write a program using generator to print the even numbers between 0 and n, where n is a randomly generated integer.

Example:
If n = 10

Then, the output of the program should be:

[0,2,4,6,8,10]


```python
from numpy import random

n = random.randint(0,200)

print(n)

```


```python
# Start Coding!
```

#### _Optional Challenge_

Write a `while` loop that takes a string, and produces a new string with the characters in reverse order, without using the `.reverse()` function:
i.e. 'Newton' becomes 'notweN'.


```python
#HINT
word = ""

word = "a" + word
print(word)
word = "b" + word
print(word)
```


```python
word = "Newton"


```


```python

```
