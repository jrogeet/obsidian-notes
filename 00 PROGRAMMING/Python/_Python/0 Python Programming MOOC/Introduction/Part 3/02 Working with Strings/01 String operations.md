---
topic: strings
part: "3.2"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #strings
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 01 String operations

--- 
Strings can be combined, or _concatenated_, with the `+` operator:

```python
begin = "ex"
end = "ample"
word = begin+end
print(word)
```
The `*` operator can also be used with a string, when the other operand is an integer. The string operand is then repeated the number of times specified by the integer. For example this would work:

```python
word = "banana"
print(word*3)
```
Using string operations together with a loop we can write a program which draws a pyramid:

```python
n = 10 # number of layers in the pyramid
row = "*"

while n > 0:
    print(" " * n + row)
    row += "**"
    n -= 1
```
his prints out the following:

```
          *
         ***
        *****
       *******
      *********
     ***********
    *************
   ***************
  *****************
 *******************
```

The `print` command within the loop prints a line, which begins with `n` spaces, followed by whatever is stored in the variable `row`. Then two stars are added to the end of the variable `row`, and the value of the variable `n` is decreased by 1.

