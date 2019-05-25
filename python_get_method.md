# Get

The `get()` method is pretty useful in python if you'd like to return values of a dictionary but you're not sure the key you're using exists.

Let's look at an example without the use of `get()` first.

```python
my_supercool_dict = {'A':'coffee', 'B':'sunshine', 'C':'music',}
print(my_supercool_dict['A'])
print(my_supercool_dict['D'])

# output:
# 'coffee'
# ...
# KeyError: 'D'
```

Oops, we got a KeyError because no keys matched letter 'D'. Effectively, this would stop our program dead in its tracks until we resolved the error.

However, what if we did the same thing using the `get()` method?

```python
print(my_supercool_dict.get('A'))
print(my_supercool_dict.get('D'))

# output:
# 'coffee'
# None
```

Yay! No errors. But we're still not getting anything really useful. It's nice to see None being returned instead of an error, but maybe we want to display some kind of information if the key we're looking for doesn't exist. Luckily for us, the `get()` method comes with a default parameter we can change to whatever we want. 

```python
print(my_supercool_dict.get('B', 'Sorry, that doesn\'t exist'))
print(my_supercool_dict.get('D', 'Sorry, that doesn\'t exist'))

# output:
# 'sunshine'
# 'Sorry, that doesn't exist'
```

So now we know how to return default values when searching by keys in a dictionary :-)

Here's one last quick function to demonstrate the usefulness of the `get()` method:

```python
existing_ids = {
        123: 'Karl',
        987: 'Jimmy',
        111: 'Edd',
        246: 'Samantha',
    }
    
def say_hey(user_id):
    return f"Hello {existing_ids.get(id, 'fellow human')!}"
    
say_hey(111)
say_hey(999999)

# output:
# 'Hello Edd!'
# 'Hello fellow human!'
```
