---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #functions
∗:[[01 Javascript|JavaScript]] 

---
# 05 Return

--- 
A function can return a value back into the calling code as the result

```javascript
function sum(a, b) {
	return a + b;
}
let result = sum(1, 2);
alert( result ); // 3
```

- `return` can be in any place of the function
- When the execution reaches it, __the function stop__.
	- the value is then returned to the calling code ( the `result` above)

```javascript
function checkAge(age) {
  if (age >= 18) {
    return true;
  } else {
    return confirm('Do you have permission from your parents?');
  }
} 

let age = prompt('How old are you?', 18); 

if ( checkAge(age) ) {
  alert( 'Access granted' );
} else {
  alert( 'Access denied' );
}
```

>[!tip] `return` without a value
>`return` without a value, exits the function immediately
>```javascript
>function showMovie(age) {
>	if ( !checkAge(age) ) {
>		return;
>	}
>	
>	alert( "Showing you the movie" ); // (*)
>	// ...
>}
>```
> - if `checkAge(age)` returns `false`, then `showMovie` won't proceed to the `alert`

>[!caution] No `return`
>A function with an _empty_ `return` or __without it__ returns `undefined`
>- If a function doesn't return a value, it's the same as if it returns `undefined`:
>```javascript
>function doNothing() { / * empty */ }
>
>alert( doNothing() === undefined ); // true
>```
>- An empty `return` is also the same as `return undefined`:
>```javascript
>function doNothing() {
>	return;
>}
>
>alert( doNothing() === undefined ); // true
>```


>[!danger] Never add a __newline__ between `return` and the value
>This doesn't work, JavaScript assumes a semicolon after `return`:
>```javascript
>return
>	(some + long + expression + or + whatever * f(a) + f(b))
>```
>Work the same as:
>```javascript
>return;
>	(some + long + expression + or + whatever * f(a) + f(b))
>```
>>[!check] Right way:
>>Put it in the same line as `return`
>>OR the opening parentheses:
>>```javascript
>>return (
>>	some + long + expression
>>	+ or +
>>	  whatever * f(a) + f(b)
>>)
>>```


---
### More Example:
>[!example] else and without else
>There's no difference between these two codes:
>```javascript
>function checkAge(age) {
>	if (age > 18) {
>		return true;
>	} else {
>		// ...
>		return confirm('Did parents allow you?');
>	}
>}
>```
>```javascript
>function checkAge(age) {
>	if (age > 18) {
>		return true;
>	}
>	// ...
>	return confirm('Did parents allow you?');
>}
>```

>[!example] `?` and `||` version of a function
>```javascript
>function checkAge(age) {
>	if (age > 18) {
>		return true;
>	} else {
>		return confirm('Did parents allow you?');
>	}
>}
>```
>`?` version:
>```javascript
>function checkAge(age) {
>	return (age > 18) ? true : confirm('Did parents allow you?');
>}
>```
>`||` version:
>```javascript
>function checkAge(age) {
>	return (age > 18) || confirm('Did parents allow you?');
>}
>```

>[!example] Return the least of two numbers `a` and `b`:
>using `if`:
>```javascript
>function min(a, b) {
>	if (a < b) {
>		return a;
>	} else {
>		return b;
>	}
>}
>```
>using ternary (question mark) operator `?`:
>```javascript
>function min(a, b) {
>	return a < b ? a : b;
>}
>```
>P.S. In the case of an _equality_ `a == b` it does not matter what to return

>[!example] Power
>A function `pow(x, n)` that returns `x` in power `n`.
>In other words: multiplies `x` by itself `n` times and returns the result
>- The function should support __only natural values__ of `n` (integers up from `1`)
>```javascript
>function power(x, n) {
>	let result = x;
>	
>	for (let i = 1; i  < n; i ++) {
>		result *= x;
>	}
>	
>	return result;
>}
>
>let x = prompt("x?", ' ');
>let n = prompt("n?", '');
>
>if (n < 1) {
>	alert(`Power ${n} is not supported, use a positive integer`);
>} else {
>	alert( power(x, n) );
>}
>```
>>[!note]- My answer:
>>```javascript
>>let x = prompt('Enter x:', '');
>>let n = prompt('Enter n:', '');
>>
>>function pow(x, n) {
>>	if (n >= 1) {
>>		return (x ** n);
>>	}
>>}
>>result = pow(x, n);
>>alert(result);
>>```



