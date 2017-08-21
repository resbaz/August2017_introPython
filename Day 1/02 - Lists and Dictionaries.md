
# Lists and Dictionaries in Python

### Learning Objectives

- Lists:
    - To understand the basic structure of a list
    - To know how to create, index and subset a list
    - Learn the difference between mutable and immutable objects
    - Adding and deleting list elements
        - Describe the difference between append(), insert(), del, remove() & pop()
    - List functions
- Dictionaries
    - Understand the underlying structure of a dictionary
    - Know how to access dictionary elements
    - Adding and deleting dictionary elements
        - Describe the difference between del & pop()
- Be able to describe when a situation is best suited for a dictionary vs. a list


## Lists

A list allows you to store many different values, of many different data types, in the same structure. 

We can make a list by putting the values into square brackets, []



```python
#we can make empty lists
[]
```




    []




```python
list()
```




    []




```python
#Or lists with things inside them
[1,2,3,4]
```




    [1, 2, 3, 4]




```python
#To save this list though we need to assign it to a variable
tempList = [1,2,3,4]

tempList
```




    [1, 2, 3, 4]



### Indexing a list
Sometimes we only want to access certain *elements*, or data, inside a list. We can do by callingthe list *index*, or the position of the data element, from inside the list


```python
tempList = [1,2,3,4]

tempList[4]
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-106-d5d2f98d7fd9> in <module>()
          1 tempList = [1,2,3,4]
          2 
    ----> 3 tempList[4]
    

    IndexError: list index out of range



```python
tempList[1]
```

Wait, but that's given us the number 2? Why?

---

This is because Python actually works based on 0-indexing, meaning that it starts counting from 0 instead of 1. 

This means that if we want to get the first element of our list, we actually have to call list[0], instead of list[1]


```python
tempList[0]
```

You can also use negative index numbers to start counting from the end of the list instead


```python
print('first and last:', tempList[0],"and", tempList[-3])
```


```python

```


```python

```

### Mutability

One of the properties of lists is that you can over-write data inside the list with new values. This means that lists are **_mutable_**, or changeable.

In contrast, strings are actually immutable. If you want to change something inside a string, you have to replace it with a whole new one.



```python
characters = ["Bugs Bunny","Spiderman","Iron Man","Batman"]
```


```python
print("characters was:", characters)

characters[3] = ["Superman","Batman", "Green Arrow"]

print("characters is now:",characters)
```


```python
characters[3]
```


```python
# Let's try this with a string
a = "Superman"

a[1] = 'b'


```

#### Mutability and Variable assignment


```python
odds1 = [1,3,5,7]
odds2 = odds1


```


```python
odds1[1] = 13

print("Odds1:",odds1)
print("Odds2:", odds2)
```


```python

```

### Slicing

Slicing allows us to access *sections* of the list, instead of the whole thing, or only a single element.

Slicing can be used on a variety of python data structures, including strings. This is because we can think of strings as being a _sequence_ of letters.


```python
indexList = ["Index 0", "Index 1", "Index 2", "Index 3"]

print('Sicing 1:3 is', indexList[1:3])
```

When doing this you probably noticed that slicing is _non-inclusive_, meaning that in a slice from indexes 0-5, the "5" is not included. This is because sequencing in Python looks sort of like this:
![image.png](attachment:image.png)

That does mean that we can do stuff like this though, while slicing:


```python
print('Index 1 to 3 is', indexList[1:4]) # 4 is normally over the edge!

print(indexList[4])

```

We can also "auto-complete" our slicing by leaving the front or back of the slice open:


```python
print('Index 2 to end is', indexList[2:])
```


```python
print("Start to index 2 is:", indexList[:2])
```


```python
#As well as do negative, or wrap-around slicing
print('Index 1 to -1 is', indexList[1:-1])
```


```python
print('Index start to end is', indexList[:])
```


```python
# You can do the same thing on strings
stringExample = "Hello World!"

print(stringExample[:5])

```


```python
#You can also use slicing to quickly assign new values to a list
odds1 = [1,3,5,7]

#change index 1 -> 14, and 2 -> 9
odds1[1:3] = [14,9] 

print(odds1)
```

#### Challenge

Given a string, `s`, of length at most 200 letters and a variety of integers, return the slice of this string from paired indices, inclusively. e.g. `a` through `b`, `c` through `d`, and `e` through `f`, etc. Make sure to include a space between each word. In other words, we should *include* the letters AT s[b] and s[d] in our slice.

E.g.

`s = "HumptyDumptysatonawallHumptyDumptyhadagreatfallAlltheKingshorsesandalltheKingsmenCouldntputHumptyDumptytogetheragain"
a = 22; b = 27; c = 97; d = 102`

Would print:

`Humpty Dumpty`



```python
zen = "BeautifulisbetterthanuglySimpleisbetterthancomplexComplexisbetterthancomplicated"
#Pair 1
a = 50; b = 56
# Pair 2
c = 31; d = 32
# Pair 3
e = 21; f = 24

```

## Adding and Deleting List Elements

### Append
To add a new variable into a list, we can use the `.append()` method. This adds the newest variable onto the *end* of the list.



```python
odds = [1,3,5,7]
```


```python
print("Odds before:", odds)
#list.append()
odds.append(9)

print("Odds after:", odds)
```

### Insert

`insert()` lets us put a new item into your list at the location of your choosing. 

The basic structure of this is list.insert(list index,variable)


```python
odds[2] = 4
```


```python
odds.insert(0,5)
print (odds)

```


```python
odds.insert(20,4)
print(odds)
```

### Deleting items

There are three options when deleting items from your list. 

The first is `del`, which removes the item at a specific index location and returns your modified list back to you. This works based on this kind of format, `del list[index]`


```python
odds = [1,3,4,5,7,8]
print(odds)
```


```python
del odds[-1]
print (odds)
```


```python
# But you can't go off the end: Error
del odds[12]
```

The second is `remove()`. Rather than deleting from a specific list index, `remove()` will find and delete the first matching *value* from your list, and return your modified list back to you.

It's typically used list this: `list.remove(variable)`


```python
odds = [1, 3, 4, 5, 4, 7, 9, 9]
```


```python
odds.remove(4)
print(odds)
```


```python
#If it doesn't exist though....Error
odds.remove(12)
```

Lastly we have `.pop()`. 

Like `del`, `pop()` is index based. However, while your list is still modified, `pop()` actually gives you back the value that you've removed. 


```python
odds
```


```python
odds.pop(-1)
```


```python
print("Odds before pop:",odds)

print(odds.pop(5))

print("Odds after pop:", odds)
```


```python
# Similarly to del...Error
odds.pop(10)
```

#### Challenge

Given a list of values, use `pop` to remove the fourth value from the list, then print out the value.

**_Hint_**: `pop` "returns" a value, meaning that it gives a value back when you use it.  What could you then do with it?



```python
challenge = [0,1,2,3,4,5,6,7]


```

### Other list functions

More useful list functions are `list.sort()`, and `list.reverse()`

`list.sort()` will sort your list based on "lexicographic order". This means that capital A-Z are sorted before lower-case a-z. 

However, sort() will not work if you have both strings and numeric data types in your list. It can only work if they are all strings, or all numeric (a combination of int and float).


```python
helpers = ["Kahli", "Mohsen","Hao","Abhi", "Anwar", "Suk Yee", "Andrew", "Jaimie"]
```


```python
helpers.sort()
print(helpers)
```


```python
helpers.append(3)
print("New names:", helpers)
```


```python
#Doesn't work with a mixture of data types
helpers.sort()
```


```python
# But is fine with both ints and floats
nums = [1,2.5,1.25,8,4]

nums.sort()

print(nums)

```

`reverse()` will take your list and reverse the order of the elements. 

So a list that was [1,2,3], would become [3,2,1]


```python
nums.reverse()
print(nums)
```


```python
#the list doesn't have to be sorted either
print(helpers)

helpers.reverse()

print(helpers)

```

#### Challenge

So far, most of the elements that we have added to our collections have been string, float, or integer data types. However, lists can store practically any other data type, including another list. This process is called nesting and it is a bit like Russian dolls.


```python
pets = ['dogs', 'cats', 'fish']

print(pets)

pets.pop(0)   # Get rid of dogs
dog_breeds = ['bulldog', 'terrier', 'greyhound']
pets.append(dog_breeds)  # append list of dog breeds available

print(pets)
```

With your team mates, work out how to index the nested list so you can sort it, and then return the greyound string

Hint: if you index a list like this, `list[0]`, how might you index a list inside a list?


```python

```


```python

```

#### _Optional Challenge_




```python

```

## Dictionaries

Dictionaries are another kind of data type used by Python.

A dictionary is an associative array (also known as hashes, for those who have programmed before). 

rather than using an index, like a list, a dictionary uses "keys", typically strings or numbers, that you define. Each "key" of this dictionary is mapped to a value. 

Like a list, a dictionary can contain any kind of data type for it's values. 

Dictionaries consist of key-value-pairs, and as they can only be accessed using the 'key' names, they are unordered. 



You can make a dictionary by using `dict()`, or `{}`


```python
# An empty dictionary
dict()
{}
```


```python
# An example of a dictionary with keys and values

released = {    
    "iphone" : str(2007),     
    "iphone3G" : str(2008),    
    "iphone3GS": str(2009),    
    "iphone4" : 2010,
    "iphone4S": '2011'
}

print(released)
```


```python
# Accessing your dictionary
released["iphone4SS"] = 2012


```


```python
# Dictionaries are mutable (they can be changed)
released["iphone4S"] = 2012


```


```python
released
```

#### Challenge

Find the other release dates for the newer iPhone models, and add them into the dictionary


```python

```


```python

```

####  Challenge

We want to create a dictionary that counts how many times a word are occurs in a body of text. For example, where

`sentence = "How many words is this so far? Too many I say. Science has gone too far!"`

The dictionary we should get back would be:

```python

counts = {"how": 1, "many": 2, "words": 1, "is": 1, "this": 1, "so": 1, "far": 2, "too": 2,
          "I": 1, "say": 1, "science": 1, "has": 1, "gone": 1}
```

Within the code, we'd have to run through the words in the sentence, and increment the dictionary count for that word by 1 each time, like so:

` counts["how"] += 1`

In your group, discuss what issues you might run into the first time you encounter a particular word? How could you get around it?


```python

```


```python

```

### Adding and deleting from your dictionary

Adding to your dicitonary is simple - you just "call" your dictionary with a new key name, and assign it a value.



```python
# Adding new elements

released
```


```python
# Deleting elements
# same as lists, "pop" gives you the deleted element
released.pop("iphone4SS")

```


```python
# While del removes the key and value from the dictionary. 
del released["iphone"]

```


```python
released
```


```python

```

#### Challenge

Add in two of the new Google Nexus models (eg. "Nexus One": 2010) (you can find some [here](https://en.wikipedia.org/wiki/Google_Nexus)) and their release dates to the previous dictionary, and then remove all iPhone entries from before 2010.


```python

```


```python

```
