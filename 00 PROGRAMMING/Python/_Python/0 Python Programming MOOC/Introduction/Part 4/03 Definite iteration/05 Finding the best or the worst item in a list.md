---
part: "4.3"
topic: lists
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc  #introduction
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Finding the best or the worst item in a list
A very common programming task is finding the best or worst item in a list, according to some criteria. A simple solution is using a helper variable to "remember" which of the items processed so far was the most suitable. This temporary best choice is then compared to each item in turn, and at the end of the iteration the variable contains the best of the bunch.

```python
best = initial_value # The initial value depends on the situation
for item in my_list:
    if item is better than best:
        best = item

# We now have the best one figured out!
```
