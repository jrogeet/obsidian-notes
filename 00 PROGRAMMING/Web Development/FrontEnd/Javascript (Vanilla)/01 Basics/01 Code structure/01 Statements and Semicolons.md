---
topic: javascript
---
Tags/Topics: #javascript #jsbasics
∗:[[01 Javascript|JavaScript]] 

---
# 01 Statements and Semicolons

--- 
## Statements
Syntax constructs and commands that perform actions.

We can have as many statements in our code as we want.
Statements can be separated with a __semicolon__.
```javascript
alert('Hello'); alert('World');
```
Usually  written on separate lines for readability
```javascript
alert('Hello');
alert('World');
```

## Semicolons
A semicolon may be omitted in most cases when a line break exists.
- a new line implies a semicolon. but NOT ALWAYS

JavaScript interprets the __line break__ as an "implicit" semicolon. (automatic semicolon insertion)
```javascript
alert('Hello')
alert('World')
```

>[!example]- Example: newline doesn't mean a semicolon:
> ```javascript
> alert(3 + 
> 1
> + 2);
> ```
> - This code outputs ___6___
> - JavaScript doesn't inert semicolons here
> - an "__Incomplete Expression__" since the line ends with a "___+___" 

>[!caution]- Example: Error
>No error:
> ```javascript
> alert("Hello");
> [1, 2].forEach(alert);
> ```
> Error:
> ```javascript
> alert("Hello")
> [1. 2].forEach(alert);
> ```
> - The engine sees it as a single statement
> ```javascript
> alert("Hello") [1, 2].forEach(alert);
>```
> - Put a semicolon after ___alert___ for the code to work correctly
> 







