Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #modules #copymodule  
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# The copy Module's copy() and deepcopy() Functions

If the function modifies the list or dictionary that is passed, you may not want these changes in the ___Original List___ or ___Dictionary value___. 

Python provides a module named __copy__ that provides both the ___copy()___ and ___deepcopy()___ functions.

## copy()
___copy.copy()___, can be used to make a __duplicate__ copy of a _mutable value_ like a list or dictionary, NOT just a copy of a reference.
```python
import copy
spam = ['A', 'B', 'C', 'D']
print(id(spam))

cheese = copy.copy(spam)
print(id(cheese))

cheese[1] = 42
print(spam)

print(cheese)
```

Now the ___spam___ and ___cheese___ variables refer to separate lists, 
which is why only the list in ___cheese___ is modified when you assign ___42___ at index ___1___.

![[Pasted image 20230722202407.png]]
The __reference ID numbers__ are not longer the same for both variables because the variables refer to _independent lists_.


## deepcopy()
> If the list you need to copy __contains lists__, then use the ___copy.deepcopy()___ function instead of ___copy.copy()___. 

>The ___deepcopy()___ function will copy these __inner lists__ as well.