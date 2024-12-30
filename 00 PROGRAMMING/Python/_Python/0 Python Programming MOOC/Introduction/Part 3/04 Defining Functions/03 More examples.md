---
topic: functions
part: "3.4"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #functions
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 03 More examples

--- 

## Examples of Functions with Arguments

**Example 1: Squaring a Number**
A function named `squared` calculates and prints the square of a given number.
```python
def squared(x):
    print(f"The square of the number {x} is {x * x}")
```
- **Calling the Function**: The function is called with different arguments.
```python
squared(2)
squared(5)
```
- **Function Output**:
```plaintext
The square of the number 2 is 4
The square of the number 5 is 25
```


**Example 2: Greeting Function**
The function `hello` uses an `if` statement to display greetings based on the given name.
```python
def hello(name):
    if name == "Emily":
        print("Hello", name)
    else:
        print("Hi", name)
```
- **Calling the Function**:
```python
hello("Emily")
hello("Mark")
```
- **Function Output**:
```plaintext
Hello Emily
Hi Mark
```

**Example 3: Sum Function**

A function `sum` takes two arguments, calculates their sum, and prints the result.

```python
def sum(x, y):
    result = x + y
    print(f"The sum of the arguments {x} and {y} is {result}")
```
- **Calling the Function**:
```python
sum(1, 2)
sum(5, 24)
```
- **Function Output**:
```plaintext
The sum of the arguments 1 and 2 is 3
The sum of the arguments 5 and 24 is 29
```


- **Using Variables in Arguments**:
The parameter names within the function have no relation to variables outside it. For instance, the function can be called with different values:

```python
x = 100
y = 30
sum(1, 2)
sum(x + y, 10)
```
- **Function Output**:
```plaintext
The sum of the arguments 1 and 2 is 3
The sum of the arguments 130 and 10 is 140
```
