Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #boolean
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] , [[006 Boolean |Boolean]]

---

# Mixing Boolean and Comparison Operators
Recall that the `and`, `or`, and `not` operators are called ***Boolean operators*** because they always operate on the Boolean values `True` and `False`.

 While expressions like `4 < 5` ***aren’t Boolean values***, they are expressions that ***`evaluate`*** down to ***Boolean values***.

```python

(4 < 5) and (5 < 6)    #True

(4 < 5) and (9 < 6)    #False

(1 == 2) or (2 == 2)   #True
```

The computer will evaluate the left expression first, and then it will evaluate the right expression. 

When it knows the Boolean value for each, it will then evaluate the whole expression down to one Boolean value. 

You can think of the computer’s evaluation process for `(4 < 5)` and `(5 < 6`) as the following:
![[Pasted image 20230518182847.png | center]]


You can also use multiple Boolean operators in an expression, along with the comparison operators:

```python
2 + 2 == 4 and not 2 + 2 == 5 and 2 * 2 == 2 + 2    #True
```
The Boolean operators have an ***order of operations*** just like the ***math operators do***. 
***`After any math and comparison operators`*** evaluate, Python evaluates the `not` operators first, then the `and `operators, and then the `or` operators.

So basically, 
`Math Operators` > `Comparison Operators` > `not operator` > `and operator` > `or operator`



