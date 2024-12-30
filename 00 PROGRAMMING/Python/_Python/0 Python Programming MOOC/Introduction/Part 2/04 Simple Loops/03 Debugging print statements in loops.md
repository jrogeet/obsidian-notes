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
# 03 Debugging print statements in loops

--- 
## Debugging Loops with Print Statements

Adding loops to programs increases the potential for bugs. Debugging print statements, introduced earlier, become even more valuable for troubleshooting loop-related issues.

### Identifying Issues in a PIN Example

Consider an example similar to the previous one, but with a crucial difference:

```python
attempts = 0

while True:
    code = input("Please type in your PIN: ")
    attempts += 1

    if attempts == 3:
        success = False
        break

    if code == "1234":
        success = True
        break

    print("Incorrect...try again")

if success:
    print("Correct PIN entered!")
else:
    print("Too many attempts...")
```

- The code should stop and print "Correct PIN entered!" when the correct code is entered on the third attempt.
- However, it wrongly prints "Too many attempts..."

### Using Debugging Print Statements

Adding targeted print statements inside the loop can help diagnose the issue:

```python
while True:
    print("beginning of the while block:")
    code = input("Please type in your PIN: ")
    attempts += 1

    print("attempts:", attempts)
    print("condition1:", attempts == 3)
    if attempts == 3:
        success = False
        break

    print("code:", code)
    print("condition2:", code == "1234")
    if code == "1234":
        success = True
        break

    print("Incorrect...try again")
```

- Print statements reveal the flow of execution and the values of variables.
- In this case, the first condition evaluates to true on the third attempt, leading to an incorrect outcome.

Order of conditional statements and their branches can lead to bugs, especially in loops. Debugging print statements are a valuable tool for finding their causes.
