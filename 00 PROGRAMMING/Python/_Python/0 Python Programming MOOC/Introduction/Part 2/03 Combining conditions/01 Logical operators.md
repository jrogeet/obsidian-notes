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
# 01 Logical operators

--- 
## Combining Conditions with Logical Operators

In Python, you can use logical operators (`and` and `or`) to combine conditions in conditional statements.

### Using `and` Operator

The `and` operator requires that all given conditions are simultaneously true.

For example:
```python
number = int(input("Please type in a number: "))
if number >= 5 and number <= 8:
    print("The number is between 5 and 8")
```

- This condition checks if the number is both greater than or equal to 5 and less than or equal to 8.

### Using `or` Operator

The `or` operator requires that at least one of the given conditions is true.

For example:
```python
number = int(input("Please type in a number: "))
if number < 5 or number > 8:
    print("The number is not within the range of 5 to 8")
```

- This condition checks if the number is either less than 5 or greater than 8.

Logical operators allow you to create more complex conditions based on multiple criteria.

---

The following truth table contains the behaviour of these operators in different situations:

|a|b|a and b|a or b|
|---|---|---|---|
|False|False|False|False|
|True|False|False|True|
|False|True|False|True|
|True|True|True|True|

Sometimes it is necessary to know if something is _not_ true. The operator `not` negates a condition:

|a|not a|
|---|---|
|True|False|
|False|True|

The above example with the range of 5 to 8 _excluded_ could also be programmed like this:

```python
number = int(input("Please type in a number: "))
if not (number >= 5 and number <= 8):
    print("The number is not within the range of 5 to 8")
```


> The condition ___`x >= a and x <= b`___ is a very common way of checking whether the number ___`x`___ falls within the range of ___`a`___ to ___`b`___. An expression with this structure works the same way in most programming languages.

>Python also allows a simplified notation for combining conditions:___`a <= x <= b`___ achieves the same result as the longer version using __`and`__. This shorter notation might be more familiar from mathematics, but it is not very widely used in Python programming, possibly because very few other programming languages have a similar shorthand.

