---
topic: commands with loops
part: "3.3"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #loops #commands
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 03 Nested Loops

--- 

## Nested Loops

Just like conditional statements, loops can also be nested inside other loops. Nested loops consist of an outer loop and an inner loop. The inner loop is completely contained within the body of the outer loop.

Example: Countdown using nested loops:
```python
while True:
    number = int(input("Please type in a number: "))
    if number == -1:
        break
    while number > 0:
        print(number)
        number -= 1
```

In this example, an outer loop repeatedly asks the user to input a number until they input -1. Inside the outer loop, there's an inner loop that prints a countdown from the given number down to 1.

The `break` and `continue` commands within nested loops only affect the innermost loop they are a part of. If there are multiple nested loops, a `break` command will exit the innermost loop that contains it.

Example: Nested loops with `break`:
```python
while True:
    number = int(input("Please type in a number: "))
    if number == -1:
        break
    while True:
        if number <= 0:
            break
        print(number)
        number -= 1
```

In this example, the inner `break` command only stops the innermost loop, which is used to print the numbers.