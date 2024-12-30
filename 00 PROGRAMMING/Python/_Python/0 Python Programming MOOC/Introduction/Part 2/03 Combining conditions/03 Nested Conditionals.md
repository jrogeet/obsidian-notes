---
topic: conditional
part: "2.3"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #combiningconditions 
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 03 Nested Conditionals

--- 
Conditional statements can also be nested within other conditional statements. For example, the following program checks whether a number is above zero, and then whether it is odd or even:

```python
number = int(input("Please type in a number: "))

if number > 0:
    if number % 2 == 0:
        print("The number is even")
    else:
        print("The number is odd")
else:
    print("The number is negative or zero")
```

Certainly, here's a summarized version of your provided content:

## Nested Conditional Statements and Logical Operators

In Python, proper indentations are crucial when using nested conditional statements. Indentations define the structure and relationships between different branches.

### Understanding Indentation

Indentations determine which branches belong to the same conditional statement. For example, an `if` branch and an `else` branch with the same amount of indentation are treated as part of the same statement.

### Choosing Between Approaches

You can often achieve the same result using either nested conditional statements or conditions combined with logical operators. The following example produces the same output using both approaches:

```python
number = int(input("Please type in a number: "))

if number > 0 and number % 2 == 0:
    print("The number is even")
elif number > 0 and number % 2 != 0:
    print("The number is odd")
else:
    print("The number is negative or zero")
```

### No Inherent Better Approach

Neither approach is inherently better than the other. The choice between them depends on the situation.

- Both nested statements and logical operators achieve the same functionality.
- The choice can be based on readability and what seems more logical in context.

In certain cases, like the given example, nesting may appear more intuitive to some programmers.
