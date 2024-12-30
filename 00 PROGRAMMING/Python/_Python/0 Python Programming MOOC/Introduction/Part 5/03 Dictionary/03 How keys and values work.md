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
# 03 How keys and values work

--- 
_Each key can appear only once in the dictionary._
If you add an entry using a key that _already exists_ in the dictionary,
the original value mapped to that key is __replaced__ with the __new value__:

```python
my_dictionary["suuri"] = "big"
my_dictionary["suuri"] = "large"
print(my_dictionary["suuri"])
```

> All keys in a dictionary must be _immutable_
> So, a __list__ cannot be used as a ___key___, because it can be changed.


For example, executing the following code causes an error:
```python
my_dictionary[[1, 2, 3]] = 5
```
```
TypeError: unhashable type: 'list'
```

> [!Hash Table]
> Notice the word __'unhashable'__ in the error message above.
> This is a reference to the inner workings of the dictionary data type.
> Python stores the contents of a _dictionary_ in a ___hash table___.
> Each __key__ is reduced to a ___hash value___, which determines where the __key__ is stored in computer memory.
> The error message above indicates that a __list__ cannot be processed into a ___hash value___, so it cannot be used as a __key__ in a _dictionary_. <br>
> The ___Data Structures and Algorithms___ courses will further explore hash tables.

Unlike __keys__, the _values_ stored in a ___dictionary___ can change, so any type of data is acceptable as a _value_.

A _value_ can also be mapped to more than one __key__ in the same ___dictionary___.

