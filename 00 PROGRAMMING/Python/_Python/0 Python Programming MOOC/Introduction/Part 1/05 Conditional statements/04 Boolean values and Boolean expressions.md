---
topic: conditional
part: "1.5"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #boolean
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 04 Boolean values and Boolean expressions

--- 
Certainly, here's your text formatted and summarized for your markdown text editor:

## Boolean Values and Expressions in Python

In Python, conditions used in conditional statements always yield a truth value, which can be either `True` or `False`. These values are known as Boolean values, named after mathematician George Boole. In Python, they're managed using the `bool` data type, and variables of this type can only hold `True` or `False`.

A piece of code that evaluates to a Boolean value is called a Boolean expression. For instance, the condition `a < 5` is a Boolean expression, producing `True` if `a` is less than 5, and `False` otherwise.

### Using Boolean Expressions

You can store the result of a Boolean expression in a variable like any numerical result:

```python
a = 3
condition = a < 5
print(condition)
if condition:
    print("a is less than 5")
```

Output:
```
True
a is less than 5
```

### Direct Usage of `True` and `False`

Python's keywords `True` and `False` can be used directly as well. Here's an example where the `print` command executes every time because the condition holds:

```python
condition = True
if condition:
    print("This is printed every time.")
```

Output:
```
This is printed every time.
```

Boolean values and expressions are fundamental in programming for creating conditions and controlling the flow of your code.