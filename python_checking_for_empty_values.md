# Checking For Empty Values In Python

According to PEP 8 (the official style guide for python code), you should never check for empty values by checking the length, e.g. `if len(randomlist) == 0`.

I can't tell you how many times I've broken this simple rule, but it's definitely been a lot. The first time I heard this *rule*, I thought "what? why not?". 

Well, according to PEP 8, it's because you should always assume empty values will return false. So rather than checking the length, you should do something like this:

```python
# Checking if something is empty
boring_list = []

if not boring_list:
    print("Yep, it's empty.")
    
# output: Yep it's empty.
```

And, as you may have guessed, if you want to check if a value is **not** empty, simply remove the "not" from the above code. For example:

```python
cool_list = ['some', 'stuff',]

if cool_list:
    print("That's cool, yo!")
    
# output: That's cool, yo!
```

And there you have it! A simple rule to follow, but one that may not be intuitive for those just starting to learn python. I certainly never thought about it when I was starting out. 

As a side note, all empty containers (strings, lists, dictionaries, tuples, sets, ...) are evluated as false.

Don't believe me? Give it a try yourself ;-)
