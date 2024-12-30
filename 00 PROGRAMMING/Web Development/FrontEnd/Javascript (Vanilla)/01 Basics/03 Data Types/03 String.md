---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# 03 String

--- 
Strings must be surrounded by quotes.
```javascript
let str = "Hello";
let str2 = 'Single quotes are ok too';
let phrase = `can embed another ${str}`;
```

3  Types of Quotes:
1. Double quotes: "Hello"
2. Single quotes: 'Hello'
3. Backticks `Hello`

Backticks are "extended functionality" quotes.

```javascript
let name = "John";

//embed a variable
alert( `Hello, ${name}!` ); // Hello, John!

// embed an expression
alert( `the result is $(1 + 2}` ) // the result is 3
```
