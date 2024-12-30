---
topic: terminology
part: "2.1"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #terminology
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 04 Function

--- 
A _function_ executes some functionality. Functions can also take one or more _arguments_, which are data that can be fed to and processed by the function. Arguments are sometimes also referred to as _parameters_. There is a technical distinction between an argument and a parameter, but the words are often used interchangeably. For now it should suffice to remember that both terms refer to the idea of some data passed to the function.

A function is executed when it is _called_. That is, when the function (and its arguments, if any) is mentioned in the code. The following statement calls the `print` function with the argument `"this is an argument"`:

```python
print("this is an argument")
```

Another function you've already used often is the `input` function, which asks the user for input. The argument of this function is the message that is shown to the user:

```python
name = input("Please type in your name: ")
```

In this case the function also _returns_ a value. After the function has been executed, the section of code where it was called is replaced by the value it returns; it is another expression that has now been evaluated. The function `input` returns a string value containing whatever the user typed in at the prompt. The value a function returns is often stored in a variable so that it can be used in the program later on.

