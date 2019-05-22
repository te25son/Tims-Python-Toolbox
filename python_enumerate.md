# Enumerate

`enumerate()` is a built-in python function that takes an iterable as an argument and returns an *enumerate object*. The enumarte object can be understood as a series of tuples containing each element of the original iterable as well as each element's index within that iterable. 

Yikes! That's an ugly sentence, so here's an example:

```python
evil_companies = ['Comcast', 'Disney', 'Monsanto', 'McDonalds',]
list(enumerate(evil_companies))
# output: [(0, 'Comcast'), (1, 'Disney'), (2, 'Monsanto'), (3, 'McDonalds')]
```

As you can see, each company within `evil_companies` was separated into its own tuple along with its index number. 

The same thing can be achieved by creating our own function like this:

```python
def make_numbers_happen(iterable, count=0):
    num = count
    for element in iterable:
        yield num, element
        num += 1
```

`enumerate()` can be useful when we're looking to keep track of the index of the elements in our iterables. 

For example, if I wanted to make a pretty list of my favorite foods and their line index, I could use `enumerate()`.

```python
fav_foods = ['pizza', 'tacos', 'veggie burgers', 'curry',]
for idx, food in enumerate(fav_foods):
    print(f'{idx}: {food}')
    
# output:
# 0: pizza
# 1: tacos
# 2: veggie burgers
# 3: curry
```

And there you have it, indexing with iterables made simple! :-)
