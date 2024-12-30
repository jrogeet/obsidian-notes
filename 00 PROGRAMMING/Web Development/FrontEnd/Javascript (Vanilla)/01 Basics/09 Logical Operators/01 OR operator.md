---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #logical
∗:[[01 Javascript|JavaScript]] 

---
# 01 OR ( || ) operator

--- 
Two vertical line symbols `||`
- Meant to manipulate __boolean__ values ONLY.
- If any of its arguments are `true`, it returns `true`
	- otherwise it returns `false`
```javascript
result = a || b;
```

>[!Example] Four possible combinations:
>```javascript
>alert( true || true ); // true
>alert( false || true ); // true
>alert( true || false ); // true
>alert( false || false ); // false
>```

>[!abstract] If operand is NOT a boolean, it's converted to a boolean for the evaluation
>- `1` is treated as `true`, `0` as `false`
> ```javascript
> if (1 || 0) { // works just like if( true || false )
> 	alert( 'truthy' );
> }
> ```

>[!important] OR `||` operator does the following:
>- Evaluates operands from __left__ to _right_
>- ___Each operand are converted into boolean___
>	- If result is `true` , stops and returns the original value of that operand.
> - If all operands are `false`, returns the last operand.
> 
> For instance:
> ```javascript
> alert( 1 || 0 ); // 1 (1 is truthy)
> 
> alert( null || 1 ); // 1 (1 is the first truthy value)
> alert( null || 0 || 1 ); // 1 (the first truthy value)
> 
> alert( undefined || null || 0 ); // 0 (all falsy, returns the last value)
> ```


OR `||` used in `if` statement:
```javascript
let hour = 9;

if (hour < 10 || hour > 18) {
	alert( 'The office is closed.' );
}
```

More conditions:
```javascript
let hour = 12;
let isWeekend = true;

if (hour < 10 || hour > 18 || isWeekend) {
	alert( 'The office is closed.' ); // it is the weekend
}
```
## Other usage:

>[!Example] Getting the first truthy value from a list of variabes or expressions.
> We have `firstName`, `lastName` and `nickName` variables,
>  all optional (i.e. can be undefined or have a falsy values.)
>  
> Use OR `||` to choose the one that has data and show it.
> 	or `"Anonymous"` if nothing set:
> ```javascript
> let firstName = "";
> let lastName = "";
> let nickName = "SuperCoder";
>
> alert( firstName || lastName || nickName || "Anonymous" ); // SuperCoder
> ```
> If all variables were __falsy__, `"Anonymous"` would show up.

>[!example] Short-circuit evaluation
> - `||` Processes it's arguments until first __truthy__ value is reached
> 	- Then the value is returned immediately, _without touching the other argument_
> 
> Imporance: If an ___operand isn't just a value___, but an expression with a side effect.
> Such as:
> -  Variable assignment
> -  Function call
> 
> ```javascript
> true || alert("not printed");
> false || alert("printer");
> ```
> OR `||` operator stops evaluation upon seeing `true`, so `alert` isn't run



## More examples:
```javascript
alert( null || 2 || undefined ); // 2
```

---

```javascript
alert( alert(1) || 2 || alert(3) ); // first `1`, then `2`
```
- `alert` doesn't return a value.
	- in other words, it returns `undefined`
1. first OR `||` evaluates `alert(1)`
	- Shows the first message `1`
2. `alert` returns `undefined`, OR goes to the second operand
3. second operand `2` is __truthy__, so execution is halted
	- `2` is returned and then shown by the outer alert
There will be no `3`, because the evaluation does not reach `alert(3)`.

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
// Runs
// the result of -1 || 0 = -1, truthy
if (-1 || 0) alert( 'first' );

//Doesn't run
// -1 && 0 = 0, falsy
if (-1 && 0) alert( 'second' );

//Executes 
// Operator && has a higher precedence than ||
// so -1 && 1 executes first, giving us the chain:
// null | -1 && 1 -> null || 1 -> 1
if (null || -1 && 1) alert( 'third' );
```
