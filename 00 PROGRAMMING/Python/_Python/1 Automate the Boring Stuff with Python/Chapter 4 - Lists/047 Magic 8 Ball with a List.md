Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list 
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[023 List Data Type|List]] 

---
# Magic 8 Ball with a List

```python
import random  
  
messages = ['It is certain',  
		'It is decidely so',  
		'Yes definitely',  
		'Reply hazy try again',  
		'Ask again later',  
		'Concentrate and ask again',  
		'My reply is no',  
		'Outlook not so good',  
		'Very doubtful']  
  
print(messages[random.randint(0, len(messages) - 1)])
```

___messages[random.randint(0, len(messages) - 1)])___ this  produces a random number to use for the index,
regardless of the size of ___messages___. 

You'll get a random number between ___0___ and the values of ___len(messages) - 1___. 

The benefit of this approach is that you can easily __ADD__ and __REMOVE__ strings to the ___messages___ list without changing other lines of code.