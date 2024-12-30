---
topic: conditional
part: "1.5"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #numbers #conditional
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Conditional statements

--- 
## Conditional Execution in Programming

In programming, not all lines of code need to be executed every time a program runs. You can use conditional execution to control when certain sections of code are executed based on specific conditions.

### Example: Checking User's Age

Consider the following code that checks whether the user is of age:

```python
age = int(input("How old are you? "))

if age > 17:
    print("You are of age!")
    print("Here's a copy of GTA6 for you.")

print("Next customer, please!")
```

- The user is prompted for their age using `input`.
- The `if` statement checks if the user's age is greater than 17.
- If the condition is met, the indented code block is executed.
- In this case, a message and an additional action are executed.
- Regardless of the condition, the final line is executed.

### Conditional Execution Flow

When the user is over the age of 17, the execution of the program should look like this:

```
How old are you? 18
You are of age!
Here's a copy of GTA6 for you.
Next customer, please!
```

- The program follows a logical flow based on the condition.
- If the user is not of age, the specific actions inside the `if` block are skipped.

Conditional execution allows you to create more dynamic and responsive programs that adapt to different situations.

These examples show us that the value given as input affects which parts of the program are executed. The program contains a _conditional statement_ with a block of code which is executed only if the condition in the statement is true.

![[Pasted image 20230828171444.png]]
In a conditional statement the keyword `if` is followed by a _condition_, such as a comparison of two values. The code block following this header line is only executed if the condition is true.

Notice the colon character following the `if` header. In the following code there is no colon:

```python
age = 10

# no colon at the end of the following line
if age > 17
    print("You are of age.")
```

