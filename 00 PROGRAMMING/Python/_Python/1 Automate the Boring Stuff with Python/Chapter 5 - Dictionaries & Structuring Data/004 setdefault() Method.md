Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python 
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# setdefault() Method
```python
spam = {'name': 'Pooka', 'age': 5} 
if 'color' not in spam: 
	spam['color'] = 'black'
```

Do this in one line of code using `setdefault()`

```python
spam = {'name': 'Pooka', 'age': 5}
spam.default('color', 'black')
# black
print(spam)
# {'color':'black', 'age':5, 'name':'Pooka'}
spam.setdefault('color', 'white')
# black
print(spam)
# {'color':'black', 'age':5, 'name':'Pooka'}
```


## Short Program
Count the number of occurrences of each letter in a string.

```python
message = 'It was a bright cold day in April, and the clocks were striking thirteen.'

count = {}

for character in message:
	count.setdefault(character, 0)
	count[character] = count[character] + 1

print(count)
```
