---
topic: terminology
part: "5.2"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #references
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 01 References

--- 
In Python, ___variables don't store values directly___; instead, they store __references__ to _objects in memory_. 
This concept means that the variable points to the location in memory where the actual value is stored. 
The ___`id`___ function can be used to find the exact memory location that a variable references.


- Variables in Python hold references to objects rather than the actual values.
- Objects can be ___integers___, ___strings___, ___lists___, or any ___other data type___.
- A reference is often depicted as an arrow from the variable to the actual object.
	![[Pasted image 20230902200808.png]]
- The ___`id`___ function returns a unique identifier (memory address) for an object.
```python
a = [1, 2, 3]
print(id(a))
b = "This is a reference, too"
print(id(b))
```

> [!NOTE]
> The ___reference___ or ___ID___ of the variable, is an integer <br>
Which can be thought of as the address in computer memory where the value of the variable is stored. <br>
Every time you run the code above, the result will be different as the variable point to different locations - the references will be different


### Strings
Python string are handled very much like lists, with references to locations in memory.

Many built-in types in Python, such as ___str___, are immutable.
The value of the object cannot change but the value can be replaced with a new value:
![[Pasted image 20230902201839.png]]

---
Some Python types are __mutable__. 
	 For example: The contents of a list can change without needing to create a whole new list:
	 ![[Pasted image 20230902201946.png]]

___int, float___ and ___bool___ are __immutable__ in Python.
```python
number = 1
number = 2
number += 10
```

It seems that the commands above are just changing the value stored in the variable, but in fact each command _creates a whole new number in the computer's memory._

The printout from the following program illuminates the situation:
```python
number = 1
print(id(number))
number += 10
print(id(number))
a = 1
print(id(a))
```
	At first, the variable `number` points to the memory location 4535856912. When `number` is assigned a new value, it points to the location 4535856944. Now, when the variable `a` is assigned the value 1, `a` points to the very same location where `number` was pointing, when it was also assigned the value 1.

	It seems Python has stored the value 1 in the memory location 4535856912. Whenever a variable is assigned the value 1, it _refers_ to that location in computer memory.



> [!NOTE]
> It is good to keep in mind that _almost everything is a reference_ in Python, but all this is rarely relevant to everyday programming tasks. So let's get back to more practical matters.

