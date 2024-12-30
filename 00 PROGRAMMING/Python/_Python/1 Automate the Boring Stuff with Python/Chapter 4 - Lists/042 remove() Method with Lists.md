Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list #methods
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]]  [[023 List Data Type|List]] [[039 Methods|Methods]] 

---
# Removing Values from Lists with the remove() Method

The ___remove()___ Method will delete or remove the value that you passed on it from the list.
```python
spam = ['cat', 'bat', 'rat', 'elephant']
spam.remove('bat')
print(spam)
```

It will cause a __ValueError__ if you try to delete a value that doesn't exist.

```python
spam = ['cat', 'bat', 'rat', 'elephant']
spam.remove('chicken')
```

If the value appears multiple times in the list, only the FIRST instance of the value will be removed.

```python
spam = ['cat', 'bat', 'rat', 'cat', 'hat', 'cat']
spam.remove('cat')
print(spam)
```

The ___del___ statement is good to use when you know the __INDEX__ of the value you want to remove from the list.

The ___remove()___ method is useful when you know the __VALUE__ you want to remove from the list.