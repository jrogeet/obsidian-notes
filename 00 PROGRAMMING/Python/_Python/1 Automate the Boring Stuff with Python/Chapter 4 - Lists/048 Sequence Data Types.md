Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list 
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[023 List Data Type|List]] 

---
# Sequence Data Types
Lists aren’t the only data types that represent ordered sequences of values.

___Strings___ and ___Lists___ are actually similar if you consider a string to be a "list" of single text characters.

The Python ___sequence data types___ include _lists_, _strings_, __range objects__ returned by ___range()___, and _tuples_.

Things you can do with __Lists__ can also be done with __Strings__ and other values of sequence types: _indexing_; _slicing_; 
and using them with ___for___ loops, with ___len()___ and with ___in___ and ___not in___ operators.

```python
name = 'Zophie'

print(name[0])

print(name[-2])

print(name[0:4])

print('Zo' in name)

print('z' in name)

print('p' in name)

for i in name:
	print('* * *' + i + '* * *')
```

