---
topic: javascript
---
Tags/Topics: #javascript #operators #jsbasics
∗:[[01 Javascript|JavaScript]] 

---
# 06 Assignment

--- 
Precedence of  ___=___ with the very low priority of __2__

the calculations of `x = 2 * 2 + 1` are done first before the `=` is evaluated, storing the result in `x`

```javascript
let x = 2 * 2 + 1;

alert( x ); // 5
```

## Assignment = returns a value
All operators in JavaScript return a value.
The call `x = value` writes the `value` into `x` and then returns it.

```javascript
let a = 1;
let b = 2;

let c = 3 - (a = b + 1);

alert( a ); // 3
alert( c ); // 0
```

## Chaining assignments
```javascript
let a, b, c;

a = b = c = 2 + 2;

alert( a ); // 4
alert ( b ); // 4
alert( c ); // 4
```
- the expression at the right (`2 + 2`) is evaluated and assigned to the variables to the left (`c, b` and `a`)
- All the variables share a single value
for the purpose of readability, its better to split the codes into few lines:
```javascript
c = 2 + 2;
b = c;
a = c;
```
