---
topic: variables
part: "1.3"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #variables #numbers
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 04 Combining values when printing

--- 
Similarly, the following program will not work, because __`"The result is "`__ and ___`result`___ are of two different types:

```python
result = 10 * 25
# the following line produces an error
print("The result is " + result)
```
The program does not print out anything, but instead throws an error:
```
TypeError: unsupported operand type(s) for +: 'str' and 'int'
```

Here, Python tells us that combining two different types of values will not work just like that. In this case, `"The result is "` is of type string, while the value stored in `result` is of type integer.

If we do want to print out a string and an integer in a single command, the integer can be cast as a string with the `str` function, and the two strings can then be combined normally. For example, this would work:

```python
result = 10 * 25
print("The result is " + str(result))
```

The `print` command also has built-in functionalities that support combining different types of values. The simplest way is to add a comma between the values. All the values will be printed out regardless of their type:

```python
result = 10 * 25
print("The result is", result)
```

