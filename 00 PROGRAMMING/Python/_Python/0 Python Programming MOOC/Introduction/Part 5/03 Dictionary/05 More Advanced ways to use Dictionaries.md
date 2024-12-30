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
# 05 More Advanced ways to use Dictionaries

--- 
We would like to analyze this list of words in different ways.
```python
word_list = [
  "banana", "milk", "beer", "cheese", "sourmilk", "juice", "sausage",
  "tomato", "cucumber", "butter", "margarine", "cheese", "sausage",
  "beer", "sourmilk", "sourmilk", "butter", "beer", "chocolate"
]
```
For instance, we would like to know how many times each word appears in the list.

A ___dictionary___ can be a useful tool in managing this kind of information.


### How many times a word appeared in a list:
In the example below, we go through the _items_ in the list one by one. 
Using the words in the _list_ as __keys__ in a new dictionary, 
the value mapped to each __key__ is the number of times the word has appeared:

```python
def counts(my_list):
    words = {}
    for word in my_list:
        # if the word is not yet in the dictionary, initialize the value to zero
        if word not in words:
            words[word] = 0
        # increment the value
        words[word] += 1
    return words

# call the function
print(counts(word_list))
```

### Categorize words based on their initial letter
What if we wanted to categorize the words based on the initial letter in each word? One way to accomplish this would be to use dictionaries:

```python
def categorize_by_initial(my_list):
    groups = {}
    for word in my_list:
        initial = word[0]
        # initialize a new list when the letter is first encountered
        if initial not in groups:
            groups[initial] = []
        # add the word to the appropriate list
        groups[initial].append(word)
    return groups

groups = categorize_by_initial(word_list)

for key, value in groups.items():
    print(f"words beginning with {key}:")
    for word in value:
        print(word)
```

The structure of the function is very similar to the previous exercise but this time the values mapped to the keys are lists.