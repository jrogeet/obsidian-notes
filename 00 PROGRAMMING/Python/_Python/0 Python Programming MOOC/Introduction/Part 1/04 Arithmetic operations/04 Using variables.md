---
topic: arithmetic
part: "1.4"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #numbers #variables 
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 04 Using variables

--- 
Let's have a look at a program which calculates the sum of three numbers given by the user:

```python
number1 = int(input("First number: "))
number2 = int(input("Second number: "))
number3 = int(input("Third number: "))

sum = number1 + number2 + number3
print(f"The sum of the numbers: {sum}")
```
An example execution of the program:
```
First number: 5 
Second number: 21 
Third number: 7 
The sum of the numbers: 33
```

The program uses four different variables, but two would easily suffice in this case:

```python
sum = 0

number = int(input("First number: "))
sum = sum + number

number = int(input("Second number: "))
sum = sum + number

number = int(input("Third number: "))
sum = sum + number

print(f"The sum of the numbers: {sum}")
```

## Summing Up User Inputs

When working with user inputs in programming, particularly for summing up multiple values, it's important to understand how variables are used and manipulated.

### Storing User Inputs

- User inputs are collected in the variable `number`.
- The variable `sum` holds the running total of these inputs.

### Adding Numbers Explicitly

The explicit way to add values to the sum is using the following line of code:

```python
sum = sum + number
```


Here's how it works:
- The values of `sum` and `number` are added together.
- The result is stored back in the `sum` variable.
- For instance, if `sum` is 3 and `number` is 2, executing this line makes `sum` equal 5.

## Shortcut Notation

A more concise way to achieve the same result is using shorthand notation:

```python
sum += number
```

This line increments `sum` by the value of `number`.

## Putting it Together

Consider this program example:

```python
sum = 0

sum += int(input("First number: "))
sum += int(input("Second number: "))
sum += int(input("Third number: "))

print(f"The sum of the numbers: {sum}")
```

- Here, user inputs are immediately added to the sum.
- Depending on the context, the number of variables used can vary.

## Reusing Variables

Reusing a variable makes sense when temporarily storing similar data, like for summing. For example:

```python
number1 = int(input("First number: "))
number2 = int(input("Second number: "))
print(f"{number1} + {number2} = {number1 + number2}")
```

- In this case, there's no separate variable for storing the sum.

## Using Descriptive Variables

For clarity and maintainability, use descriptive variables:

```python
name = input("What is your name? ")
print("Hi " + name + "!")

age = int(input("What is your age? "))
# program continues...
```

Descriptive variables help you understand the purpose of each piece of data.

Remember, the choice of how to handle variables depends on your program's specific needs and readability goals.