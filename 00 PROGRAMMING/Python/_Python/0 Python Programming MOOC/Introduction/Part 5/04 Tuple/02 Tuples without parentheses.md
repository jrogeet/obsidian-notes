---
topic: ""
part: ""
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #tuple
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 02 Tuples without parentheses

--- 
__Parentheses__ aren't strictly necessary when defining ___Tuples___.
The following are the same:
```python
numbers = (1, 2, 3)
```

```python
numbers = 1, 2, 3
```

This means we can ___return multiple values___ using __tuples__.
Example:
```python
def minmax(my_list):
   return min(my_list), max(my_list)

my_list = [33, 5, 21, 7, 88, 312, 5]

min_value, max_value = minmax(my_list)
print(f"The smallest item is {min_value} and the greatest item is {max_value}")
```

The return value is assigned to two variables at once:
```python
min_value, max_values = minmax(my_list)
```

Although it is more clear when using parentheses
```python
(min_value, max_value) = minmax(my_list)
```

## items Method

The dictionary method ___items___ is used to access all keys and values stored in a dictionary:
```python
my_dictionary = {}

my_dictionary["apina"] = "monkey"
my_dictionary["banaani"] = "banana"
my_dictionary["cembalo"] = "harpsichord"

for key, value in my_dictionary.items():
    print("key:", key)
    print("value:", value)
```

___Tuples___ are used here too
The method ___my_dictionary.items()___ returns each key-value pair as a tuple.
where the first item is the key and the second item is the value.


## Common use
Another common use for tuples is swapping the values of two variables:
```python
number1, number2 = number2, number1
```

This assignment statement swaps the values stored in the variable __number1__ and __number2__.
The result is identical to what is achieved with the following bit of code, using a helper variable:

```python
helper_var = number1
number1 = number2
number2 = helper_var
```

