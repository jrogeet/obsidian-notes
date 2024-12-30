---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
## Clean Code Cheat Sheet
--- 
![[Pasted image 20240108230702.png]]


---
## Line Length

--- 
It's best practice to split long horizontal line of code.
```javascript
// backtick quotes `` allow to split the string into multiple lines
let str = `
	ECMA International's TC39 is a group of JavaScript developers, implementers, academics, and more, collaborating with the community to maintain and evlve the definition of JavaScript.
`;

```

for `if` statements:
```javascript
if (
  id === 123 &&
  moonPhase === 'Waning Gibbous' &&
  zodiacSign === 'Libra'
) {
  letTheSorceryBegin();
}
```


---
## Nesting Levels
---
Try to avoid nesting code too many levels deep.


>[!example] Examples:
>Option 1:
>``` javascript
>function pow(x, n) {
>	if (n < 0) {
>		alert("Negative 'n' not supported");
>	} else {
>		let result = 1;
>		
>		for (let i = 0; i < n; i++) {
>			result *= x;
>		}
>		
>		return result;
>	}
>}
>```
>Option 2:
>```javascript
>function pow(x, n) {
>	if (n < 0) {
>		alert("Negative 'n' not supported");
>		return;
>	}
>	
>	let result = 1;
>	
>	for (let i = 0; i < n; i++) {
>		result *= x;
>	}
>	
>	return result;
>}
>```
