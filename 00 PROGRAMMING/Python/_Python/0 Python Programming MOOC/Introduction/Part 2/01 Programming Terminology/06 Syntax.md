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
# 06 Syntax

--- 
Similarly to natural languages, the _syntax_ of a programming language determines how the code of a program should be written. Each programming language has its own specific syntax.

The syntax of Python specifies, among other things, that the first line of an `if` statement should end in a colon character, and the block of the statement should be indented:

```python
if name == "Anna":
    print("Hi!")
```

If the syntactic rules of the programming language are not followed, there will be an error:

```python
if name == "Anna"
    print("Hi!")
```

Sample output
```
  File "test.py", line 1
    if name == "Anna"
                    ^
SyntaxError: invalid syntax
```