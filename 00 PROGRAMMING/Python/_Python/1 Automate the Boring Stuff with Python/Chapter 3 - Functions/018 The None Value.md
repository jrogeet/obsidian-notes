Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #nonevalue
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[015 Functions|Functions]] 

---
# None Value
The value called ***None*** represents the absence of a value.

It is the only value of the ***NoneType*** Data Type. (which is ***null***,***nil***, or ***undefined*** in other programming languages.)

The ***None*** must have a capital **N** just like the Boolean ***True*** and ***False***.


This value-without-a-value can be helpful **when you need to store something that won’t be confused for a real value** in a variable.

***None*** is used as the return value of ***print()***. The print function doesn't need to return anything in the same way ***len()*** or ***input()*** does.

Since all function calls need to evaluate to return a value, ***print()*** returns ***None***.

> Python adds ***return None*** to the end of any function definition with no ***return*** statement. Similar to how a ***while*** or ***for loop*** implicitly ends with a ***continue*** statement. Also, if you use ***return*** statement without a value, then ***None*** is returned.