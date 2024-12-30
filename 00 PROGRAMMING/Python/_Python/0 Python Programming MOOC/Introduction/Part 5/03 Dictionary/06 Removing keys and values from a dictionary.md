---
topic: dictionary
part: "5.3"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #dictionary
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 06 Removing keys and values from a dictionary

--- 
It is naturally possible to also remove key-value pairs from the dictionary.

## 2 Ways to Remove key-value pairs

### 1. ___del___ command

```python
staff = {"Alan": "lecturer", "Emily": "professor", "David": "lecturer"}
del staff["David"]
print(staff)
```

Deleting a key which doesn't exist in the dictionary will cause an error
```
>>> del staff["Paul"]
Traceback (most recent call last):
  File "", line 1, in 
KeyError: 'Paul'
```

So, before deleting a key you should check if it is present in the dictionary:

```python
staff = {"Alan": "lecturer", "Emily": "professor", "David": "lecturer"}
if "Paul" in staff:
  del staff["Paul"]
  print("Deleted")
else:
  print("This person is not a staff member")
```

### 2. ___pop___ method

The other way to delete entries in a dictionary is the method ___`pop`___:

```python
staff = {"Alan": "lecturer", "Emily": "professor", "David": "lecturer"}
deleted = staff.pop("David")
print(staff)
print(deleted, "deleted")
```

___pop___ also returns the value from the deleted entry.

By default, ___`pop`___ will also cause an error if you try to delete a key which is not present in the dictionary.

It is possible to avoid this by giving the method a second argument, which contains a _default return value_.



This value is returned in case the key is not found in the dictionary. The special Python value ___`None`___ will work here:

```python
staff = {"Alan": "lecturer", "Emily": "professor", "David": "lecturer"}
deleted = staff.pop("Alan", None)
if deleted == None:
  print("This person is not a staff member")
else:
  print(deleted, "deleted")
```


### Deleting entire dictionary

 To delete the contents of the ___ENTIRE Dictionary___, try to do it with a __for loop__
```python
staff = {"Alan": "lecturer", "Emily": "professor", "David": "lecturer"}
for key in staff:
  del staff[key]
```

 It will result in an ___ERROR___:
```
RuntimeError: dictionary changed size during iteration
```


>When traversing a collection with a ___`for` loop___, the contents may not change while the loop is in progress.
>
   Luckily, there is a __dictionary method__ for just this purpose:

```python
staff.clear()
```





