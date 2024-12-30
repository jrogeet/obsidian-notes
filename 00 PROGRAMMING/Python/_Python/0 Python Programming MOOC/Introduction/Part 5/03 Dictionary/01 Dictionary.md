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
# 01 Dictionary

--- 
__Lists__ are limited because items are accessed through indexes; 0, 1, 2, etc. 

So to find some item in a list, you have to know its ___Index___, or, at worst, traverse through the entire list.

---

Another central data structure in Python is the ___dictionary___.

> [!DICTIONARY]
> - Items are indexed by __keys__.
> - Each __key__ maps to a ___value___.
> - The ___values___ stored in the dictionary can be accessed and changed using the __key__.


## Using a dictionary

The following example shows you how the dictionary data structure works. Here is a simple dictionary from Finnish to English:

```python
my_dictionary = {}

my_dictionary["apina"] = "monkey"
my_dictionary["banaani"] = "banana"
my_dictionary["cembalo"] = "harpsichord"

print(len(my_dictionary))
print(my_dictionary)
print(my_dictionary["apina"])
```

- The notation ___{ }___ creates an empty dictonary, to which we can now add content.
- Three key-value pairs are added: 
	- __"apina"__ maps to ___"monkey___, 
	- __"banaani"__ maps to ___"banana"___, and 
	- __"cembalo"__ maps to ___"harpsichord"___.
- Finally, the number of key-value pairs in the dictionary is printed,
- Along with the entire dictionary, and
- the value mapped to the key __"apina"__.

After defining the dictionary we could also use it with user input:

```python
word = input("Please type in a word: ")
if word in my_dictionary:
    print("Translation: ", my_dictionary[word])
else:
    print("Word not found")
```

