---
topic: tuple
part: "5.4"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #tuple
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 01 Tuple

--- 
Tuple is a data structure which is, in many ways, similar to a list. The most important differences between the two are:

- ___Tuples___ are enclosed in parentheses ___`()`___, while __lists__ are enclosed in square brackets __`[]`__
- ___Tuples___ are _immutable_, while the contents of a __list__ may __change__
- Items stored in a ___Tuple___ are accessed by __Index__, just like the items stored in a _list_.
- Values stored in a ___tuple___ cannot be changed once defined.
Example: Coordinates

```python
point = (10, 20)
print("x coordinate:", point[0])
print("y coordinate:", point[1])
```


## What is the purpose of a Tuple?
Tuples are ideal for when there is a set collection of values which are in some way connected.
Example:
	when there is a need to handle the x and y coordinates of a point, a tuple is a natural choice, because coordinates will always consist of two values:

```python
point = (10, 20)
```

Technically it is of course possible to also use a list to store these:

```python
point = [10, 20]
```
Although, Collections in a list needs to be in consecutive order, so when you store a coordinate in a list, you need to store the x and y coordinates specifically, not an arbitrary list containing those values.

Unlike lists, ___Tuples___ are __IMMUTABLE__, they can be used as keys in a dictionary.

This example creates a __Dictionary__ where the _keys_ are the __COORDINATE POINTS__
```python
points = {}
points[(3, 5)] = "monkey"
points[(5, 0)] = "banana"
points[(1, 2)] = "harpsichord"
print(points[(3, 5)])
```
This would not work if you use __Lists__
```python
points = {}
points[[3, 5]] = "monkey"
points[[5, 0]] = "banana"
points[[1, 2]] = "harpsichord"
print(points[[3,5]])
```



