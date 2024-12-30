---
topic: variables
part: "1.3"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #variables
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 01 More about variables

--- 
Variables are needed for various purposes in programming. 
You can use variables to store any information that will be needed later in the program's execution.

In Python programming variables are created like so:

```python
variable_name = ...
```

Here ___`...`___ means the value stored in the variable.

For example, when you used the ___`input`___ command to read a string from the user, you stored the string in a variable and then used the variable later in your program:

```python
name = input("What is your name? ")
print("Hi, " + name)
```

The value stored in a variable can also be defined using other variables:

```python
given_name = "Paul"
family_name = "Python"

name = given_name + " " + family_name

print(name)
```