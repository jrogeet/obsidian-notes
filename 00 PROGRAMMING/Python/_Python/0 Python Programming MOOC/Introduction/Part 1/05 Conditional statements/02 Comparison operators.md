---
topic: conditional
part: "1.5"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #numbers #comparison
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 06 Comparison operators

--- 
Very typically conditions consist of comparing two values. Here is a table with the most common comparison operators used in Python:

|Operator|Purpose|Example|
|---|---|---|
|`==`|Equal to|`a == b`|
|`!=`|Not equal to|`a != b`|
|`>`|Greater than|`a > b`|
|`>=`|Greater than or equal to|`a >= b`|
|`<`|Less than|`a < b`|
|`<=`|Less than or equal to|`a <= b`|

Let's have a look at a program which prints out different things based on whether the number the user inputs is negative, positive, or equal to zero:

```python
number = int(input("Please type in a number: "))

if number < 0:
    print("The number is negative.")

if number > 0:
    print("The number is positive.")

if number == 0:
    print("The number is zero.")
```

