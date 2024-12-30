---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #loops
∗:[[01 Javascript|JavaScript]] 

---
# 01 While Loop

--- 
Syntax:
```javascript
while (condition) {
	// code
	// so-called "loop body"
}
```

While the `condition` is true, the `code` from the loop body is executed.

This loop outputs `i` while `i < 3`:
```javascript
let i = 0;
while (i < 3) { // show 0, then 1, then 2
	alert( i );
	i++;
}
```
- The loop would iterate __forever__ if `i++` is missing.

---
Shorter way to write `while (i != 0)` is `while (i):`
```javascript
let i = 3;
while (i) { // when i becomes 0, the condition becomes falsy, and the loop stops
	alert( i );
	i--;
}
```
>[!tip] Curly braces aren't required for __single-line body__
>If loop body has a __single statement__
>```javascript
>let i = 3;
>while (i) alert(i--);

---
### More Examples:
```javascript
let i = 3;

while (i) {
	alert( i-- );

}
```
-  Every iteration `i` decreases by `1`
- the check `while(i)` stops the loop when `i = 0`

Steps / sequence:
```javascript
let i = 3;
	
	alert(i--); // shows 3, decreases i to 2
	
	alert(i--) // shows 2, deceases i to 1
	
	alert(i--) // shows 1, decreases i to 0
	
	// done, while(i) check stops the loop
```

---
```javascript
let i = 0;
while (++i < 5) alert( i );
```
- From 1 to 4
- `++i` increments `i` and returns new value.
	- First comparison is `1 < 5` and `alert` shows `1`
	- Finally, `i = 4` incremented to `5`
		- comparison `while(5 < 5)` fails, the loop stops. So `5` is not shown.

```javascript
let i = 0;
while (i++ < 5) alert(i);
```
- From 1 to 5
- `i++` increments `i` and returns _old value_
	- `i = 4`, increments `i` to `5`, but returns _old value_
		- comparison is actually `while(4 < 5)`

---


