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
# CSV files

--- 
__CSV file__ or _comma-separated Values_
- Contains data separated by a _predetermined character_
	- Most common characters used is comma `,` and semicolon `;`
	- __any character in is possible__

> [!Question ]- How can we separate the different fields on a single line
> - String method `split` takes __separator character(s)__ as string argument
> - Returns the contents as a list of strings, separated by separator
> ```python
> text = "monkey, banana, harpsichord"
> words = text.split(",")
> for word in words:
> 	print(word)
> ```

```python
with open("grades.csv") as new_file:
	for line in new_file:
		line = line.replace("\n", "")
		parts = line.split(";")
		name = parts[0]
		grades = parts[1:]
		print("Name:", name)
		print("Grades:", grades)
```

```text
Name: Paul 
Grades: ['5', '4', '5', '3', '4', '5', '5', '4', '2', '4'] 
Name: Beth 
Grades: ['3', '4', '2', '4', '4', '2', '3', '1', '3', '3'] 
Name: Ruth 
Grades: ['4', '5', '5', '4', '5', '5', '4', '5', '4', '4']
```

