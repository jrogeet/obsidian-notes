---
part: "4.3"
topic: loops
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc  #introduction
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# range to a list
The function ___range___ returns a range object, which in many ways behaves like a list, but isn't actually one. 
If you try printing out the value the function returns, you will only see a description of a range object:

```python
numbers = range(2, 7)
print(numbers)
```

The function ___list___ will convert a _range_ into a ___list___. 
The list will contain all the values that are in the range. 
The Advanced Course in Programming course, which follows this one, will shed more light on this subject.

```python
numbers = list(range(2, 7))
print(numbers)
```

