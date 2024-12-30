Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list #forloop
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[023 List Data Type|List]] 

---
# Using For Loops with Lists

a ___for loop___ repeats the code block __once for each item__ in a list value.

```python
for i in range(4):
	print(i)
```
This is because the __return value__ from ___range(4)___ is a sequence value that Python considers similar to __[0, 1, 2, 3]__.

This has the same output as the previous one:
```python
for i in [0, 1, 2, 3]:
	print(i)
```

A common Python technique is to use ___range(len(someList))___ with a ___for loop___ to iterate over the indexes of a list.

```python
supplies = ['pens', 'staplers', 'flamethrowers', 'binders']

for i in range(len(supplies)):
	print('Index ' + str(i) + ' in supplies is: ' + supplies[i])
```



Using ___range(len(supplies))___ is handy because the code `in the loop` can access the __index__ (as the variable ___i___ )

And the value at that __index__ (as ___supplies[i]___) 

>___range(len(supplies))___ will iterate through all the indexes of supplies, no matter how many items it contains.