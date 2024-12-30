---
topic: loops
part: "2.4"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #loops
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 04 Simple loops

--- 

## Introduction to While Loops

Repetition, or iteration, is a fundamental programming technique. It involves controlling which code lines execute and when. Control structures allow you to manage code execution flow. Conditional structures help you choose between code sections, while iteration structures let you repeat code sections. These structures are often called loops because they enable code to loop back to previously executed lines. Each iteration of the loop executes one repetition.

### Basic Structure of a While Loop

A simple `while` loop is introduced in this section. It resembles the conditional statements covered earlier.

```python
while True:
    number = int(input("Please type in a number, -1 to quit: "))

    if number == -1:
        break

    print(number ** 2)

print("Thanks and bye!")
```

- The loop continues until the user enters -1.
- The `break` command exits the loop when -1 is entered.

### Ensuring Loop Termination

Loops must have an exit point; otherwise, they could run indefinitely. Consider this example:

```python
number = int(input("Please type in a number, -1 to quit: "))
while True:
    if number == -1:
        break

    print(number ** 2)

print("Thanks and bye!")
```

- This example demonstrates an infinite loop because the exit condition is missing.

### Interactive PIN Example

Here's an example where the user must enter the correct PIN (1234) to proceed:

```python
while True:
    code = input("Please type in your PIN: ")
    if code == "1234":
        break
    print("Incorrect...try again")

print("Correct PIN entered!")
```

- The loop requires the correct PIN to exit.
- Incorrect entries trigger a retry message.

While loops are crucial in programming, but proper exit conditions are essential to avoid infinite repetition.
