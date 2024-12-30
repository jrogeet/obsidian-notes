Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #list #methods
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]]  [[023 List Data Type|List]] [[039 Methods|Methods]] 

---
# Finding a Value in a List with the index() Method

List values have an ___index()___ method that can be __passed a value__,
and if that value __exists in the list__, the index of the value is __returned__.
If the value __isn’t in the list__, then Python produces a ___ValueError___ error.

```python
spam = ['hello', 'hi', 'howdy', 'heyas']
print(spam.index('hello'))

print(spam.index('heyas'))

print(spam.index('howdy howdy howdy'))
```

When there are __duplicates__ of the value in the list, the index of its __first appearance__ is returned.

```python
spam = ['Zophie', 'Pooka', 'Fat-tail', 'Pooka']
print(spam.index('Pooka'))
```