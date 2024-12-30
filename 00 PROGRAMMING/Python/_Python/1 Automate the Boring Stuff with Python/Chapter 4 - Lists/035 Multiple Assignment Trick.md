Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[023 List Data Type|List]] 

---
# The Multiple Assignment Trick

The _multiple assignment trick_ (technically called _tuple unpacking_) is a shortcut that lets you assign multiple variables with the values in a list in one line of code. 

So instead of doing this:
```python
cat = ['fat', 'gray', 'loud']
size = cat[0]
color = cat[1]
disposition = cat[2]
```

you could type this line of code:
```python
cat = ['fat', 'gray', 'loud']
size, color, disposition = cat

print(color)
```
The __order__ should be the same for ex: ___size is fat___, ___color is gray___ etc.



>The number of variables and the length of the list must be exactly equal, or Python will give you a ValueError:
```python
cat = ['fat', 'gray', 'loud']
size, color, disposition, name = cat
```

