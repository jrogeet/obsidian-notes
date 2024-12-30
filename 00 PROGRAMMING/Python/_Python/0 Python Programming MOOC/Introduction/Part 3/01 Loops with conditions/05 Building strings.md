---
topic: loops with conditions
part: "3.1"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #strings
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 05 Building strings

--- 
```python
words = "pride"
words = words + ", prejudice"
words = words + " and python"

print(words)
```

The `+=` operator allows us to write this a little more compactly:

```python
words = "pride"
words += ", prejudice"
words += " and python"

print(words)
```

This also applies to f-strings, which may come in handy if values stored in variables are needed as parts of the resulting string. For example this would work:

```python
course = "Introduction to Programming"
grade = 4

verdict = "You have received "
verdict += f"the grade {grade} "
verdict += f"from the course {course}"

print(verdict)
```

In the previous exercise you calculated the sum of consecutive numbers by always adding a new value inside a loop.

The exact same idea applies to strings as well: you can add new parts to a string within a loop. This technique should be useful in the following exercise.

