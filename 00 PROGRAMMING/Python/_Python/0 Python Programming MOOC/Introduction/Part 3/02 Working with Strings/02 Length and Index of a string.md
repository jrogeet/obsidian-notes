---
topic: strings
part: "3.2"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #strings
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 02 Length and Index of a string

--- 
## Length

The function ___`len`___ returns the number of characters in a string, which is always an integer value. 

For example, ___`len("hey")`___ returns __3__, because there are three characters in the string ___`hey___`.

The following program asks the user for a string and then prints it "underlined". The program prints a second line with as many ___`-`___ characters as is the length of the input:

```python
input_string = input("Please type in a string: ")
print(input_string)
print("-"*len(input_string))
```

> The length of a string includes all the characters in the string, including whitespace. For example, the length of the string `bye bye` is 7.


---
## Index
### Accessing Characters in Strings

Strings in Python are sequences of characters, and you can retrieve individual characters using the index operator `[]`.

- The index starts from 0, where the first character has index 0, the second character has index 1, and so on.
- The last character's index is `length - 1`.
- Negative indexing lets you access characters from the end of the string. The last character is `-1`, the second to last is `-2`, and so on.
- `input_string[-1]` is equivalent to `input_string[len(input_string) - 1]`.
![[Pasted image 20230828183730.png]]
### Examples:

1. Printing First and Last Characters:
```python
input_string = input("Please type in a string: ")
print("First character: " + input_string[0])
print("Last character: " + input_string[-1])
```

2. Looping Through Characters:
```python
input_string = input("Please type in a string: ")
index = 0
while index < len(input_string):
    print(input_string[index])
    index += 1
```

Using these techniques, you can access and manipulate individual characters within strings effectively.

You can also use negative indexing to access characters counting from the end of the string. The last character in a string is at index -1, the second to last character is at index -2, and so forth. You can think of `input_string[-1]` as shorthand for `input_string[len(input_string) - 1]`.

![[Pasted image 20230828184329.png]]

The example from above can be simplified with negative indexing:

```python
input_string = input("Please type in a string: ")
print("First character: " + input_string[0])
print("Last character: " + input_string[-1])
```