---
topic: variables
part: "1.3"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #fstring #variables
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 05 Printing with f-strings

--- 
What if we want to have more flexibility and control over what we print out? So called _f-strings_ are another way of formatting printouts in Python. The syntax can initially look a bit confusing, but in the end f-strings are often the simplest way of formatting text.

With f-strings the previous example would look like this:

```python
result = 10 * 25
print(f"The result is {result}")
```

Let's break this apart. In the very beginning of the string we are printing out there is the character _f_. This tells Python that what follows is an f-string. Within the string, enclosed in curly brackets, is the variable name `result`. The value it contains becomes a part of the printed string.

The printout is exactly the same as in the previous examples:

```
The result is 250
```

A single f-string can contain multiple variables. For example this code

```python
name = "Mark"
age = 37
city = "Palo Alto"
print(f"Hi {name}, you are {age} years old. You live in {city}.")
```

It is difficult to create a printout exactly like this using the comma notation in the `print` command. For example, this program

```python
name = "Mark"
age = 37
city = "Palo Alto"
print("Hi", name, ", you are", age, "years old. You live in", city, ".")
```

Notice the automatically inserted whitespace between each comma-separated part of the printout. Preventing `print` from adding the extra spaces is technically possible, but not worth the trouble given that we can instead use f-strings.

In its simplicity the comma notation of the `print` command can often be useful, but it does sometimes cause more trouble than it's worth. F-strings are usually a more reliable option. In part 4 you will learn more about the handy features of f-strings when it comes to formatting printouts.

> [!F-strings and Python versions]
> If you are using an older version of Python, f-strings may not work. They were introduced in Python version 3.6. Later on during the course you will install Python on your own computer. Unfortunately, the more modern versions of Python are not always available for older operating systems. If that is the case with your computer, when there are exercises requiring the use of f-strings, you can always try them out in the in-browser exercise templates in these early parts of this course.

