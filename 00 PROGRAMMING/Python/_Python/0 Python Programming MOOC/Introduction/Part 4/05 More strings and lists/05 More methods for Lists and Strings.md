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
# More methods for lists and strings

The method ___count___ counts the number of times the specified item or substring occurs in the target.

The method works similarly with both strings and lists:

```python
my_string = "How much wood would a woodchuck chuck if a woodchuck could chuck wood"
print(my_string.count("ch"))

my_list = [1,2,3,1,4,5,1,6]
print(my_list.count(1))
```

The method will not count overlapping occurences. 
For example, in the string ___aaaa___ the method counts only two occurrences of the substring ___aa___, even though there would actually be three if overlapping occurrences were allowed.

---
The method ___replace___ creates a new string, where a specified substring as replaced with another string:
```python
my_string = "Hi there"
new_string = my_string.replace("Hi", "Hey")
print(new_string)
```

The method will replace all occurrences of the substring:
```python
sentence = "sheila sells seashells on the seashore"
print(sentence.replace("she", "SHE"))
```

When using the ___replace___ method, a typical mistake is forgetting that ___strings___ are __immutable__:
```python
my_string = "Python is fun"

# Replaces the substring but doesn't store the result...
my_string.replace("Python", "Java")
print(my_string)
```

If the old string is no longer needed, the new string can be assigned to the same variable:
```python
my_string = "Python is fun"

# Replaces the substring and stores the result in the same variable
my_string = my_string.replace("Python", "Java")
print(my_string)
```

### isupper()

The Python string method ___isupper()___ returns ___True___ if a string consists of only __uppercase characters__.

```python
print("XYZ".isupper())

is_it_upper = "Abc".isupper()
print(is_it_upper)
```