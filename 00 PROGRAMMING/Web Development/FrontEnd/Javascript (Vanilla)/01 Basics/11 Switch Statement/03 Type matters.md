---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #switch 
∗:[[01 Javascript|JavaScript]] 

---
# 03 Type matters

--- 
`case` uses `===` (strict equality check).
The values must be of the __same type__ to match.

```javascript
let arg = prompt("Enter a value?");
switch (arg) {
	case '0':
	case '1':
		alert( 'One or zero' );
		break;
	
	case '2':
		alert( 'Two' )
		break;
	
	case 3:
		alert( 'Never executes!' );
		break;
	default:
		alert( 'An uknown value' );
}
```
- For `0`, `1`, first `alert` runs
- For `2` the second `alert` runs
- But for `3`, the result of the `prompt` is a string `"3"` which are NOT `=== 3` or `'3'!== 3`
- `default` will execute

--- 
### More examples:
- `switch/case` and `if-else` versions
```javascript
switch (browser) {
	case 'Edge':
		alert( "You've got the Edge!" );
		break;
	
	case 'Chrome':
	case 'Firefox':
	case 'Safari':
	case 'Opera':
		alert('Okay we support these browsers too');
		break;
	
	default:
		alert( 'We hope that this page looks ok!' );
}
```
```javascript
if (browser === 'Edge') {
    alert("You've got the Edge!");

} else if (browser === 'Chrome' 
|| browser === 'Firefox' 
|| browser === 'Safari' 
|| browser === 'Opera') {
    alert('Okay we support these browsers too' );
} else {
    alert( 'We hope that this page looks ok!' );
}
```

---

```javascript
let a = +prompt('a?', '');

switch(a) {
    case 0:
        alert( 0 );
        break;
    case 1:
        alert( 1 );
        break;

    case 2:
    case 3:
        alert( '2,3' );
        break;
}
```
```javascript
let a = +prompt('a?', '');

if (a == 0) {
	alert(0);
}
if (a == 1) {
	alert(1);
}

if (a == 2 || a == 3) {
	alert( '2,3' );
}
```
