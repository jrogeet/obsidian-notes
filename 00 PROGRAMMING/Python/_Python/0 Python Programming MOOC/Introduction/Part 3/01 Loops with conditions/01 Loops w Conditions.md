---
topic: loops with conditions
part: "3.1"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #loops #conditional 
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Loops with Conditions

--- 
## Using the While Loop with Conditional Statements

In the previous section, we explored the `while True` loop, where the loop continues until explicitly broken. However, loops can be controlled by any Boolean expression, not just `True`.

### Structure of the While Loop

The general structure of the `while` loop is as follows:

```python
while <condition>:
    <block>
```

- The loop executes the code within the `<block>` while the `<condition>` is `True`.
- Once the `<condition>` becomes `False`, the program continues from the line after the `while` block.

### Example: Printing Numbers Until a Condition

Here's an example that prints numbers until the variable `a` equals 5:

```python
a = 1
while a != 5:
    print(a)
    a += 1
```

- The loop iterates as long as `a` is not equal to 5.
- It prints the value of `a` and increments it until `a` becomes 5.

Using the `while` loop with a conditional statement allows you to control the flow of your program based on specific conditions.

![[Pasted image 20230828182242.png]]

## Controlling Loop Execution with Conditions

In a loop, the condition determines whether the block of code within the loop is executed or not.

### Example: Loop with Condition

Consider the following loop with the condition `number < 10`:

```python
number = int(input("Please type in a number: "))

while number < 10:
    print(number)
    number += 1

print("Execution finished.")
```

- The block within the loop is executed only if `number` is less than 10.
- The loop repeatedly prints the value of `number` and increments it by 1.
- The loop stops when `number` becomes 10 or greater.

### Possible Outputs

1. If user input is 4, the loop prints numbers from 4 to 9 and then finishes execution.
2. If user input is 12, the loop's condition is never met, and the loop doesn't execute. The program directly prints "Execution finished."

In this loop structure, the condition is evaluated before the block execution, ensuring that the block is executed only when the condition is met.
