---
topic: conditional
part: "2.2"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #conditional
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 02 Alternative branches using the elif statement

--- 
A conditional statement can be added to with an `elif` branch. It is short for the words "else if", which means the branch will contain an alternative to the original condition. Importantly, an `elif` statement is executed only if none of the preceding branches is executed.

![[Pasted image 20230828174829.png]]

Let's have a look at a program which determines the winner of a match:

```python
goals_home = int(input("Home goals scored: "))
goals_away = int(input("Away goals scored: "))

if goals_home > goals_away:
    print("The home team won!")
elif goals_away > goals_home:
    print("The away team won!")
else:
    print("It's a tie!")
```

This program could print out three different statements given different inputs:

Sample output

```
Home goals scored: 4 
Away goals scored: 2 
The home team won!
```
Sample output

```
Home goals scored: 0 
Away goals scored: 6 
The away team won!
```
Sample output

```
Home goals scored: 3 
Away goals scored: 3 
It's a tie!
```

In the above example there are three alternative branches, exactly one of which will always be executed. However, there is no limit to the number of `elif` branches a conditional statement can contain, and the `else` branch is not mandatory.

This is also a valid conditional statement:

```python
print("Holiday calendar")
date = input("What is the date today? ")

if date == "Dec 26":
    print("It's Boxing Day")
elif date == "Dec 31":
    print("It's Hogmanay")
elif date == "Jan 1":
    print("It's New Year's Day")

print("Thanks and bye.")
```

Notice the previous example has no `else` branch. If the user inputs a date which is not mentioned in any of the `if` or `elif` branches, or inputs a date in a different format, none of the three branches of the conditional statement is executed.

Sample output

```
Holiday calendar 
What is the date today? Dec 25 
Thanks and bye.
```

