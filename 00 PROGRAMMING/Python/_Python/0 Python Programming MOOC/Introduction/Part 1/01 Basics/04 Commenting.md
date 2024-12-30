---
topic: basics
part: "1.1"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #basics #comments
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Commenting

--- 
Any line beginning with the pound sign ___`#`___, also known as a hash or a number sign, is a comment. 
This means that any text on that line following the ___`#`___ symbol will not in any way affect how the program functions. 
__Python will simply ignore it.__


> [!NOTE]
> Comments are used for explaining how a program works, to both the programmer themselves, and others reading the program code.

In this program a comment explains the calculation performed in the code:

```python
print("Hours in a year:")
# there are 365 days in a year and 24 hours in each day
print(365*24)
```

When the program is run, the comment will not be visible to the user:
```
Hours in a year:
8760
```

