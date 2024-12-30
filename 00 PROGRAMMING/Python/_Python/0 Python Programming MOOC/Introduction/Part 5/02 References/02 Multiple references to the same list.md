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
# 02 Multiple references to the same list

--- 
__What actually happens when you assign a list variable to a new variable - is the list copied over?__

```python
a = [1, 2, 3]
b = a
b[0] = 10
```

Variable ___a___ which is not the __list itself__, but a _reference_ to the list.
The __assignment__ ___b = a___ copies the reference
And now there's ___two references to the same memory___ location containing the list.

![[Pasted image 20230903114721.png]]

The list can be accessed through either of the two references:
```python
list1 = [1, 2, 3, 4]
list2 = list1

list1[0] = 10
list2[1] = 20

print(list1)
print(list2)
```

> [!NOTE]
> If there is _more than one_ reference to the same list, _any_ one of the references can be used to access the list. 
> On the other hand, a _change_ made through __any one of the references__ affects also the __other references__, as their target is the _same_.

