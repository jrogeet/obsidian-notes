Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list #methods
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]]  [[023 List Data Type|List]] [[039 Methods|Methods]] 

---
# Sorting the Value in a List with the sort() Method

Lists of number values or lists of strings can be sorted with the ___sort()___ method.
```python
spam = [2, 5, 3.14, 1, -7]
spam.sort()
print(spam)

spam = ['ants', 'cats', 'dogs', 'badgers', 'elephants']
spam.sort()
print(spam)
```


To ___sort()___ in reverse order, pass ___True___ into the ___reverse___ keyword
```python
spam = ['ants', 'cats', 'dogs', 'badgers', 'elephants']

spam.sort(reverse=True)

print(spam)
```

## 3 Things to note about the ___sort()___ Method.

- First, ___sort()___ method sorts the list in place; don't try to capture the return value by writing code like ___spam = spam.sort()___. 

- Second, you __cannot sort lists__ that both have ___NUMBER values___ and ___STRING values___ in them, since Python doesn't know how to compare these values.
	This will result to a __TypeError__ error:
	```python
spam = [1, 3, 2, 4, 'Alice', 'Bob']
spam.sort()
	```

- Third, ___sort()___ uses "__ASCIIbetical order__" than actual alphabetical order for sorting strings. This means ___UPPERCASE___ letters come __BEFORE__ ___lowercase___ letters. 
- _lowercase_ ___a___ is sorted so that it comes __after__ the _UPPERCASE_ ___Z___.
	```python
	spam = ['Alice', 'ants', 'Bob', 'badgers', 'Carol', 'cats']
	spam.sort()
	print(spam)
	```