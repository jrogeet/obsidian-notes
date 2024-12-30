---
topic: functions
part: "4.1"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #functions 
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 06 Type of the argument

--- 
**Recap of Data Types and Type Hints**

A summary of data types and type hints in Python:

- **Data Types We've Covered:**

  | Type                | Python Data Type | Example           |
  |---------------------|------------------|-------------------|
  | Integer             | int              | 23                |
  | Floating Point Num. | float            | -0.45             |
  | String              | str              | "Peter Python"    |
  | Boolean Value       | bool             | True              |

- **Type Hints and Function Arguments:**

  - Functions require correct argument types to work properly.
  - Example function:

    ```python
    def print_many_times(message, times):
        while times > 0:
            print(message)
            times -= 1
    ```

  - Calling the function correctly: `print_many_times("Hello there", 5)`
  - Calling the function with incorrect types: `print_many_times("Hello there", "Emily")`
    - This leads to a `TypeError` as string and integer cannot be directly compared.
  - **Type Hints**: Indicate argument types to avoid such issues:

    ```python
    def print_many_times(message: str, times: int):
        while times > 0:
            print(message)
            times -= 1
    ```

- **Type Hints for Return Values:**

  - Functions can also hint at the type of their return value.
  - Example:

    ```python
    def ask_for_name() -> str:
        name = input("What is your name? ")
        return name
    ```

  - Indicates that the function should return a string.

**Using type hints helps prevent errors and provides clarity in function usage and return values.**

> [!NOTE]
> ___Type hinting___ is literally just hinting about the type of the argument or the return value. It is not a guarantee of type, and definitely not a safeguard against type errors. If a function receives an argument or returns a value of the wrong type, the function is still executed, but it might not work correctly.