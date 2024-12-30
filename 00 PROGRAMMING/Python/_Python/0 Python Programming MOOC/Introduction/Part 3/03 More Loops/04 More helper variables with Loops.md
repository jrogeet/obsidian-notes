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
# 04 More helper variables with Loops

--- 
We've already used helper variables, which increase or decrease with every iteration of a loop, many times before, 
so the following program should look quite familiar in structure. 

The program prints out all even numbers above zero until it reaches a limit set by the user:

```python
limit = int(input("Please type in a number: "))
i = 0
while i < limit:
    print(i)
    i += 2
```

The helper variable ___`i`___ is set to 0 before the loop, and it increases by two with every iteration.

Using nested loops sometimes necessitates a separate helper variable for the inner loop. 
The program below prints out a "number pyramid" based on a number given by the user:

```python
number = int(input("Please type in a number: "))
while number > 0:
    i = 0
    while i < number:
        print(f"{i} ", end="")
        i += 1
    print()
    number -= 1
```

In this program the outer loop uses the helper variable `number`, which decreases by 1 with each iteration until it reaches 0. The helper variable `i` is set to 0 just before the inner loop is entered, each time the outer loop repeats.

The inner loop uses the helper variable `i`, which increases by 1 with each iteration of the inner loop. The inner loop repeats until `i` is equal to `number`, and prints out each value of `i` on the same line, separated by a space character. When the inner loop finishes, the `print` command in the outer loop starts a new line.

Now remember that with each iteration of the outer loop the value of `number` decreases, so the amount of times the inner loop repeats also decreases. With each repetition the line of numbers gets shorter, and thus we get the pyramid shape.

Nested loops can get confusing fast, but understanding the way they work is essential. You may well find the Python Tutor [visualisation tool](http://www.pythontutor.com/visualize.html#mode=edit) helpful in understanding how this example works. Copy the above code into the code window of the tool and follow the formation of the printout and the changing values of the helper variables as the execution progresses.