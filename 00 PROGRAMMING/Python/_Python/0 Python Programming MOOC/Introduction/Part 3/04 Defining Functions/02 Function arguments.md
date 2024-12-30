---
topic: functions
part: "3.4"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 02 Function arguments

--- 

**Functions and Arguments**

Functions often use arguments that affect their behavior. For instance, Python's built-in functions like `print` and `input` take arguments for displaying text.

```python
print("Hi!")                           # Argument is the string "Hi!"
name = input("What is your name? ")    # Argument is the string "What is your name? "
print(name)                            # Argument is the value of the variable name
```

- **Argument vs. Parameter**: The terms "argument" and "parameter" are often used interchangeably. The distinction lies in their usage during function calls and within function definitions, respectively.

- **Function Definition**: Functions are defined using the `def` keyword, followed by function name and parameters in parentheses.

**Defining Functions with Parameters**
Defining functions with parameters allows them to accept inputs. Parameters are defined within the function's parentheses.

```python
def hello(target):
    print("Hello", target)
```

- **Calling Functions**: Calling a function with parameters passes values to the parameters. The function uses these values within its body.

```python
hello("Emily")
hello("world!")
```

- **Function Output**: Function calls return output based on the arguments passed.

```plaintext
Hello Emily
Hello world!
```

- **Parameter Assignment**: Inside the function, parameters are assigned values from the provided arguments.

**Function Parameters and Naming**

Function names and parameter names follow similar naming conventions as variables. They should be descriptive, using lowercase letters and underscores.
