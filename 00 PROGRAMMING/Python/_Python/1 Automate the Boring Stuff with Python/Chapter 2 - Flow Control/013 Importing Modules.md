Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #modules
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
## Importing Modules
Python has built-in functions such as **print()**, **input()**, and **len()** that you can use in your programs. 

Additionally, Python provides a standard library consisting of modules, which are collections of related functions.

These modules cover various areas, like mathematics (math module) and random number generation (random module).

You must import the module with an ***import statement***, Before you can use the functions in a module.
- ***import*** keyword
- Name of the module
- Optional (more module names, as long as they are separated by commas.)

Let's try the ***random*** module, which will give us access to the **random.randint()** funciton.
```python
import random  
for i in range(5):  
    print(random.randint(1, 10))
```

### DON'T OVERWRITE MODULE NAMES
>DO NOT give your python files names that is used by one of Python's modules,

such as **random.py**, **sys.py**, **os.py**, or **math.py**.

If you accidentally name one of your programs (Ex: **random.py**)
and you use ***import random*** in one of your other programs, 
the **random.py** file will get imported instead of the Python's ***random*** module

#### Here is an example of import statement that imports four different modules:
```python
import random, sys, os, math
```


## from import Statements
An alternative form of the ***import*** statement is composed of the **from** keyword, followed by the **module name**, the **import** keyword, and a **star**(\*)* ; for example, **from random import \***.

With this form of import statement, calls to functions in random will not need the random. prefix. However, using the full name makes for more readable code, so it is better to use the import random form of the statement.