---
part: "4.2"
topic: lists
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #list  #introduction
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# A list as an argument or a return value

Just like the built-in functions above, our own functions can also take a list as an argument and produce a list as a return value. The following function works out the central value in an ordered list, also called the _median_ value:

```python
def median(my_list: list):
    ordered = sorted(my_list))
    list_centre = len(ordered) // 2
    return ordered[list_centre]
```

The function creates an ordered version of the list given as an argument and returns the item in the very middle. Notice the integer division operator `//` used here. The index of a list should always be an integer.

The function works like this:

```python
shoe_sizes = [45, 44, 36, 39, 40]
print("The median of the shoe sizes is", median(shoe_sizes))

ages = [1, 56, 34, 22, 5, 77, 5]
print("The median of the ages is", median(ages))
```

A function can also return a list. The following function asks the user to type in integers and returns the input as a list:

```python
def input_numbers():
    numbers = []
    while True:
        user_input = input("Please type in an integer, leave empty to exit: ")
        if len(user_input) == 0:
            break
        numbers.append(int(user_input))
    return numbers
```

The function makes use of a helper variable `numbers`, which is a list. All the numbers typed in by the user are added to the list. When the loop is exited from, the function returns the list with the statement `return numbers`.

Calling the function like this

```python
numbers = input_numbers()

print("The greatest number is", max(numbers))
print("The median of the numbers is", median(numbers))
```

This small example demonstrates one of the most important uses of functions: they can help you divide your code into smaller, easily understandable and logical wholes.

Of course the same functionality could be achieved without writing any of our own functions:

```python
numbers = []
while True:
    user_input = input("Please type in an integer, leave empty to exit: ")
    if len(user_input) == 0:
        break
    numbers.append(int(user_input))

ordered = sorted(numbers)
list_centre = len(ordered) // 2
median = ordered[list_centre]

print("The greatest number is", max(numbers))
print("The median of the numbers is", median)
```

In this version, following the programming logic is more difficult, as it is no longer clear which commands are a part of which functionality. The code fulfils the same purposes - reading in input, calculating the median value, and so on - but the structure is less clear.

Organising your code into separate functions will improve you program's readability, but also make it easier to handle logical wholes. This in turn helps you that verify the program works as intended, as each function can be tested separately.

Another important use for functions is making code _reusable_. If you need to achieve some functionality twice is your program, it is a good idea to create your own function and name it appropriately:

```python
print("Shoe sizes:")
shoe_sizes = input_numbers()

print("Weights:")
weights = input_numbers()

print("Heights:")
heights = input_numbers()
```