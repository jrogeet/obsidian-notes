Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[023 List Data Type|List]] 

---
# Working with Lists

if I wanted to store the names of my cats, I might be tempted to write code like this
```python
catName1 = 'Zophie'  
catName2 = 'Pooka'  
catName3 = 'Simon'  
catName4 = 'Lady Macbeth'  
catName5 = 'Fat-tail'  
catName6 = 'Miss Cleo'
```
It turns out that this is a bad way to write code.

if the number of cats changes, your program will never be able to store more cats than you have variables.

```python
print('Enter the name of cat 1:')  
catName1 = input()  
print('Enter the name of cat 2:')  
catName2 = input()  
print('Enter the name of cat 3:')  
catName3 = input()  
print('Enter the name of cat 4:')  
catName4 = input()  
print('Enter the name of cat 5:')  
catName5 = input()  
print('Enter the name of cat 6:')  
catName6 = input()  
print('The cat names are:')  
print(catName1 + ' ' + catName2 + ' ' + catName3 + ' ' + catName4 + ' ' +  
catName5 + ' ' + catName6)
```

Instead of using multiple, repititive variables, you can use a single variable that contains a list value.

This uses a single list and can store any number of cats that the user types in.

```python
catNames = []
while True:
	print('Enter the name of cat ' + str(len(catNames) + 1) + ' (Or enter nothing to stop.):')
	name = input()
	if name == '':
		break
	catNames = catNames + [name] # list concatenation
print('The cat names are: ')
for name in catNames:
	print('      ' + name)
```

### My Code:
I tweaked the code above so that the program will ask how many cats the user have.
```python
catNames = []  
  
catnum = int(input('Enter how many Cats you have: '))  
  
for i in range(catnum):  
	names = input('Enter the name of cat ' + str(len(catNames)+ 1) + ': ')  
	catNames = catNames + [names]  
  
print('Your cat names are: ')  
for names in catNames:  
	print(names)
```