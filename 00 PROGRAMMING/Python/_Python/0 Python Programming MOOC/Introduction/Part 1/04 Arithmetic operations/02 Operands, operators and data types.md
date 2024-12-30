---
topic: arithmetic
part: "1.4"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #arithmetic #numbers
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 02 Operands, operators and data types

--- 
A calculation usually consists of _operands_ and _operators_

![[Pasted image 20230828165929.png]]

The data type of an operand usually determines the data type of the result: if two integers are added together, the result will also be an integer. 
If a floating point number is subtracted from another floating point number, the result is a floating point number. 
In fact, if a single one of the operands in an expression is a floating point number, the result will also be a floating point number, regardless of the other operands.

Division ___`/`___ is an exception to this rule. 
Its result is a floating point number, even if the operands are integers. 
For example ___`1 / 5`___ will result in the floating point number ___`0.2`___.

Example:
```python
height = 172.5
weight = 68.55

# the Body Mass Index, or BMI, is calculated by dividing body mass with the square of height
# height is converted into metres in the formula
bmi = weight / (height / 100) ** 2

print(f"The BMI is {bmi}")
```

Notice Python also has an integer division operator ___`//`___. If the operands are integers, it will produce an integer. The result is rounded down to the nearest integer. For example this program

```python
x = 3
y = 2

print(f"/ operator {x/y}")
print(f"// operator {x//y}")
```