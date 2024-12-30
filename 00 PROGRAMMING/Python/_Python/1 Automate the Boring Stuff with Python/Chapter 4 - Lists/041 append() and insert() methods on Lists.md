Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list #methods
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]]  [[023 List Data Type|List]] [[039 Methods|Methods]] 

---
# Adding Values to Lists with the append() and insert() Methods

To add new values to a list, use the ___append()___ and ___insert()___ methods.

```python
spam = ['cat', 'dog', 'bat']
spam.append('moose')
print(spam)
```

The ___insert()___ method can insert a value at __any index__ in the list.
The __first argument__ to ___insert()___ is the __index__ for the new value,
and the __second argument__ is the ___new value___ to be inserted.

```python
spam = ['cat', 'dog', 'bat']
spam.insert(1, 'chicken')
print(spam)
```

The ___append()___ and ___insert()___ methods are list methods and can be called only on list values, __not on other values such as ___strings___ or ___integers_____. 

Note the ___AttributeError___ error message that show up:
```python
eggs = 'hello'
eggs.append('world')

bacon = 42
bacon.insert(1, 'world')
```