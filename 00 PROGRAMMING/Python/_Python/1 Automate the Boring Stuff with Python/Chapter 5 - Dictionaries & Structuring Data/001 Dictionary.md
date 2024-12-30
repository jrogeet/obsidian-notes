Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python 
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Dictionary Data Type
- __MUTABLE__
- typed with _Braces_ `{}`
- __NOT IN ORDER__
- Instead of _Indexes_, In __Dictionaries__ it's called `keys`
	- a `key` has it's associated value and they're called a __key-value pair__

```python
myCat = {'size':'fat', 'color':'gray', 'disposition':'loud'}
```

Access these values through `keys`:
```python
myCat['size']
# 'fat'

'My cat has ' + myCat['color'] + ' fur.'
# My cat has gray fur.
```

_Integer_ value `keys`:
```python
spam = {12345: 'Luggage Combination', 42: 'The Answer'}
```

