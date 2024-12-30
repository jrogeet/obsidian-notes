---
topic: input
part: "1.2"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #input #variables
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Information from the user

--- 
_Input_ refers to any information a user gives to the program. 
Specifically, the Python command ___`input`___ reads in a line of input typed in by the user. 
It may also be used to display a message to the user, to prompt for specific input.

```python
name = input("What is your name? ")
print("Hi there, " + name)
```

What this program prints out is partially dependent on input from the user.

> [!NOTE]
> The word ___`name`___ in this program is a variable.
> In the context of programming, a variable is a location for storing some _value_ , such as a string or a number. 
> This value can be used later, and it can also be changed.


> [!Naming Variables]
> In principle, variables can be named quite freely, within certain limits specified in the Python language. It is a common international programming practice to name variables in English, but you may come across code where variables are named in other languages, such as the native language of the programmer. The name of the variable has no direct effect on its content, so the name, in that sense, does not matter. However, it can often be helpful in understanding how code functions if variables are named logically and in English.
