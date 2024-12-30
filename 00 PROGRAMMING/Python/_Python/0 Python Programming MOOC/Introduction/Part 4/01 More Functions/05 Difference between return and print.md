---
topic: functions
part: "4.1"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #functions
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 05 Difference between return and print

--- 
Sometimes the difference between a function _returning_ a value and a _print statement_ within a function can be confusing. Let's have a look at two different ways of implementing a function for working out which of two values is greater:

```python
def max1(a, b):
    if a > b:
        return a
    else:
        return b

def max2(a, b):
    if a > b:
        print(a)
    else:
        print(b)

result = max1(3, 5)
print(result)

max2(7, 2)
```

Sample output

```
5 
7
```

Both versions seem to be working just fine, as the maximum values are printed correctly. There is a fundamental difference between the two, however. The first of the two functions, `max1`, does not print out anything on its own, but instead it _returns_ the value which is greater. If we execute the following line

```python
max1(3, 5)
```

nothing seems to happen. The return value of the function has to be _used_ in some way in the code which called the function. For instance, it can be store in a variable and printed out:

```python
result = max1(3, 5)
print(result)
```

The second version, `max2`, uses the `print` command _within the function_ to print out the greater value. If we want to see the value, it is enough to call the function

```python
max2(7, 5)
```

and the greater value is printed out. The downside of this handy function is that the value worked out by the function is not available for use in the program which called it. That is why functions which return values are often the better option.