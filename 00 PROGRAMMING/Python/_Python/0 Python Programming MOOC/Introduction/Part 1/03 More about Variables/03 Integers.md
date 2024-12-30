---
topic: variables
part: "1.3"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #integers #numbers
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 03 Integers

--- 
Thus far, we have only stored strings in variables, but there are also many other types of information we will want to store and access later. Let's have a look at integers first. Integers are numbers that do not have a decimal or fractional part, such as `-15`, `0` and `1`.

The following program creates the variable `age`, which contains an integer value.

```python
age = 24
print(age)
```

Notice the lack of quotation marks here. In fact, if we were to add quotation marks around the number, this would mean our variable would no longer be an integer, but a string instead. A string can contain numbers, but it is processed differently.

So, why does it matter that variables have a type, when the following program still prints out the same thing twice?

```python
number1 = 100
number2 = "100"

print(number1)
print(number2)
```

Variable types matter because different operations affect different types of variables in different ways. Let's have a look at an example:

```python
number1 = 100
number2 = "100"

print(number1 + number1)
print(number2 + number2)
```

For integer values the `+` operator means addition, but for string values it means concatenation, or "stringing together".

Not all operators are available for all types of variables. While numbers can be divided using the division operator `/`, attempting to divide a string by a number causes an error:

```python
number = "100"
print(number / 2)
```