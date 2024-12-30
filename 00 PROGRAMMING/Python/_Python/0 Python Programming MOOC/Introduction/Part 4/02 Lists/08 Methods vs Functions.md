---
topic: lists
part: "4.2"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #list  #introduction
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Methods vs Functions
There are two different ways of processing lists in Python, which can get confusing. 
For the most part you will use list __methods__, such as ___append___ and ___sort___. 
They are used with the _dot_ _._ operator on the list variable:

```python
my_list = []

# method calls
my_list.append(3)
my_list.append(1)
my_list.append(7)
my_list.append(2)

# another method call
my_list.sort()
```

Some __functions__ are happy to take a list as an `argument`. Above we saw the functions ___max___, ___min___, ___len___ and ___sorted___ do just that:

```python
my_list = [3, 2, 7, 1]

# function calls take the list as an argument
greatest = max(my_list))
smallest = min(my_list))
length = len(my_list))

print("Smallest:", smallest)
print("Greatest:", greatest)
print("Length of the list:", length)

# another function call 
# the list itself is an argument, the function returns a sorted copy
in_order = sorted(my_list))
print(in_order)
```

