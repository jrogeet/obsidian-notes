---
part: "4.5"
topic: lists
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc  #introduction #strings #list
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Strings are immutable
_Strings_ and _lists_ have a lot in common, especially in the way they behave with different operators. 
The main difference is that _strings_ are __immutable__. That means _they cannot be changed_.

```python
my_string = "exemplary"
my_string[0] = "a"
```

A similar error follows if you try to sort a string with the ___sort___ method.

_Strings_ themselves are __immutable__, but the _variables_ holding them are __not__. 
A string can be replaced by another string.

The following two examples are thus fundamentally different:

```python
my_list = [1,2,3]
my_list[0] = 10
```
![[Pasted image 20230815180106.png]]
```python
my_string = "Hey"
my_string = my_string + "!"
```
![[Pasted image 20230815180121.png]]
The first example changes the contents of the referenced list. 
The second example replaces the reference to the original string with a reference to another string. 
The original string is still somewhere in computer memory, but there is no reference to it, and it cannot be used in the program any longer.

