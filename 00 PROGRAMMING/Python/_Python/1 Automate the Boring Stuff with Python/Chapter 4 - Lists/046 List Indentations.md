Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list #indentation
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[023 List Data Type|List]] 

---
# Exception to Indetation rules in Python

Lists can actually span several lines in the source code file.

>The indentation of these lines does not matter.

Python knows that the list is not finished until it sees the __ending square bracket__ ( ___[ ]___ ).
```python
spam = ['apples',
	   'oranges',
						'bananas',
'cats']
print(spam)
```

We can also split up a single instruction across multiple lines using the ___\ `line continuation character`___ at the end.

```python
print('Four score and seven ' + \
	  'years ago...')
```

>These tricks are useful when you want to rearrange long lines of Python code to be a bit more readable.