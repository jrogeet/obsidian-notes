---
topic: loops
part: "4.3"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc  #introduction
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Definite iteration
You can use a ___while___ loop to go through the items in a list, just like we used while loops to go through strings. The following program prints out the items in the list, each on a separate line:
```python
my_list = [3, 2, 4, 5, 2]

index = 0
while index < len(my_list):
    print(my_list[index])
    index += 1
```

This obviously works, but it is a rather complicated way of going through a list, as you have to use a helper variable ___index___ to remember which item in the list you're at. 
Fortunately, Python offers a more intuitive way of traversing through lists, strings and other similar structures.

