---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #conditional
∗:[[01 Javascript|JavaScript]] 

---
# 01 If statement

--- 
`if(...)` evaluates condition in parentheses, if `true` the block of code will execute.

```javascript
let year = prompt('In which year was ECMAScript - 2015 specification published?', '');

if (year == 2015) alert('You are right!');
```
To execute more than one statement,
Wrap the code block inside __curly braces__:
```javascript
if (year == 2015) {
	alert( "That's correct!" );
	alert( "You're so smart!" );
}
```
Using curly braces are better for readability.


---
## More Example:

```javascript
if ("0") {
	alert( 'Hello' );
}
```
- The code inside ran because: 
	- Any string except an _empty_ one (`"0"` is __not empty__) becomes ___true___

```html
<!DOCTYPE html>
<html>

<body>
	<script>
		'use strict';
		
		let value = prompt('What is the "official" name of Javascript', '');
		
		if (value == 'ECMAScript') {
			alert('Right!');
		} else {
			alert("You don't know? ECMAScript!");
		}
	</script>

</body>
</html>
```

