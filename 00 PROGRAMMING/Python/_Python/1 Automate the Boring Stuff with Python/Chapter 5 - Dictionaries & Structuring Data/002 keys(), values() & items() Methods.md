Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python 
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---

- a `for` loop can iterate over the `keys`, `values`, or _key-value pairs_ in a __Dictionary__

```python
spam = {'color':'red', 'age':42}

for k, v in spam.items():
	print('Key: ' + k + ' Value: ' + str(v))
```

## Checking Whether a Key or Value Exists in a Dictionary

Check if `key` or `value` exists in a dictionary using __in__ and __not in__

```python
spam = {'name':'Zophie', 'age':7}
'name' in spam.keys()
# True

'Zophie' in spam.values() 
# True

'color' in spam.keys() 
# False

'color' not in spam.keys() 
# True

'color' in spam 
# False
```

