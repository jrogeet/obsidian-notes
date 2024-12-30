---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# 02 prompt

--- 
the Function __prompt__ accepts two arguments:
```javascript
result = prompt(title, [default])
```
shows a modal window with a text message, an input field for the visitor, and the buttons OK/Cancel.

___title___ - text to show the visitor.
___default___ - optional second parameter, the initial value for the input field

Square brackets means the parameter is __optional, not required__ 

```javascript
let age = prompt('How old are you?', 100);

alert(`You are ${age} years old!`) // You are 100 years old!
```
- Visitor can type something in the prompt input field and press OK
	- they can cancel the input by pressing Cancel or hitting `ESC` 
	- then, we get ___null___ as the result.__