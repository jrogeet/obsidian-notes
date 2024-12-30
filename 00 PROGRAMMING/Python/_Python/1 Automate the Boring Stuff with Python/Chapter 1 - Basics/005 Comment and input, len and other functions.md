Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python 
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
#  Comments
The following line is called a _comment_.
```python
# This program says hello and asks for my name.
```

Any text for the rest of the line following the hash mark (#) is part of a comment.
This is used for the readability of your code, you can explain a part of your code with a comment.

And is also used to temporarily remove a code with a `#` so the python wouldn't read it but without deleting the entire text of code.

# print() Function
The `print()` function displays the string value inside its parentheses on the screen.

```python
print('Hello, world!')  
print('What is your name?') # ask for their name
```

> NOTE:
> to Put a ***BLANK LINE*** on the screen; just call `print()` with nothing between the parentheses.


# input() Function
The` input() `function waits for the user to type some text on the keyboard and press ENTER.

```python
myName = input()
```
Whatever the user types will be the value of the Variable `myName`.
Example: if user typed `Carti`, the variable `myName` will have a value of string `Carti` / `myName = 'Carti'`.


## Printing the User's Name
The following call to `print(`) actually contains the expression `'It is good to meet you, '` + `myName` between the parentheses.

```python
myName = input()

print('It is good to meet you, ' + myName)
```

# len() Function

You can pass the `len()` function a string value (or a variable containing a string), and the `function` will tell ***how many characters is in that string***.

```python
myName = input()
print('The length of your name is:')  

print(len(myName))
```

```python
print(len('hello'))

print(len('My very energetic monster just scarfed nachos.'))

print(len(''))
```

# str(), int(), and float() functions

If you want to concatenate an integers such as `29` with a string, you'll need to get the value `'29'` which is the string form of `29`.

The `str()` function will convert or pass the integer to a string value version.

```python
print(str(29))
```

```python
print('I am ' + str(29) + ' years old.')
```

The `str()`, `int()`, and `float()` functions will evaluate to the string, integer, and floating-point forms of the value you pass, respectively.

These functions, will convert the values into string( `str()` ), integer ( `int()` ), floating-point number ( `float()` ).

```python
print(str(0))

print(str(-3.14))

print(int('42'))

print(int('-99'))

print(int(1.25))

print(int(1.99))

print(float('3.14'))

print(float(10))
```

---
#
`int()` function is useful if you want to store numbers instead of strings.
`input()` automatically store the values given to `string`, even the user enters a number
```python
spam = input() #input a number

print(spam)
```

if you input `101` it will store in the `spam` variable but it's not an integer, it's a `String`. 

Use the `int()` function to get the integer form of the value stored in the variable `spam`

```python
spam = input() #input a number
spam = int(spam)

print(spam)
```
> To shorten the first 2 lines of code you can just put it like this:

```python
spam = int(input())
```

Now, you can treat `spam` variable as an integer instead of string.

```python
spam = int(input()) #type a number

print(spam * 2)
```


The `int()` function is also useful if you need to **round a floating-point number down***.

```python
print(int(7.7))
print(int(7.7) + 1)
```

Another example:
```python
print('What is your age?') # ask for their age  
myAge = input()  
print('You will be ' + str(int(myAge) + 1) + ' in a year.')
```

![[Pasted image 20230518141307.png | center]]


![[Pasted image 20230518141338.png]]

