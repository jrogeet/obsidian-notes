Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #return #returnstatement
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[015 Functions|Functions]] 

---
# Return Values and return Statements
```python
import random  
  
def getAnswer(answerNumber):  
	if answerNumber == 1:  
		return 'It is certain'  
	elif answerNumber == 2:  
		return 'It is decidedly so'  
	elif answerNumber == 3:  
		return 'Yes'  
	elif answerNumber == 4:  
		return 'Reply hazy try again'  
	elif answerNumber == 5:  
		return 'Ask again later'  
	elif answerNumber == 6:  
		return 'Concentrate and ask again'  
	elif answerNumber == 7:  
		return 'My reply is no'  
	elif answerNumber == 8:  
		return 'Outlook not so good'  
	elif answerNumber == 9:  
		return 'Very doubtful'  
  
r = random.randint(1, 9)  
fortune = getAnswer(r)  
print(fortune)
```
Step-by-step process of this code:
- imports the ***random*** module
- defined ***getAnswer()*** function
- ***random.randint()*** function is called with two arguments: ***1*** and ***9***( generates a number from 1 to 9)
- ***getAnswer()*** function is called with ***r*** as argument
- the value ***r*** value is stored in a parameter named ***answerNumber***
- depends on the value of ***r*** in ***answerNumber***, the function returns one of many possible string values.
- returns to the line originally called ***getAnswer()***
- returned string is assigned to the variable named ***fortune*** which is printed with ***print()***

> NOTE: You can shorten these three lines:

```python
r = random.randint(1, 9)  
fortune = getAnswer(r)  
print(fortune)
```
> Since you can pass return values as an argument to another function call

```python
print(getAnswer(random.randint(1, 9)))
```

