
from the website or book - [Automate the Boring Stuff with Python](https://automatetheboringstuff.com/)


# Chapter 1: Python Basics
## Questions:
[1](https://automatetheboringstuff.com/2e/chapter1/#calibre_link-1657). Which of the following are operators, and which are values?

*  
'hello'  
-88.8  
-  
/  
+  
5

[2](https://automatetheboringstuff.com/2e/chapter1/#calibre_link-1658). Which of the following is a variable, and which is a string?

spam  
'spam'

[3](https://automatetheboringstuff.com/2e/chapter1/#calibre_link-1659). Name three data types.

[4](https://automatetheboringstuff.com/2e/chapter1/#calibre_link-1660). What is an expression made up of? What do all expressions do?

[5](https://automatetheboringstuff.com/2e/chapter1/#calibre_link-1661). This chapter introduced assignment statements, like spam = 10. What is the difference between an expression and a statement?

[6](https://automatetheboringstuff.com/2e/chapter1/#calibre_link-1662). What does the variable bacon contain after the following code runs?

bacon = 20  
bacon + 1

[7](https://automatetheboringstuff.com/2e/chapter1/#calibre_link-1663). What should the following two expressions evaluate to?

'spam' + 'spamspam'  
'spam' * 3

[8](https://automatetheboringstuff.com/2e/chapter1/#calibre_link-1664). Why is eggs a valid variable name while 100 is invalid?

[9](https://automatetheboringstuff.com/2e/chapter1/#calibre_link-1665). What three functions can be used to get the integer, floating-point number, or string version of a value?

[10](https://automatetheboringstuff.com/2e/chapter1/#calibre_link-1666). Why does this expression cause an error? How can you fix it?

'I have eaten ' + 99 + ' burritos.'
## My Answers
1. `(* - / +)` is Operators and `('hello' -88.8 and 5)` is Values
2. `spam` is a variable and `'spam'` is a string
3. `integer, float, string`
4. Expression is anything you write in the code
5. Expressions is facts and Statement is code declared by the user like you're stating that spam is equal to 10 `spam = 10` 
6. bacon contains the value `21`
7. `spamspamspam`
8. Because variables can't start with a number.
9. `int(), float(), str()`
10. put `99` inside  `str()` 

## RIGHT Answers
[1](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1250). The operators are +, -, *, and /. The values are 'hello', -88.8, and 5.

[2](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1251). The variable is spam; the string is 'spam'. Strings always start and end with quotes.

[3](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1252). The three data types introduced in this chapter are integers, floating-point numbers, and strings.

[4](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1253). An expression is a combination of values and operators. All expressions evaluate (that is, reduce) to a single value.

[5](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1254). An expression evaluates to a single value. A statement does not.

[6](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1255). The bacon variable is set to 20. The bacon + 1 expression does not reassign the value in bacon (that would need an assignment statement: bacon = bacon + 1).

[7](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1256). Both expressions evaluate to the string 'spamspamspam'.

[8](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1257). Variable names cannot begin with a number.

[9](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1258). The int(), float(), and str() functions will evaluate to the integer, floating-point number, and string versions of the value passed to them.

[10](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1259). The expression causes an error because 99 is an integer, and only strings can be concatenated to other strings with the + operator. The correct way is I have eaten ' + str(99) + ' burritos.'.








# Chapter 2: Flow Control
## Questions
[1](https://automatetheboringstuff.com/2e/chapter2/#calibre_link-1550). What are the two values of the Boolean data type? How do you write them?

[2](https://automatetheboringstuff.com/2e/chapter2/#calibre_link-1551). What are the three Boolean operators?

[3](https://automatetheboringstuff.com/2e/chapter2/#calibre_link-1552). Write out the truth tables of each Boolean operator (that is, every possible combination of Boolean values for the operator and what they evaluate to).

[4](https://automatetheboringstuff.com/2e/chapter2/#calibre_link-1553). What do the following expressions evaluate to?

(5 > 4) and (3 == 5)  
not (5 > 4)  
(5 > 4) or (3 == 5)  
not ((5 > 4) or (3 == 5))  
(True and True) and (True == False)  
(not False) or (not True)

[5](https://automatetheboringstuff.com/2e/chapter2/#calibre_link-1554). What are the six comparison operators?

[6](https://automatetheboringstuff.com/2e/chapter2/#calibre_link-1555). What is the difference between the equal to operator and the assignment operator?

[7](https://automatetheboringstuff.com/2e/chapter2/#calibre_link-1556). Explain what a condition is and where you would use one.

[8](https://automatetheboringstuff.com/2e/chapter2/#calibre_link-1557). Identify the three blocks in this code:

spam = 0  
if spam == 10:  
    print('eggs')  
    if spam > 5:  
        print('bacon')  
    else:  
        print('ham')  
    print('spam')  
print('spam')

[9](https://automatetheboringstuff.com/2e/chapter2/#calibre_link-1558). Write code that prints Hello if 1 is stored in spam, prints Howdy if 2 is stored in spam, and prints Greetings! if anything else is stored in spam.

[10](https://automatetheboringstuff.com/2e/chapter2/#calibre_link-1559). What keys can you press if your program is stuck in an infinite loop?

[11](https://automatetheboringstuff.com/2e/chapter2/#calibre_link-1560). What is the difference between break and continue?

[12](https://automatetheboringstuff.com/2e/chapter2/#calibre_link-1561). What is the difference between range(10), range(0, 10), and range(0, 10, 1) in a for loop?

[13](https://automatetheboringstuff.com/2e/chapter2/#calibre_link-1562). Write a short program that prints the numbers 1 to 10 using a for loop. Then write an equivalent program that prints the numbers 1 to 10 using a while loop.

[14](https://automatetheboringstuff.com/2e/chapter2/#calibre_link-1563). If you had a function named bacon() inside a module named spam, how would you call it after importing spam?
## My Answers
1. **True** and **False**
2. **or**, **and** , **not**
3. T or/and T, T or/and F, F or/and T, F or/and F. not T, not F
4. False, False, True, True, False, True
5. == , < , > , !=, __ , __
6. equal to operator compares two variables whether they have the same amount or if they are the same, while assignment operators, assign or store data into a variable.
7. conditions are used when there is many possible outcomes
8. spam
9.

```python
if spam == 1:
	print('Hello')
elif spam == 2:
	print('Howdy')
else:
	print('spam')
```
10 . F5
11 . break will stop or exit the current loop, and continue will continue the loop or through the next line or code 
12 . the difference is range(10)

and range(0, 10) is like a counter the 0 is the beginning but its not included in the count and the 10 is the last number. so its only gonna print 1 to 10

and range(0, 10, 1) is just like the previous one but the 1 at the end is how many steps or skips is it counting(For example: if it's 2 then it will count 2, 4, 6 etc.)

13 . 
```python
#FOR LOOP
for i in range(0, 10):  
	i = i + 1  
	print(i)
#WHILE LOOP
i = 0  
  
while True:  
	if i < 10:  
		i = i + 1  
		print(i)
```
14 . 
```python
bacon()
```

## Right Answers:
[1](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1260). True and False, using capital _T_ and _F_, with the rest of the word in lowercase

[2](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1261). and, or, and not

[3](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1262). True and True is True.

True and False is False.

False and True is False.

False and False is False.

True or True is True.

True or False is True.

False or True is True.

False or False is False.

not True is False.

not False is True.

[4](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1263). False

False

True

False

False

True

[5](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1264). ==, !=, <, >, <=, and >=

[6](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1265). == is the equal to operator that compares two values and evaluates to a Boolean, while = is the assignment operator that stores a value in a variable.

[7](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1266). A condition is an expression used in a flow control statement that evaluates to a Boolean value.

[8](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1267). The three blocks are everything inside the if statement and the lines print('bacon') and print('ham').

```python
print('eggs')  
if spam > 5:  
    print('bacon')  
else:  
    print('ham')  
print('spam')
```

[9](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1268). The code:

```python
if spam == 1:  
    print('Hello')  
elif spam == 2:  
    print('Howdy')  
else:  
    print('Greetings!')
```
[10](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1269). Press CTRL-C to stop a program stuck in an infinite loop.

[11](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1270). The break statement will move the execution outside and just after a loop. The continue statement will move the execution to the start of the loop.

[12](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1271). They all do the same thing. The range(10) call ranges from 0 up to (but not including) 10, range(0, 10) explicitly tells the loop to start at 0, and range(0, 10, 1) explicitly tells the loop to increase the variable by 1 on each iteration.

[13](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1272). The code:

```python
for i in range(1, 11):  
    print(i)

# AND: 

i = 1  
while i <= 10:  
    print(i)  
    i = i + 1
```

[14](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1273). This function can be called with ***spam.bacon()***.

# Chapter 3: Functions
## Questions:
[1](https://automatetheboringstuff.com/2e/chapter3/#calibre_link-1215). Why are functions advantageous to have in your programs?

[2](https://automatetheboringstuff.com/2e/chapter3/#calibre_link-1216). When does the code in a function execute: when the function is defined or when the function is called?

[3](https://automatetheboringstuff.com/2e/chapter3/#calibre_link-1217). What statement creates a function?

[4](https://automatetheboringstuff.com/2e/chapter3/#calibre_link-1218). What is the difference between a function and a function call?

[5](https://automatetheboringstuff.com/2e/chapter3/#calibre_link-1219). How many global scopes are there in a Python program? How many local scopes?

[6](https://automatetheboringstuff.com/2e/chapter3/#calibre_link-1220). What happens to variables in a local scope when the function call returns?

[7](https://automatetheboringstuff.com/2e/chapter3/#calibre_link-1221). What is a return value? Can a return value be part of an expression?

[8](https://automatetheboringstuff.com/2e/chapter3/#calibre_link-1222). If a function does not have a return statement, what is the return value of a call to that function?

[9](https://automatetheboringstuff.com/2e/chapter3/#calibre_link-1223). How can you force a variable in a function to refer to the global variable?

[10](https://automatetheboringstuff.com/2e/chapter3/#calibre_link-1224). What is the data type of None?

[11](https://automatetheboringstuff.com/2e/chapter3/#calibre_link-1225). What does the import areallyourpetsnamederic statement do?

[12](https://automatetheboringstuff.com/2e/chapter3/#calibre_link-1226). If you had a function named bacon() in a module named spam, how would you call it after importing spam?

[13](https://automatetheboringstuff.com/2e/chapter3/#calibre_link-1227). How can you prevent a program from crashing when it gets an error?

[14](https://automatetheboringstuff.com/2e/chapter3/#calibre_link-1228). What goes in the try clause? What goes in the except clause?
## My Answers:
1.  _Why are functions advantageous to have in your programs?_ 
	Functions makes programs more organized
2. _When does the code in a function execute: when the function is defined or when the function is called?_
	When the function is called
3. _What statement creates a function?_
	def or define function
4. _What is the difference between a function and a function call?_
	Function is the whole block of code that we can execute using the function call
5. _How many global scopes are there in a Python program? How many local scopes?_
	There's only 1 global scope and local scope depends on how many functions you create.
6. _What happens to variables in a local scope when the function call returns?_
	The variables are destroyed
7.  _What is a return value? Can a return value be part of an expression?_
	Yes, a return value is the value that is being returned into the function. 
8. _If a function does not have a return statement, what is the return value of a call to that function?_
	None
9. _How can you force a variable in a function to refer to the global variable?_
	by using the global statement
10. _What is the data type of None?_
	Boolean __CORRECT ANSWER: NoneType__
11. _What does the import areallyourpetsnamederic statement do?_
	importing the function areallyourpetsnamederic 
12. _If you had a function named bacon() in a module named spam, how would you call it after importing spam?_
	import bacon __CORRECT ANSWER: spam.bacon()__ 
13. _How can you prevent a program from crashing when it gets an error?_
	use try and except 
14. _What goes in the try clause? What goes in the except clause?_
	you test or put the code that could output an error in the try clause, then put the expected error in the except clause. 
	__CORRECT ANSWER: The code that could potentially cause an error goes in the try clause. The code that executes if an error happens goes in the except clause.__

## Correct Answers:
[1](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1274). Functions reduce the need for duplicate code. This makes programs shorter, easier to read, and easier to update.

[2](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1275). The code in a function executes when the function is called, not when the function is defined.

[3](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1276). The def statement defines (that is, creates) a function.

[4](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1277). A function consists of the def statement and the code in its def clause. A function call is what moves the program execution into the function, and the function call evaluates to the function’s return value.

[5](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1278). There is one global scope, and a local scope is created whenever a function is called.

[6](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1279). When a function returns, the local scope is destroyed, and all the variables in it are forgotten.

[7](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1280). A return value is the value that a function call evaluates to. Like any value, a return value can be used as part of an expression.

[8](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1281). If there is no return statement for a function, its return value is None.

[9](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1282). A global statement will force a variable in a function to refer to the global variable.

[10](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1283). The data type of None is NoneType.

[11](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1284). That import statement imports a module named areallyourpetsnamederic. (This isn’t a real Python module, by the way.)

[12](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1285). This function could be called with spam.bacon().

[13](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1286). Place the line of code that might cause an error in a try clause.

[14](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1287). The code that could potentially cause an error goes in the try clause. The code that executes if an error happens goes in the except clause.


# Chapter 4: Lists
## Questions:
[1](https://automatetheboringstuff.com/2e/chapter4/#calibre_link-722). What is []?

[2](https://automatetheboringstuff.com/2e/chapter4/#calibre_link-723). How would you assign the value 'hello' as the third value in a list stored in a variable named spam? (Assume spam contains [2, 4, 6, 8, 10].)

For the following three questions, let’s say spam contains the list ['a', 'b', 'c', 'd'].

[3](https://automatetheboringstuff.com/2e/chapter4/#calibre_link-724). What does spam[int(int('3' * 2) // 11)] evaluate to?

[4](https://automatetheboringstuff.com/2e/chapter4/#calibre_link-725). What does spam[-1] evaluate to?

[5](https://automatetheboringstuff.com/2e/chapter4/#calibre_link-726). What does spam[:2] evaluate to?

For the following three questions, let’s say bacon contains the list [3.14, 'cat', 11, 'cat', True].

[6](https://automatetheboringstuff.com/2e/chapter4/#calibre_link-727). What does bacon.index('cat') evaluate to?

[7](https://automatetheboringstuff.com/2e/chapter4/#calibre_link-728). What does bacon.append(99) make the list value in bacon look like?

[8](https://automatetheboringstuff.com/2e/chapter4/#calibre_link-729). What does bacon.remove('cat') make the list value in bacon look like?

[9](https://automatetheboringstuff.com/2e/chapter4/#calibre_link-730). What are the operators for list concatenation and list replication?

[10](https://automatetheboringstuff.com/2e/chapter4/#calibre_link-731). What is the difference between the append() and insert() list methods?

[11](https://automatetheboringstuff.com/2e/chapter4/#calibre_link-732). What are two ways to remove values from a list?

[12](https://automatetheboringstuff.com/2e/chapter4/#calibre_link-733). Name a few ways that list values are similar to string values.

[13](https://automatetheboringstuff.com/2e/chapter4/#calibre_link-734). What is the difference between lists and tuples?

[14](https://automatetheboringstuff.com/2e/chapter4/#calibre_link-735). How do you type the tuple value that has just the integer value 42 in it?

[15](https://automatetheboringstuff.com/2e/chapter4/#calibre_link-736). How can you get the tuple form of a list value? How can you get the list form of a tuple value?

[16](https://automatetheboringstuff.com/2e/chapter4/#calibre_link-737). Variables that “contain” list values don’t actually contain lists directly. What do they contain instead?

[17](https://automatetheboringstuff.com/2e/chapter4/#calibre_link-738). What is the difference between copy.copy() and copy.deepcopy()?
## My Answers:
1. Brackets, used for lists, inside the brackets is the list values
2. ___spam[2] = 'Hello'
3. ___spam[int(int('3' * 2) // 11)]___ will evaluate to ___'d'___
4. ___'d'___
5. ___'c'___ `WRONG`
6. bacon.index('cat') will evaluate to ___1___
7. ___[3.14, 'cat', 11, 'cat', True, 99]___
8. ___[3.14, 11, 'cat', True].___
9. __+__ is the operator for list concatenation and * for replication
10.  appending would add the value to the last index, but in insert you can put it specifically what index you want it.
11. __remove()__ and __del()___
12. Lists and Strings both contain values `NOT ENOUGH / WRONG`
13. Lists can be modified while tuples are like strings which cannot be modified
14. tuple = `WRONG`
15. ___tuple = ([1, 2, 3])___ by adding square brackets inside the tuples and ___[(((1, 2, 3)))]___ by adding 3 parentheses inside the lists `WRONG`
16. They contain references of the actual values
17. __copy.copy()__ is for simple lists and __copy.deepcopy()__ is for lists that contains more lists.

## Correct Answers:
[1](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1288). The empty list value, which is a list value that contains no items. This is similar to how '' is the empty string value.

[2](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1289). spam[2] = 'hello' (Notice that the third value in a list is at index 2 because the first index is 0.)

[3](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1290). 'd' (Note that '3' * 2 is the string '33', which is passed to int() before being divided by 11. This eventually evaluates to 3. Expressions can be used wherever values are used.)

[4](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1291). 'd' (Negative indexes count from the end.)

[5](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1292). ['a', 'b']

[6](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1293). 1

[7](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1294). [3.14, 'cat', 11, 'cat', True, 99]

[8](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1295). [3.14, 11, 'cat', True]

[9](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1296). The operator for list concatenation is +, while the operator for replication is *. (This is the same as for strings.)

[10](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1297). While append() will add values only to the end of a list, insert() can add them anywhere in the list.

[11](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1298). The del statement and the remove() list method are two ways to remove values from a list.

[12](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1299). Both lists and strings can be passed to len(), have indexes and slices, be used in for loops, be concatenated or replicated, and be used with the in and not in operators.

[13](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1300). Lists are mutable; they can have values added, removed, or changed. Tuples are immutable; they cannot be changed at all. Also, tuples are written using parentheses, ( and ), while lists use the square brackets, [ and ].

[14](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1301). (42,) (The trailing comma is mandatory.)

[15](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1302). The tuple() and list() functions, respectively

[16](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1303). They contain references to list values.

[17](https://automatetheboringstuff.com/2e/appendixc/#calibre_link-1304). The copy.copy() function will do a shallow copy of a list, while the copy.deepcopy() function will do a deep copy of a list. That is, only copy.deepcopy() will duplicate any lists inside the list.
