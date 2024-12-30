---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #logical 
∗:[[01 Javascript|JavaScript]] 

---
# 02 AND operator

--- 
Two ampersands `&&`:
```javascript
result = a && b;
```

>[!Example] AND returns `true` if both operands are truthy and `false` otherwise:
>```javascript
>alert( true && true ); // true
>alert( false && true ); // false
>alert( true && false ); // false
>alert( false && false )
>```

Example with `if`:
```javascript
let hour = 12;
let minute = 30;

if (hour == 12 && minute == 30) {
	alert( 'The time is 12:30' );
}
```

Just like [[01 OR operator | OR `ll`]] , any value is allowed as an operand of AND:
```javascript
if (1 && 0) { // evaluated as true && false
	alert( "won't work, because the result is falsy" );
}
```

>[!important] AND `&&` operator does the following:
> AND `&&` FINDS THE FIRST __FALSY__ VALUE
> - Evaluates operands from left to right
> - Each operand converts into a boolean
> 	- If result is `false`, stops and returns the original value of that operand
> 	- If all were `true` / _truthy_, return the last operand
> Examples:
> ```javascript
> // if the first operand is truthy,
> // AND returns the second operand:
> 
> // if the first operand is falsy,
> // AND returns it.
> // The second operand is ignored
> alert( null && 5 ); //null
> alert( 0 && "no matter what" ); // 0
> ```
> First `falsy` is returned:
> ```javascript
> alert( 1 && 2 && null && 3 ); //null
> ```
>>[!caution] If all values are `truthy`, the last value is returned
>>```javascript
>>alert ( 1 && 2 && 3 ); // 3, the last one
>>```

>[!abstract] Precedence of AND `&&` is __HIGHER__ than OR `||`
>The precedence of AND `&&` operator is higher than OR `||`
>`a && b || c && d` is the same as:
>- if the `&&` expressions were in parentheses: `(a && b) || (c && d)`

>[!DANGER]- Don't replace `if` with `||` or `&&`
>```javascript
>let x = 1;
>
>(x > 0) && alert( 'Greater than zero!' );
>```
>```javascript
>let x = 1;
>
>if (x  > 0) alert( 'Greater than zero!' );
>```
>`&&` variant appears shorter, `if` is more obvious and little bit more readable.


---
### More Examples:
```javascript
alert( 1 && null && 2 ); // null
```
- `null`, first __falsy__ value from the list.

---

```javascript
alert( alert(1) && alert(2) ); // `1`, and then `undefined`
```
- `alert` returns `undefined`
	- `&&` evaluates the left operand(outputs `1`), and immediately stops
	- `undefined` is a __falsy__ value.
	- `&&` looks for a __falsy__ value and returns it.

---

```javascript
alert( null || 2 && 3 || 4 ); // 3
```
- precendence `&&` than `||`, so it executes first.
	- `2 && 3` = `3`, the expression became:
	```javascript
	null || 3 || 4
	```

---

```javascript
if (age >= 14 && age <= 90)
```
- Checks if `age` is greater than or equal `14`
	- and less than or equal `90`

---

