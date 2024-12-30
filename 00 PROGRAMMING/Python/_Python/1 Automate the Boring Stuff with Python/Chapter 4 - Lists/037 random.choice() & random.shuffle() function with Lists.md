Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list #random
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]]  [[023 List Data Type|List]] 

---
# Using the random.choice() and random.shuffle() Functions with Lists

___random___ module has some functions that accept lists for arguments. 

## random.choice()

The ___random.choice()___ function will return a randomly selected item from the list.

```python
import random
pets = ['Dog', 'Cat', 'Moose']
print(random.choice(pets))

print(random.choice(pets))

print(random.choice(pets))
```
___random.choice(someList)___ is a shorter form of __someList[random.randint(0, len(someList) -1]__.

## random.shuffle()

The ___random.shuffle()___ function will __reorder__ the items in a list.

This function __modifies__ the list in place, rather than __returning a new list__.

```python
import random
people = ['Alice', 'Bob', 'Carol', 'David']
random.shuffle(people)
print(people)

random.shuffle(people)
print(people)
```