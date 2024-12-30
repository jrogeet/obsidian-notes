---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #loops 
∗:[[01 Javascript|JavaScript]] 

---
# Label

--- 
An identifier with a colon before a loop:
```javascript
labelName: for (...) {
	...
}
```

The `break <labelName>` statement in the loop below breaks out to the label:
```javascript
outer: for (let i = 0; i < 3; i++) {
	for (let j = 0; j < 3; j++) {
		let input = prompt(`Value at coords (${i}, ${j})`, '');
		
		// if an empty string or canceled, then break out of both loops
		if (!input) break outer; // (*)
		
		// do something with the value...
	}
}
alert('Done!');
```
- `break outer` look upwards for label named `outer` and breaks out of that loop

Move the label onto a seperate line:
```javascript
outer:
for (let i = 0; i < 3; i++) { ... }
```

>[!Caution] Labels don't allow to "jump" anywhere
>Impossible:
>```javascript
>break label; // jump to the label below (doesn't work)
>
>labell: for ( ... )
>```
>- A `break` directive __must be inside a code block__
>	- Any labelled code block will do:
>```javascript
>label: {
>	// ...
>	break label; // works
>	// ...
>}
>```
>A `continue` is only possible from inside a loop.



---
### More Example:
Output prime numbers in the interval from `2` to `n`:
```javascript
let n = 10;

nextPrime:
for (let i = 2; i <= n; i++) { // for each i...

	for (let j = 2; j < i; j++) { // look for divisor...
		if (i % j == 0) continue nextPrime; // not a prime, go next i
	}

	alert( i ); // a prime
}
```
 