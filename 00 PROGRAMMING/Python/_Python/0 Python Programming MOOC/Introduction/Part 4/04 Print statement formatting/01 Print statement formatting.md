---
topic: strings
part: "4.4"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website 
Topics: #python #mooc  #introduction
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Print statement formatting

Three Methods for formulating the argument given to the ___print___ command.


The first is the ___+___ operator for strings. 
It allows simple concatenation of string segments:
```python
name = "Mark"
age = 37
print("Hi " + name + " your age is " + str(age) + " years" )
```
This method will not work if any of the segments are not strings.
In the example above, the variable ___age___ has been converted into a string with the ___str___ function, since it is an integer and cannot be concatenated as is.


The second method is considering each segment of the argument as a separate argument, and splitting them up with commas:
```python
print("Hi", name, "your age is", age, "years" )
```

This code produces the exact same result as the previous version. 
The ___print___ command normally __adds a space character between each argument__. 
The _advantage_  here is that the segments can be of __different types__, so there is no need to convert anything into a string.

If you want to remove the automatically added spaces, you can add a special named argument ___sep___:
```python
print("Hi", name, "your age is", age, "years", sep="")
```

___sep=""___ is a keyword argument, and its name is short for __separator__. 
It specifies that the other arguments should now be separated by an empty string.
You can set the separator to __any string__ you like. 

For example, if you wanted each argument on a separate line, 
you could set the separator to ___"\n"___, which is the newline character:

```python
print("Hi", name, "your age is", age, "years", sep="\n")
```

