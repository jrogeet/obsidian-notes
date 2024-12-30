Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list #enumeratefunction #enumerate
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]]  [[023 List Data Type|List]] 

---
# Using the enumerate() Function with Lists

Instead of using the ___range(len(someList))___ technique with a ___for loop___ to obtain the integer index of the items in the list, you can call the ___enumerate()___ function instead.


On each iteration of the loop, ___enumerate()___ will __return two values__: the ___index___ of the item in the list, and the ___item___ in the list itself.

```python
supplies = ['pens', 'staplers', 'flamethrowers', 'binders']
for index, item in enumerate(supplies):
	print('Index ' + str(index) + ' in supplies is: ' + item)
```

>The ___enumerate()___ function is useful if you need both the item and the item’s index in the loop’s block.

