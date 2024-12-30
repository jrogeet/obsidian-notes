---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# 03 confirm

--- 
```javascript
result = confirm(question);
```

The function ___confirm___ shows a modal window with a __question__ and two buttons: OK and Cancel

The result is ___true___ if OK is pressed
and ___false___ otherwise.

example:
```javascript
let isBoss = confirm("Are you the boss?");

alert( isBoss );
```