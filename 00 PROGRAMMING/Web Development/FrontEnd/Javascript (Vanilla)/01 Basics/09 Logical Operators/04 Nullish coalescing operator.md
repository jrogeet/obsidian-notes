---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #logical
∗:[[01 Javascript|JavaScript]] 

---
# 04 Nullish coalescing operator

--- 

>[!Abstract]- Summary
>- `??` provides a short way to choose the first __defined__ value from a list.
>- Used to assign ___default values___ to variables:
>```javascript
>// set height=100, if height is null or undefined
>height = height ?? 100;
>```
>- `??` very low precedence, a bit higher than `?` and `=`
>	- consider Using a _parentheses_
>- __Forbidden__ to use with `||` or `&&` without explicit _parentheses_




>[!INFO]
>Two question marks `??`
>`??` returns __first argument__ if it's not `null/undefined`. Otherwise, the ___second one___.
>- Treats `null` and `undefined` similarly
>- A __value__ is "defined" when it's _neither_ `null` or `undefined`
>
>The result of `a ?? b` is:
>- if `a` ___is defined___, then `a`
>- if `a` _isn't defined_, then `b`

`result = a ?? b` is the same as:
```javascript
result = (a !== null && a !== undefined) ? a : b;
```

>[!Example]
>- show `user` if its value isn't `null/undefined`, otherwise `Anonymous`:
>```javascript
>
>alert( user ?? "Anonymous" ); // Anonymous (user is undefined)
>```
>- `user` assigned to a name:
>```javascript
>let user = "John"
>
>alert( user ?? "Anonymous" ); // John (user is not null/undefined)
>```

### Modify in-place
`??=` __Nullish coalescing assignment__ operator:
```javascript
let num = null;
console.log(num ??= 10)
// 10

let int = 1;
console.log(int ??= 10)
// 1
// not modified, int is not `null` nor `undefined`
```

### Comparison with ||
>[!WARNING] Difference:
>- `??` returns the first __defined__ value
><br>
>- `||` returns the first ___truthy___ value
>	- `||` doesn't distinguish between `false`, `0`, _empty string_ `""` and `null/undefined.`
>		- They are all the same ___falsy___ values.
>			- If any of these are first argument `||` will get the second argument as the result
>```javascript
>	let height = 0;
>	
>	alert(height || 100); // 100
>	alert(height ?? 100); // 0
>```


Example:
- Replace `??` with `||` and still get the _same result_
```javascript
let firstName = null;
let lastName = null;
let nickName = "Supercoder";

// shows the first truthy value:
alert(firstName || lastName || nickName || "Anonymous"); // Supercoder
```

### Precedence
Precedence of `??` is the same as `||`
They both equal to `3`
- `||` and `??` is evaluated before `=` and `?`
	- but after most other operations: `+`, `*`

__add parentheses__:
```javascript
let height = null;
let width = null;

// important: use parentheses
let area = (height ?? 100) * (width ?? 50);

alert(area); // 5000
```

Otherwise, `*` with _higher precedence_, would execute first
- leading to ___incorrect results___
```javascript
//widthout parentheses
let area = height ?? 100 * width ?? 50;

// ...works this way (not what we want):
let area = height ?? (100 * width) ?? 50;
```

>[!CAUTION] Using `??` with `&&` or `||`
>JavaScript forbids using `??` together with `&&` and `||` operators.
>Syntax Error:
>```javascript
>let x = 1 && 2 ?? 3; // Syntax error
>```
>__UNLESS__ the precedence explicitly specified with parenthesis
>```javascript
>let x = (1 && 2) ?? 3; // Works
>
>alert(x); // 2
>```

---
### More example:
```javascript
const nullValue = null;
const emptyText = ""; // falsy
const someNumber = 42;

const valA = nullValue ?? "default for A";
const valB = emptyText ?? "default for B";
const valC = someNumber ?? 0;

console.log(valA); // "default for A"
console.log(valB); // "" (as the empty string is not null or undefined)
console.log(valC); // 42
```