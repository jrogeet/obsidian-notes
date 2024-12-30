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
# 04 Substrings and slices

---
## Substrings and Slicing in Python Strings

A substring of a string is a sequence of characters that forms a part of the string. This process of selecting substrings is often referred to as slicing.

To extract a substring using slicing, you can use the notation `[a:b]`, where the slice begins at index `a` and ends at the character just before index `b` (including the first character but excluding the last).

For example:
```python
text = "example"
substring = text[1:4]  # Returns "xam"
```

You can visualize the slicing as separator lines drawn on the left side of the indexed characters. The character at index `a` is included in the slice, while the character at index `b` is not.

As illustrated in the image below:
![[Pasted image 20230828184951.png]]
Let's have a closer look at some sliced strings:

```python
input_string = "presumptious"

print(input_string[0:3])
print(input_string[4:10])

# if the beginning index is left out, it defaults to 0
print(input_string[:3])

# if the end index is left out, it defaults to the length of the string
print(input_string[4:])
```

> [!Half open intervals]
> In Python string processing the interval `[a:b]` is _half open_, which in this case means that the character at the beginning index `a` is included in the interval, but the character at the end index `b` is left out. Why is that?
> 
   There is no profound reason for this feature. Rather it is a convention inherited from other programming languages.
  Half open intervals may feel unintuitive, but in practice they do have some advantages. For example, you can easily calculate the length of a slice with `b-a`. On the other hand, you must always remember that the character at the end index `b` will not be included in the slice.
