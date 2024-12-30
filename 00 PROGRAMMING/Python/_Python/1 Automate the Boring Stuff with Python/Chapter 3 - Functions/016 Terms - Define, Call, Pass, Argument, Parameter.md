Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #terms
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[015 Functions|Functions]] 

---
# Define, Call, Pass, Argument, Parameter
```python
def sayHello(name):
	print('Hello, ' + name)
sayHello('Al')
```
- **define**-ing a function means to create it, the ***def*** statement defines ***sayHello()*** function.
- **call**, we call the created function like ***sayHello('Al')***, executing the function ***sayHello(name)***, and PASSING the string value ***'Al'*** to the function.
- **argument** - the value being passed **to a function in a function call**, the argument ***'Al'*** is assigned to a local variable named ***name***. 
- **parameters** - **Variables** that have **arguments** assigned to them are _parameters_.
- **expressions** are composed of values and operators. A **function call** can be used in an **expression** because the call evaluates to its return value.