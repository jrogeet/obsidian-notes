---
topic: conditional
part: "2.2"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #conditional
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 01 More conditionals

--- 
Certainly, here's your provided content formatted and ready for copying into your markdown text editor:

## Using the `else` Statement in Conditional Statements

When working with conditional statements, using the `else` statement can streamline your code and make it more concise. Let's explore an example:

### Original Approach

Consider this program that classifies a number as negative, positive, or zero:

```python
number = int(input("Please type in a number: "))

if number < 0:
    print("The number is negative")

if number >= 0:
    print("The number is positive or zero")
```

### Streamlined Approach with `else`

The original code can be improved by utilizing the `else` statement:

```python
number = int(input("Please type in a number: "))

if number < 0:
    print("The number is negative")
else:
    print("The number is positive or zero")
```

- The `if` statement covers the condition where the number is negative.
- The `else` statement covers the case where the number is zero or positive.

### Why Use `else`?

- When conditions are mutually exclusive (one must be true and the other false), `else` offers a cleaner alternative to using multiple `if` statements.
- It eliminates the need for repeating the same condition with a reversed inequality.

By employing the `else` statement, you create a more streamlined and efficient code structure for handling different cases.

When using an if-else construction, one and exactly one of the branches will always be executed. The following picture illustrates the structure:
![[Pasted image 20230828174203.png]]

Certainly, here's the content formatted and ready for copying into your markdown text editor:

## Using `if-else` Statements and Examples

The `if-else` construction is used to create a single conditional statement with two branches: one for when the condition is met (`if`) and one for when it's not (`else`).

### Checking for Parity

An example that checks whether a user-provided number is even or odd:

```python
number = int(input("Please type in a number: "))

if number % 2 == 0:
    print("The number is even")
else:
    print("The number is odd")
```

- The `%` operator calculates the remainder of the division.
- If the remainder is zero, the number is even; otherwise, it's odd.

### String Comparison Example

Here's another example using string comparison for a password check:

```python
correct = "kittycat"
password = input("Please type in the password: ")

if password == correct:
    print("Welcome")
else:
    print("No admittance")
```

- If the entered password matches the correct one, the user is welcomed.
- Otherwise, access is denied.

### Understanding `if-else`

- The `if-else` construction creates a unified conditional statement.
- The `else` branch only executes when the `if` condition is not met.

Remember, the `if-else` statement is a powerful tool for branching your code based on specific conditions.
