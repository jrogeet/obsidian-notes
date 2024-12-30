Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #boolean
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] , [[006 Boolean|Boolean]]

---
# Comparison Operators
`Comparison operators`, also called `Relational operators`, compare two values and evaluate down to a single [[006 Boolean|Boolean]] value.

![[Pasted image 20230518175639.png | center]]

These values will result to `True` or `False` depends on the values you give them.

```python
42 == 42
```
This would result to `True` since `42` is indeed equals to `42`
```python
42 == 99 #False

2 != 3 #True

2 != 2 #False
```

---
The `==` and `!=` operators can actually ***`work with values of any data type`***.

```python
'hello' == 'hello'    #True

'hello' == 'Hello'    #False

'dog' != 'cat'        #True

True == True          #True

True != False         #True

42 == 42.0            #True

42 == '42'            #False
```

The `<`, `>`, `<=`, and `>=` operators, on the other hand, ***`work properly only with integer and floating-point values`***.

```python
42 < 100        #True

42 > 100        #False

42 < 42         #False

eggCount = 42   #True
eggCount <= 42

myAge = 29      #True
myAge >= 10
```


# **THE DIFFERENCE BETWEEN THE == AND = OPERATORS**

You might have noticed that the ***`==`*** operator (`equal to`) has two equal signs, while the ***`=`*** operator (`assignment`) has just one equal sign. It’s easy to confuse these two operators with each other. Just remember these points:

-   The ***`==`*** operator (`equal to`) asks whether two values are the same as each other.
-   The ***`=`*** operator (`assignment`) puts the value on the right into the variable on the left.

To help remember which is which, notice that the ***`==`*** operator (`equal to`) consists of two characters, just like the`!=` operator (`not equal to`) consists of two characters.