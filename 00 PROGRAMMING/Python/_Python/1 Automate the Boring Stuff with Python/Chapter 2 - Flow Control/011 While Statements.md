Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #boolean #whileloop #whilestatement
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Flow Control Statements

## while Loop Statements

You can make a block of code execute over and over again using a ***while*** statement.

The code in a ***while*** clause will be executed as long as the ***while statement***’s condition is **True**.

***while statement*** consists of the following:
- **while*** keyword
- A condition (evaluates to **True** or **False**)
- A colon
- Next line, an indented block of code (called the ***while*** clause)
Example:

Using ***If statement***:
```python
spam = 0  
if spam < 5:  
    print('Hello, world.')  
    spam = spam + 1
```
![[Pasted image 20230519174126.png | center | 400]]

Using ***While Statement***:
```python
spam = 0  
while spam < 5:  
    print('Hello, world.')  
    spam = spam + 1
```


![[Pasted image 20230519174030.png | center | 400]]

Annoying while Loop:
```python
name = ''  
while name != 'your name':  
	print('Please type your name.')  
	name = input()  
print('Thank you!')
```

![[Pasted image 20230519174411.png | center | 400]]


## break Statements

If the execution reaches a ***break*** statement, it immediately exits the ***while loop***’s clause.


```python
while True:  
	print('Please type your name.')  
	name = input()  
	if name == 'your name':  
		break  
print('Thank you!')
```

The (1) First line creates an **infinite loop**; it is a ***while loop*** whose condition is always **True**.

After the program execution enters this loop, it will exit the loop only when a ***break statement*** is executed.

![[Pasted image 20230519174842.png | center | 400]]



## continue Statements

When the program execution reaches a ***continue statement***, the program execution immediately **jumps back to the start of the loop** and reevaluates the loop’s condition.

```python
while True:  
	print('Who are you?')  
	name = input()  
	if name != 'Joe':  
		continue  
	print('Hello, Joe. What is the password? (It is a fish.)')  
	password = input()  
	if password == 'swordfish':  
		break  
print('Access granted.')
```

![[Pasted image 20230519175149.png | center | 500]]

## “TRUTHY” AND “FALSEY” VALUES

Conditions will consider *some values* in other data types equivalent to **True** and **False**.

***0***, ***0.0*** and ***' ' (Empty String)*** are considered **False**,

while ***ALL OTHER VALUES*** are considered **True**

```python
name = ''
while not name:
	print('Enter your name:')  
    name = input()  
print('How many guests will you have?')  
numOfGuests = int(input())
if numOfGuests:
	print('Be sure to have enough room for all your guests.')
print('Done')
```

### **An Equivalent while Loop**

You can actually use a ***while loop*** to do the same thing as a ***for loop***; for loops are just more concise.

```python
print('My name is')  
i = 0  
while i < 5:  
    print('Jimmy Five Times (' + str(i) + ')')  
    i = i + 1
```

