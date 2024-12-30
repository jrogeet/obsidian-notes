---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #loops
∗:[[01 Javascript|JavaScript]] 

---
# 04 Breaking the loop

--- 
Force loops to exit using `break`

```javascript
let sum = 0;

while (true) {

	let value = +prompt("Enter a number", '');

	if (!value) break; // (*)

	sum += value;
}
alert( 'Sum: ' + sum);
```
- If user enters _empty line_ or cancels the input, The loop stops then runs `alert` outside the loop.


