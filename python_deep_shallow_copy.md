<h1 align="center">Deep Vs. Shallow Copy</h1>

In Python, variables are references to objects. In the example `a = 3`, `a` is a variable which references the integer object `3`. When I call `a`, Python fetches the object at the referenced location and returns that object, in this case `3`.

Variables can also reference other variables. Consider this example:

```python
org_list = [[1,2,3],[4,5,6],[7,8,9]]
copied_list = org_list
```

Both variable reference the same object. It's like putting two name tags on the same person. Therefore it makes sense that whatever I do to one variable will have an effect on the other. 

```python
org_list.pop()
print(org_list)
print(copied_list)

# output --
# [[1,2,3],[4,5,6]]
# [[1,2,3],[4,5,6]]
```

This is hardly useful if I actually want to make a copy of an object in Python that doesn't affect the orginal object.

Luckily, Python offers a way to solve this problem

```python
org_list = [[1,2,3],[4,5,6],[7,8,9]]
copied_list = list(org_list)
```

Python offers several ways to make a copy of an object, but the most "pythonic" way is use the function named after the class you want to copy. `dict()`, `set()`, `tuple()` are some examples.

If I make changes to `copied_list` now, it doesn't affect `org_list`.

```python
copied_list.append(['this', 'is', 'neat'])
print(org_list)
print(copied_list)

# output --
# [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
# [[1, 2, 3], [4, 5, 6], [7, 8, 9], ['this', 'is', 'neat']]
```

At first, this seems to be exactly what we want. But Python (and programming in general) has what is known as shallow copies and deep copies. And what we have successfully done here is make a shallow copy of `org_list`.

The difference between the two is quite important:

* A **shallow copy** builds a new collection object and populates it with references to the original object. The child objects are not copied because shallow copy does not recurse. In other words, we copy only the first level of the object.
* A **deep copy** does recurse. It first builds a new collection object and then recurses through the original object making copies of each child element.

Therefore, the child objects within our copy of `org_list` are not independent. If we make a change to one of them, this will still have an effect on the copied object. 

```python
org_list[0][0] += 24
print(copied_list)

# output
# [[25, 2, 3], [4, 5, 6], [7, 8, 9], ['this', 'is', 'neat']]
```

If we would like to make a copy that's completely independent on all levels, we'll have to make a deep copy. To do this, first import the copy module and run `copy.deepcopy(<object to be copied>)`.

```python
import copy

deep_copy_list = copy.deepcopy(org_list)
print(org_list)
print(deep_copy_list)

# output --
# [[25, 2, 3], [4, 5, 6], [7, 8, 9]]
# [[25, 2, 3], [4, 5, 6], [7, 8, 9]]
```

If we make a change to our deepcopied list, the change will no longer affect our original list. 

```python
deep_copy_list[0][0] -= 24
print(deep_copy_list)
print(org_list)

# output --
# [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
# [[25, 2, 3], [4, 5, 6], [7, 8, 9]]
```
