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
# 03 Writing conditions

--- 
## Loop Conditions and Examples

In a loop, any Boolean expression or combination of expressions can serve as a valid condition. This allows for dynamic and versatile loop behavior.

### Example: Printing Every Third Number

The following program prints every third number as long as the number is less than 100 and not divisible by 5:

```python
number = int(input("Please type in a number: "))

while number < 100 and number % 5 != 0:
    print(number)
    number += 3
```

- For input 28, the loop ends at 37 since the next number (40) is divisible by 5.
- For input 96, the loop ends at 99 since the next number (102) is not less than 100.

### Ensuring Loop Termination

It's crucial to ensure that a loop's execution will eventually end. Consider this example:

```python
number = int(input("Please type in a number: "))

while number != 10:
    print(number)
    number += 2
```

- If the input is an even number 10 or less, the loop terminates as `number` reaches 10.
- For other cases like input 3 or 12, the loop becomes an infinite loop since `number` will never equal 10.
- A well-structured loop should always have a condition that guarantees termination.