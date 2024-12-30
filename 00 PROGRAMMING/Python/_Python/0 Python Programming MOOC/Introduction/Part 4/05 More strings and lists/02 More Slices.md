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
# More Slices
The ___[]___ syntax works very similarly to the ___range___ function,
which means we can also give it a __step__:
```python
my_string = "exemplary"
print(my_string[0:7:2])

my_list = [1,2,3,4,5,6,7,8]
print(my_list[6:2:-1])
```

If we omit either of the indexes, the operator _defaults to including everything_. 
Among other things, this allows us to write a very short program to __reverse a string__:

```python
my_string = input("Please type in a string: ")
print(my_string[::-1])
```

