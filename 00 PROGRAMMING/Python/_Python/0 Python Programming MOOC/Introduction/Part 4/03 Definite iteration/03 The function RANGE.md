---
part: "4.3"
topic: loops
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc  #introduction
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# RANGE function
Often you know how many times you want to repeat a certain bit of code. 

You might, for example, wish to go through all the numbers between ___1___ and ___100___. 

The ___range___ function plugged into a ___for loop___ will do this for you.

There are a few different ways to call the range function. 
The simplest way is to give the function just one argument, which signifies the end-point of the range. The end-point itself is excluded, just like with string slices. 
In other words, the function call ___range(n)___ provides a loop with a range from __0__ to __n-1__:

```python
for i in range(5):
    print(i)
```
With two arguments, the function will return a range between the two numbers. 
The function ___range(a,b)___ provides a range starting from __a__ and ending at __b-1__:

```python
for i in range(3, 7):
    print(i)
```

Finally, with a third argument you can also specify the size of the _step_ the range takes between each value. The function call ___range(a, b, c)___ provides a range starting from __a__, ending at __b-1__, and changing by __c__ with every step:

```python
for i in range(1, 9, 2):
    print(i)
```

A step can also be __negative__. 
Then the range will be in ___reversed order___. 
Notice the first two arguments are also flipped here:

```python
for i in range(6, 2, -1):
    print(i)
```