Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #variables 
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
#  Storing Values in Variables
A _variable_ is like a box in the computer’s memory where you can store a single value. If you want to use the result of an evaluated expression later in your program, you can save it inside a variable.

## Assignment Variables
Store values in Variables with an Assignment Statement.

It consists of a Variable name(example: `spam`), an equal sign(`=` or the *assignment operator*), and the value to be stored.
```python
spam = 42
```
`spam` is a Variable and it has stored integer value `42`
![[Pasted image 20230518123306.png| center]]

Examples:
```python
#1
miyamoto = 42
print(miyamoto)

#2
musashi = 420
print(musashi + miyamoto)
print(musashi + miyamoto + musashi)

#3
thorfinn = musashi + 2
print(thorfinn)
```
in `#1` we assigned a value to the variable `miyamoto` which is `42` and then printed it.

And in `#2` we assigned a value to the variable `musashi` which is `420` and added the values of `miyamoto` + `musashi` which would result to `462`.

Last, in `#3` we declared a variable named `thorfinn` and it's value is the value of the variable `musashi` + `2` which would result to `422`.

---
We can also store `Strings` in a *Variable*.
```python
spam = 'Hello'
print(spam)

spam = 'Goodbye'
print(spam)
```
![[Pasted image 20230518124254.png | center]]


## Variable Names
You can name your Variables almost anything, but Python still have some naming restrictions.
-   It can be only one word with no spaces.
-   It can use only letters, numbers, and the underscore (_) character.
-   It can’t begin with a number.
![[Pasted image 20230518124454.png| center]]

Variable names are `CASE-SENSITIVE`, meaning that spam, SPAM, Spam, and sPaM are four different variables.