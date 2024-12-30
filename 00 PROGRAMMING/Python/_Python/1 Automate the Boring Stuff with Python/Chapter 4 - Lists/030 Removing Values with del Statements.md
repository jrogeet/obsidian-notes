Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[023 List Data Type|List]] 

---
# Removing Values from Lists with del Statements

The ___del___ statement will delete values at an index in a list.

All of the values in the list after the deleted value will be __moved up one index__.

```python
spam = ['cat', 'bat', 'rat', 'elephant']

del spam[2]
print(spam)

del spam[2]
print(spam)
```

>If you try to use the variable after deleting it, you will get a ___NameError___ error because the variable no longer exists.

The del statement can also be used on a simple variable to delete it, as if it were an “unassignment” statement.

In practice, you almost _never need to delete simple variables_. The del statement is __mostly used to delete values from lists__.