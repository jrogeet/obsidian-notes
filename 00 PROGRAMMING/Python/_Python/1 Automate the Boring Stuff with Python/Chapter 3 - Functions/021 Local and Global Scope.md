Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python 
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[015 Functions|Functions]] 

---
# Local and Global Scope

_Parameters_ and _Variables_ assigned in a function exist in that function's **Local Scope**.  A variable that exists in a local scope is called a ___local variable___.

_Variables_ that are assigned outside all functions exist in the __Global Scope__. A variable that exists in the global scope is called a ___global variable___.

Scopes matter for several reasons:
- Code in the global scope, outside of all functions, cannot use any local variables.
- However, code in a local scope can access global variables.
- Code in a function's local scope cannot use variables in any other local scope.
- You can use the __same name__ for different variables if they are in the _different scopes_. 
	- That is, there can be a __local variable__ named ___spam___ and a __global variable__ also named ___spam___.

> While using global variables in small programs is fine, it is a bad habit to rely on global variables as your programs get larger and larger.

## Local Variables cannot be used in the Global Scope

```python
def spam():  
	eggs = 31337  
  
spam()  
print(eggs)
```
This program will result to an error because ___eggs___ variable exists only in the __Local Scope__ created when ___spam()___ is called.

## Local Scopes cannot use Variables in Other Local Scopes

```python
def spam():
	eggs = 99
	bacon()
	print(eggs)

def bacon():
	ham = 101
	eggs = 0

spam()
```

- The local variables ___eggs___ is set to ___99___. 
- Then ___bacon()___ function is called, and a second local scope is created. 
- In this new local scope variable ___ham___ is set to ___101___, and local variable ___eggs___(which is different from the one in ___spam()___’s local scope) is also created and set to ___0___.
- When ___bacon()___ returns, the local scope for that call is destroyed, including its ___eggs___ variable. 
- The program execution continues in the ___spam()___ function to print the value of ___eggs___. 
- Since the local scope for the call to ___spam()___ still exists, the only ___eggs___ variable is the ___spam()___ function’s ___eggs___ variable, which was set to ___99___. This is what the program prints.

## Global Variables can be read from a Local Scope

```python
def spam():  
    print(eggs)  
eggs = 42  
spam()  
print(eggs)
```

## Local and Global Variables with the Same Name

It's acceptable to use the same variable name for a global variable and local variables in different scopes in Python. But, to simplify your life, avoid doing this.

```python
def spam():  
	eggs = 'spam local'  
	print(eggs) # prints 'spam local'  
  
def bacon():  
	eggs = 'bacon local'  
	print(eggs) # prints 'bacon local'  
	spam()  
	print(eggs) # prints 'bacon local'  
  
eggs = 'global'  
bacon()  
print(eggs)# prints 'global`
```

## Global Statement
You can modify a global variable from within a function, use the ___global___ statement.

```python
def spam():  
	global eggs  
	eggs = 'spam'  
  
eggs = 'global'  
spam()  
print(eggs)
```
___eggs___ is declared global at the t op of ___spam()___, when ___eggs___ is set to ___'spam'___, this assignment is done to the globally scoped ___eggs___. No local ___eggs___ variable is created. 

Four Rules to tell whether a variable is in a local scope or global scope:
- If a variable is __being used in the global scope__ (that is, outside of all functions), then it is always a _global variable_.
- If there is a ___global___ statement for that variable in a function, it is a _global variable_.
- Otherwise, if the variable is used in an __assignment statement__ in the function, it is a _local variable.
- But if the variable is __not used in an assignment statement__, it is a _global variable_.

```python 
def spam():  
	global eggs  
	eggs = 'spam' # this is the global  
  
def bacon():  
	eggs = 'bacon' # this is a local  
  
def ham():  
	print(eggs) #this is the global  
  
eggs = 42 #this is the global  
spam()  
print(eggs)
```

In the ___spam()___ function, ___eggs___ is the ___global eggs___ variable because there’s a global statement for ___eggs___ at the beginning of the function. 
In ___bacon()___, ___eggs___ is a local variable because there’s an assignment statement for it in that function. 
In ___ham()___, ___eggs___ is the global variable because there is no assignment statement or global statement for it in that function.

>NOTE:
>_If you ever want to modify the value stored in a global variable from in a function, you must use a global statement on that variable._

```python
def spam():
	print(eggs) # ERROR!
	eggs = 'spam local'

eggs = 'global'
spam()
```
This error happens because Python sees that there is an assignment statement for ___eggs___ in the ___spam()___ function ➊ and, therefore, considers ___eggs___ to be local. 
But because ___print(eggs)___ is executed before ___eggs___ is assigned anything, the local variable ___eggs___ doesn’t exist. 
Python will _not_ fall back to using the ___global eggs___ variable ➋.
