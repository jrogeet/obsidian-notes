Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list 
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[023 List Data Type|List]] 

---
# Mutable and Immutable Data Types

A `list` value is a __mutable data type__: it can have values ___added___, ___removed___, or ___changed___.

A `string` is __immutable__: it ___cannot be changed___. 
Trying to reassign a single character in a string results in a ___TypeError___ error.

```python
name = 'Zophie a cat'
name[7] = 'the'
```

The proper way to "__mutate__" a string is to use ___slicing___ and ___concatenation___ to build a new string by _copying_ from parts of the old string.
```python
name = 'Zophie a cat'
newName = name[0:7] + 'the' + name[8:12]
print(name)

print(newName)
```
We used ___[0:7]___ and ___[8:12]___ to refer to the characters that we don't wish to replace.

Notice that the original ___'Zophie a cat'___ string is not modified, because _strings_ are __immutable__.

---

Although a list value is mutable, the second line does not modify the list ___eggs___:
```python
eggs = [1, 2, 3]
eggs = [4, 5, 6]
print(eggs)
```
The list value in ___eggs___ isn't being changed here; rather, an entirely new and different list value ( ___[4, 5, 6]___ ) is overwriting the old list value ( ___[1, 2, 3]___ ).

To actually modify the original list in ___eggs___ to contain ___[4, 5, 6]___:
```python
eggs = [1, 2, 3]
print(eggs)
del eggs[2]
del eggs[1]
del eggs[0]

eggs.append(4)
eggs.append(5)
eggs.append(6)
print(eggs)
```

![[Pasted image 20230721212514.png]]
![[Pasted image 20230721212254.png]]

