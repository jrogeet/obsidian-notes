---
topic: 
part: "5.2"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 05 Editing a list given as an argument

--- 
The following is an attempt at a function which should augment each item in a list by ten:
```python
def augment_all(my_list: list):
    new_list = []
    for item in my_list:
        new_list.append(item + 10)
    my_list = new_list

numbers = [1, 2, 3]
print("in the beginning:", numbers)
augment_all(numbers)
print("after the function is executed:", numbers)
```

- The function takes a _reference_ to a list as an argument. 
- This is stored in the variable ___`my_list`___. 
- The assignment ___`my_list = new_list`___ assigns a new value to that same variable.
-  The variable ___`my_list`___ now points to the new list created inside the function, and the reference to the original list is no longer available within the function. 
- This assignment has no effect outside the function, however.

The variable ___new_list___, which contains the new, augmented values,_NOT ACCESSIBLE_ from __outside the function__. 
it's "lost" after the execution of the function finishes

The variable ___numbers___ in the main function always points to the original list.

### FIX:
Copy all the items from the new list to the old list, __one by one__:
```python
def augment_all(my_list: list):
    new_list = []
    for item in my_list:
        new_list.append(item + 10)

    # copy items from the new list into the old list
    for i in range(len(my_list)):
        my_list[i] = new_list[i]
```

---

Another way is using ___slice___ [[03 Copying a list]]
	Example:
```python
my_list = [1, 2, 3, 4]
my_list[1:3] = [10, 20]
print(my_list)
[1, 10, 20, 4]
```

A slice can include the entire collection:
```python
my_list = [1, 2, 3, 4]
my_list[:] = [100, 99, 98, 97]
print(my_list)
```

The entire contents of the old list are replaced.

---

```python
def augment_all(my_list: list):
    new_list = []
    for item in my_list:
        new_list.append(item + 10)

    my_list[:] = new_list
```

> [!NOTE]
> Actually, there is no need to create a new list within the function at all. We can just assign the new values directly into the original list:

```python
def augment_all(my_list: list):
    for i in range(len(my_list)):
        my_list[i] += 10
```

