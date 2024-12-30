---
topic: variables
part: "1.3"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #variables
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 02 Changing the value of a variable

--- 
As implied by the name _variable_, the value stored in a variable can change. In the previous section we noticed that the new value replaces the old one.

During the execution of the following program, the variable `word` will have three different values:

```python
word = input("Please type in a word: ")
print(word)

word = input("And another word: ")
print(word)

word = "third"
print(word)
```
The value stored in the variable changes each time the variable is assigned a new value.

The new value of a variable can be derived from its old value. In the following example the variable `word` is first assigned a value based on user input. Then it is assigned a new value, which is the old value with three exclamation marks added to the end.

```python
word = input("Please type in a word: ")
print(word)

word = word + "!!!"
print(word)
```

> [!Choosing a good name for a variable]
> - It is often useful to name variables according to what they are used for. For example, if the variable contains a word, the name `word` is a better choice than, say, `a`.
    - There is no set limit to the length of a variable name in Python, but there are some other limitations. A variable name should begin with a letter, and it can only contain letters, numbers and underscores .
    - Lowercase and uppercase letters are different characters. The variables `name`, `Name` and `NAME` are all different variables. While this rule has a few exceptions, we will ignore those for now.
    - It is a common programming practice in Python to use only lowercase characters in variable names. If the variable name consists of multiple words, use an underscore between the words. While this rule also has a few exceptions, we will ignore those for now.
