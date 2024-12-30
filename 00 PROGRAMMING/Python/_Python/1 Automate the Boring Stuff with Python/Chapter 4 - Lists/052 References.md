Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python  #references #pythontheory 
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]]

---
# References
As you’ve seen, variables “_store_” strings and integer values.

However, that was just a simplification.

Technically, variables are __storing references__ to the computer memory locations where the values are stored.

```python
spam = 42
cheese = spam

spam = 100

print(spam)
print(cheese)
```

After assigning ___42___ to the ___spam___ variable, you create the ___42___ value in the computer's memory and storing a __reference__ to it in the ___spam___ variable. 

When the value from ___spam___ was copied to the variable  ___cheese___, you are actually copying the __reference__. Both ___spam___ and ___cheese___ variables refer to the ___42___ value in the computer's memory.

After changing the value in ___spam___ to __100__, you're creating a new ___100___ value and storing a reference to it in ___spam___. 

This doesn't affect the value in ___cheese___. 
Integers are __immutable values__ that don't change;

changing the spam variable is actually making it refer to a _completely different value_ in memory.

Lists don't work this way, because list values can change;
that is, lists are __mutable__. 
```python
spam = [0, 1, 2, 3, 4, 5]
cheese = spam # The reference is being copied, not the list.

cheese[1] = 'Hello!' # This changes the list value.
print(spam)

print(cheese) # The cheese variable refers to the same list.
```

The code only touched the ___cheese___ list, but both the ___cheese___ and ___spam___ lists have changed. 

--- 
When you create the list, you assign a reference to it in the ___spam___ variable.

But ___cheese___ only copies the reference of ___spam___ , NOT the list value itself.

This means the values stored in ___spam___ and ___cheese___ now both refer to the same list.

So when you modify the first element of ___cheese___, YOU ARE modifying the SAME LIST that ___spam___ refers to.

---
List variables _don't actually contain lists_
They CONTAIN __references__ to lists.

![[Pasted image 20230722183211.png]]
The __reference__ in ___spam___ is copied to ___cheese___. Only a __new reference__ was created and stored in ___cheese___, _NOT A NEW LIST_. now both references refer to the same list.
![[Pasted image 20230722183227.png]]

When you alter the list that ___cheese___ refers to, the list that ___spam___ refers to is also changed, because both ___cheese___ and ___spam___ refer to the same list.
![[Pasted image 20230722183233.png]]

> Although Python variables technically contain __references__ to values, people often casually say that the variable contains the value.