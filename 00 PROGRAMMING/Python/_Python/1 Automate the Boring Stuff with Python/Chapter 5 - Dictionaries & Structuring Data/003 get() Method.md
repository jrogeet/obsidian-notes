Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python 
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# get() Method

takes two arguments: 
- the `key` of value to retrieve and
- a fallback `value` to return if that key does not exist.

```python
dictionary.get(key, value)
```

```python
picnicItems = {'apples':5, 'cups':2}
'I am bringing ' + str(picnicItems.get('cups', 0)) + ' cups.'
# I am bringing 2 cups

'I am bringing ' + str(picnicItems.get('eggs', 0)) + ' eggs.' 
# 'I am bringing 0 eggs.'
```

There's no `eggs` key in the `picnicItems` dictionary,
the default value `0` is returned by the `get()` method.

without `get()` Method, it would've caused an error message:
```python
>>> picnicItems = {'apples': 5, 'cups': 2} 
>>> >>> 'I am bringing ' + str(picnicItems['eggs']) + ' eggs.' 
>>> >>> Traceback (most recent call last): File "", line 1, in 'I am bringing ' + str(picnicItems['eggs']) + ' eggs.' KeyError: 'eggs'
```