---
topic: strings
part: "3.2"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #strings
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 05 Searching for substrings

--- 
The `in` operator can tell us if a string contains a particular substring. The Boolean expression `a in b` is true, if `b` contains the substring `a`.

For example, this bit of code

```python
input_string = "test"

print("t" in input_string)
print("x" in input_string)
print("es" in input_string)
print("ets" in input_string)
```

The program below lets the user search for substrings within a string hardcoded into the program:

```python
input_string = "perpendicular"

while True:
    substring = input("What are you looking for? ")
    if substring in input_string:
        print("Found it")
    else:
        print("Not found")
```

The operator `in` returns a Boolean value, so it will only tell us _if_ a substring exists in a string, but it will not be useful in finding out _where_ exactly it is. Instead, the Python string method `find` can be used for this purpose. It takes the substring searched for as an argument, and returns either the first index where it is found, or `-1` if the substring is not found within the string.

The image below illustrates how it is used:
![[Pasted image 20230828185138.png]]
The above substring search example implemented with `find`:

```python
input_string = "perpendicular"

while True:
    substring = input("What are you looking for? ")
    index = input_string.find(substring)
    if index >= 0:
        print(f"Found it at the index {index}")
    else:
        print("Not found")
```

> [!Methods]
> Above we used the string _method_ `find`. Methods work quite similarly to the _functions_ covered in the previous part. What distinguishes them from functions is that methods are always attached to the _object_ they are called on. The object is the entity named before the method in the method call. In the case of `find` the object is the string where the method looks for the substring it has as an argument.

