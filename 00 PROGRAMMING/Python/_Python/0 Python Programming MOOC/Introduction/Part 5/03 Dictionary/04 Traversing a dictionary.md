---
topic: dictionary
part: "5.3"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #dictionary
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 04 Traversing a dictionary

--- 
The familiar ___`for item in collection`___ loop can be used to traverse a dictionary, too.

When used on the ___dictionary___ directly, the loop goes through the __keys__ stored in the dictionary, _one by one_.

In the following example, all keys and values stored in the dictionary are printed out:

```python
my_dictionary = {}

my_dictionary["apina"] = "monkey"
my_dictionary["banaani"] = "banana"
my_dictionary["cembalo"] = "harpsichord"

for key in my_dictionary:
    print("key:", key)
    print("value:", my_dictionary[key])
```

## Method: items

Sometimes you need to traverse the entire contents of a dictionary. The method `items` returns all the keys and values stored in the dictionary, one pair at a time:

```python
for key, value in my_dictionary.items():
    print("key:", key)
    print("value:", value)
```

---

You may have noticed that the __keys__ are processed in the _same order as they were added_ to the dictionary.

As the __keys__ are processed based on a ___hash value___, the order should not usually matter in applications.

In fact, in many older versions of Python the order is not guaranteed to follow the time of insertion.

