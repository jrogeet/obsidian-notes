Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list #listslice
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[023 List Data Type|List]] 

---
# Getting a List from another List with Slices

An _index_ can get a single value from a list,

a ___Slice___ can get several values from a list, in the form of a new list.

- A slice is typed _between square brackets_, like an ___index___, but it has __two integers__ separated by a ___colon___.
	- ___spam\[2]___ is a list with an index (one integer).
	- ___spam\[1:4]___ is a list with a slice (two integers).

The ___first integer___ is the index where the slice __starts__. 
The ___second integer___ is the index where the slice __ends__ 
>BUT __it will not include__ the _Value_ at the ___second index___.

```python
spam = ['cat', 'bat', 'rat', 'elephant']

print(spam[0:4])

print(spam[1:3])

print(spam[0:-1])
```

## Shortcut
You can leave out _ONE_ or _BOTH_ of the indexes on either side of the ___Colon___ of the Slice.

- Leaving out the __first index__ is the same as using ___0___ or the _beginning of the list_
- Leaving out the __second index__ is the same as using the ___length of the list___, which will slice to the _end of the list_.
```python
spam = ['cat', 'bat', 'rat', 'elephant']

print(spam[:2])

print(spam[1:])

print(spam[:])
```