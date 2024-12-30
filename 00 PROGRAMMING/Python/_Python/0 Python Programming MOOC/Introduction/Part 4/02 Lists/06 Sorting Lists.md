---
part: "4.2"
topic: lists
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #list  #introduction
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Sorting Lists

The items in a list can be _sorted_ from smallest to greatest with the method `sort`.

```python
my_list = [2,5,1,2,4]
my_list.sort()
print(my_list)
```

Notice how the method modifies the list itself. Sometimes we don't want to change the original list, so we use the function `sorted` instead. It _returns_ a sorted list:

```python
my_list = [2,5,1,2,4]
print(sorted(my_list)))
```

Remember the difference between the two: `sort` changes the order of the original list in place, whereas `sorted` creates a new, ordered copy of the list. With `sorted` we can preserve the original order of the list:

```python
original = [2, 5, 1, 2, 4]
in_order = sorted(original)
print(original)
print(in_order)
```

