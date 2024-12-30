---
topic: lists
part: "5.1"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #lists
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 02 Lists within lists

--- 
The __items__ in a list can be ___lists themselves___:

```python
my_list = [[5, 2, 3], [4, 1], [2, 2, 5, 1]]
print(my_list)
print(my_list[1])
print(my_list[1][0])
```

This concept is known as a list of lists, or nested lists. Here's an example:

- Nested lists store complex data structures.
- Access elements using multiple indices.

### Usefulness of Nested Lists:
- Lists can contain items of different types, including other lists.
```python
["Anne", 12, 1.45]
```

- Nested lists are useful for creating structured data.
- Examples: Storing information about people with multiple attributes.

```python
persons = [["Betty", 10, 1.37], ["Peter", 7, 1.25], ["Emily", 32, 1.64], ["Alan", 39, 1.78]]

for person in persons:
  name = person[0]
  age = person[1]
  height = person[2]
  print(f"{name}: age {age} years, height {height} meters")
```

- The outer list holds lists with person data.
- Looping through nested lists using a `for` loop.
- Useful for structured data but not always optimal.