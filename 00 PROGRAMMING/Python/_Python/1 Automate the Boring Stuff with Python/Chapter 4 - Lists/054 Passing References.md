Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #references #pythontheory 
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Passing References

When a function is called, the values of the arguments are copied to the parameter variables. 

For _lists_ and _dictionaries_, this means __a copy of the reference__ is used for the ___parameter___.

```python
def eggs(someParameter):
	someParameter.append('Hello')

spam = [1, 2, 3]
eggs(spam)
print(spam)
```
a return value is not used to assign a new value to ___spam___. 
Instead, it modifies the list in place, __directly__.


--- 
Even though ___spam___ and ___someParameter___ contain separate references,
they both refer to the same list.

That's why the ___append('Hello')___ method call inside the function affects the list __even after the function call has returned__.

> Keep this behavior in mind: Forgetting that Python __handles list and dictionary variables this way__ can lead to confusing bugs.

