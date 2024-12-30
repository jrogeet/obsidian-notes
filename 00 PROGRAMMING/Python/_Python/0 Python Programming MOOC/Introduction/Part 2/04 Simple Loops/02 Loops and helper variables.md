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
# 02 Loops and helper variables

--- 
Let's make the PIN checking example a bit more realistic. This version gives the user only three attempts at typing in a PIN.

The program uses two helper variables. The variable `attempts` keeps track of how many times the user has typed in a PIN. The variable `success` is set to either `True` or `False` based on whether the user is successful in signing in.

```python
attempts = 0

while True:
    code = input("Please type in your PIN: ")
    attempts += 1

    if code == "1234":
        success = True
        break

    if attempts == 3:
        success = False
        break

    # this is printed if the code was incorrect AND there have been less than three attempts
    print("Incorrect...try again")

if success:
    print("Correct PIN entered!")
else:
    print("Too many attempts...")
```

The loop is exited _either_ when the user types the correct PIN _or_ if there have been too many attempts. The `if` statement after the loop checks the value of the variable `success` and prints out a message accordingly.