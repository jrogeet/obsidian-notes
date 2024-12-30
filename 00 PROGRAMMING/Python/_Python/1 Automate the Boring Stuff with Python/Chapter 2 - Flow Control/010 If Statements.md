Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #boolean #ifelse #ifstatement
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Flow Control Statements

## if Statements
The most common type of flow control statement is the ***if statement***.

***if statement***'s clause will execute if the statement's condition is **True**. It will skip if it's **False**.
> If the statement is true, execute the code in the clause.

***if statement*** consists of the following:
- ***if*** keyword
- A condition(evaluates to *True* or *False*)
- A colon
- Next line, indented block of code (called the *if* clause)

Example:
```python
if name == 'Alice';
	print('Hi, Alice.')
```



![[Pasted image 20230519161452.png |center | 400]]

## else Statements
An ***if*** clause can **optionally** be followed by an ***else statement***. 

The ***else*** clause is executed only when the ***if statement***’s condition is **False**.
>“If this condition is true, execute this code. Or else, execute that code.”

An ***else*** statement doesn't have a condition

***else statement*** consists of the following:
- The ***else*** keyword
- A colon
- Next line,  an indented block of code (called the ***else*** clause)

```python
if name == 'Alice':  
    print('Hi, Alice.')  
else:  
    print('Hello, stranger.')
```

![[Pasted image 20230519163539.png | center | 400]]


## elif Statements
The ***elif statement*** is an “**else if**” statement that always follows an ***if*** or another ***elif statement***.

***elif statement***  consists of the following:
- ***elif*** keyword
- A condition (evaluates to **True** or **False**)
- A colon
- Next line, an indented block of code (called the ***elif*** clause)

```python
if name == 'Alice':  
    print('Hi, Alice.')  
elif age < 12:  
    print('You are not Alice, kiddo.')
```


![[Pasted image 20230519163522.png | center | 400]]

Example: 
```python
name = 'Carol'  
age = 3000  
if name == 'Alice':  
    print('Hi, Alice.')  
elif age < 12:  
    print('You are not Alice, kiddo.')  
elif age > 2000:  
    print('Unlike you, Alice is not an undead, immortal vampire.')  
elif age > 100:  
    print('You are not Alice, grannie.')
```


![[Pasted image 20230519163458.png | center | 400]]


The order of the ***elif statements*** does MATTER. 

if ***elif statement*** found a **True** Condition, it will ignore the rest of the ***elif statements***.
So, if there is Two **True** ***elif statements*** the FIRST one would be the output.

Example:
```python
 name = 'Carol'  
   age = 3000  
   if name == 'Alice':  
       print('Hi, Alice.')  
   elif age < 12:  
       print('You are not Alice, kiddo.')  
➊ elif age > 100:  
       print('You are not Alice, grannie.')  
   elif age > 2000:  
       print('Unlike you, Alice is not an undead, immortal vampire.')
```

We put the **age > 100** first which would result to **True**.

Optionally, you can have an ***else statement*** after the last ***elif statement***.
If the conditions in every ***if*** and ***elif statement*** are **False**, then the ***else*** clause is executed.

```python
name = 'Carol'  
age = 3000  
if name == 'Alice':  
    print('Hi, Alice.')  
elif age < 12:  
    print('You are not Alice, kiddo.')  
else:  
    print('You are neither Alice nor a little kid.')
```

>If the first condition is true, do this. Else, if the second condition is true, do that. Otherwise, do something else.

![[Pasted image 20230519172251.png | center | 400]]
 
 The ***X path*** will logically never happen, because if **age** were greater than **2000**, it would have already been greater than **100**.

![[Pasted image 20230519172756.png | center | 400]]

