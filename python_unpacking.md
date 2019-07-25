# Unpacking Arguments in Python

The asterik ('*') is a commonly used operator in python, and is likely one of the first things newcomers to python learn when dealing with multiplication and power operations.

```python
a = 2 * 2    # output: 4  
b = 2 ** 3   # output: 8
```

But the usefulness of the asterik extends far beyond simple mulitplication and power operations. It can also be used to *unpack* iterables in a simple way. 

Take the following function for example:

```python
def print_items(a, b, c):
    print(f'<{a}, {b}, {c}>')
```

As you can see, `print_items` takes three positional arguments and prints them in a nicely formatted way. However, what if the argument we wanted to pass wasn't three separate items, but rather a tuple or list containing three items? In this case, we would have to call each item in the iterable by its index...

```python
tuple_iter = (1, 2, 3)
list_iter = [1, 2, 3]

print_items(list_iter[0],
            list_iter[1],
            list_iter[2])
            
# output: <1, 2, 3>
```

But there's an easier way! **By adding a '*' before an iterable in a function call, the iterable will be *unpacked* and each element will be passed as a separate positional argument to the function**. 

```python
print_items(*list_iter)

# output: <1, 2, 3>
```
Cool right?
