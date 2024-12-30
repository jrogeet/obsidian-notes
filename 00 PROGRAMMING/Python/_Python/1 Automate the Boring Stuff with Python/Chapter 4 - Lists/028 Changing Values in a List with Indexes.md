Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[023 List Data Type|List]] 

---
# Changing Values in a List with Indexes

Normally, a variable name goes on the left side of an assignment statement, like ___spam = 42___.

However, you can also use an index of a list to change the value at that index.

For example, ___spam\[1] = 'aardvark'___ means “__Assign the value__ at __index ___1___ in the list ___spam___ to the string ___'aardvark'___.”

```python
spam = ['cat', 'bat', 'rat', 'elephant']
spam[1] = 'aardvark'
print(spam)

spam[2] = spam[1]
print(spam)

spam[-1] = 12345
print(spam)
```