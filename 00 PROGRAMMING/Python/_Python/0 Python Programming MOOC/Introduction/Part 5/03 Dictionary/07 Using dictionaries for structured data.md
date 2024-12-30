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
# 07 Using dictionaries for structured data

--- 
___Dictionaries___ are very useful for __structuring data__. 
The following code will create a _dictionary_ which contains some personal data:
```python
person = {"name": "Pippa Python", "height": 154, "weight": 61, "age:" 44}
```

- This means that we have here a person _named_ __Pippa Python__, whose _height_ is __154__, _weight_ __61__, and _age_ __44__. 

The same information could just as well be stored in variables:
```python
name = "Pippa Python"
height = 154
weight = 61
age = 44
```

---
> The advantage of dictionary is that it is a collection.

- It collects related data under __one variable__, so it is easy to access the different components.

This same advantage is offered by a ___list___:
```python
person = ["Pippa Python", 153, 61, 44]
```
>but the problem with lists is that you will _have to remember what is stored at each index in the list._
- There is no indicator that ___person[2]___ contains the __weight__ and ___person[3]___ contains the age of the person.

BUT this problem is avoided when using a ___DICTIONARY___ because every data is accessed through a named __key__.

---
Assuming we have defined multiple people using the same format, we can access their data in the following manner:
```python
person1 = {"name": "Pippa Python", "height": 154, "weight": 61, "age": 44}
person2 = {"name": "Peter Pythons", "height": 174, "weight": 103, "age": 31}
person3 = {"name": "Pedro Python", "height": 191, "weight": 71, "age": 14}

people = [person1, person2, person3]

for person in people:
    print(person["name"])

combined_height = 0
for person in people:
    combined_height += person["height"]

print("The average height is", combined_height / len(people))
```


