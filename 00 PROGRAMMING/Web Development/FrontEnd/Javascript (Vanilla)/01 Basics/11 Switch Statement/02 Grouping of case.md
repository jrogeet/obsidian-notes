---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #switch 
∗:[[01 Javascript|JavaScript]] 

---
# 02 Grouping of case

--- 
`case` which share the same code can be grouped.
"group"-ing cases is a side effect of how `switch/case` works __without__ `break`.

```javascript
let a = 3;

switch(a) {
	case 4:
		alert('Right!');
		break;
	case 3: .. (*)grop
}
```
Example: If we want the same code to run for `case 3` and `case 5`
```javascript
let a = 3;

switch(a) {
	case 4:
		alert('Right!');
		break;
	
	case 3: // (*) grouped two cases
	case 5:
		alert('Wrong!');
		alert("Why don't you take a math class?");
		break;
		
	default:
		alert('The result is strange. Really.');
}
```
- Both `3` and `5` show the same message
- the execution `case 3` goes through `case 5`, because there's no `break`
