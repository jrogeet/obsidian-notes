Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python 
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[015 Functions|Functions]] 

---
# Exception Handling
Error or ___exception___, in your Python program means the entire program will crash.

```python
def spam(divideBy):  
    return 42 / divideBy  
  
print(spam(2))  
print(spam(12))  
print(spam(0))  
print(spam(1))
```

A ___ZeroDivisionError___ happens whenever you try to divide a number by ___zero___.

Errors can be handled with ___try___ and ___except___ statements.
The code that could potentially have an error is put in a try clause. The program execution moves to the start of a following ___except___ clause if an error happens.

```python
def spam(divideBy):  
    try:  
        return 42 / divideBy  
    except ZeroDivisionError:  
        print('Error: Invalid argument.')  
  
print(spam(2))  
print(spam(12))  
print(spam(0))  
print(spam(1))
```

When code in a ___try___ clause causes an __error__, the program execution immediately moves to the code in the ___except___ clause. 
After running that code, the execution continues as normal.

```python
def spam(divideBy):  
    return 42 / divideBy  
  
try:  
    print(spam(2))  
    print(spam(12))  
    print(spam(0))  
    print(spam(1))  
except ZeroDivisionError:  
    print('Error: Invalid argument.')
```