Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list #tuple
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[023 List Data Type|List]] 

---
# The Tuple Data Type
the _Tuple_ data Type is almost identical to the _List_ data type,
Except in Two Ways:
1. Tuples are typed with parentheses, ___(___  ___)___  , instead of square brackets ___[ ]___ .
	```python
	eggs = ('hello', 42, 0.5)
	print(eggs[0])

	print(eggs[1:3])
	print(len(eggs))
	```
2. Tuples like _strings_, are ___immutable___(cannot have their values __modified__, __appended__, or __removed__)
	```python
	eggs = ('hello', 42, 0.5)
	eggs[1] = 99
	```


If there's _only one value in your tuple_, you can indicate this by placing a __trailing comma__ after the value inside the parentheses.
```python
print(type(('hello',)))

print(type(('hello')))
```
The __comma__ is what lets Python know this is a tuple value.