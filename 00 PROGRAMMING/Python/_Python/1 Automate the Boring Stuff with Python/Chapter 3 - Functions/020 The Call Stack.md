Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #pythontheory #functions
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[015 Functions|Functions]] 

---
# Call Stack
The ***call stack*** is how Python remembers where to return the execution after each function call.
![[Pasted image 20230618205009.png]]
__Calling a function doesn’t send the execution__ on a one-way trip to the top of a function.

Python will remember which line of code called the function so that the execution can return there when it encounters a ___return___ statement.

If that original function called other functions, the execution would return to _those_ function calls first, before returning from the original function call.

```python
def a():  
	print('a() starts')  
	b()  
	d()  
	print('a() returns')  
  
def b():  
	print('b() starts')  
	c()  
	print('b() returns')  
  
def c():  
	print('c() starts')  
	print('c() returns')  
  
def d():  
	print('d() starts')  
	print('d() returns')  
  
a()
```
![[Pasted image 20230618205940.png]]
The top of the call stack is which function the execution is __currently in__. When the call stack is _empty_, the execution is on a line _outside of all functions_.