Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list #listindexes
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[023 List Data Type|List]] 

---
# Negative Indexes

- __Indexes__: starts at ___0___ and go up

- __Negative Indexes__: ___-1___ refers to the __last__ _index_ in a list, __-2__ refers to the __second-to-last__ _index_ in a list, and so on.

```python
spam = ['cat', 'bat', 'rat', 'elephant']

print(spam[-1])

print(spam[-3])

print('The ' + spam[-1] + ' is afraid of the ' + spam[-3] + '.')
```