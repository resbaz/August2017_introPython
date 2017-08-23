# Homework Challenges

I've included a few programming problems to challenge your budding programming skills. I'd like for everybody to give the first question a try, and everything past that is optional/if you want to challenge yourself further. Happy coding!

## Question 1

Create a for loop that will go through the example list given below. If the list item is a number below or equal to 10, add this number to another list for "odd" or "even" numbers. Ignore numbers larger than 10. If it's a string, add it to another list.

Sort the contents of these three lists, then print the outputs of all three on separate lines.

An example of the list you might recieve is below, along with some code to help you get started.

Example:
```python
list1 = [1, 3.2, "Are you having a nice day?", 2, 4, "difficulty increased!", 10, 15, 11.5, 5, 6, 
            9, 8.2, 7, 14.8, 13, ["Nested list", "This makes it a bit harder, eh?", "3000000", 4.6], 9.9]
```
---
Should give you the output:

even list is: [1, 2, 4, 4.6, 6, 8.2, 10]

odd list is: [1, 3.2, 5, 7, 9, 9.9]

string list is: ['3000000', 'Are you having a nice day?', 'Nested list', 'This makes it a bit harder, eh?', 'difficulty increased!']

---

I've included some code below to help you get started:

```python
list1 = [1, 3.2, "Are you having a nice day?", 2, 4, "difficulty increased!", 10, 15, 11.5, 5, 6, 9, 8.2, 7, 
            14.8, 13, ["Nested list", "This makes it a bit harder, eh?", "3000000", 4.6],9.9]

odd = []
even = []
strings = []

for i in range(len(list1)):
    if (type(list1[i]) is int) or (type(list1[i]) is float):
        #Hint: what happens when you convert a float to an int?
        if (condition):
            odd.append(list1[i])
        
        
    elif type(list1[i]) is (condition):
        # perform an action
        
    elif type(list1[i]) is list:
        for j in range(len(list[i])): # <- what do you think is happening on this line?
        
        # Hint: if we can index a single list with list[index], how might we index a list within a list?
        # Hint: remember that we actually have a couple of data types inside our list. 
                    # What do we have to test for again?
        

# Now outside the for loop

# Sorting the lists
odd.sort()

strings.sort()


# Printing Output
print("even list is:", even)
```



## Question 2

Write a Python script that iterates/loops over a list of words, and counts how many times each of those words occurs. Then, output the word that occurs the most amount of times, and how many times it appeared.

Hint: a dict() might come in handy for this...

``` python
wordList = ['Bravely', 'bold', 'Sir', 'Robin', 'rode', 'forth', 'from', 'Camelot',
            'Yes', 'brave', 'Sir', 'Robin', 'turned', 'about',
            'He', 'was', 'not', 'afraid', 'to', 'die', 'O', 'brave', 'Sir', 'Robin',
            'And',  'gallantly', 'he', 'chickened', 'out',
            'He', 'was', 'not', 'at', 'all', 'afraid', 'to', 'be', 'killed', 'in', 'nasty', 'ways',
            'Bravely', 'talking', 'to', 'his', 'feet',
            'Brave', 'brave', 'brave', 'brave', 'Sir', 'Robin',
            'He', 'beat', 'a', 'very', 'brave', 'retreat']

# An empty dictionary
wordCount = dict()

for word in wordList:
    #remember that strings are case sensitive in Python. i.e. Brave != brave. How could we fix this while counting?
    
    #what would happen if you tried to call a key that doesn't exist? How do you fix that?
    if word in wordCount:
        
    else:
        
    
max = 0
maxWord = None

for key,value in wordCount.items():
    
```

