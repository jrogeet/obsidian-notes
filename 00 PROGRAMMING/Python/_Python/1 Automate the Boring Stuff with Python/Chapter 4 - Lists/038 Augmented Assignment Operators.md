Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list #augmentedassignmentoperators
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]]  [[023 List Data Type|List]] 

---
# Augmented Assignment Operators 

When assigning a value to a variable, you will frequently use the variable itself. 

For example, after assigning ___42___ to the variable ___spam___, 
you would increase the value in ___spam___ by ___1___

```python
spam = 42
spam = spam + 1
print(spam)
```
As a shortcut, you can use the __augmented assignment operator__ ___+=___ to do the same thing:
```python
spam = 42
spam += 1
print(spam)
```

There are augmented assignment operators for the +, -, *, /, and % operators

__Augmented assignment statement Equivalent assignment statement__

|            |                 |
| ---------- | --------------- |
| spam += 1  | spam = spam + 1 |
| spam -= 1  | spam = spam - 1 |
| spam \*= 1 | spam = spam * 1 |
| spam /= 1  | spam = spam / 1 |
| spam %= 1  | spam = spam % 1 |


___+=___ operator can also do string and list concatenation, and 
the ___*=___ operator can do string and list replication.

```python
spam = 'Hello'
spam += 'world!'
print(spam)

bacon = ['Zophie']
bacon *= 3
print(bacon)
```