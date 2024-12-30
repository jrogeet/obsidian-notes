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
# 03 Expression

--- 
An _expression_ is a bit of code that results in a determined data type. When the program is executed, the expression is evaluated so that it has a value that can then be used in the program.

Here are a few examples of expressions:

|Expression|Value|Type|Python data type|
|---|---|---|---|
|`2 + 4 + 3`|`9`|integer|`int`|
|`"abc" + "de"`|`"abcde"`|string|`str`|
|`11 / 2`|`5.5`|floating point number|`float`|
|`2 * 5 > 9`|`True`|Boolean value|`bool`|

Because all expressions have a type, they can be assigned to variables:

```python
# the variable x is assigned the value of the expression 1 + 2
x = 1 + 2
```

Simple expressions can be assembled together to form more complicated expressions, for example with arithmetic operations:

```python
# the variable y is assigned the value of the expression '3 times x plus x squared'
y = 3 * x + x**2
```

