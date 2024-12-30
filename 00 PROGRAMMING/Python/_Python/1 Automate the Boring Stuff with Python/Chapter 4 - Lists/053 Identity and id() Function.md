Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #references #idfunction #pythontheory 
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Identity and the id() Function

All values in Python have a unique identity that can be obtained with the ___id()___ function.

```python
id('Howdy')
```

When python runs ___id('Howdy')___, it creates the 'Howdy' string in the computer's memory.

The numeric memory address where the string is stored is returned by the ___id()___ function.

Python picks this __address__ based on which _memory bytes_ happen to be _free on your computer at the time_, so it'll be different each time you run this code.

___'Howdy'___ like all strings, is __immutable__. 
If you _change_ the string in a variable, a __new string object__ is being made at a _different place_ in memory,

and the variable refers to this _new string_.

```python
bacon = 'Hello'
print(id(bacon))

bacon += ' world!' # An ew string is made from 'Hello' and ' world!'.
print(id(bacon)) # bacon now refers to a completely different string.
```

---
However, lists can be modified because they are __mutable__ objects.
The ___append()___ method doesn't create a new list object; 
it changes the existing list object. This is called "_modifying the object in-place_"

```python
eggs = ['cat', 'dog']
print(id(eggs))

eggs.append('moose') # append() modifies the list "in place".
print(id(eggs)) # eggs still refers to the same list as before.

eggs = ['bat', 'rat', 'cow'] # This creates a new list, which has a new identity.

print(id(eggs))
```

if two variables refer to the same list(like ___spam___ and ___cheese___) and the list value itself changes,
_BOTH_ variables are __AFFECTED__ because they both refer to the same list.

The ___append()___, ___extend()___, ___remove()___, ___sort()___, ___reverse()___, and other list methods __modify their lists in place__.