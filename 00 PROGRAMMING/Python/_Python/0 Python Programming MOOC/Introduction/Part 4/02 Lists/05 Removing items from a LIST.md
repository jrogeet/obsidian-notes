---
topic: lists
part: "4.2"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #list  #introduction
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Removing items from a LIST
There are two different approaches to removing an item from a list:

- If the __index__ of the item is known, you can use the method ___pop___.
- If the __contents__ of the item are known, you can use the method ___remove___`.

## Pop
So, the method ___pop___ takes the __index__ of the item you want to remove as its argument. 
The following program removes items at indexes 2 and 3 from the list. 
Notice how the indexes of the remaining items change when one is removed.

```python
my_list = [1, 2, 3, 4, 5, 6]

my_list.pop(2)
print(my_list)
my_list.pop(3)
print(my_list)
```

It's useful to remember that the method ___pop___ also __returns__ the removed item:

```python
my_list = [4, 2, 7, 2, 5]

number = my_list.pop(2)
print(number)
print(my_list)
```

## Remove
The method ___remove___, on the other hand, takes the value of the item to be removed as its argument. For example, this program

```python
my_list = [1, 2, 3, 4, 5, 6]

my_list.remove(2)
print(my_list)
my_list.remove(5)
print(my_list)
```

The method removes the _first_ occurrence of the value in the list, much like the string function ___find___ returns the first occurrence of a substring:

```python
my_list = [1, 2, 1, 2]

my_list.remove(1)
print(my_list)
my_list.remove(1)
print(my_list)
```

If the specified item is not in the list, the `remove` function causes an error. Just like with strings, we can check for the presence of an item with the `in` operator:

```python
my_list = [1, 3, 4]

if 1 in my_list:
    print("The list contains item 1")

if 2 in my_list:
    print("The list contains item 2")
```

