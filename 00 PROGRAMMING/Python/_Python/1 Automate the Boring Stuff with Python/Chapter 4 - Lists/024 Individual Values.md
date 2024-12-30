Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list #listvalues
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[023 List Data Type|List]] 

---
# Getting Individual Values in a List with Indexes
```python
spam = ['cat', 'bat', 'rat', 'elephant']
```
___spam[0]___ would evaluate to ___'cat'___
___spam[1]___ would evaluate to ___'bat'___
___spam[2]___ would evaluate to ___'rat'___
___spam[3]___ would evaluate to ___'elephant'___
![[Pasted image 20230712221101.png]]

>Note that because the first index is _0_, the last index is one less than the size of the list; __a list of four items__ has _3_ as its last index.

```python
spam = ['cat', 'bat', 'rat', 'elephant']

spam[0]
spam[1]
spam[2]
spam[3]

['cat', 'bat', 'rat', 'elephant'][3]

'Hello, ' + spam[0]

'The ' + spam[1] + ' ate the ' + spam[0] + '.'

spamz = ['cat', 'bat', 'rat', 'elephant']  
  
print(spamz[0])  
print(spamz[1])  
print(spamz[2])  
print(spamz[3])  
  
print(['cat', 'bat', 'rat', 'elephant'][2])  
  
print('Hello, ' + spamz[0])  
  
print('The ' + spamz[1] + ' ate the ' + spamz[0] + '.')
```

> Python will give you an _IndexError_ error message if you use an index that exceeds the number of values in your list value.

```python
spam = ['cat', 'bat', 'rat', 'elephant']
spam[10000]
```

> Indexes can be ___only integer values___, __not floats__. The following example will cause a _TypeError_ error:

## Lists can also contain other list values

The values in these lists of lists can be accessed using multiple indexes, like so:
```python
spam = [['cat', 'bat'], [10, 20, 30, 40, 50]]
spam[0]

spam[0][1]
spam[1][4]
```
The first index dictates which list value to use, and the second indicates the value within the list value. 

The group values with _cat_ and _bat_ is __0__ and the _10_ to _50_ numbers are __1__. 

For example, ___spam\[0]\[1]___ prints __'bat'__, the second value in the first list. 

>If you only use one index, the program will print the full list value at that index.