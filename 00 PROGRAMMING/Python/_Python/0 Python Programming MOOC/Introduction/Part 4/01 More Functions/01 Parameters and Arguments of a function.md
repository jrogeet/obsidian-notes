---
topic: functions
part: "4.1"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #introduction #mooc #functions
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Parameters and Arguments of a function



**Function Parameters and Arguments**
A function can accept one or more arguments. When the function is called, these arguments are assigned to variables known as parameters, which are declared within the function's parentheses.

**Example: Defining Functions with Parameters**
```python
def greet(name):
    print("Hello there,", name)

def sum(a, b):
    print("The sum of the arguments is", a + b)
```
- **Function Calls**:
```python
greet("Emily")
sum(2, 3)
```
- **Function Output**:
```plaintext
Hello there, Emily
The sum of the arguments is 5
```

> **Formal vs Actual Parameters**
The terms "parameter" and "argument" are used for clarity. Other terms like "formal" and "actual parameters" might be encountered, but the Python documentation uses "parameter" and "argument".

>**Argument Assignment Process**
-In function definition `greet(name)`, `name` acts like a normal variable within the function.
-In function call `greet("Emily")`, the argument "Emily" is assigned to the parameter variable `name`.
-The parameter's value changes based on the argument provided during each function call.
Using precise terminology helps maintain accuracy in programming.



