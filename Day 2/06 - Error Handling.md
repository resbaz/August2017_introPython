
# Error Handling

**Learning Objectives**:

- Explain the purpose of defensive programming
- Explain how and why we use assertions
- Create a function that uses `try` and `except` to catch errors
- Create a function that uses `assert` to prevent errors

As you may have already noticed when making our functions, and loops, etc, we encounter errors. A lot.

Sometimes these errors are because we've mis-spelled a command (damn those typos!), or tried to use the wrong variable name, or the wrong variable, etc.

However, you can actually choose to define how your computer handles errors, including what kind of messages it returns, and when to actually raise an error.


```python
# Sometimes it's better to cause an error early, than to have your computer throw a fit later

# What if someone put in a string instead? Or a number < 1?
num = input("Please input a number > 1: ")

num = int(num)

while num > 1:
    print("My loop is running! At least %i more times to go" % (num - 2))
    num -= 1
```

    Please input a number > 1: This
    


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-6-fbbd743bdc88> in <module>()
          4 num = input("Please input a number > 1: ")
          5 
    ----> 6 num = int(num)
          7 
          8 while num > 1:
    

    ValueError: invalid literal for int() with base 10: 'This'


In one case, we have what is called a "silent error", where the program fails or doesn't perform the thing that you want it to, but it doesn't give you any error messages.

In the other, the user has obviously given us data that is incompatible with the code that we've written, and we're getting a type error.

There are two ways we can deal with this; assertions, and try/except

## Assertions

Like an `if` statement, `assert` tests that a condition (which you give it) is true, and throws an error and terminates your code if it's not.

Assertions are a systematic way to check that the internal state of a program is as you, the programmer, expects, with the goal of catching bugs. 

In particular, they're good for catching false assumptions that were made while writing the code, or abuse of an interface (like user input). 

In addition, they can act as in-line documentation to some extent. When you're going through your code later on, or when another programmer is going through it, they can immediately see what assumptions and requirements are required.

To program an assertion, you simply do: `assert(condition), "Error Message You Want To Print"


```python
#The basics of how to write an assert
num = 1

assert num > 1, "Number is less than 1. Please try again"

print("We've successfully made it past the assertion")
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-11-47034a926c68> in <module>()
          2 num = 1
          3 
    ----> 4 assert num > 1, "Number is less than 1. Please try again"
          5 
          6 print("We've successfully made it past the assertion")
    

    AssertionError: Number is less than 1. Please try again


### Mini Challenge 

Try to write our previous while loop again, but this time with assertions to check that all of the conditions we need are correct.


```python

```


```python

```


```python

```

## Try/Except

Another way to catch errors is within `try`/`except` blocks.

What happens here is that you write the code that you think will give you errors inside a `try` block. 

If the error occurs, your code will cut off where it's currently at, and then go into your `except` block instead.

For example:




```python
try:
    num = str(input("Please write an integer: "))
    num = int(num)
    
except Exception as e:
    print("Please input a valid number")
    print (repr(e)) # can also add this to print out both the error info, and the value
```

    Please write an integer: t
    Please input a valid number
    ValueError("invalid literal for int() with base 10: 't'",)
    


```python

```

In addition to using an except block after the try block, you can also use the
finally block. 

The code in the finally block will be executed regardless of whether an exception
occurs.


```python
try:
    num = str(input("Please write an integer: "))
    num = int(num)
    
except Exception as e:
    print("Please input a valid number")

finally:
    print("I might choose to put some code here to close a file, for example")
```

    Please write an integer: tr
    Please input a valid number
    I might choose to put some code here to close a file, for example
    


```python

```


```python

```

Above all, we want our error messages to be *informative*, and tell you what's going wrong. 

So for example, say that you've placed a lot of code into a single try block. Inside this code, you're reading in a file, taking some user input, and doing some type conversion. This means there are three major areas where an error could occur. 

If your file doesn't exist, you don't want it to print the same error message as the user input error. That wouldn't make any sense! How could you tell which problem your code is having?

Instead, we can chain different `except` blocks together, with each only representing a single type of error. This is similar to how we used `elif` statements in the past, where we can type one many different elif statements, each testing for a condition specific to that block.

Some of the common exception errors are:

**IOError**: 
If the file cannot be opened.

**ImportError**:
If python cannot find the package you're trying to import

**ValueError**:
Raised when a built-in operation or function receives an argument that has the right type but an inappropriate value. E.g. A function only wants you to type in "float", "int" or "str", but you've instead written "apple"

**KeyboardInterrupt**:
Raised when the user hits the interrupt key (normally Control-C or Delete)

**EOFError**:
Raised when one of the built-in functions (input() or raw_input()) hits an end-of-file condition (EOF) without reading any data


```python
try:
    num = str(input("Please write an integer: "))
    num = int(num)
    print(num**num)
    
except ValueError as e:
    print("Please insert an integer")
    
except EOFError as e:
    print("You didn't read in any data. Why.")
    
except Exception as e:
    print("This would catch most other errors")

finally:
    print("Error? No error? I dont know!")
```

    Please write an integer: t
    Please insert an integer
    ValueError("invalid literal for int() with base 10: 't'",)
    Error? No error? I dont know!
    


```python

```

You can also include the `raise` statement within your try blocks, or even inside your functions, to MAKE the code break if a particular condition isn't met.


```python
try:
    num = str(input("Please write an integer greater than 0: "))
    num = int(num)
    if num <= 0:
        raise ValueError("Your integer wasn't greater than 0") #this message here represents e
    
except ValueError as e:
    print("Please insert a valid integer")
    
except Exception as e:
    print("This would catch most other errors")

finally:
    print("Error? No error? I dont know!")
```

    Please write an integer greater than 0: 0
    Please insert a valid integer
    Error? No error? I dont know!
    


```python

```

### Challenge

Try to write our previous code from the challenge, but this time combine assertions and try, with specific error messages that tell us what went wrong

```python
# What if someone put in a string instead? Or a number < 1?
num = input("Please input a number > 1: ")

num = int(num)

while num > 1:
    print("My loop is running! At least %i more times to go" % (num - 2))
    num -= 1
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

# Final Challenge!

Read in the file, "Zen_of_Python.txt", and - using dictionaries and appropriate error handling - count the number of times each case-insensitive word occurs. (Remember, Python will read "Word" =/= "word").

Then, find a print out the word that occurs the most amount of times, EXCEPT if the word is "if", "is" or "the".

You can find a skeleton of the code required below. You will need to add extra code to make the current lines work, and add extra conditions and checks to ensure that you get the right answer


```python
try:

    
except Exception as e:




counts = dict()

for line in file:

    
    
file.close()

maximum = 0
maxWord = None



print("The most common word was %s, which appeared %i times" % (maxWord,maximum))

```

    The most common word was None, which appeared 0 times
    


```python

```
