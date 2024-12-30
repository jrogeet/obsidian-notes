Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list #tuple
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[023 List Data Type|List]] 

---
# Converting Types with list() and tuple() Functions

Just like how ___str(42)___ will return ___'42'___, the string representation of the integer ___42___,

the functions ___list()___ and ___tuple()___ will return list and tuple versions of the values of the values passed to them.

```python
tuple(['cat', 'dog', 5])

list(('cat', 'dog', 5))

list('hello')
```

> Converting a tuple to a list is handy if you need a _mutable version_ of a __tuple__ value.