---
topic: commands with loops
part: "3.3"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #commands #loops
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 01 Break command

--- 
## Using the `break` Command in Loops

The `break` command is used to immediately stop the execution of a loop. It's commonly used in situations where the loop should end when a specific condition is met.

Two versions of a program calculating the sum of numbers until -1 is entered:
- 1st version using `break`:
```python
sum = 0

while True:
    number = int(input("Please type in a number, -1 to exit: "))
    if number == -1:
        break
    sum += number

print(f"The sum is {sum}")
```

- 2nd version without `break`:
```python
sum = 0
number = 0

while number != -1:
    number = int(input("Please type in a number, -1 to exit: "))
    if number != -1:
        sum += number

print(f"The sum is {sum}")
```

Both versions produce the same output, but the 1st version is often preferred due to its simplified condition structure and avoiding the need to initialize `number` outside the loop.

The `break` command can also be used alongside a condition in a while loop. For example, the following loop calculates the sum of numbers until the sum reaches 100 or -1 is entered:
```python
sum = 0

while sum <= 100:
    number = int(input("Please type in a number, -1 to exit: "))
    if number == -1:
        break
    sum += number

print(f"The sum is {sum}")
```

Both `break` and conditions can be used together to create more complex loop behaviors, providing flexible control over the loop's termination.

