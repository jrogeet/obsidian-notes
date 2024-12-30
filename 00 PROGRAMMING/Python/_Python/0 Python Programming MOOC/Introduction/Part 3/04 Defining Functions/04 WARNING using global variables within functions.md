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
# 04 Warning: using global variables within functions

--- 

**Using Global Variables in Functions**
In functions, new variables can be assigned and global variables from outside the function can be accessed. However, relying on global variables within functions is generally discouraged due to potential bugs and complications.

**Example: Using Global Variable Incorrectly**
```python
# Global variable
name = "Betty"

def hello(given_name):
    # Incorrectly using the global variable instead of the parameter
    print("Hello", name)
```

- **Function Calls**:
```python
hello("Steve")
hello("Betty")
```
- **Function Output**:
```plaintext
Hello Betty
Hello Betty
```

- **Explanation**:
The function mistakenly uses the global variable `name` instead of the parameter `given_name`. This leads to the function consistently printing the global variable's value, regardless of the arguments passed to it.

---

>Using global variables within functions can lead to unexpected behavior and difficulties in debugging. It's generally better to pass variables as arguments to functions, promoting better organization and reducing the risk of bugs.

