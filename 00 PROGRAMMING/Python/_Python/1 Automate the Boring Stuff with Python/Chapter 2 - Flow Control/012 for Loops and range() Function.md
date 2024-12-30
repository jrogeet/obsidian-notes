Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #forloop #rangefunction
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Flow Control Statements

## for Loops and range() Function

The [[011 While Statements#while Loop Statements|While Loop]] keeps looping while its condition is ***True***.

but if you want to execute a block of code *only a certain number of times*.

You need to use ***For Loops*** statement and the ***range()*** function.

```python
for i in range(5):
```

It includes the following:
-   The ***for*** keyword
-   A variable name
-   The in keyword
-   A call to the ***range()*** method with up to three integers passed to it
-   A colon
-   Starting on the next line, an indented block of code (called the ***for*** clause)

```python
print('My name is')  
for i in range(5):  
    print('Jimmy Five Times (' + str(i) + ')')
```

**NOTE:**
You can also use ***[[011 While Statements#break Statements|break]]*** and ***[[011 While Statements#continue Statements |continue]]*** statements inside for loops

The ***[[011 While Statements#continue Statements |continue]]*** statement will continue to the next value of the ***for loop***’s counter, as if the program execution had reached the end of the loop and returned to the start.

![[Pasted image 20230519181036.png | center | 400]]

Sample Program:
```python
total = 0
for num in range(101):
	total = total + num
print(total)
```

>There are 50 pairs of numbers that add up to 101: 1 + 100, 2 + 99, 3 + 98, and so on, until 50 + 51. Since 50 × 101 is 5,050, the sum of all the numbers from 0 to 100 is 5,050.

## **The Starting, Stopping, and Stepping Arguments to range()**

Some functions can be called with *multiple arguments separated by a comma*, and ***range()*** is one of them. 

This lets you change the integer passed to ***range()*** to follow any sequence of integers, including starting at a number other than zero.

### Start and Stop
```python
for i in range(12, 16):
	print(i)
```
The ***FIRST*** number/argument will be where the ***for loop*** variable starts,
and the ***SECOND*** number/argument will be **UP TO**, but **NOT INCLUDING**, the number to **stop** at.

### Steps
It can also call THREE numbers/arguments. the First TWO is the start and stop values,
the THIRD is the **steps** argument.
```python
for i in range(0, 10, 2):  
    print(i)
```
So the **steps** will be by TWOs (example: 0, 2, 4, 6 ... etc.)


The ***range()*** function is flexible in the sequence of numbers it produces for ***for loops***.
We can use **NEGATIVE NUMBER** for the **STEP** argument to make the ***for loop*** COUNT DOWN instead of UP.

```PYTHON
for i in range(5, -1, -1):
	print(i)
```

