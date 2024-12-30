---
topic: ""
part: ""
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Reading the same file multiple times

--- 
```sample data
Peter;40;Helsinki 
Emily;34;Espoo 
Eric;42;London 
Adam;100;Amsterdam 
Alice;58;Paris
```

>[!danger] Running this will result in a somewhat cryptic error message:
>```python
>with open("people.csv") as new_file:
>	# print out the names
>	for line in new_file:
>		parts = line.split(";")
>		print("Name:", parts[0])
>
>	# find the oldest
>	age_of_oldest = -1
>	for line in new_file:
>		parts = line.split(";")
>		name = parts[0]
>		age = int(parts[1])
>		if age > age_of_oldest:
>			age_of_oldest = age
>			oldest = name
>	print("the oldest is", oldest)
>```
> - The last `for` loop is not executed at all
> 	- because the file can only be processed once

>[!done] Solutions:
>1. This would work but it contains unnecessary repetition.
>```python
>with open("people.csv") as new_file:
>	# print out the names
>	for line in new_file:
>		parts = line.split(";")
>		print("Name:", parts[0])
>		
>with open("people.csv") as new_file:
>	# find the oldest
>	age_of_oldest = -1
>	for line in new_file:
>		parts = line.split(";")
>		name = parts[0]
>		age = int(parts[1])
>		if age > age_of_oldest:
>			age_of_oldest = age
>			oldest = name
>	print("the oldest is", oldest)
>```
>2. 
>```python
>people = []
># read the contents of the file and store it in a list
>with open("people.csv") as new_file:
>	for line in new_file:
>		parts = line.split(";")
>		people.append((parts[0], int(parts[1]), parts[2]))
>		
># print out the names
>for person in people:
>	print("Name:", person[0])
>	
># find the oldest
>age_of_oldest = -1
>for person in people:
>	name = person[0]
>	age = person[1]
>	if age > age_of_oldest:
>		age_of_oldest = age
>		oldest = name
>print("the oldest is", oldest)
>```

