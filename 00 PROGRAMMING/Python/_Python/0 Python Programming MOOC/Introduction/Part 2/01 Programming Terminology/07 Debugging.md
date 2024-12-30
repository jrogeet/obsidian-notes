---
topic: terminology
part: "2.1"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #terminology
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 07 Debugging

--- 

## Debugging and Debugging Techniques

When a program's syntax is correct but it doesn't function as intended, it likely contains a bug. Bugs can manifest in various ways, causing errors during execution or producing incorrect results.

### Errors During Execution

Some bugs lead to errors during execution. For example, this code snippet:

```python
x = 10
y = 0
result = x / y

print(f"{x} divided by {y} is {result}")
```

Produces this error:
```
ZeroDivisionError: integer division or modulo by zero on line 3
```
In this case, division by zero is the issue.

### Debugging Process

Debugging is the process of identifying and resolving bugs. It's an essential skill for programmers.

- Debugging can be challenging as the cause might not be where the error occurs.
- Errors can result in incorrect output, revealing bugs that need fixing.

### Debugging Techniques

#### Debugging Print Statements

- Add print statements to track program flow and variable values.
- Verify expected values, ensuring code behaves as intended.
- Use print statements to quickly confirm code functionality.

#### Problem Isolation

- When debugging, run the program multiple times.
- For quick isolation, temporarily "hard-code" inputs instead of asking user input.

#### Debugging Example

Consider the following buggy program:

```python
hourly_wage = float(input("Hourly wage: "))
hours = int(input("Hours worked: "))
day = input("Day of the week: ")

daily_wages = hourly_wage * hours
if day == "sunday":
    daily_wages * 2

print(f"Daily wages: {daily_wages} euros")
```

- The program fails for certain inputs, producing incorrect output.

#### Debugging Steps

1. Replace input statements with hard-coded values to isolate the issue.
2. Add debugging print statements to trace program behavior.
3. Identify the problem: condition not met due to capitalization mismatch.
4. Correct the condition and ensure code execution within the if block.
5. Address the issue of doubling daily wages by using `daily_wages *= 2`.

### Importance of Debugging

- Debugging is a critical skill for programmers.
- Professional programmers spend significant time debugging.
- Debugging print statements provide insights into code behavior.

Remember, debugging is a valuable tool for beginners and experts alike. Use it to identify and fix issues in your code effectively.
