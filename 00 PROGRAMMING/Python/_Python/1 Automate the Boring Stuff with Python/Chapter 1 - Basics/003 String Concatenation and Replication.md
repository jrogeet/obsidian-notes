Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics:  #python  #strings #concatenation #replication
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[002 Data Types]]

---

# String Concatenation and Replication
[STRING](002%20Data%20Types.md#Strings)

The ***plus(`+`)*** operator when used with integers or floating-point values will do addition. 

However, ***plus(`+`)***  could also be used on two String Values, When used with two String Values, it will join the strings as the ***`String Concatenation Operator`*** 

```python
print('Sponge' + 'Bob')
```

The output would be `Spongebob` combining the two string you've input. 
However, If you try to concatenate a String and an Integer, Python would give you an error message.

```python
print('Sponge' + 420)
```

The error message would say `can only concatenate str (not "int") to str` means that Python thought you were trying to concatenate an integer to the string `'Sponge'`. 

---
The ***multiply(`*`)*** operator will multiply Two Integers or Floating-point values. 
But, If used on One String Value (example: `Sponge`) and One Integer Value (example: `5`), It will `replicate` the string *5* times. The operator will be called ***`String Replication Operator`***.

```python
print('Sponge' * 5)
```

This would make the single string value repeats by the number of times equal to the integer value.
`Sponge` repeats `5` times.

The ***`*`*** can only be used with two numeric values(for Multiplication), or One STRING Value and One INTEGER Value(for String REPLICATION). Otherwise it will result to an ERROR.

```python
print('Sponge' * 'Bob')
```

