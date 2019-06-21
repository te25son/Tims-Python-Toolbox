# Decorators in Python

The number of times I've tried to explain this to myself has been, well... numerous to say the least. But here I go again.

To understand how a python decorator works, let's begin at the beginning.

**Everything in python is an object**. I put that sentence in bold in the hopes that it'll stick in your head (and hopefully mine too). Functions, classes, everything and anything in python is an object. Variables are simply identifiers of our program's objects.

Did you not know that you could set your functions to variables? Don't worry, neither did I at first. In fact, I'm still grappling with the idea, but it really does make sense when you think about it. Consider the following example:

```python
def bro_coder():
    return "Bro do you even code?"
    
fun_func1 = bro_coder
fun_func2 = bro_coder
```

*In order to avoid confusion (because decorators can get out of control and confusing very quickly), I'll take this one small step at a time.*

So..."what the hell is going on here?" you might be asking. Have no fear, I'll explain. 

At first we create a function called `bro_coder` and have it return a string. Now if you'll recall from earlier, I said "everything in python is an object" even functions. 

What exactly do I mean by this? Well an object is an instance of a class. Think of it like a class is the blueprint and an object is the house. Python already comes with its own blueprints that you can use so you're not reinventing the wheel (does anyone else feel like this phrase is overused?) every time. And guess what! 'Function' is a built in blueprint (i.e. class) in Python! Take a look:

```python
bro_coder.__class__

# <class 'function'>
```

Whoa dude is right! Now `__class__` is a built-in method in python that we can quite literally call on anything, even our variables. It tells us which class our variable or function or whatever is using. Cool huh? Here's another quick example of the `__class__` method in action:

```python
var1 = 5
var2 = 'hello'
var3 = (1, 2)
var4 = {'thing': 1, 'stuff': 2}

var1.__class__
var2.__class__
var3.__class__
var4.__class__

# <class 'int'>
# <class 'str'>
# <class 'tuple'>
# <class 'dict'>
```

You don't need to worry about using the `__class__` method pretty much ever, but I just wanted to make sure you understand that functions are objects, and objects are like houses whereas classes are like blueprints. If that's all you take away from what's been said so far, I'd say you're doing great. Hold onto that knowledge because we'll add onto it in a moment.

And like I said, things get out of control fast with decorators, so let's take our heads out from under the hood and return to my first example where I defined `bro_coder()`.

You might have been confused when I first assigned my function to a variable, but now you know it's really no different than when I assign a string or an integer to a variable. Why? Because, as you now know, they're all objects. 

However, you may have also noticed that there are no parentheses at the end of my function when I assign it to each variable. This is because the blueprint (class) for function says that parentheses will call the function we're naming. But I don't want to call it, I only want to assign it to some other variable. That's why the parentheses are gone, so the blueprint knows not to call the function. Instead, the variables I've assigned to `bro_coder()` will point to a location in memory where `bro_coder()` lives. That way we can call it later on.  


<h4 align="center">To be continued...</h4>
