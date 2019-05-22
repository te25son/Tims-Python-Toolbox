# Sorting By Dict Value In Python

```python
my_dict = {'A': 5, 'B': 4, 'C': 3, 'D': 2, 'E': 1,}
sorted(my_dict.items(), key=lambda x: x[1])

# output: [('E', 1), ('D', 2), ('C', 3), ('B', 4), ('A', 5)]
```

So what's going on here?

First we call `sorted()` which is a built-in function in python that builds a new sorted list from an iterable. Then we input the iterable we want sorted, in this case `my_dict`.

However, we can't just say `sorted(my_dict)`. Why? Because this would return a list of `my_dict`'s keys only, and we want the values. And we don't want _just_ the values displayed either, but the values **and** the keys together — because life isn't hard enough as it is.

So to do this, we call `items()` on our dictionary. `items()` is another built-in function that returns a [_view object_](https://docs.python.org/3/library/stdtypes.html?highlight=items#dict-views) of the dictionary's contents. In other words, it returns a list of tuples containing the elements of our dictionary. So if I call `my_dict.items()`, I receive `[('A', 5), ('B', 4), ('C', 3), ('D', 2), ('E', 1)]`.

`sorted()` also has a _key_ parameter that you can use to call a function on each list element before making a camparison. So we say `key=lambda x: x[1]`. This tells `sorted()` that for each element in the list `my_dict.items()`, you want to sort the element at index 1. Therefore, the first element in `[('A', 5), ('B', 4), ('C', 3), ('D', 2), ('E', 1)]` is `('A', 5)`, and the element at index one is `5`.

It will then iterate through each list element, comparing the items found at index one. Once the comparison is finished, it will return the same list of tuples, but with the sorted values :-)

Congratulations! You've sorted your dictionary by it's values in python!

If you're wondering how to get the list back into dictionary format, simply call `dict()` on your sorted list. For example:

```python
# continuation from code above

sorted_list = sorted(my_dict.items(), key=lambda x: x[1])
dict(sorted_list)

# output: {'E': 1, 'D': 2, 'C': 3, 'B': 4, 'A': 5}
```
