---
topic: terminology
part: "2.1"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #terminology
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 02 Block

--- 
A _block_ is a group of consecutive statements that are at the same level in the structure of the program. For example, the block of a conditional statement contains those statements which are executed only if the condition is true.

```python
if age > 17:
    # beginning of the conditional block
    print("You are of age!")
    age = age + 1
    print("You are now one year older...")
    # end of the conditional block

print("This here belongs to another block")
```

In Python blocks are expressed by indenting all code in the block by the same amount of whitespace.

NB: the main block of a Python program must always be at the leftmost edge of the file, without indentation:

```python
# this program will not work because it is not written at the leftmost egde of the file
  print("hello world")
  print("this program is not very good...")
```

