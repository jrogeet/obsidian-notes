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
# 04 Concatenating strings with the + operator

--- 
## Tracking PIN Attempts and Codes

Helper variables can be used to track user attempts or codes in loops.

### Tracking Attempts

In a PIN checking scenario, a variable `attempts` is used to count how many times the user tries to enter a code:

```python
attempts = 0

while True:
    code = input("Please type in your PIN: ")
    attempts += 1
    # ...
```

- The `attempts` variable is incremented with each iteration.

### Tracking Codes

Similarly, you can track all the PIN codes entered by the user:

```python
codes = ""
attempts = 0

while True:
    code = input("Please type in your PIN: ")
    attempts += 1
    codes += code + ", "
    # ...
```

- The `codes` variable starts as an empty string.
- With each iteration, the entered code is appended along with a comma.

For example, if the user enters the codes 1111, 2222, and 1234, the value of `codes` would be:

```
1111, 2222, 1234,
```

Helper variables like `attempts` and `codes` help manage information and provide insights into the program's behavior during its execution.
