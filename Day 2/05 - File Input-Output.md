
# File I/O and String Manipulations

__Learning Objectives__:

- Read in a file and be iterate over each line
- Be able to edit a file and clean your data
- Write your own data into a new file
- Use what we've learned so far within the whole workshop to perform a useful task

## File Input/Output

Reading in files is an essential part of beingable to do any kind of data analysis, and thankfully Python makes this really easy.

You create the varaible that you want your data to be inside, and you use a function called `open()`.

`open()` takes three arguments - the file path/file name you want to open, the "access mode" (or way that you want to open it), and a buffering value. The last two values are optional though.

There are 3 general "access_modes"

- "r" = read. 
    - only lets you _read_ the data from the file.
- "w" = write
    - lets you _add_, or _write_ data into a file
- "a" = append
    - lets you _add_ data to the end of an existing file. 
- "r+" = special read/write
    - lets you both read and write to/from the same file. 

Be careful using "w"/write though! If you open a file using the "w" option, anything that used to be inside that file will be erased. 


```python
#open(file name , method of opening)
file = open("Zen_of_Python.txt","r")
```

Let's test the "write" access mode


```python
example = open("example.txt", "w")
example.close()
```

Open the file again on your computer. See how this has erased the contents of the file?

### File Input - read() function

Opening your file is pretty useless if you can't actually see what's in it though


```python
type(file)
```




    _io.TextIOWrapper




```python
# This will give me the whole file's contents at once
file.read()
```




    "The Zen of Python, by Tim Peters\n\nBeautiful is better than ugly.\nExplicit is better than implicit.\nSimple is better than complex.\nComplex is better than complicated.\nFlat is better than nested.\nSparse is better than dense.\nReadability counts.\nSpecial cases aren't special enough to break the rules.\nAlthough practicality beats purity.\nErrors should never pass silently.\nUnless explicitly silenced.\nIn the face of ambiguity, refuse the temptation to guess.\nThere should be one -- and preferably only one -- obvious way to do it.\nAlthough that way may not be obvious at first unless you're Dutch.\nNow is better than never.\nAlthough never is often better than right now.\nIf the implementation is hard to explain, it's a bad idea.\nIf the implementation is easy to explain, it may be a good idea.\nNamespaces are one honking great idea -- let's do more of those!"



So there are a few things to examine in here. 

When you look at the original file, you can see that each of these sentences are on different lines - but here they're all jumbled together. That's because those `\n` symbols are "newline" characters - when the computer is interpreting text, it will use this newline character to tell it to print that text on a new line. 

We can demonstrate this by using `print()` on this text:


```python
file = open("Zen_of_Python.txt","r")
file_all = file.read()

print(file_all)
```

    The Zen of Python, by Tim Peters
    
    Beautiful is better than ugly.
    Explicit is better than implicit.
    Simple is better than complex.
    Complex is better than complicated.
    Flat is better than nested.
    Sparse is better than dense.
    Readability counts.
    Special cases aren't special enough to break the rules.
    Although practicality beats purity.
    Errors should never pass silently.
    Unless explicitly silenced.
    In the face of ambiguity, refuse the temptation to guess.
    There should be one -- and preferably only one -- obvious way to do it.
    Although that way may not be obvious at first unless you're Dutch.
    Now is better than never.
    Although never is often better than right now.
    If the implementation is hard to explain, it's a bad idea.
    If the implementation is easy to explain, it may be a good idea.
    Namespaces are one honking great idea -- let's do more of those!
    

The most common non-printable characters you need to know are:

- \n : new line. You may also sometimes see \r\n on files written by Windows systems.
- \t : tab


```python
# Or I can specify the number of "bytes", or characters, that I want to read in at once
file = open("Zen_of_Python.txt","r")
file.read(99)
```




    'The Zen of Python, by Tim Peters\n\nBeautiful is better than ugly.\nExplicit is better than implicit.\n'




```python
# If I read the whole file though, the "pointer" is set at the bottom of the file. 
file = open("Zen_of_Python.txt","r")
file.read() #this reads in the whole file
file.read() #what if I run it again?
```




    ''



### File Output

Let's first go over how to write to a file

This is actually really easy - just use `open` to create a file that you want to write to, and then you can use the `file.write()` function to write any _string_ values into that file.


```python
file_out = open("example2.txt", "w")
```


```python
file_out.write(3) #what happens if I try to "write" an int?
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-125-e6cbfe2df4c9> in <module>()
    ----> 1 file_out.write(3) #what happens if I try to "write" an int?
    

    TypeError: write() argument must be str, not int



```python
file_out.write("My name is Kahli")
file_out.write("Today I am your Python instructor")
file_out.write("Now let's do a challenge")

file_out.close()

```

Now let's have a look at what's in the file:

"My name is KahliToday I am your Python instructorNow let's do a challenge"

Oops! It's all on the same line. What could I do to make them be on a separate line?

#### Challenge

Using the `write()` function, create your own haiku inside a new file, called "poem.txt". Give it a title, and make sure there are two lines between the title and the poem text. 

Example:  
"""   
My Poem

This is my poem   
My poem is amazing   
It's the best poem

p.s. This poem is terrific. Don't listen to the corrupt media. CNN is fake news.   
"""


```python

```


```python

```


```python

```

### File Input - Take 2
Often though, you only want to read through one line at a time. There are a few ways you can do this:

1. You can use the `.readline()` function
2. You can use the `.readlines()` function, and loop over it
3. A `for` loop

**Option 1: `readline()`**

This allows you to read a single line of the file each time you run the function. Can be used in a for loop. Handy if you want to read through two different files (of the same length!) at the same time.


```python
file = open("Zen_of_Python.txt","r")
```


```python
file.readline()
```

You can also specifically tell it which lines to open


```python
file.readline(10)
```


```python

```

**Option 2: `readlines()`**

Reads the entire file in at once as a list, with each line occupying a list element


```python
file = open("Zen_of_Python.txt","r")
file_all = file.readlines()
print(type(file_all))
file_all
```

 **Option 3: Using a `for` loop**
 
 When you `open` a file, the data type returned is naturally iterable. Just like using the range function, this means that you're able to loop over each element in the file.


```python
type(file)
```


```python
for line in file:
    print(line)
```

---

Why it is printing double spaces though?

If you remember looking at our `readlines()` function, you'll see that there's actually a `\n` on the end of every line. We don't see when using the `print()` function, because the computer automatically removes those when rendering the text - they're non-printed characters. 

However, when we've previously used the `print()` function multiple times in the same cell, you'll notice that each output ends up on a different line:


```python
print("Line 1")
print("Line 2")
print("Line 3")
```

Although we can't see them in the output, `print()` is actually adding it's _own_ newline characters to end of each line's output as well. That means that when we print our own lines - which already _have_ newlines, we're actually printing double spaces.

To remove this issue, we'll want to remove those characters before we print.

**with open() as name**  
Another option while reading our files is open the file as a _handle_, like so:


```python
with open("Zen_of_Python.txt","r") as file:
    for line in file.readlines():
        print(line)
```

This version is popular because it will automatically `close()` the file once it reaches the end of the document. 

#### Challenge

Using the file "Robin.txt", print out every second line of the file.  
Assume that the lines of the file start counting from 1, not 0. 



```python

```


```python

```

## String Manipulations

We've already seen a couple of string manipulations on Day 1 - functions like `upper()`, `lower()`, `capitalize()` and `title()`. Today, you're going to learn about:

- `strip()`, `lstrip()` & `rstrip()`
- `split()`
- `find()`
- `replace()`
- `join()`


#### Strip()


```python
string = "\nThis is a string that I want to get rid of stuff from\tWoot!\t\n"
```


```python
# Strip() will remove whitespace and all non-printed characters from either end of a string
string.strip()
```


```python
# You can also specify what you want to remove. It doesn't have to be whitespace either!

string = "\nThis is a string that I want to get rid of stuff from. Woot!\t\n"
string.rstrip("\n")
```


```python
string = "\nThis is a string that I want to get rid of stuff from. Woot!"
string.rstrip(" Woot!")
```

I can also specify multiple items to strip off


```python
string = "Example!*%#^"
string.strip("*^#%") #characters in any order
```


```python

```

#### Split()

We can also use the `split()` command to split our strings into a list


```python
string = "This\nis a\tstring I want to split"

string.split()
```

This works on _all_ whitespace (including non-printed characters) as standard, but you can specify what you want it to split on.


```python
string = "This\nis a\tstring I want to split"

string.split(" ") #will split on the spaces only
```

#### Challenge

For every line inside the Zen of Python, strip each line of the unwanted non-printed characters and spaces. Then, split the line on whitespace, and print each line/list

e.g.   
_Input:_  
file = "First Line\n Second Line\n"  

_Output:_  
[First,Line]  
[Second,Line]  



```python

```


```python

```

** Find() **

Find allows you to...you guessed it! Find something inside your string.

The general structure is `"str to search inside".find("string to find", start pos, end pos)`

The start and end are optional - the default values for those are just the start and end of your first string


```python
str1 = "This is my long string"
str2 = "is"
```


```python
str1.find(str2)
```


```python
str1.find(str2,3)
```

If the thing you're searching for doesn't exist, `find()` will just return a -1


```python
str1.find("k")
```

#### Team Discussion

How do you think you might use `find`? What applications could it be useful for?


```python

```

#### Replace()

Replace kind of works like "find and replace all" in MS Excel. 

`replace()` takes two arguments - the string to find, and what to replace it with.

`"string".replace("what to replace", "what to replace it with")`


```python
str1
```


```python
str1.replace("is"," ")
```


```python
str1.replace("is","")
```


```python

```

#### Join()

Join() will take a list and then join all of the elements together to make a single string

`"what to place between each list element".join(list to join)`


```python
stringList = ["This", "is", "my", "string","example"]

# Placing spaces bwtween each word
" ".join(stringList)
```


```python
# Tab characters - could be useful for spreadsheets?
"\t".join(stringList)
```


```python
# commas. Useful for *.csv files?
",".join(stringList)
```


```python
# No spaces. Just join the words
"".join(stringList)
```


```python
# BUT all list elements MUST be strings
stringList = ["This", "is", "my", "string","example", 3]
"".join(stringList)
```

#### Challenge

Read in the Zen of Python, and print the poem again, but with all of the punctuation removed from each line.

e.g.   
Input: "The Zen, of Python!\n"   
Output: "The Zen of Python"
    
Hint 1 - how might you remove any punctuation characters from within a sentence?  
Hint 2 - remember that you can combine multiple characters inside `strip()`


```python

```
