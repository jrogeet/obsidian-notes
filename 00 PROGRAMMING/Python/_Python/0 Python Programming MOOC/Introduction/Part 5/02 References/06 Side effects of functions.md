---
topic: functions
part: "5.2"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 06 Side effects of functions

--- 
> [!NOTE]
> If a function takes a reference to a list as an argument, it will be able to modify that list. If direct modifications were not intended by the programmer, accidentally modifying the list received as a parameter could cause problems elsewhere in the program.

Let's take a look at a function which is supposed to find the second smallest item in a list:
```python
def second_smallest(my_list: list) -> int:
    # in an ordered list, the second smallest item is at index 1
    my_list.sort()
    return my_list[1]

numbers = [1, 4, 2, 5, 3, 6, 4, 7]
print(second_smallest(numbers))
print(numbers)
```

The function does find the second smallest item, but it sorts the list in place, changing the order of the items.

f the order is significant elsewhere in the program, calling the function could cause errors. 
Unintentional modifications to an object accessed through a reference is called a _side effect_ of a function.

---

We can avoid the side effect by making a small change to the function:

```python
def second_smallest(my_list: list) -> int:
    list_copy = sorted(my_list)
    return list_copy[1]

numbers = [1, 4, 2, 5, 3, 6, 4, 7]
print(second_smallest(numbers))
print(numbers)
```
- The function ___`sorted`___ returns a new, sorted copy of the list, so looking for the second smallest item no longer messes with the order of the original list.

It is generally considered a good programming practice to avoid causing side effects with functions. Side effects can make it more difficult to verify that the program functions as intended in all situations.

Functions free of side effects are also called _pure functions_. Especially when adhering to a functional programming style, this is a common ideal to follow. We will explore this topic further in _Advanced Course in Programming_, which is the course following this one.