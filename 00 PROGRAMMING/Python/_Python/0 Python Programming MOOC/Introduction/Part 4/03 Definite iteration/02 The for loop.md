---
part: "4.3"
topic: loops
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc  #introduction
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# The for loop
When you want to go through some ready collection of items, 
the Python ___for loop___ will do this for you. 
For instance, the loop can go through all items in a list from first to last.

When using a ___while loop___ the program doesn't "know" beforehand how many iterations the loop will perform. 
It will repeat until the condition becomes false, or the loop is otherwise broken out of. 

That is why it falls under __indefinite iteration__.

With a ___for loop___ the number of iterations is determined when the loop is set up, and so it falls under __definite iteration__.

The idea is that the ___for loop___ takes the items in the collection one by one and performs the same actions on each. 
The programmer does not have to worry about which item is being handled when. The syntax of the for loop is as follows:
```python
for <variable> in <collection>:
    <block>
```
---
The ___for loop___ takes an item in the collection, assigns it to the variable, processes the block of code, and moves on to the next item. 
When all items in the collection have been processed, execution of the program continues from the line after the loop.
![[Pasted image 20230813142045.png]]
The following program prints out all the items in a list using a `for` loop:

```python
my_list = [3, 2, 4, 5, 2]

for item in my_list:
    print(item)
```

Compared to the example at the beginning of this section, the structure is much easier to understand. 
A ___for loop___ makes straightforward traversal through a collection of items very simple.

The same principle applies to characters in a string:

```python
name = input("Please type in your name: ")

for character in name:
    print(character)
```

