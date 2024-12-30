---
part: "4.4"
topic: strings
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc  #introduction
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# f-strings
The third method to prepare strings is ___f-strings___. 
The previous example with the name and the age would look like this formulated with f-strings:

```python
name = "Erkki"
age = 39
print(f"Hi {name} your age is {age} years")
```

One very common use case is settings the number of decimals that are printed out with a floating point number.

```python
number = 1/3
print(f"The number is {number}")
```

It can be set within the curly brackets of the variable expression.
Add a _colon_ character ad a __format specifier__ after the variable name:
```python
number = 1/3
print(f"The number is {number:.2f}")
```
The __format specifier__ ___.2f___ states that we want to display 2 decimals.

The letter ___f___ at the end means that we want the variable to be displayed as a ___float___ / a floating point number.

Here's another example, where we specify the amount of whitespace reserved for the variable in the printout. 
Both times the variable ___name___ is included in the resulting string, it has a space of 15 characters reserved. 
First the names are justified to the left, and then they are justified to the right:

```python
names =  [ "Steve", "Jean", "Katherine", "Paul" ]
for name in names:
  print(f"{name:15} centre {name:>15}")
```

---
The uses of ___f-strings___ are not restricted to ___print___ commands. 
They can be assigned to variables and combined with other strings:
```python
name = "Larry"
age = 48
city = "Palo Alto"
greeting = f"Hi {name}, you are {age} years of age"
print(greeting + f", and you live in {city}")
```

You can think of an ___f-string___ as a sort of function, which creates a normal string based on the "arguments" within the curly brackets.

