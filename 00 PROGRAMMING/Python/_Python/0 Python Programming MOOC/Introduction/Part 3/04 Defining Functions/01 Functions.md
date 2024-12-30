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
# 01 Function

--- 
We have already used functions such as ___`len`___, ___`print`___ and ___`input`___ in our programs. 
These are functions built into Python, and so they are always ready at our disposal, no matter which environment we are programming in. However, it is also possible to define your own functions.



- __Functions must be defined before they are used.__
- A function definition starts with the keyword `def`, followed by the function name, parentheses, and a colon.
- The function header is followed by the function body, indented like other code blocks.
- The function body contains the code to be executed when the function is called.
- To define a function, use the syntax: ___`def function_name():`___
- To call a function, simply use its name followed by parentheses.
- The code in the function body is executed only when the function is called.
- Calling a function multiple times repeats the code in its body each time.

For example:

```python
def message():
    print("This is my very own function!")

message()
message()
message()
```

Output:
```
This is my very own function!
This is my very own function!
This is my very own function!
```