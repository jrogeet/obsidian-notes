---
topic: lists
part: "5.2"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #references #lists 
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 04 Using lists as parameters in functions

--- 
Passing a list as an argument to a function means passing a reference to that list.
The function can modify the list directly.

```python
def add_item(my_list: list):
    new_item = 10
    my_list.append(new_item)

a_list = [1,2,3]
print(a_list)
add_item(a_list)
print(a_list)
```

___add_item___ function does not have a return value.
It only changes the list it takes as an argument.
![[Pasted image 20230903122357.png]]
	- __Global frame__ refers to the variables defined in the __main function__
	- ___add_item___ frame with a blue background represents the parameters and variables _within that function_.
	- As you can see from the visualisation, the ___`add_item`___ function refers to the very same list as the main function. 
	- The changes made within the ___`add_item`___ function also affect the main function.

Another way to implement this functionality would be to create a new list within the function, and return that:

```python
def add_item(my_list: list) -> list:
    new_item = 10
    my_list_copy = my_list[:]
    my_list_copy.append(new_item)
    return my_list_copy

numbers = [1, 2, 3]
numbers2 = add_item(numbers)

print("original list:", numbers)
print("new list:", numbers2)
```

